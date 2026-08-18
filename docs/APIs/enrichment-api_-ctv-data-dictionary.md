---
title: "Enrichment API: CTV Data Dictionary"
excerpt: "Explore data points available within the Enrichment API. Data points vary by platform, see below for CTV related fields."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### Dimensions: 

App ID |  App Unique Identifier Package Name on Google Play Track ID for App Store  
---|---  
Region |  Region: Global, NA(North America), EMEA, LATAM, APAC  
Device |  Device: Global (all), smartphone , tablet, desktop for domains  
App Store |  App Store: Google Play (for android), App Store (for ios)  
Include Spoofing |  For CTV, include or exclude spoofing in the app results  
  
#### App Overview:

App Title |  App Title  
---|---  
Description |  App brief description, previewed from the app store  
Categories |  The category of the app  
Screenshot URLs |  List of app screenshots  

#### Risk Overview:

Risk |  Overall pixalate's unique advertising risk assessment based on blended risk factors including brand safety, invalid traffic and inventory for all regions and devices. (Please find below Possible Risks section)  
---|---  
IVT |  The overall percentage of Invalid Traffic (IVT)  
IVTRisk |  Invalid traffic Risk (low/medium/high)  
SSAI Impressions Ratio |  The percentage of traffic observed to utilize server-side-ad-insertion (SSAI) integrations for ad/ad content delivery to the end user  
Transparent SSAI Impressions Ratio |  SSAI tracked impressions that come from proxies passing X-Device-User-Agent headers for more transparency.  
Description Brand Safety Risk |  Risk factors to advertiser Brand Safety broken down by descriptive text about the app (low/medium/high)  
Content Brand Safety Risk |  Risk factors to advertiser Brand Safety broken down by both in-app content such as images (low/medium/high)  

#### Pixalate Advisories:

Has App-Ads.Txt |  True if App-Ads.txt is enabled for the app's domain.  
---|---  
Delisted App |  A flag that indicates whether the app was delisted from the app store or not.true indicates the app was delisted from the app store.  
Delisted Date |  App delisted date from app store. Format, YYYY-MM-DD  
Private Domain |  True if domain is privately registered  
Has Terms And Conditions |  True if app has terms and conditions  
Has Privacy Policy |  True if app has privacy policy  
App Age Risk |  Risk rating based on the amount of time the app has been listed within the app store. Apps which have been listed for an extended period of time may present less risk than those recently published. (low/medium/high)  

#### App Spoofing:

Victim Of Spoofing |  True if app is a victim of spoofing  
---|---  
Spoofing Risk |  Risk of spoofing in this app (low/medium/high)  
By Fraud Type |  Spoofing by fraud type denoting the fraud type with set of apps with detected Bundle ID, declared Bundle ID, SOV Risk  

#### App Details:

App Store Url |  App page on the store.  
---|---  
Available Countries |  The countries in which the app is available.  
Available Languages |  The languages in which the app is available.  
Keywords |  Search terms and keywords typically associated with the app. (Roku only)  
Rating |  The app's average user-rating within the app store (based on a 5-star scale).  
Star Rating Count |  The number of ratings provided within the app store  
Parental Hint |  Indicates parental sensitivity considerations for the respective app content.  
Revenue Sources |  The primary sources of revenue: Ads, In-app Subscriptions, Pay to Install, and/or In-app one-time purchases  
CVAA Compliant |  Indicates whether the app is in compliance with the FCC's Communications and Video Accessibility Act (CVAA) Standards.  
App Age Risk |  Risk rating based on the amount of time the app has been listed within the app store.(low/medium/high).  
App Age |  The amount of time the app has been listed within the app store.  
Published Date |  The date of original publication within the app store.  
App Privacy Policy |  Indicates whether an app-specific privacy policy is maintained. Apps which do not maintain a privacy policy may be of higher risk to advertisers and sellers.  
App Privacy Policy Url |  Link to the app-specific privacy policy  
Delisted App |  A flag that indicates whether the app was delisted from the app store or not.true indicates the app was delisted from the app store.  
Delisted Date |  App delisted date from app store. Format, YYYY-MM-DD  
Bundle IDs |  The unique textual identifier of the app within the app store.  
Channels |  Channels available for apps considered as aggregators or providers of 'skinny bundles'  

#### Developer Overview:

Developer Name |  The business name of the app's developer.  
---|---  
Developer Website |  link to the app's developer website  
Private Domain |  Businesses with privately registered domains.  
Has Terms And Conditions |  Businesses without published terms and conditions on their website.  
Has Privacy Policy |  Businesses without published Privacy Policy on their website.  
Total Apps |  Total number of apps published by this developer.  

#### Brand Safety:

Description Brand Safety |  The overall Brand Safety risk to advertisers based on textual analysis of the app's descriptive text. App descriptive text is processed through natural language algorithms and comprehensive categorical dictionaries to predict the advertiser brand safety risk.

  * Advisories Risk - The risk to brand safety derived from the app's content advisories.
  * Adult Content Risk - The risk to brand safety from Adult themed content based on textual analysis of the app and its descriptive content.
  * Drug Content Risk - The risk to brand safety from Drug themed content based on textual analysis of the app and its descriptive content.
  * Alcohol Content Risk - The risk to brand safety from Alcohol themed content based on textual analysis of the app and its descriptive content.
  * Hate Speech Risk - The risk to brand safety from Hate Speech content based on textual analysis of the app and its descriptive content.
  * Offensive Content Risk - The risk to brand safety from content with Offensive Language based on textual analysis of the app and its descriptive content.

---|---  
Content Brand Safety |  The overall Brand Safety risk to advertisers based on computer vision driven image analysis as well as textual analysis of language extracted from images of the app's content. In-App visual content is processed through an advanced machine learning algorithm and evaluated for risk to advertiser brand safety.

  * Adult Content Risk - The risk to brand safety from potential adult images and content detected within the app.
  * Violence Content Risk - The risk to brand safety from potential violent imagery and content detected within the app.
  * Images Data - The image by image breakdown of brand safety risk factors based on advanced machine learning driven visual processing and text extraction.

#### Traffic & Inventory Insights:

Traffic Overview |  Traffic volume and ad inventory estimates for the app along with associated advertising risk factors.

  * Spoofing Risk - The risk the app may be misrepresented in advertising transactions and ads delivered to a different app or site.
  * Advertising IVT Risk - The risk of advertising impressions delivered to the app being due to invalid traffic (IVT). IVT risk is derived from standardized definitions of invalid traffic maintained by the Media Rating Council, Inc. (MRC) and the Interactive Advertising Bureau (IAB).
  * Trusted Seller - Pixalate crunches the data to rate sellers representing this app on the basis of a number of factors including audience reach and invalid traffic risk.
  * IVT Free Users Rate - The percentage of the app's individual user-base not responsible for presence of invalid traffic.
  * Estimated Daily Active Users - Estimated Daily Active Users
  * Estimated Monthly Active Users - Estimated Monthly Active Users
  * Ad Spend - Estimated AdSpend

---|---  
Traffic Overlap |  Overlap traffic illustrates the most common user journeys from app to app. It leverages shared users to not only connect apps together but also to create relationships between a series of apps. 

  * List of apps provided based on overall traffic(by overall traffic) and invalid traffic (by IVT%).
  * Device Overlap - The percentage of users of the given app that also visit the app.
  * Impression Overlap - The percentage of impressions of the given app that were generated by the users that visited the app.

Authorized Sellers |  The contribution of various sell side platforms to programmatic ad impressions sold on the app.Sellers are categorized by payment type.  
Inventory by Region |  The estimated volume of programmatic ad impressions broken down by business region.  
Inventory by Ad Size |  The estimated volume of programmatic ad impressions broken down by ad size.  
Inventory by DMA |  The estimated volume of programmatic ad impressions broken down by Designated Market Area (DMA).  

#### Invalid Traffic:

IVT |  Overall percentage of invalid traffic (IVT)   
---|---  
SIVT |  SIVT refers to Sophisticated Invalid Traffic - Probabilistically judged to be non-human traffic using advanced statistical detection methods; moderate to high risk traffic  
GIVT |  GIVT refers to General Invalid Traffic - Deterministically judged to be non-human traffic; high to very high risk.  
SIVT Fraud Types |  The type of sophisticated invalid traffic (SIVT) designation associated with such IVT. All IVT calculations are derived from standardized definitions of invalid traffic maintained by the Media Rating Council, Inc. (MRC), Interactive Advertising Bureau (IAB), and Trustworthy Accountability Group (TAG).

  * Fraud Type - The type of fraud detected
  * GIVT - The contribution of this fraud type in overall GIVT
  * SIVT - The contribution of this fraud type in overall SIVT

GIVT Fraud Types |  The type of general invalid traffic (GIVT) designation associated with such IVT. All IVT calculations are derived from standardized definitions of invalid traffic maintained by the Media Rating Council, Inc. (MRC), Interactive Advertising Bureau (IAB), and Trustworthy Accountability Group (TAG).

  * Fraud Type - The type of fraud detected
  * GIVT - The contribution of this fraud type in overall GIVT
  * SIVT - The contribution of this fraud type in overall SIVT
