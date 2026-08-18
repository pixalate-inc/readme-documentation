---
title: "Pixalate\u2019s MFA Detection Methodology and Products"
excerpt: "Learn how Pixalate flags Made for Advertising (MFA) websites, mobile and CTV apps, how you can avoid MFA to protect your advertising spend."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### **What products does Pixalate provide to fight MFA?**

Pixalate's solutions comprise of

  1. **MFA Data Feeds** : Offer real-time access to comprehensive lists for MFA mobile apps, CTV apps, and domains. Segmented by medium- and high-risk markers, the data feeds offer flexibility to implement variable risk mitigation strategies.
  2. **MFA Insights for the Media Ratings Terminal:** Pixalate's ad supply chain intelligence tool, the Media Ratings Terminal (MRT), now includes in-depth MFA insights, accessible in the UI and via API calls.

### **What are the benefits of Pixalate's MFA detection and blocking solutions**

Key Benefits: 

  * **Multi-platform support:** Pixalate harnesses its global ad impression data pool to fuel its MFA detection methodology, and cover not only websites but also mobile apps and CTV apps. 
  * **Data-driven methodology:** Employing advanced AI, Pixalate fine-tunes a range of MFA indicators, including the ad-to-content ratio, ad refresh rate, and the origins of paid and social traffic, among others. This approach extends far beyond traditional web crawlers, resulting in an industry-first multi-platform MFA identification solution
  * **Granular insights:** Another aspect that sets Pixalate apart is its commitment to transparency, providing clients with granular access to the underlying data points. This transparency empowers clients to calibrate their MFA risk, allowing for a nuanced approach rather than a binary blocking method.

### **How does Pixalate's MFA detection/designation****methodology****work?**

Pixalate bases its MFA designations on actual observed traffic from its global data pool, and does not rely solely on crawling since crawlers can be easily gamed.

**MFA Websites Methodology**

  * **MFA Risk:** Pixalate's assessment of the risk (High, Med or Low) of the website being deemed MFA 
  * **Ad Density Rate:** Number of ad placements observed per device, per minute 
  * **Ad Refresh Rate*:** Number of ad impressions observed per device, per minute
  * **Paid Traffic Rate:** Volume of traffic sourced via paid (ad) sources
  * **Social Traffic Rate:** Volume of traffic sourced via social media

**MFA CTV App Methodology**

  * **MFA Risk:** Pixalate's assessment of the risk (High, Medium or Low) of the CTV app being deemed MFA 
  * **Ad Refresh Rate*:** Number of ad impressions observed per device, per minute
  * **Age:** Age of the app on the App Store
  * **IVT:** IVT% of the App across regions
  * **Popularity Score:** Pixalate’s popularity score for the app 
  * **Reviews** : Number of Reviews 

**MFA Mobile App Methodology**

  * **MFA Risk:** Pixalate's assessment of the risk (High, Medium or Low) of the mobile app being deemed MFA
  * **Ad Refresh Rate*:** Number of ad impressions observed per device, per minute
  * **Age:** Age of the app on the App Store
  * **IVT:** IVT% of the app across regions
  * **Popularity:** Pixalate’s popularity score for the app 
  * **Reviews:** Number of Reviews   

Pixalate analyses these traffic signals, and flags _sites and apps_ as likely MFA when any of the factors fall outside the baselines calculated by analyzing quantiles for all ad impressions per website or app.

For **“Ad Refresh Rate*”** improvements, our general opinion is to focus on the volume of ads that are being displayed on the page, and how quickly they are being surfaced/triggered. This could be a combination of the number of ad placements on the page, and the timing of when the ads are signalling. For example, it may be possible that the ads are firing much before the user has the opportunity to see it, contributing to the issue. 

**_*_**_”Ad Refresh Rate” is a Pixalate-specific terminology in this context and does not refer to the rate at which individual ad placements are being refreshed._

The overall high / medium "MFA Risk" designations for websites (as seen in the data feed and in the MRT) are marked as follows:

  * Medium MFA Risk - if ONE of the MFA factors applies (High Social traffic or High Paid Traffic Rate or High Ad density or High Ad Load Rate)
  * High MFA Risk - if more than one of the MFA factors applies (High Social traffic or High Paid Traffic Rate) OR Extremely High Ad density or Extremely High Ad Load Rate)

* note - the thresholds for high or extremely high in the above are calculated by looking at the overall global traffic pool and looking for truly aberrant behavior.

#### [Get in touch with Pixalate to learn more about Made for Advertising](https://www.pixalate.com/scheduledemo). 

#### [Read Pixalate's latest research reports on Made for Advertising](https://www.pixalate.com/made-for-advertising-websites-report). 

### Related articles about Made for Advertising

\- [MFA Overview](https://www.pixalate.com/knowledgebase/made-for-advertising-mfa-solutions-from-pixalate)

\- [Using the MRT to identify MFA traffic](https://www.pixalate.com/knowledgebase/identifying-made-for-ads-websites-using-the-mrt)

\- [Using the MFA Datafeeds to block MFA Traffic](https://www.pixalate.com/knowledgebase/how-to-use-pixalates-mfa-datafeeds-to-block-mfa-traffic)

If you have any further questions or feedback, please contact us via your Customer Success Manager, or by emailing us at support@pixalate.com
