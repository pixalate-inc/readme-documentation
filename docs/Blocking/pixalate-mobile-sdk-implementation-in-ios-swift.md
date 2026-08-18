---
title: "Pixalate Mobile SDK Implementation in iOS Swift"
excerpt: "A guide to integrating Pixalate's lightweight impression library for mobile SDK implementation in your iOS app. This library facilitates the construction and sending of impression URLs with the key values needed by Pixalate for IVT measurement."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### Accessing the Library

You can install the library using CocoaPods, or by cloning the repository directly.

#### CocoaPods

Simply add the library as a dependency in your project's Podfile:

    pod 'pixalate-ios-sdk'  
  
---  
  
Then install it into the project using the pod update terminal command.

#### Framework Integration

You can download the most recent framework from the releases page in the [GitHub repository](https://github.com/pixalate-inc/pixalate-ios-sdk/releases).

#### Importing the Library

Once you've added the library to your project, you can import it into your files:

    import Pixalate  
  
---  
  
### Sample Project

A sample implementation utilizing the MoPub SDK is available via the project's [GitHub repository](https://github.com/pixalate-inc/pixalate-ios-sdk), under the sample-app-swift folder.

#### Building the Sample Project

  1. Clone the repository to your computer.
  2. Open a Terminal window to the sample app's folder.
  3. Run pod install, and then open the generated sample-app-swift.xcworkspace.

### Pre-Bid Blocking API

#### Setup

Pre-bid blocking requires a one-time setup to be called before any requests are made. If you attempt to call the pre-bid blocking API without doing the required setup, an error is thrown.

    Pixalate.setGlobalConfig(  
        PXGlobalConfig.make(  
            username: "[USERNAME]",  
            password: "[PASSWORD]",  
            builder: { builder in  
                builder.threshold = 0.75 // optional, but highly recommended -- defaults to 0.75  
                builder.timeoutInterval = 2 // optional -- defaults to two seconds  
                builder.cacheAge = 60 * 60 * 8 // optional -- defaults to eight hours  
            })  
    )  
  
---  
  
Once the global configuration has been set up, you can begin requesting blocking measurements.

#### Blocking Parameters

The immutable PXBlockingParameters object is built via its Builder class. There are three parameters by which you can attempt to identify the device: deviceId, IP, and userAgent. All three are optional, but you must include at least one when building your object, or the request will fail and return a non-block response by default. You can send up any combination of the three. More info passed can result in a more accurate determination.

#### IP Address

    let builder = PXBlockingParameters()  
    builder.ip = "[an ip address]"  
  
---  
  
If you include the IP address, you must make sure that it is not a local or private address (eg. 127.0.0.1, localhost, or any local addresses, such as 192.168.x.x, 10.x.x.x, or 172.16.x.x).

#### Device ID

    let builder = PXBlockingParameters()  
    builder.deviceId = "[a device id]"  
  
---  
  
For more information on what constitutes a valid device id, take a look at the [Pixalate API docs](https://developer.pixalate.com/?version=latest#ef3c146d-16b6-489f-9d7d-302ac9422093).

#### User Agent

    let builder = PXBlockingParameters()  
    builder.userAgent = "[a user agent]"  
  
---  
  
#### Requesting Block Status

The API is available through the class method Pixalate.requestBlockStatus(_:responseHandler:). This method takes your built PXBlockingParameters object, as well as a block that will be called with the results of the request. The block takes two parameters: a BOOL that contains whether the request should be blocked or not, and an NSError* that will contain the description of any errors that occur, and be nil otherwise.

#### Pre-Bid Blocking Example

    Pixalate.setGlobalConfig(  
        PXGlobalConfig.make(  
            username: "[USERNAME]",  
            password: "[PASSWORD]",  
            builder: {  
                $0.timeoutInterval = 2  
                $0.threshold = 0.75  
            })  
    )  
      
    Pixalate.requestBlockStatus(  
        PXBlockingParameters.make( builder: {  
            $0.userAgent = "[USER_AGENT]"  
            $0.ip = "[IP_ADDRESS]"  
            $0.deviceId = "[DEVICE_ID]"  
        }),  
        responseHandler: { (block, err) in  
            if( err != nil ) {  
                // An error occurred in the request.  
                print( err! )  
            }  
      
            if( block ) {  
                // traffic is above the threshold and should be blocked.  
            } else {  
                // traffic is below the threshold and can be allowed.  
                // Ad loading code could go here.  
            }  
        }  
    )  
  
---  
  
#### Caching

Since the parameters sent don't tend to change, the SDK includes an automatic caching feature. If you pass the same parameters more than once during the caching period, then the cached result will be used, if it exists. You can modify the age of the cache to take more advantage of Pixalate's real-time results, but a higher cache value will result in fewer requests. Cached results are not saved across sessions.

#### Probabilities (Risk Scores)

Similar to Pixalate's Blocking Lists, the Fraud Blocking API returns a probability (risk score) of 0.01 to 1 that represents the likelihood a given value is related to malicious or compromised devices. This risk scoring is calculated by Pixalate's proprietary machine learning algorithm and allows clients to set their own blocking thresholds based on the quality and scale of their supply inventory. The following is a generic guideline for setting fraud blocking thresholds:

  * Probability equal to 1, for filtering out only the worst offender for blocking (deterministic).
  * Probability greater than or equal to 0.90 for filtering out users that are fraudulent beyond a reasonable doubt.
  * Probability between 0.75 (inclusive) and 0.90 (exclusive), to filter out users that are associated with clear and convincing evidence that they are fraudulent.
  * Probability between 0.5 (inclusive) and 0.75 (exclusive), to filter out users that it is more likely than not that they are fraudulent (also known as preponderance of the evidence standard).

Pixalate does not recommend blocking any probabilities less than .5. When making adjustments to the probability threshold, Pixalate highly recommends regular checks-and-balances against impression delivery as lowering the probabilistic threshold can potentially impact the impression count.

### Change Log

#### 0.1.3

  * Enable support for builds that support x86, arm, or both
  * Fix bugs related to the request of block status

#### 0.1.2

  * Add log level
  * Add example Swift app
  * Add example Objective-C app
  * Switch impressions to use https

#### 0.1.1

  * Add block result caching
  * Improve swift integration

#### 0.1.0

  * Initial release
