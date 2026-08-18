---
title: "Supply Chain Object Validation and Verification Background"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

**What is a SCO?**

SCO (Supply Chain Object) is part of OpenRTB and is one of IAB Tech Lab’s privacy standards, meant to work alongside two other standards - ads.txt and sellers.json - to bring transparency to the supply chains involved in a bid request. 

The SCO represents all entities involved in the buying path from app/site to publisher, seller, reseller and finally to a demand partner or advertiser.

![Screen Shot 2024-05-14 at 12.17.57 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-14%20at%2012.17.57%20PM.png)

**What is SCO Validation/Verification?**

  * **SCO validation** is the process of confirming that the structure of the SCO is correct. Ie, check its integrity to ensure that it is parsable and contains all required fields.

  * **SCO verification** is the process of confirming that the data in the OpenRTB Supply Chain Object (SCO) is accurate and legitamate. This is done by checking each “node” of the SCO with corresponding entries in ads.txt and sellers.json

  1. Sellers.json to ensure that for each node, the upstream node matches the sellers.json entry
  2. ads.txt to ensure that for each node, the publisher has authorized that seller. 
     * Includes ensuring the first seller is listed as direct, and other sellers are listed as resellers

**Why is SCO Verification important/useful? / What are the benefits?**

Ad Supply Chains are very complex, and involve a large number of sellers and resellers, making it a very complex system to understand. While SCO was intended to bring transparency, it can also be faked. This can go unnoticed without verification. 

Benefits of verification - 

  * Find problematic SCOs (bad or incorrect) and address those problems to **improve SCO structural quality**
  * Find **unauthorized** sellers and resellers (entities trying to do unauthorized ad arbitrage) and block them
  * Find **inaccurate chain relationships** and block those sellers 
  * Find **potentially** “**spoofed” impressions** (entities trying to sell impressions from other sources by claiming they come from more valuable sources)
  * In addition to that, we have seen a correlation between invalid SCOs and IVT (64% higher on invalid SCOs), which provides an incentive to verify SCOs.
