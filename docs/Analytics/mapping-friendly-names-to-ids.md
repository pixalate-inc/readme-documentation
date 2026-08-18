---
title: "Mapping Friendly Names to IDs"
excerpt: "Friendly Name Mapping is a feature which allows you to map names to the ad serving IDs that are passed through the tag and reported in the Pixalate dashboard, allowing you to view both the friendly name in addition to the ID when viewing reports."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### Step-by-step guide

  * Create a new spreadsheet or use an existing one.
  * File should be saved in CSV format
  * The CSV contains two columns, first column indicates ID, second column indicates the Name of the ID in the same row.
  * Ensure the CSV includes 'id' and 'name' titles within the first header row (without quotes). 

The header titles are case sensitive.

Example: ks_advertisers.csv (file name can be any valid name)

=========================

id,name  
63244,AARP  
63245,American Cancer Society DetermiNation  
63246,Walt Disney Parks & Resorts  
63248,IU Health

==========================

  * Create an email and address to [ids@pixalate.com](mailto:ids@pixalate.com)
  * Add the subject line which includes client ID, adserver/platform ID, and dimension, separated by the # character.

##

clientId : ID of the client. Can be found within the analytics tag provided; either as the clid=[CLIENTID] value for 1x1 pixels or after # in JavaScript tags cb=[cb]#[CLIENTID]

adserver : ID of the ad server or platform serving the ad. Can be found within the analytics tag as the value for paid=[ADSERVERID]

Most common Ad Server IDs

dcm --> Google's DCM dfp --> Google's DFP  
apn --> AppNexus lkqd --> LKQD  
adroll --> AdRoll cdt --> Cedato  
turn --> Turn sr --> StreamRail

dimension : Indicates the Pixalate dimension as displayed within the dashboard. 

advertiserId --> Advertiser Identifier  
campaignId --> Campaign Identifier  
lineItemId --> Line Item Identifier  
placementId --> Placement Identifier  
publisherId --> Publisher Identifier  
creativeId --> Creative Identifier  
orderId --> Insert order Identifier  
siteId --> Site Identifier  
sellerId --> Seller Identifier

Examples: 

Mail subject line for AppNexus advertiser Ids and names for ks (clientId)

ks#apn#advertiserId

Mail subject line for Doubleclick Campaign Manager (DCM) site Ids and names for lt (clientId)

lt#dcm#siteId

  * Save the file, attach the file to the email, and send. Names will auto update within the dashboard with the data refresh, in ~6 hours. 

It is best practice is to cc either your Customer Success representative or [am@pixalate.com](mailto:am@pixalate.com) when sending emails to [ids@pixalate.com](mailto:ids@pixalate.com). This will help if in any case there are issues processing the CSV.
