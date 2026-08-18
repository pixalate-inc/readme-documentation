---
title: "Know Your Developer (KYD)"
excerpt: "A free, public database that rates all ad-funded app developers operating across Apple and Google mobile app stores on online child safety, privacy compliance, and advertising fraud risk - information that the app stores fail to disclose."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### In this article:

  * What Is “Know Your Developer” (KYD)?
  * How Are Developers Rated?
  * Risk Rating Definitions

### **What Is Know Your Developer (KYD)?**

The **Know Your Developer (KYD) Database** is a free watchdog platform that helps parents, schools, and child safety advocates identify privacy and safety risks by assigning ratings based on app developer identity accessibility, compliance under privacy laws, app store compliance, and traffic quality risks to the 350k+ Google Play and Apple App store developers who monetize mobile apps through advertising.   
  
Pixalate’s Trust & Safety Advisory Board, composed of teachers, parents, and lawyers, manually reviews mobile apps to determine the intended audience and assess key privacy compliance features, such as age gates and Verifiable Parental Consent (VPC). Those findings feed directly into the KYD database, as does advertising data monitored by Pixalate’s MRC-accredited ad fraud detection technology.

The KYD database is accessible for free on Pixalate’s website and is updated monthly with search and filters by developer/app name, developer country of registry, and app store presence.  

![Screenshot 2026-02-10 at 9.11.52 AM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202026-02-10%20at%209.11.52%20AM.png)

###   
**How Are Developers Rated?**

The KYD rates all mobile app developers with an app-ads.txt file (as measured by Pixalate) across three main risk categories: Identity Risk, Compliance Risk, and Traffic Quality Risk. Each risk category is split up into individual risk factors, which are defined below.

Criteria used to rate mobile app developers:

  * Missing Contact Info Risk
  * Anonymous Owner Risk
  * Verifiable Parental Consent Not Detected Risk
  * Missing Privacy Policy Risk
  * Children's Online Privacy Protection Act (COPPA) Violation Risk
  * Location Tracking Risk
  * Banned Apps Risk
  * Security Risk
  * Unsafe Advertising Risk

### **Risk Rating Definitions**

Risk Metrics defined in this section:

  * Identity Risk 
    * Missing Contact Info Risk
    * Anonymous Owner Risk
  * Compliance Risks 
    * Verifiable Parental Consent Not Detected Risk
    * Missing Privacy Policy Risk
    * Children's Online Privacy Protection Act (COPPA) Violation Risk
    * Location Tracking Risk
    * Banned Apps Risk
    * Security Risk
  * Traffic Quality Risk

  *     * Unsafe Advertising Risk

#### **Missing Contact Info Risk**

Measures the accessibility of the app developer’s contact email or physical address on app store pages or the developer’s website, as measured by Pixalate.

  * Low Risk → Contact email or physical address is found for the developer
  * Critical Risk → No contact email or physical address is found for the developer

#### **Anonymous Owner Risk**

Indicates whether the app developer's website is registered anonymously in the Internet WHOIS domain databases.

  * Low Risk → Developer’s website is registered publicly
  * High Risk → Developer’s website is registered anonymously

#### **Verifiable Parental Consent Not Detected Risk**

Measures whether the developer has any likely child-directed apps that do not obtain Verified Parental Consent (VPC) before collecting and sharing personal information like IP address or user location (as measured by Pixalate). Apps are manually downloaded, tested, and reviewed by Pixalate’s Trust & Safety Advisory Board in order to determine whether or not an app is likely child-directed or if they have sufficient VPC in place.

  * Low Risk → Developer does not have any manually-reviewed apps that violate VPC requirements as denoted by COPPA.
  * Critical Risk → Developer has at least one app that transmits personal user information (IP, location information) without obtaining VPC and has been manually determined to be likely child-directed. 

#### **Missing Privacy Policy Risk**

Indicates whether the developer has a publicly accessible privacy policy linked in their app store pages.

  * Low Risk → Privacy policy detected for the app developer
  * Critical Risk → No privacy policy detected for the app developer

#### **Children's Online Privacy Protection Act (COPPA) Violation Risk**

Indicates whether the app developer is at risk of violating COPPA by violating COPPA-mandated Verifiable Parental Consent (VPC) requirements.

  * Low Risk → App developer does not have any apps likely violating VPC requirements
  * Critical Risk → App developer has likely child-directed apps transmitting user information (IP, location) without VPC.

#### **Location Tracking Risk**

Indicates whether the developer operates apps that request precise geolocation data access permissions and/or transmit user location in the advertising bidstream, as measured by Pixalate. 

  * Low Risk → Developer has no apps which request access to users’ geolocation data via certain app permissions. 
  * Medium Risk → Developer has one or more apps which request access to users’ geolocation data via certain app permissions, but precise geolocation data is not transmitted in the advertising bidstream, as measured by Pixalate.
  * Critical Risk → Developer has one or more apps which request access to users’ geolocation data via certain app permissions, and precise geolocation data is transmitted in the advertising bidstream, as measured by Pixalate.

#### **Banned Apps Risk**

Measures the quantity and scale of the developer's apps that have been removed or delisted from Google Play or Apple App Stores, and whether the developer monetizes these removed apps via advertising.

  * Low Risk → The developer has no apps delisted or banned from the Google Play and Apple App stores.
  * Medium Risk → The developer has some apps delisted or banned from the Google Play and Apple App stores, but these delisted apps make up a small portion of the developer’s lifetime install base.
  * High Risk → The developer has many apps delisted or banned from the Google Play and Apple App stores, and these delisted apps make up a large portion of the developer’s lifetime install base.
  * Critical Risk → The developer has many or all apps delisted or banned from the Google Play and Apple App stores, and these delisted apps make up a significant portion of the developer’s lifetime install base. 
  * Critical Risk → The developer monetizes apps delisted or banned from the Google Play and Apple App stores, according to advertising traffic measured by Pixalate.

#### **Security Risk**

Indicates whether the developer operates apps on the Google Play and Apple App stores that have not been updated in 3+ years in accordance to app store compliance and security guidelines.

  * Low Risk → The developer has no apps which have not been updated in 3+ years.
  * High Risk → The developer has at least one app which has not been updated in 3+ years.
  * Critical Risk → The developer has many or all apps which have not been updated in 3+ years, and/or these abandoned apps make up a significant portion of the developer’s lifetime install base. 

#### **Unsafe Advertising Risk**

Indicates the rate of impressions that are [designated as IVT](https://www.pixalate.com/knowledgebase/reported-invalid-traffic-ivt-types?hsLang=en) measured on the developer’s apps. The Unsafe Advertising Risk section is composed of both Sophisticated Invalid Traffic (SIVT) and General Invalid Traffic (GIVT) measurements.

Low, Medium, High, and Critical Risk evaluations are conducted using statistical analysis and clustering methods to derive dynamic risk thresholds for SIVT and GIVT rates at the global scale.   

#### **Overall Child Safety Risk Determination**

The KYD’s overall Child Safety Risk determination is based on the risk ratings for the above 9 risk metrics. The risk metrics are split into three risk categories: **Identity Risk, Compliance Risk,** and**Traffic Quality Risk.**

These risk categories are aggregations of their relevant risk metrics.

For each Risk Category, the aggregate risk level is that of the highest risk metric within that category. For example, Compliance Risk would be ‘Critical’ if Missing Privacy Policy Risk was Critical, even if Banned Apps Risk, Security Risk, and the other Compliance risk metrics were rated ‘Low’. The only exception is Anonymous Owner Risk, which can only increase the Identity Risk level to ‘Medium’ even if flagged as ‘High’. 

Each app developer is rated based on the risk levels for these categories and given an overall **Child Safety Risk** rating. The overall risk determination is as follows:

  * **Failure**

      * Any one of three risk categories is Critical Risk
      * Two or more of the three risk categories are High Risk

  * **High Risk**

      * One of the three risk categories is High Risk
      * None of the risk categories are Critical Risk. 

  * **Medium Risk**

      * One or more of the three risk categories are Medium Risk
      * None of the risk categories are High or Critical Risk. 

  * **Low Risk**

    * All three risk categories are Low Risk

[**See Full Methodology Here.**](https://www.pixalate.com/pixalate-know-your-developer-methodology-download)

* * *

#### **Disclaimer**

Pixalate’s Mobile Application Know Your Developer Ratings (“KYD”) reflect Pixalate’s opinions that Pixalate believes may be useful to parents, guardians, educators, regulators, researchers, and participants in the digital media industry. Any data shared is grounded in Pixalate’s proprietary technology and analytics, which Pixalate is continuously evaluating and updating. Any references to outside sources should not be construed as endorsements, affiliations, or associations with any third-parties. Pixalate is sharing this data not to impugn the standing or reputation of any entity, person or app, but, instead, to report research findings and trends pertaining to the time period studied.

It is important to note however, that classification of a mobile application developer (“app developer”) within a particular risk tier does not mean that the app developer, its applications, or any associated practices are in violation of any laws or regulations, including the Children’s Online Privacy Protection Act (COPPA) or any other global privacy framework. Further, the app(s) of an app developer(s) that appear(s) to be directed to children (e.g., users under 13 years of age, as defined by the COPPA Rule) does not mean that any such app, or its operator, is failing to comply with the COPPA Rule. 

Pixalate’s determinations are based on a proprietary methodology that incorporates a combination of signals and automated processes. Additionally, with respect to app developers that appear to have characteristics that, in Pixalate’s opinion, may trigger related privacy law or regulatory compliance obligations and/or risk, such assertions reflect Pixalate’s opinions i.e., they are neither facts nor guarantees. While Pixalate endeavours to apply rigorous standards in compiling this KYD, no assurances or guarantees can be, or are, made as to the accuracy or completeness of any classification. This article/expose, including all content set forth herein–constitutes Pixalate “Materials” under Pixalate’s Terms of Use, and is licensed subject to–and conditioned expressly upon–compliance with each of the applicable terms and conditions of such Pixalate Terms of Use.

_Per the MRC, “'Fraud' is not intended to represent fraud as defined in various laws, statutes and ordinances or as conventionally used in U.S. Court or other legal proceedings, but rather a custom definition strictly for advertising measurement purposes. Also per the MRC, “‘Invalid Traffic’ is defined generally as traffic that does not meet certain ad serving quality or completeness criteria, or otherwise does not represent legitimate ad traffic that should be included in measurement counts. Among the reasons why ad traffic may be deemed invalid is it is a result of non-human traffic (spiders, bots, etc.), or activity designed to produce fraudulent traffic.”._

Apple and the Apple logo are trademarks of Apple Inc; Google, Google Ad Exchange, the brand “Google Play,” its logos, and other Google logos are trademarks of Google LLC. These companies are not affiliated with, nor do they endorse or sponsor, any products, data, content, reports, materials or services associated with Pixalate. Any other brand logos, names, or trademarks not explicitly mentioned herein – but otherwise mentioned, displayed, or used in any of Pixalate’s materials, including this report – are the property of their respective owners.
