---
title: "Pixalate Mobile SDK Implementation in Android Studio"
excerpt: "A guide to integrate Pixalate's light-weight impression library for mobile SDK implementation in Android Studio. This library facilitates the construction and sending of impression URLs with the key values needed by Pixalate for IVT measurement."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### Accessing the Library

To access the latest .aar file, please access via [MavenCentral](https://mvnrepository.com/artifact/com.pixalate.pxsdk/pxsdk) or reach out to your Customer Success representative. 

### Integrating the Library

### As a compiled .aar file

  1. Copy the .aar file to your project's libs directory, or wherever your default library directory is inside your project.
  2. Add the following line to your project's build.gradle file:
         
         dependencies {  
         	// other dependencies  
           
             implementation(name:'pxsdk', ext:'aar')  
         }  
  
---  
  
  3. If you have not set up the default library directory yet, or are getting a 'Failed to resolve: :pxsdk:' error when syncing gradle, make sure you add the libs folder (or your folder of choice) to your project's build.gradle file:
         
         repositories {  
         	// other repositories  
         	flatDir {  
         		dirs 'libs'  
         	}  
         }  
  
---  

### As a JCenter .aar dependency

  1. Add the following lines to your project's build.gradle file:
         
         repositories {  
         	// other repositories  
         	jcenter()  
         }  
           
         dependencies {  
         	// other dependencies  
           
             implementation 'com.pixalate.pxsdk:pxsdk:0.2.0'  
         }  
  
---  

### Required Permissions

The only permission required by the library is the internet permission. If your app does not already require this permission, you must add the following line to your AndroidManifest.xml file before the application tag:

---  
  
### ProGuard Configuration

This library does not require any special ProGuard configuration at this time.

### Sample Project

A sample implemention utilizing the MoPub SDK is available via the project's [GitHub repository](https://github.com/pixalate-inc/pixalate-android-sdk), under the pxsdk-sample folder. To test, simply clone the repository to your computer and open the project folder in Android Studio.

### API Reference

#### Pre-Bid Blocking API

### Setup

Pre-bid blocking requires a one-time setup to be called before any requests are made. If you attempt to call the pre-bid blocking api without doing the required setup, an error is thrown.

    Pixalate.initialize( new PixalateConfig.Builder( "[YOUR USERNAME]", "[YOUR PASSWORD]" )  
    	.setBlockingThreshold( 0.75 ) // optional, but highly recommended -- defaults to 0.75  
    	.setRequestTimeout( 2000 ) // optional -- defaults to two seconds  
    	.setCacheAge( 28800000 ) // optional -- defaults to 8 hours   
    	.build()  );  
  
---  
  
Once Pixalate.initialize has been called with your appropriate user name and password, you can begin requesting blocking measurements.

When provided with an API key, visit the "Authentication and Basic Configuration" section in the documentation [here](https://github.com/pixalate-inc/android-prebid-blocking/tree/master?tab=readme-ov-file#authentication--basic-configuration). 

### Blocking Parameters

The BlockingParameters object is built via its Builder interface. There are three parameters by which you can attempt to identify the device: deviceId, ip, and userAgent. All three are optional, but you must include at least one when building your object, or an error will be thrown.

#### IP Address

    new BlockingParameters.Builder()  
    	.setIp( "[an ip address]" );  
  
---  
  
If you include the IP address, you must make sure that it is not a local or private address (eg. 127.0.0.1, localhost, or any local addresses, such as 192.168.x.x, 10.x.x.x, or 172.16.x.x).

#### Device ID

    new BlockingParameters.Builder()  
    	.setDeviceID( "[a device id]" );  
  
---  
  
For more information on what constitutes a valid device id, take a look at the [Pixalate API docs](https://developer.pixalate.com/?version=latest#ef3c146d-16b6-489f-9d7d-302ac9422093).

#### User Agent

    new BlockingParameters.Builder()  
    	.setUserAgent( "[a user agent string]" );  
  
---  
  
### Requesting Block Status

The API is available through the static method Pixalate.requestBlockStatus. This method takes your built BlockingParameters object, as well as a BlockingStatusListener interface to listen for the results of the request. The listener has three methods:

#### BlockingStatusListener.onAllow

If the traffic is determined to have a lower probability than your preferred threshold, then onAllow is called. Here is where you would want to do your ad loading.

#### BlockingStatusListener.onBlock

If the traffic is determined to have a probability higher than your set threshold, then onBlock will be called. In the simplest case, you can just do nothing.

#### BlockingStatusListener.onError

Something went wrong unrelated to the probability. If the connection timed out, onError will be called with an errorCode of 408. If your credentials are incorrect, onError will be called with a 401.

### Pre-Bid Blocking Example

    Pixalate.initialize( new PixalateConfig.Builder( "[USERNAME]", "[PASSWORD]" )  
        .setThreshold( 0.9 )  
        .build() );  
      
    BlockingParameters parameters = new BlockingParameters.Builder()  
            .setDeviceId( "[device id]" )  
            .setIp( "[ip address]" )  
            .setUserAgent( "[user agent]" )  
            .build();  
      
    Pixalate.requestBlockStatus( parameters,  
        new BlockingStatusListener() {  
            @Override  
            public void onBlock () {  
    			// traffic is above the threshold and should be blocked.  
            }  
      
            @Override  
            public void onAllow () {  
    			// traffic is below the threshold and should be allowed.  
    			// Ad loading code could go here.  
            }  
      
            @Override  
            public void onError ( int errorCode, String message ) {  
    			// An error occurred in the request.  
            }  
        });  
  
---  
  
### Caching

Since the parameters sent don't tend to change, the SDK includes an automatic caching feature. If you pass the same parameters more than once during the caching period, then the cached result will be used, if it exists. You can modify the age of the cache to take more advantage of Pixalate's real-time results, but a higher cache value will result in fewer requests. Cached results are not saved across sessions.

### Probabilities (Risk Scores)

Similar to Pixalate's Blocking Lists, the Fraud Blocking API returns a probability (risk score) 0.01 to 1 that represents the likelihood a given value is related to malicious or compromised devices. This risk scoring is calculated by Pixalate's proprietary machine learning algorithm and allows clients to set their own blocking thresholds based on the quality and scale of their supply inventory. The following is a generic guideline for setting fraud blocking thresholds:

  * Probability equal to 1, for filtering out only the worst offender for blocking (deterministic).
  * Probability greater than or equal to 0.90 for filtering out users that are fraudulent beyond reasonable doubt.
  * Probability between 0.75 (inclusive) and 0.90 (exclusive), to filter out users that are associated with clear and convincing evidence that they are fraudulent.
  * Probability between 0.5 (inclusive) and 0.75 (exclusive), to filter out users that it is more likely than not that they are fraudulent (also known as preponderance of the evidence standard).

Pixalate does not recommend blocking any probabilities less than .5. When making adjustments to the probability threshold, Pixalate highly recommends regular checks-and-balances against impression delivery as lowering the probabilistic threshold can potentially impact the impression count.

#### Change Log

### 0.3.2

  * Added sample project to [GitHub](https://github.com/pixalate-inc/pixalate-android-sdk) page.

### 0.3.0

  * Implemented Pre-Bid Blocking API.
  * Changed Builder namespaces to be more consistent, and moved files out to their own classes. eg. Pixalate.ImpressionBuilder => Impression.Builder

### 0.2.0

  * Added ping backoff retrying
  * Added log interface and error reporting at LogLevel.DEBUG.

### 0.1.0

  * Initial release
