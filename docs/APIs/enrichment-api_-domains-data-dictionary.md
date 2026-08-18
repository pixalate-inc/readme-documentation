---
title: "Enrichment API: Domains Data Dictionary"
excerpt: "Explore data points available within the Enrichment API. Data points vary by platform, see below for domain related fields."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### Dimensions: 

Ad Domain |  Ad Domain  
---|---  
Region |  Region - GLOBAL, US, NON-US (International)  
Device |  Device - GLOBAL, desktop , mobile  

#### Domain Overview:

IAB Primary Category |  IAB primary categories  
---|---  
IAB Sub Category |  IAB secondary categories  
Has Ad Txt |  True if Ads.txt is enabled for the domain.  

#### Domain Details:

Inventory |  The estimated number of monthly impressions this domain makes available programmatically  
---|---  
Desktop Traffic Ratio |  The percentage of desktop ads trafficked on the domain  
Mobile Traffic Ratio |  The percentage of mobile ads trafficked on the domain  
Video Traffic Ratio |  The percentage of video ads trafficked on the domain  
CTR |  Average CTR of the domain  
Family Of Sites |  Number of family sites associated with the domain  
Pixalate Risk |  Overall pixalate's unique advertising risk assessment based on blended risk factors including brand safety, invalid traffic and inventory  
Bid Price Low |  Low bid price in dollars   
Bid Price High |  High bid price in dollars  
Trusted Seller |  Authorized trusted seller.  
True Reach |  The estimated number of unique users per 1 Million internet users that can be reached on this domain.  

#### Risk Overview:

IVT |  Percentage of invalid traffic associated with advertising transactions for the domain  
---|---  
IVT Risk |  Invalid traffic Risk (low/medium/high)  
Viewability |  The average viewability for all display ad impressions in the domain  
Viewability Risk |  Viewability Risk (low/medium/high)  
Brand Safety Risk |  The overall risk to advertise Brand Safety from the domain  
Risk |  Overall pixalate's unique advertising risk assessment based on blended risk factors including brand safety, invalid traffic and inventory for all regions and devices. It includes risk reasons.  

#### Traffic Quality Risk:

IVT Risk |  Invalid traffic Risk (low/medium/high)  
---|---  
Click Fraud Risk |  Click Fraud Risk (low/medium/high)  
Viewability Risk |  Viewability Risk (low/medium/high)  
Domain Masking Risk |  Domain Masking Risk (low/medium/high)  
Top Traffic Source |  Major Traffic Source  

#### Site Info & Risk:

Domain Age |  Domain age in years  
---|---  
Has Privacy Policy |  True if domain has privacy policy  
Has Terms And Conditions |  True if domain has terms and conditions  
Private Domain |  True if domain is privately registered  
Corporate Email |  True indicates WHOIS registration was done with a corporate email address False indicates WHOIS registration was done with a personal email address  
Ad Injection Risk |  Ad Injection Risk, unauthorized ads on site (low/medium/high)  
Owner |  Owner of the domain  
Email Address |  Email info  
Contact Number |  Contact number  
Mailing Address |  Email address  

#### Brand Safety Risk:

Adult Content Risk |  Adult Content Risk (low/medium/high)  
---|---  
Alcohol Content Risk |  Alcohol Content Risk (low/medium/high)  
Drugs Content Risk |  Drug Content Risk (low/medium/high)  
Hate Speech Words Risk |  Hate Speech Risk (low/medium/high)  
Phishing Risk |  Phishing Risk (low/medium/high)  
Malware Risk |  Malware Risk (low/medium/high)  

#### Social Media Risk:

Facebook Risk |  Facebook Risk (low/medium/high) Low social media engagement on Facebook can be a risk factor  
---|---  
LinkedIn Risk |  LinkedIn Risk (low/medium/high) Low social media engagement on LinkedIn can be a risk factor  
Twitter Risk |  Twitter Risk (low/medium/high) Low social media engagement on Twitter can be a risk factor  
Social Traffic Ratio |  Percentage of Social Traffic Ratio  

#### Invalid Traffic:

IVT |  Percentage of Invalid traffic associated with advertising transactions for the domain  
---|---  
GIVT |  Percentage of General Invalid traffic associated with advertising transactions for the domain  
SIVT |  Percentage of Sophisticated Invalid traffic associated with advertising transactions for the domain  
GIVT Types |  The percentage of invalid traffic associated with each Pixalate's taxonomy of GIVT invalid traffic types  
SIVT Types |  The percentage of invalid traffic associated with each Pixalate's taxonomy of SIVT invalid traffic types  
By Data Centers |  The estimated volume of programmatic ad impressions broken down by Data Center  

#### Inventory & Ad Performance Insights:

By Region |  The estimated volume of programmatic ad impressions broken down by Region  
---|---  
By State |  The estimated volume of programmatic ad impressions broken down by State  
By Country |  The estimated volume of programmatic ad impressions broken down by Country  
By AdSize |  The estimated volume of programmatic ad impressions broken down by Ad Size  
By DMA |  The estimated volume of programmatic ad impressions broken down by Designated Market Area (DMA)  
By Device |  The estimated volume of programmatic ad impressions broken down by device(desktop, mobile)  
By DesktopOS |  The estimated volume of programmatic ad impressions broken down by desktop OS  
By MobileOS |  The estimated volume of programmatic ad impressions broken down by mobile OS  
Authorized Sellers |  The contribution of various sell side platforms to programmatic ad impressions sold on the domain.Sellers are categories(paymentType),

  * Direct - The contribution of direct sellers to programmatic ad impressions sold on the app.
  * ReSeller - TODO
  * Unauthorized - The contribution of unauthorized sellers (based on exclusion from Ads.Txt file) to programmatic ad impressions sold on the app.

Traffic Sources |  The volume of programmatic ad impressions broken down by traffic source.  
Sub Domains |  The volume of programmatic ad impressions broken down by the sub domains.  
Viewability |  The average viewability for all display ad impressions in the domain  
Viewability By Ad Size |  The average viewability for all display ad impressions in the domain broken down by Ad Size  
CTR |  Average Click Through Rate of the domain  
By Ad Size |  Average Click Through Rate of the domain broken down by Ad Size
