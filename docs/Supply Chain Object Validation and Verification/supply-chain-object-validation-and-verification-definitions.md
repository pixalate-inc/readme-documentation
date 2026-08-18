---
title: "Supply Chain Object Validation and Verification Definitions"
excerpt: "For the purpose of this subject, please reference the below definitions:"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

* Supply Chain Object -The Supply Chain Object is composed of a set of nodes where each node represents a specific entity that participates in the transacting of an ad placement. The entire chain of nodes from beginning to end represents all entities who are involved in the direct flow of payment for inventory. 
  * Node - A node contains two required properties; the advertising system identifier (asi) and the seller ID (sid). The advertising system identifier is the domain name of the advertising system. The seller ID is used to identify the seller of the inventory; who the advertising system pays for this inventory. Both the advertising system identifier and the seller ID should be the same values that are provided in ads.txt files. It is invalid for a Seller ID to represent multiple entities. Every Seller ID must map to only a single entity that is paid for inventory transacted with that Seller ID. It is valid for a selling entity to have multiple Seller IDs within an advertising system. 
  * Seller.json - A published and accessible file that enables buyers to discover who the entities are that are either direct sellers of or intermediaries in the selling of digital advertising. It's important to ensure that for each node, the upstream node matches the sellers.json entry.

  * ads.txt/app-ads.txt - A published and accessible file that allows publishers to declare which entities are authorized to sell said publisher's advertising inventory. It's important to ensure that for each node, the publisher has authorized that seller.

  * SCO validation - The process of confirming that the structure of the SCO is correct. Ie, check its integrity to ensure that it is parsable and contains all required fields.
  * SCO verification - The process of confirming that the data in the OpenRTB Supply Chain Object (SCO) is accurate and legitimate. This is done by checking each “node” of the SCO with corresponding entries in ads.txt and sellers.json
  * Seller - The numerical ID associated with a partner that a user is accessing/buying supply from. This value differs from the SCO and is passed via a separate macro. 
  * Seller Type - This refers to position that an entity holds within the SCO. For example the developer would be denoted as PUBLISHER and a seller or reseller would be classified as INTERMEDIARY.
  * Seller Domain - The owner domain tied to the publisher, seller or reseller listed within the SCO. An example of this is an app titled com.peoplefun.wordcross would have the associated seller domain of peoplefun.com.
  * Valid Chain - The passed supply chain object is in proper OpenRTB formatting with all nodes and correct IDs included. Additionally, the chain must present a complete flag. 
  * Incomplete Chain - If a node is missing or not passed properly, this may result in an incomplete chain. If the complete flag is missing, then the chain will be marked as incomplete as well. 
  * Reason/Error Codes - Across Validation and Verification of the SCO, Pixalate checks for missing or improperly passed values and exposes the activity in one of the possible reason codes. This may populate as an incomplete chain or a possible node in the SCO is missing. From here, a user can take action in a number of different ways, which will be described below. Direct Seller Unauthorized is listed below, but please check **[here](https://www.pixalate.com/knowledgebase/how-to-interpret-sco-validation-and-verification-error-codes)** for a full list of reason/error codes. 
  * Direct Seller Unauthorized - The 1st seller in the SCO was not listed in the publisher’s ads.txt/app-ads.txt as a DIRECT seller.
