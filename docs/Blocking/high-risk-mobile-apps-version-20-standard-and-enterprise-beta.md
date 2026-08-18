---
title: "High Risk Mobile Apps (Version 2.0) - Standard and Enterprise (Beta)"
excerpt: "The 2.0 mobile app block lists, the risk reason codes attached to each app, and when app-level blocking is the appropriate control."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### **Overview**

High Risk Mobile Apps 2.0 Standard and Enterprise (Beta) are mobile app blocklists that identify known dangerous and fraudulent sources by combining high historical IVT rates, app store compliance signals, app-ads.txt compliance, and privacy risk indicators into a unified feed with transparent risk reason codes.

Apps are evaluated across multiple risk dimensions including IVT rates, app store compliance, developer transparency, and inventory quality signals. Apps are included on the list when app-level blocking is the appropriate control — meaning impression-level filtering cannot reliably isolate valid traffic from invalid traffic.

Each app on the list is tagged with one or more risk reason codes, providing transparency into the specific signals that triggered inclusion.

**Risk Types**

**Risk Type** |  **Code** |  **Description**  
---|---|---  
High GIVT |  `highGivt` |  Apps with General Invalid Traffic rates exceeding Pixalate's threshold.   
High SIVT |  `highSivt` |  Apps with Sophisticated Invalid Traffic rates exceeding Pixalate's threshold.   
Missing Privacy Policy |  `missingPrivacyPolicy` |  Apps missing mandatory privacy policies required by Google Play and Apple App Store  
Abandoned App |  `abandonedApp` |  Apps that have not been updated by developers for 3+ years and may be unmaintained, insecure, or non-compliant with current app store requirements  
Missing app-ads.txt |  `noAdsTxt` |  Apps generating ad impressions without a valid app-ads.txt file, indicating unauthorized inventory  
Developer Anonymity |  `developerAnonymity` |  Apps where the developer has missing or unverifiable contact information  
VPC Bypass Risk |  `vpcBypass` |  Child-directed apps transmitting IP or location data without Verifiable Parental Consent, creating COPPA compliance exposure  
Delisted App |  `delistedApp` |  Apps removed from app stores that continue to generate ad traffic  
Made for Advertising |  `mfaApp` |  Apps designed primarily to generate ad impressions rather than deliver genuine user value, including apps exhibiting ad stacking and other manipulative ad placement tactics  
Known Threat Actor |  `knownThreatActor` |  Apps confirmed as fraudulent sources through Pixalate’s internal fraud investigations.  
  
### **  
File Format and Delivery**

**Attribute** |  **Value**  
---|---  
File Format |  CSV  
Delivery Method |  FTP or S3 Bucket  
Naming Convention |  MobileHighRiskAppSelection_YYYYMMDD  
Update Frequency |  **Daily**  
  
### **  
Schema**

High Risk Mobile Apps 2.0 Standard and Enterprise (Beta) evaluate each app against ten risk dimensions. An app can be flagged for multiple risk types simultaneously — for example, an app may be both abandoned and missing a privacy policy.

The probability field is set to 1 for all entries. High Risk Mobile Apps 2.0 (Beta) uses deterministic inclusion criteria — an app either meets the threshold for a risk type or it does not.

### **High Risk Mobile Apps 2.0 Standard****(Beta)**

In Version 2.0 Standard (Beta), when an app has multiple risk types, the riskType field displays the string value **"various"**.

**Column** |  **Type** |  **Description**  
---|---|---  
appId |  STRING |  The identifier for the mobile app (e.g., "310633997" or "com.whatsapp")  
bundleId |  STRING |  The bundle ID associated with the app, if available  
osName |  STRING |  The operating system associated with the app (iOS or Android)  
riskType |  STRING |  Risk type code; displays the string value **"various"** when multiple risk types apply  
probability |  FLOAT |  Value of 1 for all entries  
appStoreUrl |  STRING |  URL to the app store listing  
appStoreName |  STRING |  Name of the app store (Google Play or Apple App Store)  
  
### **Example:**

### **![Screenshot 2026-03-26 at 09.01.59](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.01.59.png)**

### **  
High Risk Mobile Apps 2.0 Enterprise****(Beta)**

High Risk Mobile Apps 2.0 Enterprise (Beta) provides full granularity by listing all applicable risk types as comma-separated values (e.g., highSivt,abandonedApp,missingPrivacyPolicy) instead of displaying various. This enables you to build custom blocking logic based on specific risk type combinations.

**Column** |  **Type** |  **Description**  
---|---|---  
appId |  STRING |  The identifier for the mobile app (e.g., "310633997" or "com.whatsapp")  
bundleId |  STRING |  The bundle ID associated with the app, if available  
osName |  STRING |  The operating system associated with the app (iOS or Android)  
riskType |  STRING |  Comma-separated list of all applicable risk types  
appStoreUrl |  STRING |  URL to the app store listing  
appStoreName |  STRING |  Name of the app store (Google Play or Apple App Store)  
  
### **Example:**

![Screenshot 2026-03-26 at 09.02.15](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.02.15.png)

Contact your Customer Success representative to upgrade to High Risk Mobile Apps 2.0 Enterprise (Beta).

**Note:** Access to High Risk Mobile Apps 2.0 Standard (Beta) requires acceptance of an updated Master Service Terms (MST). Access to the Enterprise (Beta) version requires an upgrade to your subscription. Contact your Customer Success representative for details.

### **Integration Recommendations**

**Pre-bid blocking:** When blocking apps from this list, use appId + osName at minimum to ensure you block the correct app. For greater precision, use appId + bundleId + osName.

**Risk-based filtering:** Use the riskType field to implement selective blocking based on your risk tolerance. For example, you may choose to block only apps flagged for highSivt or mfaApp while permitting apps flagged solely for abandonedApp.  

### **OS Decisioning**

App/bundle IDs for the same application are often named differently for each OS platform. For example, the app XYZ may list its bundle ID on iOS as "com.company.xyz", but on Android it is listed as "com.xyz.app".

If the entry on the High Risk App List includes the app ID "com.company.xyz" but the osName is "Android", it is likely the app is either spoofed or using a deceptive name.

In this case, you would only want to block "com.company.xyz" on Android so as to not block users on the official XYZ app on iOS. It is for this reason that it is highly advised to match both app ID and OS when determining blocking decisions.

### **Frequently Asked Questions**

**How should I use the App ID, Bundle ID, and OS columns?**

When blocking an app, use appId + osName at minimum. This prevents inadvertently blocking an app on a different operating system that shares the same identifier. For better precision, include bundleId as well.

**Why do some apps appear on the list and then disappear?**

Apps are evaluated using a rolling lookback window. If an app's risk indicators improve over time (e.g., IVT rates fall below thresholds), the app will age off the list for that particular risk type. However, an app that ages off may be re-added in the future if risk indicators resurface, or may be flagged for different risk types.

**What is the difference between High Risk Mobile Apps 2.0 Standard(Beta) and Enterprise (Beta)?**

High Risk Mobile Apps 2.0 Standard (Beta) maintains backward compatibility with existing integrations by showing a single risk type value (or various for multiple) and includes a probability field. High Risk Mobile Apps 2.0 Enterprise (Beta) provides full granularity with comma-separated risk type codes and removes the probability field. Enterprise subscribers also gain access to the new High Risk App data points in Analytics scheduled reports and the Analytics API.

**How can an app be removed from the list?**

Apps are automatically removed when they no longer meet the inclusion criteria for any risk type. For IVT-based risk types, this occurs when IVT rates fall below thresholds over the lookback period. For compliance-based risk types (e.g., missingPrivacyPolicy, abandonedApp), removal occurs when the app resolves the underlying issue.

**How does this list relate to IVT reporting in Analytics?**

Impressions from apps on this list are not automatically classified as IVT. The MRC's Invalid Traffic Detection and Filtration Interim Update Memo emphasize that IVT measurement should occur at the traffic level, distinct from app-level risk assessment. High Risk Mobile Apps 2.0 (Beta) aligns with this guidance by separating app-level risk signals from impression-level IVT classification.

**If an app is on this list, does that mean the app is flagged for IVT?**

Not necessarily. Apps on the list may be present due to reasons that may or may not include IVT risk. There are a couple of risk types that are IVT-related (highGivt and highSivt) but High Risk Mobile Apps 2.0 (Beta) also identifies apps that could present other types of risk (e.g., app store compliance, developer transparency, and inventory quality signals).

**What data sources are used to compile this list?**

Pixalate collects data from various sources to compile the list, including traffic data, third-party data, and app store metadata.

**I work directly with a publisher on this list. What should I do?**

The list provides app-level risk signals based on observed data across the ecosystem. If you have a direct relationship with a publisher and have visibility into their traffic quality, you may choose to use the risk type codes to make informed decisions about which risk types to block based on your risk tolerance and business requirements.

### **  
Related Resources**

  * [Pre-Bid Blocking Data Feeds](https://www.pixalate.com/knowledgebase/blocking) — Overview of all blocking data feeds including IP, Device ID, and Domain blocklists
  * [Invalid Traffic (IVT) Types](https://www.pixalate.com/knowledgebase/ivt-types) — Definitions of GIVT and SIVT categories detected by Pixalate
  * [App-Ads.txt Overview](https://www.pixalate.com/knowledgebase/app-ads-txt) — Understanding app-ads.txt and app-ads.txt compliance
  * [Made for Advertising (MFA) Lists](https://www.pixalate.com/knowledgebase/mfa) — MFA detection for websites, mobile apps, and CTV
  * [Mobile In-App Fraud Detection](https://www.pixalate.com/knowledgebase/mobile-in-app) — Mobile-specific IVT detection methodology
  * [CTV/OTT Fraud Protection](https://www.pixalate.com/knowledgebase/ctv) — Connected TV fraud detection and blocking
  * [Analytics Dashboard](https://www.pixalate.com/knowledgebase/analytics) — Using the Analytics platform to monitor traffic quality
  * [API Documentation](https://www.pixalate.com/knowledgebase/api) — Integration guides for Pixalate APIs

### **Contact**

For questions about High Risk Mobile Apps 2.0 (Beta), contact your Customer Success representative or reach out to support@pixalate.com.
