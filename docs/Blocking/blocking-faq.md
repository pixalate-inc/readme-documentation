---
title: "Blocking FAQ"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### Blocklists

  * **How many domains are on the pre-bid block lists?**

    * 40,000

  * **How many mobile apps are on the pre-bid block lists?**

    * 30,000

  * **How are bad IPs added to the block list?**

    * We provide IPs that can belong to data centers, bad proxies, infected machine/cable IP or organization IP. It does not necessarily have to be a botnet. In short, if we see any sort of suspicious activity on an IP we flag it. The IP is checked against the percentage of bad behavior before it is added (i.e. the IP must have statistical significance to be added).

  * **What is the difference between the TOR/Proxy blocklist and the Gateway “reference” list?**

    * The TOR/Proxy IP blocklist is a list that can be used to prevent high risk users that hide behind proxies in order to rotate their IP frequently, as well as spoof their location, in order to conduct various IVT activities. In addition, given the fact that TOR browsers by default have ad blockers enabled, seeing ad transactions behind TOR can also indicate additional risks since the user must have taken an explicit action to disable the ad blocker with the potential intent to generate ad impressions. 

    * On the other hand, the Gateway IP list is a reference list and NOT a blocklist. It is intended to be used as an additional vetting mechanism that can enhance IP or other device blocking datafeed, since it contains the total number of users seen behind a given gateway IP (e.g. a home router that acts as a NAT and it shows the same user IP to multiple different devices behind it). To take advantage of such additional information, it is recommended that it is used to build additional logic and, for example, block only IPs that have a small number of devices behind, etc.

  * **Is the "Proxy" IVT Type covered by the Generic IP Block List, or Data Centre List, or Gateway Blocklist?**

    * The Proxy IVT type is covered by the regular IP blocklists as long as certain high IVT criteria are met. In addition, as explained above, the gateway list should not be used for blocking but as an additional information source to enhance IP blocking, since it contains the total number of users detected behind all active IPs.

  * **Is the TOR/Proxy list just baked into the Generic IP blocklist? I do see there is a type of “proxy” in that list for some IPs, though I don’t see any explicit reference to TOR.**

    * Yes, TOR/Proxy IPs are included in the Generic IP blocklist. TOR IPs show up less in the blocklist because there are very few TOR IPs in general.

  * **What are the average file sizes for each blocklist?**_(Updated as of Aug 2025)_

    * **IP Addresses:**
      * **IP (v4):** up to 1.8GB

      * **IP (v6):** up to 1GB

      * **Datacenter IPs:** up to 5MB
      * **Proxy Gateway:** up to 1GB

  *     * **User Agent:** up to 5MB

  *     * **Feeds for Mobile:**

      * **Mobile Device ID:** up to 5GB

      * **High Risk Mobile App List:** Up to 6MB
      * **Mobile Apps Delisted From the App Store (DEFASE):** up to 1GB 
      * **Mobile Apps Blocklist (DEFASE):** up to 5.5MB

  *     * **Feeds for Connected TV:**

      * **CTV Device ID:** up to 2GB

      * **High Risk CTV App List:** up to 1MB
      * **CTV Apps Delisted From the App Store (DEFASE):** up to 3MB 

  *     * **High Risk Domain List:** up to 5MB
    * **COPPA Datafeeds:**
      * **COPPA Audience (child directed):** up to 35MB
      * **Compliance Risk Rating:** up to 8MB

  *     * **Supply Path Optimization (SPO):** up to 2MB
    * **"Made For Advertising" lists:**
      * **"MFA" for Websites:** up to 2MB
      * **"MFA" for CTV Apps:** up to 1MB
      * **"MFA" for Mobile Apps:** up to 1MB

  * **In the IP data feeds, we sometimes have "highriskapp" as the reason for the inclusion of the IP. What is the relationship between the IP and IVT designation in this case?**

    * The IP in the data feed is an IP that generates high volumes on one or more high risk apps, i.e. apps that have been blocked due to high IVT rates.

  * **In the IDFA block list, are illegal or malformed or whatever IDFAs like that included?**
    * The device ID blocklist consists of various device identifiers that cover all the major platforms including iTunes and Google play. Spoofed device identifiers are included in the device ID blocklist, however, the blocking effectiveness can be limited if the spoofed devices are short-lived, since, by definition, they get reset pretty quickly. For cases like this, IP or app level blocklist can provide assistance in preventing IVT from bad sources. 
  * **Is IDFA in the format of 000-000000-0000-and so on considered to be illegal IDFA?**
    * IDFAs in the “Do-Not-Track” (DNT) format are not added to the blocklist since by definition, they belong to multiple users not all of the generating invalid traffic. For this, users with DNT enabled that generate IVT should be blocked using other blocking identifiers including the IPv6 blocklist (that targets individual devices using their unique IPv6 address), IPs, or app IDs (if the app aggregates large volumes of invalid traffic).

### General

  * **How often are the pre-bid blocklists updated?**
    * Our pre-bid blocklists are updated daily. IP and Device lists are updated twice daily.

  * **What is our latency or response time to the API?**  

    * Response time is the amount of time our API takes to respond to a request once received. For example, once we get a request, the time between the execution of the request, and a result is returned of its computation, that’s the response time, to which our average response time is ~1ms.   
  
Latency is otherwise known as Remote Response time. For instance, you want to invoke a web service or access a web page. Apart from the processing time that is needed on the server to process the request, there is a delay involved for the request to reach the server. It can be affected by geographic location relative to our data centers, a person's network connection, computer speed, etc. to which our average Remote Response time is ~200ms as measured by Pingdom a third party measurement and monitoring tool, which measures from all over the globe
  * **How does Blocking relate to the first-party data measured in Analytics and the representation in the MRT?**
    * It is important to note that there are differences on how IVT is being presented depending on what platform and data set is being reviewed:  
  
\- The first party data in a client's Analytics dashboard and the level of IVT in that context  
\- MRT IVT data and how that is based on Pixalate's global data pool and not just a client's measured first-party data  
\- How apps are flagged in the the Pixalate blocklists  
  
Not all the IVT types we identify and measure using a client's first-party data via the Analytics dashboard goes into the MRT for a combination of reasons. Likewise, not all IVT types flagged in a client’s first-party data leads to the app to being flagged in the blocklist.  
  
IVT can be a product of compromised devices, bot farms, or behavior observed from the app themselves.   
  
When evaluating IVT, we take all of this into consideration and behavioral correlations in order to determine whether the flagged impressions show a stronger association to the app itself or the devices generating the impressions.   
  
This is in order to avoid penalizing an app for misrepresented traffic or bad devices.   
  
In addition, this is why we advise clients to work directly with the seller or publisher in order to figure out where the sources of these problematic devices are coming from. 

### How to Use

  * **How do you share the pre-bid blocking lists? Is it via API, or a downloadable .csv file, or some other way?**
    * We have an FTP server; clients can download from that FTP server.

  * **If there is a domain or app on the blocklist that I don't want to block, can I do that?**
    * Yes. Because our blocklists are pre-bid, clients can apply the pre-bid lists any way they want.

  * **What is the fraud scoring and how do we use it?**
    * It's a normalized score between 0-1. The closer to 1, the higher the likelihood that it is fraudulent. To get a placement with the least fraud, sort by fraud score in descending order.

  * **Where should I place the fraud threshold? What is Pixalate's recommendation?**
    * Pixalate does not make a strong recommendation to clients on where to place the threshold. That being said, most clients generally start around .75 - 1 for testing and adjust accordingly.

  * **What is the recommended ping frequency for each blocklist?**
    * IP Block List: hourly daily 
    * Data Center IPs: hourly every Friday (Pacific time)
    * Domain Block List: hourly daily
    * User Agent List: hourly daily

  *     * Device ID: hourly daily
    * App: hourly daily
    * DEFASE (Delisted from the App Store): hourly daily  

    * COPPA datafeeds: hourly every Sunday and Monday (Pacific time)

The user agent list has a daily and weekly version, you may reach out to your CS rep to confirm what version you are on.

  * **What are the steps to whitelist an IP?**
    1. The client answers the following questions: Who does the IP belong to, how is it being used, are bots used in the testing process, and when did the problem occur?
    2. Pixalate check: Pixalate checks the fraud type and determines how many impressions are coming from that IP each day and at what frequency.
    3. Action: If Pixalate confirms the IP is for legitimate testing, Pixalate whitelists the IP and applies it to the whitelist; if not, the IP remains on the blocklist.

  * **What are all of the integration options for your pre-bid solution?**
    * API
    * Data Feeds (pre-bid blocklists): IP, Device ID, User Agent, Data Center, Domain, App ID.

### DElisted From the App StorE (DEFASE) 

  * **What is the defaseApp IVT Type?**

    * The IVT type called “defasedApp” characterizes traffic seen from apps that were available for download through one of the two major app stores (namely Google Play and iTunes) over the last 12 months but got delisted and currently are not available any more. 

  * **Are there any data feeds that can protect us from “defasedApps”?**

    * Yes. Pixalate has developed two datafeeds related to delisted apps:

      * A data feed containing all the removed apps from Google Play and iTunes store within the last 6 months. The friendly name for this data feed is “Defase App List”.

      * A data feed containing all the apps removed from Google Play and iTunes store within the last 6 months, which have generated impressions in the last 2 weeks and which also have shown evidence of suspicious or invalid behavior. The friendly name for this data feed is “Defase App Blocklist”.

    * Based on the above definitions, the first list can contain apps that do not have ads or do not have impressions at all, but nevertheless they can be useful if proactively blocked to avoid being manipulated for IVT in the future. 

    * The second list contains apps that have been seen generating impressions and in general should be treated as IVT and be blocked. Note: Pixalate has developed algorithms to detect and exclude from the second list potential cases of removed apps that should not be blocked and treated as IVT because their removal was likely not related to IVT. Examples of such apps include cases removed temporarily due to legal issues, that are usually put back in the app store a few days or weeks later.

  * **What is the schema of the two DEFASE data feeds?**

    * Both data feeds have the same schema as shown in the table below:

Column Name |  Data Type |  Description  
---|---|---  
osName |  STRING |  The name of the Operating System (OS) that the app is installed. Currently only iOS (for Apple iTunes) and Android (for Google Play) are supported.   
appId |  STRING |  The app identifier that uniquely characterises an app for a given operating system. This will be the (numeric) “trackId” for Apple iTunes apps, and “package name” for Google Play.   
bundleId |  STRING |  This is the bundleId that exists for iTunes apps only.  
lastSeen |  STRING |  This is the date the app was removed from the app store.  
appStoreUrl |  STRING |  This is the URL that was making the app available for download. A delisted app is expected to trigger an HTTP 404 error code (not found) when the URL is accessed.   
appStoreName |  STRING |  The friendly name of the app store that was serving the app (i.e. Google Play and Apple iTunes).   
  
  * **How should I apply the DEFASE data feeds?**
    * Both data feeds have the same schemas and semantics behind, so both should be applied the same way, as described below: 
      * For an iOS app, the matching can be done on either the appId column (which contains the numeric trackId of the iOS app) or the bundleId column. 
      * For an Android app, the matching needs to be done at the appId column, which contains the bundleId for an android app.

  * **What is the update frequency of the DEFASE data feeds?**
    * The two data feeds are updated daily. 

  * **Regarding DEFASE, if the apps have recently been seen doing IVT, wouldn’t they already be on the high risk app list we already consume? In other words, what is the incremental utility of the DEFASE app blocklist given that we consume the high risk app list already?**

    * Regarding the utility of the DEFASE app blocklist with respect to the HighRisk app blocklist, while it is true that the high risk app list does include apps with high IVT, it doesn’t label apps that have been recently removed from their respective app stores as such. 

The rationale behind a separate blocklist from the HighRisk app blocklist comes from the fact that: 

      * Blocking all delisted apps might not fit the needs of all organizations since some might only care about the apps that have shown impressions in the past (e.g. for more efficient blocking), and/or some indicators of IVT (e.g. to avoid flagging apps that have been removed for non IVT reasons such as copyright violations), and
      * Moderate IVT apps might not be showing enough evidence to be included in the HighRisk app blocklist. 

For this, we choose to cover this intermediate IVT risk use-case with a separate blocklist that can be applied according to the business needs of an organization. 

In other words, for the DEFASE blocklist that has IVT data, it does not mean that the IVT levels before were necessarily extreme enough across the board in order for the app to be included in the HighRisk app list (i.e. IVT may be coming only from a small subset of sources). 

On the other hand, the fact that a given set of apps with moderate IVT got removed from an app store acts as an additional strong indicator of risk that is used in conjunction with other indicators of IVT to compile a separate blocklist from the HighRisk app blocklist. 

### IPv6

  * **What is IPv6?**
    * IPv6, though introduced in the late 90s, is now becoming more widely used as a way to mitigate the problem of IPv4 address exhaustion. Particularly for our growing IoT world, IPv4 could not supply the number of distinct IPs needed for each device. 
    * IPv6 addresses are 128-bits in length, instead of the 32bits of IPv4. This longer identifier provides enough address bandwidth to uniquely identify all the connected devices across the IoT ecosystem. 
    * IPv6 adoption is escalating, with growth being driven by residential and wireless ISPs. IPv6 will eventually replace IPv4 but this will take time. Until complete adoption takes place, we are in a transition period where the ISPs that support IPv6 also support a IPv4 (i.e. dual stack interfaces). 

  * **How is IPv6 related to OTT?**
    * IPv6 addresses are not limited to OTT/CTV devices. However, because OTT/CTV devices are relatively new and mainly served by residential ISPs, they have a high coverage of IPv6 thus giving the capability to uniquely identify an OTT device using its IPv6, even if the device ID (e.g. UDID) changes or gets spoofed. Of course, this does not mean that IPv6 can replace device identifiers, since IPv6 might change over time while the device identifier might remain the same. In case of IPv4, an entire household would have the same IPv4 for all the devices behind the router/NAT. This creates targeting and device identification challenges for advertisers. Because it acts as a more granular user identifier, IPv6 has significant advantages for precise fraud detection, accurate pre-bid solutions and device graph/audience targeting. 

  * **How much IP traffic is IPV6 (vs IPV4)?**
    * Currently, most IPs are still IPv4, however, IPv6 is gaining share in residential and cellular (mobile) IP ranges with the adoption rates exceeding 90% in many cases. The exact number of IPv6 enabled interfaces differs by ISP.

  * **Why would I need to implement both IPv4 and IPv6 lists?**
    * The current market transitional state, which is likely to last for several years, is one where IPv4 and IPv6 will coexist. An IPV4 based blocking solution, since it is less granular in terms of identifying a traffic point (entire household could have the same IP, or one cell tower), is also less precise in identifying IVT. This means IPv6 will, in many cases, be able to fill that gap - targeting “good” IPv6 devices while blocking the “bad”, all of which would have been blocked under IPv4. Since IPv6 support might not be available everywhere (or even be disabled), being able to work with both formats is highly recommended for the duration of the IPv6 transitional period. For example, if only 10% of the impressions seen behind an IPv4 are IVT, then blocking the whole IP would result to blocking a lot of good traffic. However, if IPv6 is enabled for this 10% of the bad impressions, then we can block the 10% without blocking any traffic from the 90%. 

  * **Why are the lists separate?**
    * IPv6 is an entirely different addressing scheme that would require a different integration due to the disparate address format as well as the separate locations where the IPv6 data will be observed at the client’s side (e.g. a client can have a separate IPv6 and IPv4 servers to perform blocking). In addition, since one IPv4 can be associated with multiple IPv6, it might be that a given IPv4 is not added to the blacklist because of significant volumes of good traffic, but some of its IPv6 counterparts are added because they are very fraudulent. In order to accurately identify fraud at the IP-level, the two lists are independently needed.

  * **Do the two lists coordinate with each other?**
    * Yes, one of the unique benefits of Pixalate’s IPv6 and IPv4 lists is the way our data collection takes place. Pixalate has developed a proprietary mechanism to collect, for each ad transaction, both IPv4 and IPv6 (if available) without compromising one for the other. This means we are able to create threat intelligence at both levels while providing much better coverage. For example, we can say that an IPv4 that is known to be bad can be used to block (proactively) previously unseen IPv6 addresses associated with it. Alternatively, an IPv6 can be used to block only the bad traffic portions of its associated IPv4. 

  * **How often is the IPv6 list updated?**
    * The IPv6 list is updated twice per day.
