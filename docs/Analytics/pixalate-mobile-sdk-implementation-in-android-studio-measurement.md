---
title: "Pixalate Mobile SDK Implementation in Android Studio (Measurement)"
excerpt: "A guide to integrate Pixalate's light-weight impression library for mobile SDK implementation in Android Studio. This library facilitates the construction and sending of impression URLs with the key values needed by Pixalate for IVT measurement."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please login to access [this page](https://www.pixalate.com/knowledgebase/pixalate-mobile-sdk-using) with additional information.

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

#### Impression API

### Building Impressions

Creation of impressions is done through the use of a builder class, called Impression.Builder. The constructor of the builder takes your required client id, but all other parameters are optional. The typical use-case of the ImpressionBuilder is to use it as a one-line daisy chain call, and set all of your parameters at once:

    Impression impression = new Impression.Builder( "[YOUR CLIENT ID]" )  
    	.setParameter( "some-custom-parameter", "my-custom-value" )  
    	.setParameter( /* etc. */ )  
    	.build();  
  
---  
  
For your convenience, parameter names are already mapped as human-readable constant strings on the Pixalate class. For the complete list of parameter names mapped to Pixalate key values, please reach out to your Customer Success representative. 

Constant  
---  
ADVERTISER ID  
APP ID  
APP NAME  
BID PRICE  
CAMPAIGN ID  
CARRIER_ID  
CLEAR PRICE  
CONTENT ID  
CREATIVE ID  
CREATIVE SIZE  
DEVICE ID  
DEVICE MODEL  
DEVICE OS  
GEOGRAPHIC REGION  
IMPRESSION ID  
ISP  
LATITUDE  
LINE ITEM ID  
LONGITUDE  
MRAID VERSION  
PAGE URL  
PLACEMENT ID  
PLATFORM ID  
PUBLISHER ID  
SELLER ID  
SITE ID  
SUPPLY TYPE  
USER AGENT  
USER ID  
USER IP  
VIDEO LENGTH  
VIDEO PLAY STATUS  
  
The impression builder accepts **any** value as a parameter name. The mappings outlined above are merely provided as a convenience for commonly used parameters

You must explicitly provide the impression builder with **all** parameters that you are able to include.

### Sending Impressions

In order to send an impression, pass your built Impression instance into the Pixalate.sendImpression method:

    Pixalate.sendImpression( impression );  
  
---  
  
Building and sending of impressions can be compacted into a one-line call, if you do not wish to pre-build and store impression data:

    Pixalate.sendImpression( new Impression.Builder( "[YOUR CLIENT ID]" )  
    	.setParameter( "some-custom-parameter", "my-custom-value" )  
    	.build() );  
  
---  
  
### When to Send Impressions

In order to have the most accurate and MRC-compliant results from integration with Pixalate's impression library, it is important to place your impression snippet at the correct location within your ad code. For example, MoPub's SDK provides a BannerAdListener interface that you can set on your MoPub view:

    moPubView.setBannerAdListener( new BannerAdListener () {  
    	// ...  
    	public void onBannerLoaded ( MoPubView banner ) {  
    		Pixalate.sendImpression( new Impression.Builder( "[YOUR CLIENT ID]" )  
    			// ... set parameters  
    			.build() );  
    	}  
    	// ...  
    });  
  
---  
  
It's important that the impression is sent as close to the actual impression event as possible. If you retrieve an ad, make sure that you only send an impression if you intend to show it.

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
