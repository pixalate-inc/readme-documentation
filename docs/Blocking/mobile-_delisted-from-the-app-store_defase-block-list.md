---
title: "Mobile \"Delisted From the App Store\"(DEFASE) Block List"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

DEFASE stands for DElisted From the App StorE. The IVT type called “**defasedApp** ” characterizes traffic seen from apps that were available for download through one of the two major app stores (namely Google Play and iTunes) over the last 12 months but got delisted and currently are not available any more. 

In general, apps can be delisted for various reasons, including publisher level fraud, malware, adware, availability of backdoors for fraudsters to leverage bad SDKs, or simply because the developer decided to delist an app. In addition, it is also possible for an app to be delisted for other reasons such as copyright violations. So, clearly, not all delisted apps generate necessarily IVT. For this, Pixalate collects information about the behavior of a delisted app prior of it being delisted, and based on that, decides if an app should be flagged as IVT because it poses significant risks to the advertising ecosystem.

Pixalate has developed two datafeeds related to delisted apps:

  1. A data feed containing all the removed apps from Google Play and iTunes store within the last 6 months. The friendly name for this data feed is “**Defase App List”.**
  2. A data feed containing all the apps removed from Google Play and iTunes store within the last 6 months, which have generated impressions in the last 2 weeks and which also have shown evidence of suspicious or invalid behavior. The friendly name for this data feed is **“Defase App Blocklist”**.

Based on the above definitions, the first list can contain apps that do not have ads or do not have impressions at all, but nevertheless they can be useful if proactively blocked to avoid being manipulated for IVT in the future. 

The second list contains apps that have been seen generating impressions and in general should be treated as IVT and be blocked.

Pixalate has developed algorithms to detect and exclude from the blocklist removed apps where Pixalate has determined that such apps should not be blocked because removal was likely unrelated to IVT. Examples of such app removals include cases where removal appears to be temporary and due to an administrative or legal issue (i.e., Pixalate believes that the app is likely to be relisted in the app store within a few days or weeks).

Both data feeds have the same schemas and semantics behind, so both should be applied the same way, as described below:

  * For an iOS app, the matching can be done on either the appId column (which contains the numeric trackId of the iOS app) or the bundleId column. 
  * For an Android app, the matching needs to be done at the appId column, which contains the bundleId for an android app.

### DElisted From the App StorE (DEFASE) Block List Details

#### Defase App List

Description: A data feed containing all the removed apps from Google Play and iTunes store.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: DefasedAppList_YYYYMMDD.csv

Schema: osName | appId | bundleId | lastSeen | appStoreUrl | appStoreName

#### Defase App Blocklist

Description: A data feed containing all the apps removed from Google Play and iTunes store, which have generated impressions in the last 2 weeks and which also have shown evidence of suspicious or invalid behavior.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: DefasedAppBlocklist_YYYYMMDD.csv

Schema: osName | appId | bundleId | lastSeen | appStoreUrl | appStoreName

#### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
osName |  STRING |  The name of the Operating System (OS) that the app is installed. Currently only iOS (for Apple iTunes) and Android (for Google Play) are supported.   
appID |  STRING |  The app identifier that uniquely characterises an app for a given operating system. This will be the (numeric) “trackId” for Apple iTunes apps, and “package name” for Google Play.   
bundleId | STRING | This is the bundleId that exists for iTunes apps only.  
lastSeen | STRING | This is the date the app was removed from the app store.  
appStoreUrl |  STRING |  This is the URL that was making the app available for download. A delisted app is expected to trigger an HTTP 404 error code (not found) when the URL is accessed.   
appStoreName | STRING | The friendly name of the app store that was serving the app (i.e. Google Play and Apple iTunes).
