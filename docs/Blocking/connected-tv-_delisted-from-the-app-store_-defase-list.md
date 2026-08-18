---
title: "Connected TV \"Delisted from the App Store\" (DEFASE) List"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

In general, apps can be delisted for various reasons, including publisher level fraud, malware, adware, availability of backdoors for fraudsters to leverage bad SDKs, or simply because the developer decided to delist an app. In addition, it is also possible for an app to be delisted for other reasons such as copyright violations. So, clearly, not all delisted apps generate necessarily IVT.

For this, Pixalate collects information about the behavior of a delisted app prior of it being delisted, and based on that, decides if an app should be flagged as IVT because it poses significant risks to the advertising ecosystem.

Pixalate has developed a datafeed containing all the removed apps from the major CTV app stores such as Roku, FireTV, Samsung, and Apple (tvOS) within the last 6 months. The friendly name for this data feed is “**Defase CTV App List”.**

This list can contain apps that do not have ads or do not have impressions at all, but nevertheless they can be useful if proactively blocked to avoid being manipulated for IVT in the future. 

### CTV "Delisted From the App Store" (DEFASE) Block List Details

#### CTV Defase App List

Description: A data feed containing all the removed CTV apps from Roku, FireTV, Samsung, and Apple (tvOS) app stores.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: DefasedCtvAppList_YYYYMMDD.csv

Schema: osName | appId | lastSeen | appStoreUrl | appStoreName

#### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
osName |  STRING |  The name of the Operating System (OS) that the app is installed.  
appID |  STRING |  The app identifier that uniquely characterises an app for a given operating system.   
lastSeen | STRING | This is the date the app was removed from the app store.  
appStoreUrl |  STRING |  This is the URL that was making the app available for download. A delisted app is expected to trigger an HTTP 404 error code (not found) when the URL is accessed.   
appStoreName | STRING | The friendly name of the app store that was serving the app.
