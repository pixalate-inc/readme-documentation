---
title: "User-Agent Block List"
excerpt: "The daily and weekly blocklisted user-agent feeds, how bad UA strings are identified from IAB lists and Pixalate data, and how to download them."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The Blocklisted User Agent (UA) feed provides an additional method of preventing non-human traffic since bots usually use specific UA strings that reveal their identity.

The thread is created based on the list of valid UA strings and the list of known crawler and spiders provided by the Interactive Advertising Bureau (IAB). In addition, those deterministically bad UA strings are enhanced with data created by Pixalate regarding the behavior of a specific UA string in performing fraud, thus enabling a super fast detection of new bot UA strings that do not belong to the IAB list yet.

There is a list generated weekly and daily. 

  * **Daily files** : 
    * Check once every hour
    * Download only when a new file is available
    * Continue hourly checks even after downloading, as multiple files may occasionally be uploaded
  * **Weekly files** : 
    * Check once every hour on Friday
    * Download only when a new file is available
    * Stop pinging once the new file is found

Naming convention: UAblacklistingWeekXX or UAblacklisting_YYYYMMDD

Schema: browserAgent

Example: 

![Screenshot 2026-03-26 at 08.54.03](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2008.54.03.png)

In general, UAs may surface on this list for a variety of IVT types;

  * Deterministic UAs of high risk (1.0 probability) generally consist of known bots/spiders/crawlers, including those outlined by the Interactive Advertising Bureau (IAB) / IAB Tech Lab through their **IAB/ABC Spiders & Bots List**;
  * Deterministic UAs of high risk (1.0 probability) associated with pervasive sophisticated invalid traffic (SIVT) oftentimes ascribed to complex bot networks/botnets;
  * Deterministic UAs of high risk (1.0 probability) associated with observed hyperactive users with prolonged periods of activity and outlier traffic trends, in excess of ascribed thresholds across such instances

Given the nature of UAs and the rapid ability of such information to be spoofed/self-declared for purposes of perpetuating invalid traffic and ad fraud, Pixalate strongly encourages clients to utilize the most current datafeeds available; coupled with post-bid assessment to tailor such lists across monetized traffic.

### Best Practices: User Agent & IP blocklists

The User Agent (UA) and IP blocklists are two separate blocklists that should be used together as a 2-step filter in order to remove any illegitimate traffic. Using both lists at the same time improves the effectiveness of each list when used by itself.

The UA blocklist contains UA strings that are used by non-human users such as:

  1. Search engine crawlers which index web pages but they reveal their true identity (e.g. GoogleBot)

  2. UA strings that are used by customized crawlers (e.g. a UA string that contains the keyword “grabber”, or “python”, etc)

  3. UA strings that do not contain at least one of the “must-have” keywords that characterize a valid UA string, per the guidelines of the Interactive Advertising Bureau (IAB).

The IP blocklist contains IPs that have been recently used to generate invalid impressions or clicks. Each IP is associated with a probability score and a corresponding fraud type, which represent how likely a given IP is to be performing this specific fraud type. The IPs contained in the blocklists have been used by:

  1. Search engine crawlers (e.g. the IPs that the GoogleBot uses)

  2. Customized bots (e.g. the IPs that are used to crawl the web by a University research lab)

  3. Machines infected with malware that create invalid impressions or clicks

  4. Machines that are hosted in datacenters and would not be used by a real human to browse the web

  5. Machines that are used to perform some kind of fraud (e.g. a click farm)

A list that contains both UA strings and IP lists will restrict the effectiveness of fraud prevention, since if any of the two elements in a UA/IP pair changes, then the new resulting pair will not match any entry in the blocklist. In other words, in the example of the GoogleBot shown below, if you are matching against both UA and IP, then if the GoogleBot changes its' UA and/or IP address, it will not be detected. However, if you use two separate lists, the first list will catch any GoogleBot that comes from any IP in the world, and the second list will catch any crawler that comes from this specific Google IP, even if it uses a previously unseen UA string.

All incoming requests matching any UA string **OR** IP in the blocklist above the chosen threshold SHOULD be blocked. It is not recommended to use an intersection of the two lists (see following graph for reference).

Example: impression will be blocked if the IP is in the IP blocklist **OR** the UA is in the UA blocklist.

### Best Practices: User Agent & IP blocklists (Example)

UA String |  IP Address  
---|---  
Mozilla/5.0 (compatible; Googlebot/2.1; +<http://www.google.com/bot.html>) |  66.249.66.1  
  
The two blocklists should be used sequentially for maximum efficiency. The order does not matter, as long as the two lists are used with an “OR” statement (i.e. the impression should match either the UA blocklist OR the IP blocklist in order to be blocked).
