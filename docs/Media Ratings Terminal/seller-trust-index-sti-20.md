---
title: "Seller Trust Index (STI) 2.0"
excerpt: "Ranking all sellers, including supply-side platforms (SSPs), listed in ads.txt and app-ads.txt. Direct supply quality scores for 300+ sellers across 100+ markets, across web, mobile, and connected TV (CTV) inventory."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

In this article:

  * What Is the Seller Trust Index (STI) 2.0?
  * How Are Sellers Ranked?
  * Ranking Criteria and Traffic Signal Definitions
  * Interpreting STI 2.0 Scores

### **What Is the Seller Trust Index (STI) 2.0?**

The Seller Trust Index (STI) 2.0 ranks web, mobile, and connected TV (CTV) sellers based on the scale of their direct relationships with publishers within each country. Rankings are built around direct supply path data — measuring how much authorized, direct inventory a seller controls in a given market — in order to allow users to identify SSPs who are primarily reselling inventory.

It uses proprietary technology to assess seller trust and sustainability, using the Supply Chain Object (SCO) to provide a multidimensional view of ad transactions. The rankings are relative to peers within each country and rely solely on buy-side data to ensure impartiality. Other traffic signals including Invalid Traffic (IVT), Made for Advertising (MFA) Traffic rate, and Delisted App Traffic rate are surfaced as supplemental data alongside each ranking, but do not affect a seller's final position.

Pixalate analyzes **30B+** global advertising transactions per month to rank sellers across **100+** countries.

### **How Are Sellers Ranked?**

The Web Seller Trust Index 2.0 focuses on web traffic, including both mobile web and desktop inventory.

The Mobile Seller Trust Index 2.0 focuses on mobile in-app traffic across the following app stores:

  * Apple App Store (iOS)
  * Google Play (Android)

The Connected TV (CTV) Seller Trust Index 2.0 focuses on CTV traffic across the following stores:

  * Roku Channel Store
  * Samsung Smart TV
  * Amazon Fire TV
  * Apple TV tvOS App Store
  * LG TV App Store

Reports are available by quarter and by country.

**![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/undefined-Apr-01-2026-12-01-04-6178-AM.png)**

Sellers in the STI 2.0 are ranked solely on a composite index that measures the scale and authorization of a seller's direct inventory relationships within each country. Our STI 2.0 ranking model measures

  * **What Sellers Claim:** How many publishers selling ads list the seller as DIRECT in their app-ads.txt file, as detected by Pixalate
  * **Verification of Seller Claims:** The scale and ratio of a seller’s impressions that actually flowed through an authorized-direct path, per Pixalate’s SupplyChain Object (SCO) analysis
  * **Seller Arbitrage Risk:** Independent Pixalate risk rating for selling >50% of inventory as a reseller, according to Pixalate’s SCO analysis

This final composite ranking is composed of Arbitraged Inventory Ratio, ‘DIRECT’ Publisher Penetration, and Direct Impression Volume. 

Other traffic data — including GIVT Ratio, SIVT Ratio, MFA Traffic Ratio, Delisted App Traffic Ratio, and Fraudulent Bundle ID Traffic Ratio — is reported alongside each seller's ranking as supplemental context for buyers. These signals do not affect a seller's rank.

_Learn about the final Rank methodology._

### **Ranking Criteria and Traffic Signal Definitions**

Definitions of the STI 2.0's ranking criteria for web, mobile, and CTV sellers. All three inventory types are ranked using the composite score based on the scale of each seller’s direct relationships within a given country. Supplemental data signals vary by platform and are defined below.

Data metrics defined in this section:

    * Final Ranking Methodology _(Web, Mobile, CTV)_
      * Arbitraged Inventory Ratio
      * Direct Impression Volume
      * ‘DIRECT’ Publisher Penetration
    * General Invalid Traffic (GIVT) Ratio _(supplemental data for all platforms)_
    * Sophisticated Invalid Traffic (SIVT) Ratio _(supplemental data for all platforms)_
    * Made for Advertising (MFA) Traffic Ratio _(supplemental data for Web, Mobile)_
    * Fraudulent Bundle ID Traffic Ratio _(supplemental data for CTV)_
    * Delisted App Traffic Ratio _(supplemental for Mobile)_

#### **Final Rank**

The final rankings for STI 2.0 are based on a composite score measuring how much authorized, direct inventory a seller controls within a specific country, across three dimensions: the ratio of their traffic that is direct, the volume of that direct traffic relative to peers in the same country, and the breadth of local publisher relationships authorizing them as a direct seller.

This composite score is made up of three components:

  * **Arbitraged Inventory Ratio** — the proportion of a seller's total measured impressions transacted as resold inventory
  * **Direct Impression Volume** — a seller's absolute count of direct impressions, percentile-ranked against all other sellers in the same country
  * **‘DIRECT’ Publisher Penetration** — the number of domains or apps in the country generating advertising impressions that have authorized the seller as a direct seller in their ads.txt file, percentile-ranked within the country

#### **Arbitraged Inventory Ratio**

The proportion of a seller's total measured impressions in a country that are not transacted as authorized direct (non-reseller) inventory, as determined by the seller's presence in publishers' ads.txt or app-ads.txt files as a DIRECT entry. 

**Direct Impression Volume**

The absolute count of a seller's direct impressions within a country during the quarter. This is percentile-ranked against all other eligible sellers in the same country, so a seller's score on this component reflects their relative direct impression volume within that market. 

#### **‘DIRECT’ Publisher Penetration**

The number of publishers within the country generating advertising impressions that have listed the seller as a DIRECT authorized seller in their ads.txt or app-ads.txt file. For web, this is measured at the domain level. For mobile and CTV, this is measured at the app level. This component measures the breadth of a seller's direct publisher relationships at the local market level and is percentile-ranked within the country. 

_How to interpret STI 2.0 rankings_

#### **  
Fraudulent Bundle ID Traffic Ratio**

Measures the percentage of seller traffic utilizing fraudulent, malformed, or unidentifiable bundle IDs as opposed to standardized CTV app store IDs in the bid stream. Reported as supplemental data for CTV sellers.

_How to interpret Fraudulent Bundle ID Traffic Ratio_

#### **  
Sophisticated Invalid Traffic (SIVT) Ratio and General Invalid Traffic (GIVT) Ratio**

Indicates the percentage of a seller's total impressions that are[ designated as IVT](https://www.pixalate.com/knowledgebase/reported-invalid-traffic-ivt-types), per Pixalate’s MRC-accredited IVT detection methods. IVT rates are reported as supplemental data across all channels in the STI 2.0 and do not affect a seller's rank.

  * **General Invalid Traffic (GIVT) Ratio:** The share of a seller's impressions designated as GIVT.
  * **Sophisticated Invalid Traffic (SIVT) Ratio:** The share of a seller's impressions designated as SIVT.

_How to interpret GIVT and SIVT Ratios_

#### **  
Made for Advertising (MFA) Traffic Ratio**

Indicates the rate of[ Made For Advertising (MFA)](https://www.pixalate.com/knowledgebase/mfa-made-for-advertising-definitions) traffic associated with a seller as a percentage of total impressions, as measured by Pixalate. Reported as supplemental data for web and mobile sellers. 

_How to interpret MFA Traffic Ratio_

#### **  
Delisted App Traffic Ratio**

Measures the rate of a seller's traffic as a percentage of total impressions on apps delisted from the Apple App Store and Google Play Store, as well as fraudulent, malformed, and/or unidentified mobile bundle IDs. Reported as supplemental data for mobile sellers and does not affect a seller's rank.

_How to interpret Delisted App Traffic Ratio_

### **Interpreting STI 2.0 Data**

What the STI 2.0's scores reveal about web, mobile, and CTV sellers. How to navigate Pixalate's ranking criteria and assess seller quality.

In this section:

  * Final Ranking _(Web, Mobile, CTV)_
  * Fraudulent Bundle ID Traffic Ratio _(supplemental for CTV)_
  * SIVT Ratio and GIVT Ratio _(supplemental for all platforms)_
  * Made for Advertising (MFA) Traffic Ratio _(supplemental for Web, Mobile)_
  * Delisted App Traffic Ratio _(supplemental for Mobile)_

#### **Interpreting the Final Ranking**

A seller's final rank reflects the strength and depth of its direct supply presence within a specific country. Buyers can use this ranking to identify sellers with the highest proportion of authorized, direct inventory in a given market, across web, mobile, and CTV.

A higher rank in the STI 2.0 primarily indicates that a seller

  * transacts a majority of its impressions as direct, non-reseller inventory in the country
  * has meaningful volume of direct impressions relative to other sellers in that market
  * holds direct authorization relationships with a large number of local publishers

Sellers with lower ranks may still represent legitimate supply but are more dependent on reseller paths, have lower local publisher authorization breadth, or operate at smaller scale within the country. Buyers looking to minimize supply chain hops and prioritize direct access to premium local inventory should weight toward sellers with higher STI 2.0 rankings in their respective country.

Supplemental traffic signal data displayed alongside the final rank varies by platform and is provided as additional context. It should be reviewed separately when evaluating sellers.

#### **Interpreting Fraudulent Bundle ID Traffic Ratio**

The use of standardized app store IDs reduces fragmentation in the CTV space and ensures greater consistency by aligning buyers and sellers on the same inventory format. This gives buyers more confidence in the accuracy of the inventory being supplied.

[_Learn more about fraudulent and malformed Bundle IDs._](https://www.pixalate.com/blog/q2-2024-malformed-fraudulent-ctv-bundle-ids-risk-report)

#### **Interpreting SIVT Ratio and GIVT Ratio**

IVT can manifest as proxy usage, app spoofing, and high-risk devices. Reducing IVT provides buyers with greater confidence that fraud has been mitigated.

  * **Interpreting the General Invalid Traffic (GIVT) Ratio:** GIVT is deterministic, with examples including datacenter IPs, bot activity, and duplicate impressions. Reducing GIVT provides buyers with increased confidence that fraud has been mitigated.
  * **Interpreting the Sophisticated Invalid Traffic (SIVT) Ratio:** This type of traffic can include display impression fraud, app spoofing, and high-risk devices. Reducing SIVT provides buyers with greater confidence that fraud has been mitigated.

_For a complete list of reported IVT types,_[___please refer to this article_](https://www.pixalate.com/knowledgebase/reported-invalid-traffic-ivt-types) _._

#### **Interpreting the Made for Advertising (MFA) Traffic Ratio**

MFA poses risks to both buyers and sellers in the programmatic ecosystem. For sellers, it can undermine inventory quality and damage their reputation. For buyers, advertising on cluttered MFA sites can decrease campaign effectiveness.

_For more information on Pixalate's MFA solutions,_[___please refer to this article_](https://www.pixalate.com/knowledgebase/made-for-advertising-mfa) _._

#### **Interpreting the Delisted App Traffic Ratio**

The Delisted App Traffic rate assesses the overall traffic volume of each seller on delisted apps. Apps can be delisted for various reasons including publisher-level fraud, malware, adware, backdoor exploitation via bad SDKs, or developer-initiated removal. Apps may also be delisted for copyright violations or policy violations unrelated to fraud. A higher rate of Delisted App Traffic signals a higher likelihood that a seller is transacting on riskier apps not currently listed on an established app store.

_For more information on Pixalate's Delisted App blocking solutions,_[___please refer to this article_](https://www.pixalate.com/knowledgebase/delisted-from-the-app-store-defase-block-list) _._
