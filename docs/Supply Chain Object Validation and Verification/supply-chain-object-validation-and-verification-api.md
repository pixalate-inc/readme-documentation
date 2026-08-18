---
title: "Supply Chain Object Validation and Verification API"
excerpt: "Leveraging the SCO VV API"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

With the SCO VV API, a user can check a chain in real time to validate sellers in the chain and surface any unexpected issues with the supply path. The API can be utilized with a single chain or in bulk if preferred. For more information on SCO background and the Analytics dashboard reporting, please see [here](https://www.pixalate.com/knowledgebase/supply-chain-object-validation-and-verification).

Based on whether a chain is valid or not, action be taken pre-impression, improving areas such as:

  * Traffic Quality
  * Secure Buying Paths
  * Removal of Paths That do Not Pass Validation or Verification
  * Removal of Redundant Paths
  * Improving IVT 
  * Reducing Loss or Clawbacks

In terms of the expressed values that may populate, please see Pixalate's documentation on error codes [here](https://www.pixalate.com/knowledgebase/how-to-interpret-sco-validation-and-verification-error-codes). 

An example call and response would be expressed as below:

**Valid SCO**

![Screen Shot 2024-07-01 at 10.52.28 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-07-01%20at%2010.52.28%20AM.png)

**SCO Error**

From here a user can take action by either deciding not to buy on that given request or can take this data to the associated seller for further troubleshooting based on any issues or breaks that populate with the SCO.

To test and explore the API in granular fashion, please click [here](http://enterprise-api-explorer.pixalate.com/?urls.primaryName=SCOVV+API#/Bulk%20SCO%20Validation%20and%20Verification%20for%20Websites./validateVerifyWebsiteBulk).
