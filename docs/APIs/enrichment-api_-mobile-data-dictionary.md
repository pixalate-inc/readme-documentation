---
title: "Enrichment API: Mobile Data Dictionary"
excerpt: "Explore data points available within the Enrichment API. Data points vary by platform, see below for Mobile App related fields"
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
  
#### App Overview:

App Title |  App Title  
---|---  
Screenshot URLs |  List of app screenshots  
Description |  App description  
IAB Primary Category |  IAB primary categories  
IAB Sub Category |  IAB secondary categories  
Delisted Date |  App delisted date from app store (Format : YYYY-MM-DD)  
Delisted App |  A flag that indicates whether the app was delisted from the app store or not true indicates the app was delisted from the app store.  
Has Dangerous Permissions |  Dangerous permissions cover areas where the app wants data or resources that involve the user's private information, or could potentially affect the user's stored data or the operation of other apps.  
  
#### App Details:

Bundle ID |  App bundle identifier (For Google Play it is package name & For App Store it is Unique identifier for the app assigned by apple developer)  
---|---  
Track ID |  Unique identifier for the app assigned by Apple (for Only App Store) & Null for Google Play  
App Store Url |  App page on Google Play or App Store  
Trusted Seller |  Authorized trusted seller  
Incentivized Activity |  True indicates incentivized activity available in the app  
Download Range |  The estimated number of apps installed ( Only for Google Play) Ex: 500000000 - 1000000000  
Average User Rating |  The average user rating given by the app store. Ex: 4  
Content Rating |  The recommended content rating defined by the app store. Ex: Teen or 4+  
Blocklisted |  True indicates the app has been placed on Pixalate risk blocklist  
Blocklisted Reasons |  List of reasons causes the blocklist app Refer possible blocklist reasons (H144)  
  
#### Pixalate Advisories:

Has App-Ads-Txt |  True if AppAds.txt is enabled for the app's domain.  
---|---  
Has Dangerous Permissions |  True if dangerous permissions are enabled. List of app permissions are in widget "appPermissions"  
Private Domain |  True if domain is privately registered  
Has Terms And Conditions |  True if app has terms and conditions  
Has Privacy Policy |  True if app has privacy policy  
IVT Permission Risk |  IVT Permission Risk (low/medium/high)  
COPPA Rating |  COPPA Permission Risk (low/medium/high)  
  
#### Risk Overview:

IVT % |  Percentage of Invalid traffic associated with advertising transactions for the app Ex: 25%  
---|---  
IVT Risk |  Invalid traffic Risk (low/medium/high)  
Viewability |  The average viewability for all display ad impressions in the app Ex: 29%  
Viewability Risk |  Viewability Risk (low/medium/high)  
Description Brand Safety Risk |  The overall description risk to advertise Brand Safety from the app  
Content Brand Safety Risk |  The overall content risk to advertise Brand Safety from the app  
IVT Permission Risk |  The overall IVT risk to advertise Brand Safety from the app  
Risk |  Pixalate's unique advertising risk assessment based on blended risk factors including brand safety, invalid traffic and inventory for all regions and devices.It includes risk reasons. List of possible risk reasons ( Please find below Possible Risks section )  
  
#### Developer Overview:

Developer Name |  The business name of the app's developer  
---|---  
Developer Location |  The business address of the app's developer  
Developer Email |  Contact email address of the app's developer  
Developer Country |  Country name of the app's developer  
Developer Website |  App's developer website  
Developer Total Apps |  The total number of apps available from the developer  
Facebook Risk |  Facebook Risk (low/medium/high) , Low social media engagement on Facebook can be a risk factor  
LinkedIn Risk |  LinkedIn Risk (low/medium/high) , Low social media engagement on LinkedIn can be a risk factor  
Twitter Risk |  Twitter Risk (low/medium/high), Low social media engagement on Twitter can be a risk factor  
  
#### Traffic Overview:

Spoofing Risk |  Spoofing Risk (low/medium/high) , The risk the app may be misrepresented in advertising transactions and ads delivered to a different app or site  
---|---  
Location Masking Risk |  Location Masking Risk (low/medium/high) , The risk that location data is inaccurate for advertising transactions involving the app  
Advertising IVT Risk |  Advertising IVT Risk (low/medium/high) , The risk of advertising impressions delivered to the app being due to invalid traffic (IVT)  
Click IVT Risk |  Click IVT Risk (low/medium/high) , The risk of clicks originating from ads on the app being fraudulent  
Viewability Risk |  Viewability Risk (low/medium/high) , The risk of IAB viewability standards not being met for ad impressions on the app  
Estimated Daily Active Users |  Estimated daily active users of the app (Ex: 1000000)  
Estimated Monthly Active Users |  Estimated monthly active users of the app (Ex: 6000000)  
Inventory |  The estimated number of monthly impressions this app makes available programmatically  
Top Device |  The platform most commonly trafficked in programmatic advertising (Ex: Xiaomi Redmi or Galaxy A10)  
  
#### In-App Ad Capabilities:

Display Top Ad size |  The display ad size most commonly trafficked in programmatic advertising (Ex: 336x280)  
---|---  
Video Top Ad size |  The video ad size most commonly trafficked in programmatic advertising (Ex: 768x1024)  
Video Contribution |  The percentage of video ads trafficked on the app Ex: 4.77%  
Display Contribution |  The percentage of display ads trafficked on the app Ex: 95.23%  
Hyper Location Availability |  The percentage of advertising transactions containing the user's latitude and longitude Ex: 98.78%  
MRAID Version |  The most recent version of MRAID for which the app is compliant (Ex: 3.0)  
Ads Detected |  True when Ads are detected in the app. Non ad-supported apps may be at risk of spoofing.  
Interactive Elements |  List of Interactive elements focus on what information the app has access to. Possible values are : Shares Info , Shares Location , Users Interact , Digital Purchases , Unrestricted Internet , In-App Purchases , In-Game Purchases  
  
#### Brand Safety:

Description Brand Safety |  App descriptive text is processed through natural language algorithms and comprehensive categorical dictionaries to predict the advertiser brand safety risk. Description Brand Safety Risk - The overall description risk to advertise Brand Safety from the app. 1\. Advisories Risk - The risk to brand safety derived from the app's content advisories. 2\. Adult Content Risk - The risk to brand safety from Adult themed content based on textual analysis of the app and its descriptive content . 3\. Drug Content Risk - The risk to brand safety from Drug themed content based on textual analysis of the app and its descriptive content . 4\. Alcohol Content Risk - The risk to brand safety from Alcohol themed content based on textual analysis of the app and its descriptive content. 5\. Hate Speech Risk - The risk to brand safety from Hate Speech content based on textual analysis of the app and its descriptive content. 6\. Offensive Content Risk - The risk to brand safety from content with Offensive Language based on textual analysis of the app and its descriptive content . 7\. Gambling Content Risk - The risk to brand safety from Gambling focused content based on textual analysis of the app and its descriptive content . 8\. Violence Content Risk - The risk to brand safety from Gambling focused content based on textual analysis of the app and its descriptive content  
---|---  
Content Brand Safety |  In-App visual content is processed through an advanced machine learning algorithm and evaluated for risk to advertiser brand safety.

  1. Adult Risk - The risk to brand safety from Adult themed content based on textual analysis of the app and its descriptive content.
  2. Violence Risk - The risk to brand safety from potential violent imagery and content detected within the app.
  3. Image Data - The image by image breakdown of brand safety risk factors based on advanced machine learning driven visual processing and text extraction.

#### Inventory & Impression Insights:

By Device |  The estimated volume of programmatic ad impressions broken down by device  
---|---  
By Region |  The estimated volume of programmatic ad impressions broken down by business region  
By Country |  The estimated volume of programmatic ad impressions broken down by country  
By AdSize |  The estimated volume of programmatic ad impressions broken down by ad sizes  
By DMA |  The estimated volume of programmatic ad impressions broken down by Designated Market Area (DMA)  
CTR |  Click Through Rate: Average CTR of this app CTR By Ad Size - The average CTR percentage of valid traffic for all ad sizes and traffic types in the app  
  
#### Additional App Insights:

App Permissions |  App permissions types:

  * Normal permissions - Normal permissions cover areas where your app needs to access data or resources outside the app's sandbox, but where there's very little risk to the user's privacy or the operation of other apps. For example, permission to set the time zone is a normal permission. If an app declares in its manifest that it needs a normal permission, the system automatically grants the app that permission at install time.
  * Dangerous permissions - Dangerous permissions cover areas where the app wants data or resources that involve the user's private information, or could potentially affect the user's stored data or the operation of other apps. For example, the ability to read the user's contacts is a dangerous permission. If an app declares that it needs a dangerous permission, the user has to explicitly grant the permission to the app. Until the user approves the permission, the app cannot provide functionality that depends on that permission.

---|---  
Traffic Overlap |  Overlap traffic illustrates the most common user journeys from app to app. It leverages shared users to not only connect apps together but also to create relationships between a series of apps. List of apps provided based on overall traffic (by Overall Traffic) and invalid traffic (by IVT).

  * User Overlap - The percentage of users of the given app that also visit the app. Ex: 8.7 %.
  * Inventory Overlap - The percentage of impressions of the given app that were generated by the users that visited the app. Ex: 3.9%

Authorized Sellers |  The contribution of various sell side platforms to programmatic ad impressions sold on the app. Sellers are categorized by payment type:

  * Direct - The contribution of direct sellers to programmatic ad impressions sold on the app.
  * ReSeller - TO DO .
  * Unauthorized - The contribution of unauthorized sellers (based on exclusion from App-Ads.Txt file) to programmatic ad impressions sold on the app.

Viewability Percentage | 

  * Viewability - The average viewability percentage of valid traffic for all ad sizes and traffic types in the app.
    * The average viewability, according to the IAB standard of 50% in view for at least 1 second, for display advertisements in the app.
  * Viewability Risk, high medium, or low
  * By Ad Sizes - Provides Viewability details by ad sizes

#### Invalid Traffic:

Invalid Traffic |  The percentage of invalid traffic associated with each Pixalate's taxonomy of GIVT and SIVT invalid traffic types:

  * IVT - The total percentage of non-human traffic measured on the app.
  * GIVT - GIVT refers to General Invalid Traffic - Deterministically judged to be non-human traffic; high to very high risk.
  * SIVT - SIVT refers to Sophisticated Invalid Traffic - Probabilistically judged to be non-human traffic using advanced statistical detection methods; moderate to high risk traffic.
  * GIVT Types - The percentage of invalid traffic associated with each Pixalate's taxonomy of GIVT invalid traffic types.
  * SIVT Types - The percentage of invalid traffic associated with each Pixalate's taxonomy of SIVT invalid traffic types

---|---
