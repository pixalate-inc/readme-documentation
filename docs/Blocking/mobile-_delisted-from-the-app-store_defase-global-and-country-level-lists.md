---
title: "Mobile \"Delisted From the App Store\"(DEFASE) Global and Country-Level Lists"
excerpt: "The defasedApp IVT type and Pixalate's data feeds of apps delisted from Google Play and iTunes, in global and country-level versions."
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

![Screenshot 2026-03-26 at 09.29.15](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.29.15.png)

#### Defase App Blocklist

Description: A data feed containing all the apps removed from Google Play and iTunes store, which have generated impressions in the last 2 weeks and which also have shown evidence of suspicious or invalid behavior.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: DefasedAppBlocklist_YYYYMMDD.csv

Schema: osName | appId | bundleId | lastSeen | appStoreUrl | appStoreName

![Screenshot 2026-03-26 at 09.29.15](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.29.15.png)

#### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
osName |  STRING |  The name of the Operating System (OS) that the app is installed. Currently only iOS (for Apple iTunes) and Android (for Google Play) are supported.   
appID |  STRING |  The app identifier that uniquely characterises an app for a given operating system. This will be the (numeric) “trackId” for Apple iTunes apps, and “package name” for Google Play.   
bundleId | STRING | This is the bundleId that exists for iTunes apps only.  
lastSeen | STRING | This is the date the app was removed from the app store.  
appStoreUrl |  STRING |  This is the URL that was making the app available for download. A delisted app is expected to trigger an HTTP 404 error code (not found) when the URL is accessed.   
appStoreName | STRING | The friendly name of the app store that was serving the app (i.e. Google Play and Apple iTunes).   
  
### **Country-Level Delisted App Intelligence**

**An app removed from one country’s app store may still be available in the same store in other countries. Pixalate’s DEFASED blocklists include country codes to identify 100+ countries the app has been delisted from.**

**Feed Type** | **Scope** | **Description**  
---|---|---  
Global Delisted Apps | All stores | All apps removed from any app store globally. Used for proactive blocking.  
Global Delisted Apps w/ Impressions | All stores | Removed apps that are still generating ad impressions, as measured by Pixalate.  

All feeds are updated daily (estimated availability 12:00 PM) and delivered as CSV via FTP.

**Use Cases: DEFASED Data Feeds**

**For SSPs & Exchanges**

  * **Proactive Blocking:** Remove all apps no longer authorized by official stores — including apps not yet generating impressions.
  * **Block Delisted Apps With Impressions:** Block removed apps still actively serving ads.
  * **Region-Specific Filtering:** Use country-level intelligence to filter apps delisted in specific markets while preserving inventory that remains authorized in other regions.
  * **Real-Time Filtering:** Check App and Bundle IDs against Pixalate’s Enrichment API for live app delisting status.

**For DSPs & Agencies**

  * **Pre-Bid Filtering:** Automatically exclude App IDs flagged as DEFASED from campaign targeting.
  * **Brand Reputation:** Prevent ad spend from reaching developers banned for potential privacy and policy violations.
  * **Market-Level Compliance:** Apply region-specific blocking to campaigns targeting specific geographies.

**Data Schema**

All DEFASED pre-bid blocklist data feeds share the schema below:

**Column Name** | **Type** | **Description**  
---|---|---  
osName | STRING | Operating system of the delisted app.  
appId | STRING | Unique app identifier. Numeric trackId for iOS; package name for Android.  
bundleId | STRING | Bundle identifier for iOS apps. For Android, matching should be done on appId.  
lastSeen | STRING | Date the app was removed from the app store  
appStoreUrl | STRING | Original storefront URL. Delisted apps return HTTP 404.  
appStoreName | STRING | Store the app was removed from (e.g., Google Play, Roku Channel Store).  
delistedCountryCodes | Array | List of countries in which the app has been removed from app storefronts.  
  
**  
Availability**

[DEFASED data is available](https://www.globenewswire.com/Tracker?data=AHMW4KS3KgV74BViX28ZoaOvVbQsktVTwn2krT6c0glKLTdqpqsy-PQQpVnFPGDXq-rq5ZQg97rUmMHUuf6lNUBxzq8KQWFf_4citYeX8Sk=) via:

  * **FTP data feeds:** Daily CSV blocklists
  * **Enrichment API:** Programmatic lookup of delisted status by App ID
  * **Analytics and MRT dashboard:** Search and filter through Pixalate’s UI
  * **AWS RTB Fabric:** Module for delisted apps filtering
