---
title: "Mobile High Risk App Lists"
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

  * High Risk App List
  * New App List
  * VPN App List

The New App List & VPN App List do NOT contain apps that have generated evidence of some kind of invalid traffic; otherwise, they would have been included in the high risk app list. The lists are provided by Pixalate as an additional proactive mechanism for clients that want to use an extra layer of filtration.

#### High Risk App List

Apps that have shown suspicious traffic characteristics or are potentially malicious.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: MobileHighRiskAppSelection_YYYYMMDD

Schema: appId | bundleId | osName | riskType | probability | appStoreUrl | appStoreName

#### New App List

Brand-new apps (< 6 months) that have not build their reputation yet to leave our sandbox, and thus have higher likelihood to misbehave in the near future.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: MobileNewAppSelection_YYYYMMDD

Schema: appId | bundleId | osName | appStoreUrl | appStoreName

#### VPN App List

Apps that are mainly used to hide the IP of the device and its real location

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: MobileVpnAppSelection_YYYYMMDD

Schema: appId | bundleId | osName | appStoreUrl | appStoreName

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

**IVT Name** |  **Description** |  **IVT Type**  
---|---|---  
appSpoofing |  An app that has suspicious traffic characteristics and may also have data inconsistencies or mismatches in what is being declared in the bid request vs. what Pixalate is detecting. This IVT type may also include obfuscation of device information, user-agent, and other datasets, as well as misrepresentation of the appId (or bundleId) where one or more of the appIds (or bundleIds) used will not match the appId (or bundleId) of the device’s operating system. For example, at the time of this writing, if you see “com.pandora.android” on iOS, it will be a spoofed appId since this is a valid appId only for Android. In addition, the valid app identifiers for Pandora on iOS are “284035177” (appId) or “com.pandora” (bundleId) but none of them is observed here. These may also be popular apps that do not show programmatic display ads, and thus should never appear in RTB generating ad requests |  SIVT  
datacenter |  An app that persistently generates traffic originating from IPs that belong to datacenters and which cannot be used by human users. |  GIVT  
fastClicker |  Apps that generate a large volume of clicks that are 1 second apart from the ad impression. |  GIVT  
IABcrawler |  An app that persistently generates traffic that is associated with User Agent (UA) strings that belong to crawlers, according to the IAB list of crawler signatures. |  GIVT  
IABdummyBot |  An app that persistently generates traffic that is associated with an invalid User Agent (UA) string, according to the IAB list of invalid UA strings. |  GIVT  
highRisk |  Apps that generate large volumes of Sophisticated Invalid Traffic (SIVT) over long periods of time. |  SIVT  
highRiskDeveloper |  An app that belongs to a developer that has created one or more blacklisted apps, and which also generates a large volume of invalid traffic. |  SIVT  
inactiveApp |  Apps that have not generated any ad-traffic for a period of more than a month, and thus appear inactive. If they appear active again, the chances are that their identity has been spoofed in order to commit ad-fraud. Apps usually appear inactive after they are blocked or evicted due to some kind of fraudulent activities performed. |  SIVT  
locationSpoofing |  An App that persistently and inaccurately reports (spoofs) the real location of the mobile device over a long period of time. The location reported to the ad-exchange varies significantly from the location that is obtained by the IP address (IP geolocation) of the mobile device. This risk type also corresponds to devices that appear to change locations at very high velocities that no human would ever be able to travel at. |  SIVT  
malware |  An app that persistently generates traffic associated with malware domain URLs (can be due to in-app browsers). |  SIVT  
  
### Identifying the app ID provided by Pixalate 

The high risk app list provided by Pixalate consists of two major data points that uniquely characterize an app:

1) The app identifier (stored under the “appId” column in the app list) which represents an app-store specific appId. When an app has also a bundleId available, it will be stored under the “bundleId” column.

2) the operating system name on which the app is installed.

In addition to the above data points, the title of the app is provided whenever it is available through the app stores, as well as the app store link where more information regarding the app can be found, such as logos, screenshots, reviews, etc.

The appId field in the list is case-sensitive. So, “com.abc” is different than “com.Abc”. In addition, due to the fact that the appId or bundleId are not user friendly identifiers (unlike domain names on the Internet), the user should be extremely careful on how he/she interprets the data provided and what conclusions are derived from them. For example, an appId that contains the word “facebook” does NOT necessarily mean that is associated with “[facebook.com](http://facebook.com)”. The same applies in the case of keywords found in the app title column. Finally, it is very likely that low quality apps could use deceptive names that might imitate popular app names in order to increase their downloads and their overall traffic.

### Best Practices

It is highly recommended that clients ping their FTP hourly to check for new lists. If a new one is present, is should COMPLETELY REPLACE the old file. Failure to update the most recent list will lead to leakage of IVT and increased IVT rates.

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

### Probabilities

The high risk app list provides a lot of flexibility to the end-user for blocking specific risk- types, operating systems, or app/bundleIds. It also enables the filtration of specific appIds based on some probability threshold. The probability threshold will correspond to the least amount of evidence that a given appId has shown in order to be associated with a given risk factor. As a generic guideline, Pixalate recommends the following probability thresholds, depending on the client needs:

1) probability equal to 1, for filtering out only the worst offender appIds (deterministic risk)

2) probability greater than or equal to 0.9 for filtering out apps, that have a high risk factor beyond a reasonable doubt

3) probability greater than or equal to 0.75, for filtering out apps that are associated with clear and convincing evidence of a high risk factor

4) probability greater than or equal to 0.5, for filtering out apps that it is more likely than not that they are associated with a high risk factor.

In general, it is a good tactic to start implementing the list with a threshold of 0.75 and then move it up or down until the desired operating point has been achieved, in terms of overall inventory volume and risk level.
