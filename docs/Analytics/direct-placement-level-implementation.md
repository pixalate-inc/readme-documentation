---
title: "Direct Placement Level Implementation"
excerpt: "Trafficking instructions for Pixalate impression tag on the page at a placement level to get viewability and IVT level data."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### 

For Pixalate clients and users, please log in to access [this page](https://www.pixalate.com/knowledgebase/direct-placement-level-implementation) with additional information.

### Trafficking Instructions:

  1. A placement is an ad unit slot on the page to display/render creatives.

  2. A page can have multiple placements with different sizes.

  3. The impression tag should be trafficked on each and every placement on the page.

  4. The impression tag is trafficked in the same Div as the placement.

  5. Each placement should have a unique placement ID and will be hardcoded in the tag.

  6. When the Impression tag is trafficked on the page (Compared to the Ad Platform) there are no macros to be converted but there are place holders in the tag for data points predefined by Pixalate.

  7. The placeholders can be replaced by the data points using document.write or without it. Please contact your Customer Success representative for the Pixalate script to implement. 

  8. The number of data points is limited as compared to when the tag is trafficked in Ad platform, the following UTM values can be added to the tag for more granular data

  * UTM_Campaign

  * UTM_Term

  * UTM_Source

  * UTM_Medium

  * UTM_Content

9\. Following data points can be hardcoded or dynamically passed in the tag

  * Publisher ID

  * Site ID

  * Domain URL

  * Placement ID

  * Ad Size

  * Supply type 

In addition to these values if a client wants to pass any other data points Pixalate can assign a key value parameter for that.

No data will be captured with the sample tag until a client & platform ID is assigned and provided by Pixalate.
