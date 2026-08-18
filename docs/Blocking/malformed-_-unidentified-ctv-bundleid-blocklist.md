---
title: "Malformed / Unidentified CTV BundleId Blocklist"
excerpt: "The weekly feed of malformed and unidentified CTV bundle IDs, its schema, the spoofing risks it addresses and how it is delivered over FTP."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Reject malformed and unidentified CTV bundle IDs, which carry a high risk of app spoofing and lack transparency. Unidentified Bundle ID data feed is delivered via FTP, an on-prem solution, offering customized solution whereby applied to all or just some CTV traffic to mitigate risk. 

**The naming convention and format of the list is as follows**

Malformed / Unidentified Bundle ID Data feed

Update Interval: Once per week (estimated availability 8:00 AM UTC)

Naming convention in FTP folder: UnIdentifiedBundleIds_YYYYMMDD

File Format: CSV

Schema: osName | platformName | bundleid 

### Example: 

![Screenshot 2026-03-26 at 09.38.01](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-03-26%20at%2009.38.01.png)

#### **Malformed / Unidentified Bundle ID Impact**

Unmapped Bundle IDs are problematic for targeting, post-bid reporting, and may also be indicative of fraud or spoofing. This can lead to issues for buyers but also all the seller entities within a given supply chain. 

#### Integrating Data Feeds:

Pixalate pre-bid data feeds are delivered via FTP and updated twice a day, daily, or weekly depending on the type of feed.

Benefits of an FTP integration:

  * Apply the data feed to any volume of traffic, at no additional cost.
  * Implemented on-prem, allows for custom logic. Apply different rules for different traffic partners.
  * If API is preferred, please contact your sales or account manager. 

**Use Cases and Benefits**

  * Ensure that the inventory you're purchasing is actually running on the desired bundle ID pre-impression.
  * Block specific bundle IDs by platform ID to take action via different supply paths. 
  * Check for any potential post bid data that may have run against unidentified app IDs and further troubleshoot with your partner or request clawbacks. For reference, the [Q3 2024 CTV Malformed & Fraudulent CTV Bundle IDs Risk Report](https://www.pixalate.com/blog/q3-2024-malformed-fraudulent-ctv-bundle-ids-risk-report) identified that there was $174M in Estimated Connected TV Open Programmatic Ad Spend Went to Malformed, Unidentified, and/or Fraudulent Bundle IDs.
