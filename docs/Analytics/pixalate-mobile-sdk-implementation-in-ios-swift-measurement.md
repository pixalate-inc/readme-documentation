---
title: "Pixalate Mobile SDK Implementation in iOS Swift (Measurement)"
excerpt: "A guide to integrate Pixalate's light-weight impression library for mobile SDK implementation in your iOS app. This library facilitates the construction and sending of impression URLs with the key values needed by Pixalate for IVT measurement."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please login to access [this page](https://www.pixalate.com/knowledgebase/pixalate-mobile-sdk-implementation-in-ios-objective-c) with additional information.

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

### Impression API

#### Building Impressions

Creation of immutable impression objects is done through the use of a builder helper class. To make a new impression, it is easiest to use the class method PXImpression.make(clientId:builder:). This method takes a closure in which you can define all of your relevant values at once.

If you don't want to use the closure method, you can also initialize the builder yourself and pass it to PXImpression directly.

For your convenience, parameter names are mapped as human-readable string constants. The available mappings are outlined below and please contact your Customer Success representative for sample code blocks and string values for the list below.

Constant  
---  
Advertiser Id  
App Id  
App Name  
Bid Price  
Campaign Id  
Carrier Id  
Clear Price  
Content Id  
Creative Id  
Creative Size  
Device Id  
Device Model  
Device Os  
Geographic Region  
Impression Id  
Isp  
Latitude  
Line item Id  
Longitude  
Mraid Version  
Page Url  
Placement Id  
Platform Id  
Publisher Id  
Seller Id  
Site Id  
Supply Type  
User Agent  
User Id  
User Ip  
Video Length  
Video Play Status  
  
The impression builder accepts **any** value as a parameter name. The mappings outlined above are merely provided as a convenience for commonly used parameters.

You must explicitly provide the impression builder with **all** parameters that you are able to include.

#### Sending Impressions

To send an impression, pass your built PXImpression instance to the Pixalate.sendImpression(_:) class method:

    let impression = /* create an impression using your preferred method */;  
    Pixalate.sendImpression( impression )  
  
---  
  
Building and sending of impressions can be compacted into a one-line call, if you do not wish to pre-build impression data.

#### When to Send Impressions

In order to have the most accurate and MRC-compliant results from integration with Pixalate's impression library, it is important to place your impression snippet at the correct location within your ad code. For example, if you want to record impressions for a banner ad using MoPub's iOS SDK, they provide an MPAdViewDelegate protocol that you can set up on your MPAdView. In this instance, you'd probably want to send the impression when adViewDidLoadAd(_:adSize:) is called.

Please contact your Customer Success representative for sample code blocks.

It's important that the impression is sent as close to the actual impression event as possible. If you retrieve an ad, make sure that you only send an impression if you intend to show it.

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
