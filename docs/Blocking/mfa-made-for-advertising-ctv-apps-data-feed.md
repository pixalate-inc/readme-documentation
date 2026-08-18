---
title: "MFA (Made for Advertising) CTV Apps Data Feed"
excerpt: "How to use the MFA CTV Apps Data Feed to combat and mitigate MFA risk."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The MFA CTV Apps data feed consists of a list of apps that have an associated MFA Risk ranging from medium to high. The categorization is based on factors including:

  * **Ad Refresh Rate:** Number of ad impressions observed per device, per minute
  * **Age:** Age of the app on the App Store
  * **IVT:** IVT% of the App across regions
  * **Popularity Score:** Pixalate’s popularity score for the app 
  * **Reviews** : Number of Reviews 

For further methodology details across all environments, please see[ here](https://www.pixalate.com/knowledgebase/pixalate-mfa-detection-product-overview).

The list is updated daily and available for download at 8am PST.

**MFA CTV Apps Data feed:**

Folder Name: ctvappsmfa

File Format: CSV

Schema: platform (store) | appID | risk

Naming convention in FTP folder: ctvappsMFARisk_YYYYMMDD

![Screen Shot 2024-04-26 at 10.22.10 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-04-26%20at%2010.22.10%20AM.png)
