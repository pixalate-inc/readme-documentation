---
title: "SPO (Supply Path Optimization) Block List"
excerpt: "How can I use Pixalate's SPO Data Feed to combat IVT?"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

By leveraging the SPO Data Feed, a user can reduce the number of supply paths and block specific entities within the supply chain prior to an impression. For the purpose of this document and data feed, please reference the following definitions:

  * node - In a complete supply chain, a node represents a given advertising system and seller ID involved in the transaction.
  * advertising system - The domain name of the SSP, Exchange, Header Wrapper, etc system that bidders connect to. This may be the operational domain of the system if that is different than the parent corporate domain.
  * seller ID - The identifier associated with the seller or reseller account within the advertising system. This must contain the same value used in transactions (i.e. OpenRTB bid requests) in the field specified by the SSP/exchange.

**Use Cases and Benefits**

  * Focus on specific supply paths to reduce IVT and specific IVT types
  * Surgically block paths rather than an entire seller, publisher, app/site, or even user 
    * Block bid requests with supply chain objects that contain flagged nodes
  * Track nodes (adsystem:sellerID) that appear to have higher IVT associated across all supply paths, regardless of location on the given chain. This combination is important to note as it's calling for specific instance, not a complete block of that seller. 
    * With an associated probability, a user can decide how little or how much of the list can be applied when blocking specific nodes in the supply chain object.

**The naming convention and format of the lists are as follows**

SPO Data feed

Update Interval: Once per day (estimated availability 8:00 AM UTC)

Naming convention in FTP folder: SpoBlocklist_YYYYMMDD

File Format: CSV

Schema: adSystem | SellerId | riskType | probability

![](https://lh7-us.googleusercontent.com/slpbc67_Dds6I2BojbtGD0bQNL1YW0N5PKcLFF4jr2qQl3jgAz9n9zxZCalhjH7U-lOB6g3GtAgoyioIy5MjLtpNQ_1Gt21NxDr_Q81UuOmOCzktrehxL4LEWMpxiUfwB-Nza6RBded-T6em7wDuB1sEUA=s2048)
