---
title: "Integrating click-tracking"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please log in to access [this page](https://www.pixalate.com/knowledgebase/integrating-click-tracking) with additional information.

#### Click-fraud Detection Methodology

Pixalate measures the impression and clicks activity of the user. Signals from both of those sources are combined and analyzed to calculate impression-related fraud types that can be applied to clicks as well. We likewise use the same signals to determine evidence of click-specific fraud types.

#### Click-specific Fraud Types by Category

**Suspicious Users**

  * Click Farm 
    * An impression originating from a user who has been flagged as being associated with human click farm activity. Aligns with Incentivized manipulation of measurements (fraudulent incentivized promotion of an entity, without its knowledge or permission – excludes cases where the entity paying for the incentive is the entity being promoted)
  * Display Click Fraud 
    * Clicks that are generated from the same browser or device at a statistically significant inflated rate. Aligns with Sophisticated Activity-Based Detection or Analyses - Outlier Identification
  * Video Click Fraud 
    * Video ad clicks that are generated from the same browser or device at a statistically significant inflated rate. Aligns with Sophisticated Activity-Based Detection or Analyses - Outlier Identification.
  * Fast Clicker 
    * Activity originating from users which generate clicks less than one second apart from their respective impression. 
    * Fast Clicker Align with:  
○ Activity-Based - Repeat Transactions  
○ Activity-Based - Transaction Protocol Verification  
○ Activity-Based (Click Specific) - Repeat-click-refractory-period (RCRP)  
○ Activity-Based - Outlier

**Suspicious Ads**

  * Duplicate Clicks 
    * High volumes of duplicate clicks may indicate an integration issue.
    * Duplicate Clicks Align with:  
○ Activity-Based - Repeat Transactions  
○ Activity-Based - Transaction Protocol Verification  
○ Activity-Based (Click Specific) - Repeat-click-refractory-period (RCRP)  
○ Activity-Based - Outlier

**Suspicious Publishers**

  * High CTR Traffic 
    * Traffic associated with domains or apps demonstrating high-risk CTR behavior. Aligns with Sophisticated  
Activity-Based Detection or Analyses - Outlier Identification

#### Click Tag Set-up

  1. Pixalate will supply an additional Analytics tag (1x1) with macros that pertain to click fraud

  2. Implementation can be done as a click redirect tag or click tracker
  3. Analytics data will populate with additional information from the click tag
  4. Clicks will be counted as events, along with impressions

To get a sample of the Redirect Click Pixel, the Dynamic Redirect Pixel, and Click Tracking Pixel, please see your Customer Success representative. 

#### Analytics Reporting for Click Fraud

![Analytics_reporting_for_click_fraud-png](https://f.hubspotusercontent40.net/hubfs/2364596/Analytics_reporting_for_click_fraud-png.png)

![Analytics_reporting_for_click_fraud-2-png](https://f.hubspotusercontent40.net/hubfs/2364596/Analytics_reporting_for_click_fraud-2-png.png)
