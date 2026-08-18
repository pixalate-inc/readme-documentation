---
title: "How to Interpret SCO Validation and Verification Error Codes"
excerpt: "The below breaks out each SCO error type by Validation or Verification and flags for missing or improperly passed values."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For reference, the two terms are defined as:  

  * **SCO validation** is the process of confirming that the structure of the SCO is correct. Ie, check its integrity to ensure that it is parsable and contains all required fields.

  * **SCO verification** is the process of confirming that the data in the OpenRTB Supply Chain Object (SCO) is accurate and legitimate. This is done by checking each “node” of the SCO with corresponding entries in ads.txt and sellers.json

  1. Sellers.json to ensure that for each node, the upstream node matches the sellers.json entry
  2. ads.txt to ensure that for each node, the publisher has authorized that seller. 
     * Includes ensuring the first seller is listed as direct, and other sellers are listed as resellers

#### Node Validation Errors

  * Note: For the Analytics Dashboard UI, all these will map onto a single label (SCO deserialization failed).**  
  
**
  * **4101 Missing Version:** The SCO submitted does not specify a version, which is essential for determining the correct validation rules. 
    * **Action:** Ensure the SCO includes the ver field with the correct version information.
  * **4102 Missing Complete Flag:** The SCO submitted does not contain a complete flag, which is essential for determining if the SCO chain is complete or not. 
    * **Action:** Ensure the SCO includes the complete flag whether the chain is complete or not.
  * **4104 Missing Node ID:** A node within the SCO lacks an ID. 
    * **Action:** Ensure every node in the SCO includes a unique ID.
  * **4105 Invalid Node ID Format:** The format of the node ID is incorrect. 
    * **Action:** Verify the node ID matches the expected format as per the OpenRTB specification.
  * **4106 Incomplete Node Information:** Essential information for a node is missing or incomplete. 
    * **Action:** Check and fill in all required fields for each node.

#### Node Verification Errors

  * **4401 SCO not provided:** The SCO was not provided for these impressions 
    * **Action:** Ensure the direct partners (and their upstream partners) are passing the SCO
  * **4402 SCO declared incomplete:** The “complete” flag on the SCO was set to 0, indicating it is declared incomplete 
    * **Action: Action:** Work with partners to address the gaps in the SCO
  * **4403 Publisher missing in SCO:** The first node on the SCO did not point to a publisher 
    * **Action:** Ensure that the 1st entity in the SCO has a partnership with the associated publisher
  * **4404 Direct seller not authorized:** The 1st seller in the SCO was not listed in the publisher’s ads.txt/app-ads.txt as a DIRECT seller 
    * **Action:** Ensure that the 1st entity in the SCO is authorized as a seller in the relevant ads.txt/app-ads.txt file
  * **4405 Reseller not authorized:** A seller on a “reseller node” in the SCO was not listed in the publisher’s ads.txt/app-ads.txt 
    * **Action:** Ensure that the 1st entity in the SCO is authorized as a reseller in the relevant ads.txt/app-ads.txt file
  * **4406 Reseller listed as direct seller:** A seller on a “reseller node” in the SCO was not listed in the publisher’s ads.txt as RESELLER, but was listed as DIRECT 
    * **Action:** Ensure that the 1st entity in the SCO is authorized as a reseller in the relevant ads.txt/app-ads.txt file
  * **4407 Link in SCO missing in sellers.json:** A seller entry in a node on the SCO did not match the sellers.json of the seller on the next node 
    * **Action:** Ensure that the entity on that node is listed correctly, with the correct seat id in the relevant sellers.json file.
  * **4408 Unable to resolve publisher domain:** Unable to resolve publisher domain to get the ads.txt or app-ads.txt 
    * **Action:** Ensure that the correct website or app information is passed. And/or fix the confidential or missing entry in the sellers.json file.
  * **4201 Ads.txt not resolved** : The ads.txt for the site was not found 
    * **Action:** Manually check the location, and work with the publisher to fix the problem
  * **4202 App-ads.txt not resolved** : The app-ads.txt for the app was not found 
    * **Action:** Manually check the location, and work with the publisher to fix the problem
  * **4203 Sellers.json not resolved** : The sellers.json files for one or more sellers in the SCO were not found

**Action:** Manually check the location, and work with the seller to fix the problem.
