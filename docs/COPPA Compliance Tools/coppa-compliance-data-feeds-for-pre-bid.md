---
title: "COPPA Compliance Data Feeds for Pre-Bid"
excerpt: "Pixalate provides two data feeds to help companies manage their COPPA Compliance processes"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The COPPA pre-bid lists are now in production and are available via FTP. There are two lists available for **mobile apps** and **CTV apps** :

  * COPPA Compliance Risk Rating: Apps we have determined to have high COPPA risk
  * COPPA Audience (child directed): Apps we have determined to be child directed

These lists will be updated weekly and will be available to download every Monday 8am PST.

The naming convention and format of the lists are as follows

**COPPA Violation Risk Rating  
**

Folder Names:

  * Mobile apps: coppaviolationrisk
  * CTV apps: ctvcoppaviolationrisk

Naming convention:

  * Mobile apps: CoppaViolationRiskApps_2022xxxx(CoppaViolationRiskApps_20220410.csv)
  * CTV apps: CoppaViolationRiskCtvApps_2022xxxx(CoppaViolationRiskCtvApps_20220410.csv)

Format: appId, osName, risk

Example:

![Screen Shot 2022-04-21 at 11.11.56 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202022-04-21%20at%2011.11.56%20AM.png)

**COPPA Audience (a.k.a. child-directed apps)**

Folder Name:

  * Mobile apps: directedtochildren
  * CTV apps: ctvdirectedtochildren

Naming convention:

  * Mobile apps: CoppaChildDirectedMobileApps_2022xxxx(CoppaChildDirectedMobileApps_20220320)
  * CTV apps: CoppaChildDirectedCtvApps_2022xxxx(CoppaChildDirectedCtvApps_20220320)

Format: appId, osName

Example:

![Screen Shot 2022-04-21 at 2.00.45 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202022-04-21%20at%202.00.45%20PM.png)
