---
title: "Using Overlap Reports"
excerpt: "How the Data Feeds overlap reports show the effectiveness of the pre-bid lists you subscribe to and help troubleshoot implementation."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The Pixalate Analytics dashboard contains a section for Data Feed Overlap Reports where they show our clients the effectiveness of the pre-bid lists that they are subscribed to, and troubleshoot any potential issues with implementation.

On the left navigation of the dashboard, we show you a menu item called “Data Feeds”.

If you click on this menu item, you will see reports for the following as the time this KB article was published:

  * [IPv4](https://www.pixalate.com/knowledgebase/ip-block-list-ipv4-and-ipv6)

  * [](https://www.pixalate.com/knowledgebase/ip-block-list-ipv4-and-ipv6)[Mobile Device ID](https://www.pixalate.com/knowledgebase/mobile-device-id-block-list)

  * [Data Center](https://www.pixalate.com/knowledgebase/data-center-block-list)
  * [IPv6](https://www.pixalate.com/knowledgebase/ip-block-list-ipv4-and-ipv6)
  * [High Risk Mobile Apps](https://www.pixalate.com/knowledgebase/high-risk-app-lists)
  * [High Risk CTV Apps](https://www.pixalate.com/knowledgebase/connected-tv-high-risk-app-list)
  * [High Risk Websites](https://www.pixalate.com/knowledgebase/domain-/-website-block-lists)
  * [CTV Device ID](https://www.pixalate.com/knowledgebase/ott-device-id-list)
  * [Mobile DEFASE (delisted from the app store) Apps](https://www.pixalate.com/knowledgebase/delisted-from-the-app-store-defase-block-list)
  * [CTV DEFASE (delisted from the app store) Apps](https://www.pixalate.com/knowledgebase/connected-tv-delisted-from-the-app-store-defase-list)[](https://www.pixalate.com/knowledgebase/ip-block-list-ipv4-and-ipv6)
  * [Made for Advertising Mobile Apps](https://www.pixalate.com/knowledgebase/how-to-use-pixalates-mfa-data-feeds-to-block-mfa-traffic)
  * [Made for Advertising CTV Apps](https://www.pixalate.com/knowledgebase/mfa-made-for-advertising-ctv-apps-data-feed)
  * [Made for Advertising Websites](https://www.pixalate.com/knowledgebase/mfa-made-for-advertising-domain-data-feed)
  * [User Agent](https://www.pixalate.com/knowledgebase/user-agent-block-list)
  * [Supply Path Optimization ](https://www.pixalate.com/knowledgebase/how-to-use-pixalates-spo-data-feeds-to-block-traffic)
  * [COPPA Compliance Feeds:](https://www.pixalate.com/knowledgebase/coppa-compliance-data-feeds-for-pre-bid)
    * Child Directed Mobile Apps
    * Child Directed CTV Apps
    * COPPA Compliance Risk for Mobile Apps
    * COPPA Compliance Risk for Mobile Apps
  * [Malformed CTV App IDs](https://www.pixalate.com/knowledgebase/malformed-unidentified-bundleids-blocklist)
  * [Proxy Gateways](https://www.pixalate.com/knowledgebase/proxy-gateway-feed)

As more data feed types are introduced by the Pixalate team over time, we will have corresponding reports to complement and illustrate how effective those feeds are to blocking sources of traffic quality issues. 

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202025-04-04%20at%2014-23-58-png.png)

These reports have two main objectives.

  1. Give a visual overview of when Pixalate uploads new lists to a secure FTP for download and consumption, and when the list is then downloaded by you, the client. 
     1. This allows you to see if you are missing any lists or if there are any large gaps of time between when the list is uploaded and when you download it.
     2. Missing lists or having large gaps between consumption of lists and when they are made available can cause some leakage wherein bad IP’s, Device ID’s, user agents, apps or domains may end up in your traffic. 
  2. Show our clients how effective the lists are at different probability thresholds. As you may be aware, Pixalate SIVT lists have probabilities associated with different data points. This is based on back-end analysis which gives us an overview of how “risky” an IP, Device ID, etc might be to transact on. Our probabilities range from .5 to 1, with 1 being deterministic that a given data point is a risk.  

![](https://f.hubspotusercontent40.net/hubfs/2364596/Screen%20Shot%202021-08-30%20at%204-39-48%20PM-png-1.png)

![Screen Shot 2025-01-24 at 11.16.26 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202025-01-24%20at%2011.16.26%20AM.png)

![Screen Shot 2025-01-24 at 12.35.39 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202025-01-24%20at%2012.35.39%20PM.png)

The reports give a seven day window showing how much ‘leakage’ there was in your traffic at a .5, .75 and 1 probability threshold. This allows us to see if the probability should be updated or changed, and if the expectations with applying the list(s) matches the data. 

The Datacenter User Agent and Defased pre-bid lists are deterministic GIVT lists, with no probabilities. Therefore, the overlap report shows you whether the list is being applied properly. If it is being applied properly, there should be no leakage of data through your data.

![Screen Shot 2025-01-24 at 12.31.32 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202025-01-24%20at%2012.31.32%20PM.png)

![Screen Shot 2025-01-24 at 12.29.20 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202025-01-24%20at%2012.29.20%20PM.png)

MFA Domains overlap is based on the amount of traffic that has passed through and is designated with a medium or high categorization. For more on Pixalate's MFA methodology, please see [here](https://www.pixalate.com/knowledgebase/pixalate-mfa-detection-product-overview).

![Screen Shot 2025-01-24 at 11.20.25 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202025-01-24%20at%2011.20.25%20AM.png)

Overlap for the following lists will be based on mapping the passed bundle/app ID to the associated store ID. This is important to note as it will influence how the lists will be implemented for blocking purposes.

  * Made for Advertising CTV Apps
  * Child Directed Apps (CTV)
  * High COPPA Compliance Risk Apps (CTV)
