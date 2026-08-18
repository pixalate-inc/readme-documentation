---
title: "Accessing Pixalate's Enterprise APIs"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Pixalate has a comprehensive API documentation site where you will find information on how to integrate Pixalate's anti-fraud solutions into your own systems. Please visit our [Enterprise API Portal](https://enterprise-api.pixalate.com) for more information and to use our interactive documentation.

We are continually adding content, so make sure to visit often, and in case you have any questions, please reach out to your Customer Success representative.

![](https://f.hubspotusercontent40.net/hubfs/2364596/API-png.png)

### Media Ratings Terminal - Insight API

#### How do we pull app-ads.txt data from the API?

Currently, you can only pull Ads.txt data for Domains via API. Pulling app-ads.txt data via Insights API is on the roadmap. Now, this information is only available in the UI.

#### How to best pull delisted app info from API?

Make a request to Insights API with AppID (trackID or bundleID), in the JSON response find the field labeled delistedDate. This will return the date the app was delisted from the US App Store, if this value is null, then you can assume the app is not seen as delisted on the US app store. You can then check the MRT UI to see if the app is delisted, as the UI has a real-time check.

    Request URL: [http://ratings2.api.pixalate.com/services/2018/Ratings/getApp?appId=519675128&username;=*****&password;=*****](http://ratings2.api.pixalate.com/services/2018/Ratings/getApp?appId=519675128&username=*****&password=*****)  
    JSON Response:  
         {  
              "status": "OK",  
              "numFound": 1,  
              "docs": [  
                {  
                    "appId": "519675128",  
                    "region": "GLOBAL",  
                    "device": "GLOBAL",  
                    "appTitle": "Manga Rock",  
                    "bundleId": "com.notabasement.mr2",  
                    "trackId": "519675128",  
                    "appStore": "ios",  
                    ... omitted  
                    "delistedDate": "2019-09-05",  
                    ... omitted  
                }  
              ]  
           }

#### Pulling delisted app info via the Batch API

    Make a request to the Batch API with a list of App IDs in the request body. You could also pass a .csv file. The API will respond with a CSV file, within the resulting CSV file there is a column labeled {{Delisted Date}}this column will contain the date the app was delisted from the US App Store.  
      
    http://ratings2.api.pixalate.com/services/2018/Ratings/importApps?reportId=appSummary®ion=NA&username;=****&password;=****  
    Request Body:   
    519675128  
    1257909712  
    284815117  
      
    Response:  
    <http://dashboardcdn.pixalate.com/www/exported/****/2020-04-22/*****/Summary_2020-04-22.csv>

Here is the resulting CSV. Columns unrelated to delisted date Omitted

**App Id** |  **Region** |  **Device** |  **Title** |  **Bundle Id** |  **Track Id** |  **App Store** |  **Delisted Date** |  **Remarks**  
---|---|---|---|---|---|---|---|---  
**519675128** |  North America |  smartphone |  Manga Rock |  com.notabasement.mr2 |  519675128 |  ios |  2019-09-05  
**519675128** |  North America |  tablet |  Manga Rock |  com.notabasement.mr2 |  519675128 |  ios |  2019-09-05  
**1257909712** |  North America |  smartphone |  Bitcoin mining: life simulator |  net.alexplay.miner |  1257909712 |  ios |  2019-11-05  
**1257909712** |  North America |  tablet |  Bitcoin mining: life simulator |  net.alexplay.miner |  1257909712 |  ios |  2019-11-05  
**284815117** |  North America |  smartphone |  SCRABBLE Premium |  com.ea.scrabble |  284815117 |  ios |  2020-03-19  
**284815117** |  North America |  tablet |  SCRABBLE Premium |  com.ea.scrabble |  284815117 |  ios |  2020-03-19
