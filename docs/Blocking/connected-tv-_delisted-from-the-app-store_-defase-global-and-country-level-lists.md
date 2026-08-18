---
title: "Connected TV \"Delisted from the App Store\" (DEFASE) Global and Country-Level Lists"
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

Description: A data feed containing all the removed CTV apps from Roku, FireTV, Samsung, Apple (tvOS), and LG app stores.

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
  
### **Example:**

**![Screenshot 2026-03-26 at 09.34.07](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.34.07.png)**

### **Country-Level Delisted App Intelligence**

**An app removed from one country’s app store may still be available in the same store in other countries. Pixalate’s DEFASED blocklists include country codes to identify 100+ countries the app has been delisted from.**

**Feed Type** | **Scope** | **Description**  
---|---|---  
Global Delisted Apps | All stores | All apps removed from any app store globally. Used for proactive blocking.  
Global Delisted Apps w/ Impressions | All stores | Removed apps that are still generating ad impressions, as measured by Pixalate.  

All feeds are updated daily and delivered as CSV via FTP.

**Use Cases: DEFASED Data Feeds**

**For SSPs & Exchanges**

  * **Proactive Blocking:** Remove all apps no longer authorized by official stores — including apps not yet generating impressions.
  * **Block Delisted Apps With Impressions:** Block removed apps still actively serving ads.
  * **Region-Specific Filtering:** Use country-level intelligence to filter apps delisted in specific markets while preserving inventory that remains authorized in other regions.
  * **Real-Time Filtering:** Check App ID against Pixalate’s Enrichment API for live app delisting status.

**For DSPs & Agencies**

  * **Pre-Bid Filtering:** Automatically exclude App IDs flagged as DEFASED from campaign targeting.
  * **Brand Reputation:** Prevent ad spend from reaching developers banned for potential privacy and policy violations.
  * **Market-Level Compliance:** Apply region-specific blocking to campaigns targeting specific geographies.  

**Data Schema**

All DEFASED pre-bid blocklist data feeds share the schema below:

**Column Name** | **Type** | **Description**  
---|---|---  
osName | STRING | Operating system of the delisted app.  
appId | STRING | Unique app identifier.  
lastSeen | STRING | Date the app was removed from the app store  
appStoreUrl | STRING | Original storefront URL. Delisted apps return HTTP 404.  
appStoreName | STRING | Store the app was removed from (e.g., Roku Channel Store).  
delistedCountryCodes | Array | List of countries in which the app has been removed from app storefronts.  
  
**  
Availability**

[DEFASED CTV data](https://www.globenewswire.com/Tracker?data=pMMdSnpbKTAXkuKrRoRkGL2HdKuk-u1TycE7qm2lTHfdpSSvbfDxGn9tQvftEIR5euDfnnlGcAsbGhEOwtc5mOKaE56fbjCvUr_cDSWie1fY9YUSh1Kr2PfgcHpLZMbF) is available via:

  * **FTP data feeds:** Daily CSV blocklists
  * **Enrichment API:** Programmatic lookup of delisted status by App ID
  * **Analytics and MRT dashboard:** Search and filter through Pixalate’s UI
  * **Amazon S3:** Direct delivery to S3 bucket
  * **AWS RTB Fabric:** Module for delisted apps filtering
