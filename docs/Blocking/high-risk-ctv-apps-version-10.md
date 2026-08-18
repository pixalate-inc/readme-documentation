---
title: "High Risk CTV Apps (Version 1.0)"
excerpt: "The daily high risk CTV app list: how it is compiled across CTV operating systems, plus its update interval, schema and risk type definitions."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The High Risk CTV App lists are daily updated lists of the most high risk CTV app IDs from the most prominent CTV operating systems (e.g. Android, FireOS, Linux, Roku, Samsung, Sony, tvOS, WebOS, Windows, XBox).

### Methodology 

To compile the list, Pixalate analyzes the RTB traffic characteristics of thousands of CTV apps in the world that are selling inventory on RTB exchanges, and through its sophisticated Machine Learning Models captures a wide variety of risk-types in order to provide fine-grained blocking capabilities of specific app behaviors or traffic patterns. Apps are assessed based on its data available through the programmatic channel, as well as the data available through the various app stores that an app is or isn’t available from.

#### High Risk App List

Apps that have shown suspicious traffic characteristics or are potentially malicious.

Update Interval: Once per day (estimated availability 12:00 PM)

File Format: CSV

Naming convention in FTP folder: CtvHighRiskApps_YYYYMMDD

Schema: osName | platformName | appId | bundleId | riskType | probability

#### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
osName | STRING  |  The Operating System (OS) name that is associated with a given app.  
platformName |  STRING |  The platform where the CTV app is available.   
appId |  STRING |  The actual ID that characterizes a CTV app.  
bundleId |  STRING |  The bundle ID associated with the app (if available).  
riskType |  STRING |  The mnemonic name that characterizes the type of risk associated with a given appId (e.g. “locationSpoofing”)  
probability |  FLOAT |  A number between 0.5 and 1 that characterizes the likelihood that the given appId is associated with a specific risk type (e.g 0.7 is 70% probability). The higher the probability number, the higher the specific risk.  
  
### Example:

### ![Screenshot 2026-03-26 at 09.21.28](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.21.28.png)

### IVT Types

The IVT types included are all the IVT types that one can see in the Pixalate’s dashboard, except the ones that can be triggered due to integration issues such as “duplicateImpressions” and “duplicateClicks”. 

#### **What are some of the common fraud types seen in CTV?**

Ad fraud in CTV takes on several forms, but among the most common we see include:

  * Proxy IVT

Proxy IVT is when we detect SSAI that is invalid. For example, if the client’s IP doesn’t match the IP detected when the ad is rendered and if the proxy IP is determined to be invalid, then the traffic is flagged as Proxy IVT.

  * Video Impression Fraud

Video Impression Fraud is when we detect statistically significant outlier user behavior. Video Impression Fraud can occur on any device, including OTT. Pixalate’s algorithms and machine-learning models are used to detect anomalous behavior.

  * Data center

Data center traffic is any traffic with an IP address that is identified as a data center. For example, hundreds of jailbroken CTV devices can be set up to continually play CTV content on a specific app or group of apps.

  * IP Obfuscation

IP obfuscation occurs when a proxy IP is discovered, but there exists a cookie that extends to a statistically significant inflated number of unique device IDs or IPs. This could be a sign that a fraudster is using a desktop device masquerading as an CTV device.

  * App Spoofing

Device behind traffic from apps that appear to be spoofed either at the impression level or at more macroscopic levels.

### Identifying the app ID provided by Pixalate 

The high risk app list provided by Pixalate consists of two major data points that uniquely characterize an app:

1) The app identifier (stored under the “appId” column in the app list) which represents an app-store specific appId. When an app has also a bundleId available, it will be stored under the “bundleId” column.

2) the operating system name on which the app is installed.

In addition to the above data points, the title of the app is provided whenever it is available through the app stores, as well as the app store link where more information regarding the app can be found, such as logos, screenshots, reviews, etc.

Due to the fact that the appId or bundleId are not user friendly identifiers (unlike domain names on the Internet), the user should be extremely careful on how he/she interprets the data provided and what conclusions are derived from them. For example, an appId that contains the word “hulu” does NOT necessarily mean that is associated with “[hulu.com](https://hulu.com)”.

The same applies in the case of keywords found in the app title column. Finally, it is very likely that low quality apps could use deceptive names that might imitate popular app names in order to increase their downloads and their overall traffic.

### Best Practices

It is highly recommended that clients ping their FTP hourly to check for new lists. If a new one is present, is should COMPLETELY REPLACE the old file. Failure to update the most recent list will lead to leakage of IVT and increased IVT rates.

### App or Bundle IDs that look like 'Domains'

In the context of the CTV app data feed, these entries that appear to be domains **are not actual domains** but misrepresented ‘bundle IDs’ we see coming from CTV app traffic.   
  
The reason these are in the data feed is because these ‘bundle IDs’ are not valid CTV app bundle IDs and may elevate your risk of invalid traffic should ad transactions occur on inventory with these IDs. Usually bundle ids are in the form of reverse domain (for example, com.hulu.plus), but a number of the apps - especially the “bad” ones - use the incorrect form, which makes it look like a domain even though it is a bundle id.   
  
Example:  
  
\- The domain “[abc13.com](http://abc13.com/)” is a valid desktop or mobile web website but is not a valid CTV app or bundle ID.   
  
\- The CTV app equivalent for ABC13 have the following valid app ID on: 

  * Roku: 583120
  * FireTV: B01NGTU3P5
  * tvOS: 407345290

**-** There is no CTV app with the app or bundleId = “abc13.com” which is why it is in the CTV app datafeed.

### OS Decisioning

App/bundle IDs for the same application are often named differently for each OS platform. For example, the app XYZ may lists its bundle ID on Samsung as "com.company.xyz", but on FireTV it is listed as "com.xyz.app".

If the entry on the High Risk App List includes the app ID "com.company.xyz" but the osName is "FireTV", it is likely the app is either spoofed or using a deceptive name. In this case, you would only want to block "com.company.xyz" on FireTV so to not block users on the official XYZ app on Samsung.

It is for this reason that it is highly advised to match both app ID and OS when determine blocking decisions. 

### Probabilities

The CTV high risk app list provides a lot of flexibility to the end-user for blocking specific risk- types, operating systems, or app/bundleIds. It also enables the filtration of specific appIds based on some probability threshold. The probability threshold will correspond to the least amount of evidence that a given appId has shown in order to be associated with a given risk factor. As a generic guideline, Pixalate recommends the following probability thresholds, depending on the client needs:

1) probability equal to 1, for filtering out only the worst offender appIds (deterministic risk)

2) probability greater than or equal to 0.9 for filtering out apps, that have a high risk factor beyond a reasonable doubt

3) probability greater than or equal to 0.75, for filtering out apps that are associated with clear and convincing evidence of a high risk factor

4) probability greater than or equal to 0.5, for filtering out apps that it is more likely than not that they are associated with a high risk factor.

In general, it is a good tactic to start implementing the list with a threshold of 0.75 and then move it up or down until the desired operating point has been achieved, in terms of overall inventory volume and risk level.
