---
title: "Improving traffic quality with the SCO Validation and Verification Analytics Reports"
excerpt: "How can I use the Analytics Dashboard to assess and improve supply chain performance?"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Pixalate has updated the Analytics Dashboard with three supply chain reports, one for Domains, Mobile Apps and CTV Apps. These features are available to all Analytics Dashboard subscribers as a beta program. For a complete set of SCO Validation and Verification definitions, please reference [here](https://www.pixalate.com/knowledgebase/supply-chain-object-validation-and-verification-definitions).

The SCO reports allow clients to parse out traffic by various supply paths and compare buying avenues to ensure the most optimal chains are being actioned on. 

**Crawler Guidelines**

When it comes to crawling 'ads.txt', 'app-ads.txt', and 'sellers.json' files, to ensure the most up-to-date information, Pixalate employs the following guidelines:  

  * All our ads.txt and app-ads.txt files are crawled within a rolling 30-day window.
  * All our sellers.json files are crawled within a rolling 7-day window.

On mitigating SCO IVT types by updating 'ads.txt' and 'app-ads.txt' files:

  * In case of an SCOunauthorizedDirectSeller error, the ads.txt and app-ads.txt files will be retried for crawling on the next day.
  * In case of an SCOunauthorizedDirectSellerPublisherMissing error, the sellers.json file will be retried for crawling on the next day.

**1\. View the SCO Reports and Default Columns** -

  * These default reports, located under brand safety, provide an aggregated view of supply chain performance and breakout of chains that may or may not be passing validation and verification. A user can adjust scope based on header dimensions, such as incomplete or valid chain%, direct seller unauthorized and specific number of nodes. From here, the user has high level view of SCO data that can be correlated to other performance metrics, such as gross ads, IVT% and viewability. 
  * A user can focus on the chains that may not meet certain criteria, such as IVT over 10% or chains not showing a complete flag. In addition, a user can begin to consolidate paths and remove redundancies where not needed, based on validation and verification data, performance or even spend. 

In addition the default reports include the below dimensions and metrics:

  * App/Site
  * Passed supply chain object
  * Reason/Error Codes 
  * Chain Length

**![Screen Shot 2024-05-14 at 11.45.18 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-14%20at%2011.45.18%20AM.png)**

**2\. Break down the reports by various dimensions/metrics:**

  * Individual nodes (Up to 4 entries in standard or reverse direction) - Depending on how a user would like to view the data, the SCO can be put in order of inventory, followed by node 1-4 or flipped to go from inventory to node 4-1. By inputting the individual nodes, a user can surface if unexpected entities are populating in the SCO. From here, speaking with the adjacent reseller would be the next course of action. 
  * Seller - By including the seller, a user can see how many chains are tied to this given entity and where deficiencies, such as high IVT, low viewability or reason/error codes are populating. By parsing out chains that do not meet expectations, a user can work with this seller on eliminating or repairing broken and/or poor performing supply chains. 
  * Seller type and associated seller domain - With seller type, you can isolate certain roles within the supply chain. Direct relationships may pose less risk and exposure to certain IVT types, so by parsing out chains with intermediaries, focus can be applied to those chains with additional entry points for fraud. As for the associated seller domain, this can be a useful piece of information to see who the owner domain is for a given entity. This can provide an avenue for reaching out should issues or questions arise. 
  * Chain Length - This value corresponds to the number of nodes in the SCO. If you'e dealing directly with a publisher, the chain length would be 1. As intermediaries are added, the chain length increases. When it comes to longer chain lengths, Pixalate has found a correlation with failed chain validation. Per the Q2 2023 Supply Chain Verification Report, chains with 3 nodes had a 26% failed validation rate compared to 14% for chains with just 1 node. By chain length or accessing certain supply with a cap on nodes, this can help ensure a higher validation rate. 
  * Supply path completeness - In addition to segmenting the data by seller type, a user can also evaluate chains by whether they are complete or not. By checking the paths that are incomplete, a user can then work with the associated intermediary to ensure all proper nodes are being passed as well as the complete flag. In terms of why path completeness is important, Pixalate found a 69% higher IVT rate when the SCO is marked as ‘incomplete’ (Q4 2023 SupplyChain Object (SCO) Validation Report).

![Screen Shot 2024-05-14 at 12.04.33 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-14%20at%2012.04.33%20PM.png)

**3\. Compare chains for a single piece of inventory**

  * Buying efficiency - When focusing on a single app or domain, a user can compare chains across a number of different data points to ensure the proper buying paths are being leveraged. Certain companies have stringent rules for buying, including chain length and completeness. By identifying broken chains and those that exceed expected chain length, a user can shut off these paths and refocus spend in other areas.
  * Cost savings - Incorporating IVT rate can be a helpful data point to reduce wasted spend as well as clawbacks from demand partners. Not uncommon, certain partnerships are based on a threshold for IVT%, meaning anything over would be out of pocket for that seller. By checking which chains have an inflated IVT rate, one can take action by blocking that specific node or taking further preventative measures, such as pre-bid, with respect to that partnership. This allows for continued selling of the inventory without blocking that publisher altogether. Additionally, if you add in ad spend, a user can forecast possible cost savings, should a specific chain be eliminated. 

**![Screen Shot 2024-05-14 at 12.07.57 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-14%20at%2012.07.57%20PM.png)**

**4\. Filter by specific reason/error codes**

  * Reason/Error codes help to clarify what exactly is broken within the SCO or where any data is being improperly passed/omitted.
  * Important to note, 'Valid SCO' refers to a complete chain that has passed all nodes with correct seller and ad system ID and the entities are noted as the correct seller type.
  * Similar to different IVT types calling for certain actions, the same is true for SCO reason/error codes. The codes are broken out across validation and verification and based on the activity expressed, different responses will be required by a user. 
  * It is possible for more than one code to populate if multiple errors are encountered with the SCO.
  * Example Validation Codes and Responses - For the Analytics Dashboard UI, these will map onto a single label (SCO deserialization failed).**  
**
    * **4101 Missing Version:** The SCO submitted does not specify a version, which is essential for determining the correct validation rules. 
      * **Action:** Ensure the SCO includes the ver field with the correct version information.
    * **4105 Invalid Node ID Format:** The format of the node ID is incorrect. 
      * **Action:** Verify the node ID matches the expected format as per the OpenRTB specification.
    * **4106 Incomplete Node Information:** Essential information for a node is missing or incomplete. 
      * **Action:** Check and fill in all required fields for each node.
  * Example Verification Codes and Responses  

    * **4403 Publisher missing in SCO:** The first node on the SCO did not point to a publisher 
      * **Action:** Ensure that the 1st entity in the SCO has a partnership with the associated publisher

  *     * **4406 Reseller listed as direct seller:** A seller on a “reseller node” in the SCO was not listed in the publisher’s ads.txt as RESELLER, but was listed as DIRECT 
      * **Action:** Ensure that the 1st entity in the SCO is authorized as a reseller in the relevant ads.txt/app-ads.txt file
    * **4407 Link in SCO missing in sellers.json:** A seller entry in a node on the SCO did not match the sellers.json of the seller on the next node 
      * **Action:** Ensure that the entity on that node is listed correctly, with the correct seat id in the relevant sellers.json file.

![Screen Shot 2024-05-22 at 2.55.38 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-22%20at%202.55.38%20PM.png)

**Key Benefits of Pixalate’s SCO Validation and Verification Analytics Dashboard Report**

  * Evaluation of the SCO passed structure, to ensure that what is being transmitted meets expectations and is reflective of your existing buying paths. 
  * Find all sellers/partners who are not authorized (as a direct seller or maybe even as a reseller) and either block those sellers or work with them and the publisher to clean up the ads.txt.
  * Reduce clawbacks by eliminating certain paths instead of blocking an inventory source altogether.
  * Look at all the questionable/weak links in the chain and work with those sellers to fix the sellers.json files or SCOs.
  * Reduce IVT given the correlation of SCO verification failures and IVT.
