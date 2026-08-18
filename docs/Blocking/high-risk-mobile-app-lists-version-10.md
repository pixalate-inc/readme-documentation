---
title: "High Risk Mobile App Lists (Version 1.0)"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The High Risk Mobile App lists are daily updated lists of the most high risk mobile app IDs from the most prominent mobile operating systems (e.g. Google Android, Apple iOS).

### Methodology 

To compile the list, Pixalate analyzes the RTB traffic characteristics of hundred of thousands of mobile apps in the world that are selling inventory on RTB exchanges, and through its sophisticated Machine Learning Models captures a wide variety of risk-types in order to provide fine-grained blocking capabilities of specific app behaviors or traffic patterns. Apps are assessed based on its data available through the programmatic channel, as well as the data available through the various app stores that an app is or isn’t available from.

### Lists Included

  * High Risk App List (Version 1.0)*
  * New App List**
  * VPN App List**

* Pixalate now offers **Version 2.0** of the High Risk App List that supplements IVT risk mitigation by also including app store compliance signals, app-ads.txt compliance, and privacy risk indicators.

** The New App List & VPN App List do NOT contain apps that have generated evidence of some kind of invalid traffic; otherwise, they would have been included in the high risk app list. The lists are provided by Pixalate as an additional proactive mechanism for clients that want to use an extra layer of filtration.

#### High Risk App List (Version 1.0)

Apps that have shown suspicious traffic characteristics or are potentially malicious.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: MobileHighRiskAppSelection_YYYYMMDD

Schema: appId | bundleId | osName | riskType | probability | appStoreUrl | appStoreName

![Screenshot 2026-03-26 at 09.15.14](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.15.14.png)

#### New App List

Brand-new apps (< 6 months) that have not build their reputation yet to leave our sandbox, and thus have higher likelihood to misbehave in the near future.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: MobileNewAppSelection_YYYYMMDD

Schema: appId | bundleId | osName | appStoreUrl | appStoreName

![Screenshot 2026-03-26 at 09.16.35](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.16.35.png)

#### VPN App List

Apps that are mainly used to hide the IP of the device and its real location

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: MobileVpnAppSelection_YYYYMMDD

Schema: appId | bundleId | osName | appStoreUrl | appStoreName

![Screenshot 2026-03-26 at 09.16.35](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.16.35.png)

#### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
appId |  STRING |  The actual ID that characterizes a mobile app (e.g. “310633997” or “com.whatsapp”). This data point should always be populated.   
bundleId |  STRING |  The bundle ID associated with the app (if available).  
osName |  STRING |  The Operating System (OS) name that is associated with a given app.  
riskType |  STRING |  The mnemonic name that characterizes the type of risk associated with a given appId (e.g. “locationSpoofing”)  
probability |  FLOAT |  A number between 0.5 and 1 that characterizes the likelihood that the given appId is associated with a specific risk type (e.g 0.7 is 70% probability). The higher the probability number, the higher the specific risk.  
appStoreUrl |  STRING |  The URL of the app-store that one can use to download the app or get statistics regarding its' overall performance.  
appStoreName |  STRING |  The name of the app-store where the appId was found.  
  
### Included Risk Types

The high risk mobile app list contains the following risk types:

**Risk Type** |  **Description** |  **IVT Type**  
---|---|---  
appSpoofing |  An app that has suspicious traffic characteristics and may also have data inconsistencies or mismatches in what is being declared in the bid request vs. what Pixalate is detecting. This IVT type may also include obfuscation of device information, user-agent, and other datasets, as well as misrepresentation of the appId (or bundleId) where one or more of the appIds (or bundleIds) used will not match the appId (or bundleId) of the device’s operating system. For example, at the time of this writing, if you see “com.pandora.android” on iOS, it will be a spoofed appId since this is a valid appId only for Android. In addition, the valid app identifiers for Pandora on iOS are “284035177” (appId) or “com.pandora” (bundleId) but none of them is observed here. These may also be popular apps that do not show programmatic display ads, and thus should never appear in RTB generating ad requests |  SIVT  
clickFarm |  An impression originating from a user who has been flagged as being associated with human click farm activity. |  SIVT  
cookieStuffing |  Activity from a cookie that has connected to the internet via a statistically significant inflated number of different IP Addresses. |  SIVT  
datacenter |  An app that persistently generates traffic originating from IPs that belong to datacenters and which cannot be used by human users. |  GIVT  
datacenterProxy |  The impression is from an intermediary proxy device, running in a datacenter, that exists to manipulate traffic counts, pass non-human or invalid traffic or fails to comply with protocol |  SIVT  
delisted |  Apps removed from app stores that continue to generate ad traffic |  Not IVT  
deviceIdStuffing |  Activity from a unique device id that presents itself as a statistically significant inflated number of different IP addresses, unique apps, branded platforms, and/or locations |  SIVT  
displayImpressionFraud |  Impressions that are generated from the same browser or device at a statistically significant inflated rate. |  SIVT  
displayClickFraud |  Clicks that are generated from the same browser or device at a statistically significant inflated rate. |  SIVT  
fastClicker |  Apps that generate a large volume of clicks that are 1 second apart from the ad impression. |  GIVT  
IABcrawler |  An app that persistently generates traffic that is associated with User Agent (UA) strings that belong to crawlers, according to the IAB list of crawler signatures. |  GIVT  
IABdummyBot |  An app that persistently generates traffic that is associated with an invalid User Agent (UA) string, according to the IAB list of invalid UA strings. |  GIVT  
idioBots |  GIVT detection logic includes mechanisms to further detect and account for illogical placement dimension, which are inappropriate for trafficked ad creatives in accordance with the Interactive Advertising Bureau's (IAB) Standard Ad Portfolio. |  GIVT  
highRisk |  Apps that generate large volumes of Sophisticated Invalid Traffic (SIVT) over long periods of time. |  SIVT  
highRiskDeveloper |  An app that belongs to a developer that has created one or more blacklisted apps, and which also generates a large volume of invalid traffic. |  SIVT  
inactiveApp |  Apps that have not generated any ad-traffic for a period of more than a month, and thus appear inactive. If they appear active again, the chances are that their identity has been spoofed in order to commit ad-fraud. Apps usually appear inactive after they are blocked or evicted due to some kind of fraudulent activities performed. |  SIVT  
locationSpoofing |  An App that persistently and inaccurately reports (spoofs) the real location of the mobile device over a long period of time. The location reported to the ad-exchange varies significantly from the location that is obtained by the IP address (IP geolocation) of the mobile device. This risk type also corresponds to devices that appear to change locations at very high velocities that no human would ever be able to travel at. |  SIVT  
locationObfuscation |  Activity originating from an IP where multiple impressions deviate from the geographic location that is reported in the advertising transaction. |  SIVT  
malware |  An app that persistently generates traffic associated with malware domain URLs (can be due to in-app browsers). |  SIVT  
maskediCloudRelayIP |  The IP of a user does not match the IP and the associated ISP reported in the advertising transaction, and the reported IP was claimed to be an iCloud Private Relay IP address. |  SIVT  
maskedIp |  The IP of a user does not match the IP and the associated ISP reported in the advertising transaction. |  SIVT  
noAdsTxt |  Apps generating ad impressions without a valid app-ads.txt file, indicating unauthorized inventory |  Not IVT  
proxy |  The impression is from an intermediary proxy device that exists to manipulate traffic counts, pass non­human or invalid traffic or fails to comply with the protocol. |  SIVT  
videoImpressionFraud |  Video ad impressions that are generated from the same browser or device at a statistically significant inflated rate. |  SIVT  
  
### Identifying the app ID provided by Pixalate 

The high risk app list provided by Pixalate consists of two major data points that uniquely characterize an app:

1) The app identifier (stored under the “appId” column in the app list) which represents an app-store specific appId. When an app has also a bundleId available, it will be stored under the “bundleId” column.

2) the operating system name on which the app is installed.

In addition to the above data points, the title of the app is provided whenever it is available through the app stores, as well as the app store link where more information regarding the app can be found, such as logos, screenshots, reviews, etc.

The appId field in the list is case-sensitive. So, “com.abc” is different than “com.Abc”. In addition, due to the fact that the appId or bundleId are not user friendly identifiers (unlike domain names on the Internet), the user should be extremely careful on how he/she interprets the data provided and what conclusions are derived from them. For example, an appId that contains the word “facebook” does NOT necessarily mean that is associated with “[facebook.com](http://facebook.com)”. The same applies in the case of keywords found in the app title column. Finally, it is very likely that low quality apps could use deceptive names that might imitate popular app names in order to increase their downloads and their overall traffic.

### Best Practices

It is highly recommended that clients ping their FTP hourly to check for new lists. If a new one is present, it should COMPLETELY REPLACE the old file. Failure to update the most recent list will lead to leakage of IVT and increased IVT rates.

### App or Bundle IDs that look like 'Domains'

In the context of the mobile app data feed, these entries that appear to be domains **are not actual domains** but misrepresented ‘bundle IDs’ we see coming from mobile app traffic.   
  
The reason these are in the data feed is because these ‘bundle IDs’ are not valid mobile app bundle IDs and may elevate your risk of invalid traffic should ad transactions occur on inventory with these IDs. Usually bundle ids are in the form of reverse domain (for example, com.hulu.plus), but a number of the apps - especially the “bad” ones - use the incorrect form, which makes it look like a domain even though it is a bundle id.   
  
Example:  
  
\- The domain “[abc13.com](http://abc13.com/)” is a valid desktop or mobile web website but is not a valid mobile app or bundle ID.   
  
\- The mobile app equivalent for ABC13 have the following valid app or bundle ID: **com.abclocal.ktrk.news (Android)** and **407345290 (iOS)****  
****  
****-** There is no mobile app with the app or bundleId = “abc13.com” which is why it is in the mobile app datafeed.

### OS Decisioning

App/bundle IDs for the same application are often named differently for each OS platform. For example, the app XYZ may lists its bundle ID on iOS as "com.company.xyz", but on Android it is listed as "com.xyz.app". If the entry on the High Risk App List includes the app ID "com.company.xyz" but the osName is "Android", it is likely the app is either spoofed or using a deceptive name. In this case, you would only want to block "com.company.xyz" on Android so to not block users on the official XYZ app on iOS. It is for this reason that it is highly advised to match both app ID and OS when determine blocking decisions. 

### FAQs:

  * **In the High Risk App blocklist, how should I use the App ID, Bundle ID, and OS columns?**
    * When blocking an app listed in the high risk app blocklist, we recommend blocking the App ID + OS at a minimum to prevent inadvertently blocking an App ID of the version that is not flagged as high risk. You can also block App ID + Bundle ID + OS for better accuracy of blocking the right app pre-bid.
  * **Why do some Bundle IDs or App IDs appear in the high risk app blocklist but disappear after a few days or weeks?  
**
    * In general, high risk apps have a look-back period for monitoring suspicious traffic characteristics and any indication of improving or worsening traffic patterns. The addition or removal of a bundle ID in a blocklist can be dynamic because the high risk app list is generated daily.

    * The presence of IVT, if / when it improves over time after the bundle or app ID was added to the blocklist, determines whether the app “ages off” the list for a particular IVT type.

    * An app aging off the blocklist does not guarantee that it will no longer be added to the blocklist because an app can be flagged for other IVT types in the future.

    * We recommend adding the OS when decisioning to block or not block an app ID or bundle ID pre-bid. 

### Probabilities

The high risk app list provides a lot of flexibility to the end-user for blocking specific risk- types, operating systems, or app/bundleIds. It also enables the filtration of specific appIds based on some probability threshold. The probability threshold will correspond to the least amount of evidence that a given appId has shown in order to be associated with a given risk factor. As a generic guideline, Pixalate recommends the following probability thresholds, depending on the client needs:

1) probability equal to 1, for filtering out only the worst offender appIds (deterministic risk)

2) probability greater than or equal to 0.9 for filtering out apps, that have a high risk factor beyond a reasonable doubt

3) probability greater than or equal to 0.75, for filtering out apps that are associated with clear and convincing evidence of a high risk factor

4) probability greater than or equal to 0.5, for filtering out apps that it is more likely than not that they are associated with a high risk factor.

In general, it is a good tactic to start implementing the list with a threshold of 0.75 and then move it up or down until the desired operating point has been achieved, in terms of overall inventory volume and risk level.
