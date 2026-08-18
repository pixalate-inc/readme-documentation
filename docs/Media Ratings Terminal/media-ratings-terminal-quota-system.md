---
title: "Media Ratings Terminal Quota System"
excerpt: "This article details how the MRT quota system works and when deductions to the quota are done."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Upon signing up for access to the MRT, your Sales representative may give you the option to allocate monthly quotas for website and app insights, as well as for leveraging the [Pixalate MRT Enrichment API](https://developer.pixalate.com/). 

The overall monthly quota can be allocated across three supply types that the MRT currently supports:

  * Websites
  * Mobile Apps
  * CTV Apps

To avoid disruption in case monthly allocations are consumed prior to the next quota refresh cycle, your Sales representative may include overage allocations to your subscription. These overage allowances allow you to keep using the MRT for website and app insights when the base quota has been consumed but note that overage allowance use comes with an overage fee. 

### Quota Deductions 

When it comes to how quota is deducted from the monthly allocation,**** each**"input Item"** debits one (1) quota unit from the monthly quota upon submission. 

Each**"output Item"** debits one (1) additional quota unit from the monthly quota when delivered or made available to the user. 

A single "input Item" then may result in multiple debits:

  * One (1) for the "input Item" itself, and
  * One (1) for each "output Item" returned. 

All debits are applied as a shared monthly quota because no authorized user possesses a personal subset of the quota.

_**Definitions**_

  * **_“Input Item”_** _means each individual app or domain submitted by the user for processing, whether submitted (a) through the UI, (b) via Import CSV, or (c) through an API request._
  * _**"Output Item"** means each response (individual app or domain or **any** other result) returned or made available to the user in response to an "Input Item", including any item (a) displayed in the UI, (b) contained in an API response, or (c) included in a CSV or JSON download. An API response, CSV download, or JSON download may therefore encompass multiple Output Items, each of which is debited separately._  

**Tip:** Refer to the section below on how combinations of devices and regions selected can impact your quota deduction)

### Managing UI Upload Results or API Outputs

The MRT UI and API allow our clients to define the combinations of results they get back from the MRT platform. 

In the MRT Discovery section prior to importing a CSV file for processing, you will be presented with options of Region and Device combinations. 

Each combination returned will be deducted from your quota.

In most cases, setting the Region and Device as "GLOBAL" will satisfy most user requirements and this will return one combination (ie. one deduction per store). 

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202025-06-04%20at%2010-17-13-png.png)

When using the [MRT Enrichment API](https://enterprise-api.pixalate.com/#158319ab-df26-403f-862c-5ec25b802a64), you can set the Region and Device as parameters in the API request: 

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202025-06-04%20at%2010-18-35-png.png)

### Viewing Current Quota Usage via the MRT UI

The MRT also provides users with a [quota usage page](https://ratings.pixalate.com/account-settings/quota-usage) to track their remaining quota, and view usage logs directly on their account page in the MRT.

This is useful to prevent any overage charges and gives you agency on managing your MRT usage. 

The quota usage page can be accessed by hovering over your name in the upper right-hand corner of any Pixalate page when logged in, and selecting "Quota Usage" from the drop-down. 

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202024-12-18%20at%2008-42-41-png.png)

### Viewing Current Quota Usage via the MRT Enrichment API

Below is a sample cURL command you can run to get your current API quota and all you need is your API key, which you can get from your account page or through your customer success representative. 

    #! /bin/bash  
      
    KEY=""  
    echo $KEY  
    echo '***************** ANALYTICS *****************'  
    curl -v -H "x-api-key: $KEY" 'https://api.pixalate.com/api/v2/analytics/reports?pretty=true'  
    echo '*****************APPS *****************'  
    curl -v -H "x-api-key: $KEY" 'https://api.pixalate.com/api/v2/mrt/apps?pretty=true'  
    echo '*****************CTV *****************'  
    curl -v -H "x-api-key: $KEY" 'https://api.pixalate.com/api/v2/mrt/ctv?pretty=true'  
    echo '*****************DOMAINS *****************'  
    curl -v -H "x-api-key: $KEY" 'https://api.pixalate.com/api/v2/mrt/domains?pretty=true'  
    echo '*****************FRAUD *****************'  
    curl -v -H "x-api-key: $KEY" 'https://fraud-api.pixalate.com/api/v2/fraud?pretty=true'

For any questions, please reach out to your customer success representative.
