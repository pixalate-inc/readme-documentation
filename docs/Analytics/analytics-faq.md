---
title: "Analytics FAQ"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### How to Use

  * **What values can be passed as the Supply Type (kv24 parameter in the tag)?**

    * Acceptable hardcoded KV24 values include: Desktop, Desktop_Video, Desktop_Native, Mobile_Web, Mobile_Web_Video, Mobile_Web_Native, Mobile_InApp, Mobile_InApp_Video, Mobile_InApp_Native, Email_Display, Email_Video, Desktop_Native, Mobile_Web_Native

  * **Is there just one login for multiple users?**

    * We offer a login for each user to avoid password sharing and security concerns. 

  * **What do I need to do if I need to add more users?**
    * Reach out to your Customer Success representative if you need other team members to access our services.
    * Your CS rep will provide you with a form to fill out requesting additional access to be set up. If you have any further questions, please reach out to your CS rep. 

  * **If a client sets the JavaScript in HTML, how do they then organize the parameters of the JavaScript？**

    * We will generate the tags based on the macros provided by the DSP, each parameter in the tag is predefined of what data it can accept.

  * **Is there some differences in the use of a JavaScript tag vs a 1x1 tag in terms of native, video, or other environments?**

    * A 1x1 tag can be provided for display and video ad measurement while a javascript tag can be provided for tracking display and native ads. 

    * When integrating, your customer service representative will provide a 1x1 pixel with data parameters (key value pairs or "KVs") based on the macro mapping sheet you provide to integrate and this can be used to track display and video ad impressions.
    * To track native ads or measure display viewability, a javascript tag will need to be used and this is something you will need to discuss with your CS representative to add to your subscription if not already included. 
  * **What HTTP methods does the Pixalate tag support?**
    * The Pixalate tag supports both GET and POST methods. For any questions, reach out to your Customer Success representative.

  * **How does Pixalate define a user session? When would a session begin and end?**

    * We define a session based on cookies so this is the period of time (often less than a day) that is characterized by the same session cookie when available.

### Invalid Traffic and General Reporting

  * **What time zone does the platform report on?**

    * The reports listed under ‘Fraud Reports’ are only available un UTC. The reports listed under 'Reports' (aka. main reports) are in UTC by default. However, this can be updated to either EST or PST by selecting the buttons at the top right under account name.

  * **Why are the fraud reports not showing any data for today?**

    * The reports listed under ‘Fraud Reports’ are processed only once per day in UTC. However, the reports listed under 'Reports' (aka. main reports) have a 6 hour delay, updating every hour.

  * **Why does Pixalate report duplicate impressions and how are these impressions generated?**  

    * Pixalate is required by the Media Ratings Council to report on all impressions received, thus where a duplicate is identified, we are not able to discard it and will need to report it. Since duplicates are considered invalid, we are flagging them as the "duplicateImpressions" IVT type. 

Here are a few common reasons why duplicateImpressions happen, but there could be other reasons as well:

>       1. A mistake in the way the publisher is utilizing a single ad, e.g.: when an ad unit scrolls out and then is scrolled back in view, the ad is not refreshed, but the previous ad was used, this is a loss revenue opportunity
>       2. Creative Scanning, but this normally can be identified by checking the domain, being captured
>       3. The publisher is intentionally recycling the impression to try to achieve higher CTRs
>       4. Do you support multi-ad in your ORTB? If you do, maybe the auction ID might need to be changed to further handle the different ads within a response.
>       5. Integration issues, For e.g.: the pixalate pixel was attached twice, once as part of the adm, and further as an impression beacon, or the pixalate pixel is added to the event.tracker, as well as the impression pixel to handle in native ads, etc.

As mentioned, duplicateImpressions are a fundamental loss of opportunity for everyone along the supply chain, and could also result in some infrastructure cost for various parties when it happens excessively. Thus if you are working directly with the traffic source, this would be invaluable insights you can share with them that could result in more ad opportunities.

  * **Is reporting customizable?**

    * Yes. Our Analytics and Media Ratings Terminal products are highly customizable.

  * **Do you support alerts, and are your alerts customizable?**

    * You can create customizable reports, based on your data, that can be scheduled to be sent to any email address (delivery reports, IVT reports, etc). We have a standard IVT/viewability report sent out daily from our system.

  * **Do you offer scheduled reports?**

    * Yes, for post-bid.

  * **What measurement metrics do you support?**

    * Impressions, Clicks, Conversions, IVT (GIVT, SIVT), Viewability for display, various campaign level metrics.

  * **When using the Report API, what do the "isAsync" and "isLargeDataSet" parameters set?**

    * If isAsync=true parameter is specified, then the response is returned immediately, while the service continues to process the report asynchronously. The report will not be available for download until processing has completed. While processing asynchronously, a request to retrieve the report using the response URL will return an HTTP status code Not Found (404). Once asynchronous processing has completed, the report is returned as normal.

      * If asynchronous processing of a report fails because of an invalid query, the report using the response URL will return an HTTP status code Bad Request (400).

      * For all other errors a request to retrieve the report using the response URL will return an HTTP status code Internal Service Error (500).

      * When using isAsync=true, client systems should poll the response URL until the report is available, or a non 404 HTTP status code is returned.

    * If isLargeResultSet=true parameter is specified, then processing is handled identically as if the isAsync parameter is set to true. However, the returned CSV file contains a single column with each row being a URL to a CSV file that contains part of the data.

      * Note that large result sets that include an "ORDER BY" clause may cause an HTTP status code Bad Request (400) to be returned. Try removing the "ORDER BY" clause or using the limit parameter to reduce the result set size. Also, extremely large result sets may require the use of the isAsync, or isLargeResultSet parameters.'

  * **What times does data in reports and dashboard update?**

    * The processing of IVT data depends on the type:

      * Real-time: General IVT (GIVT) - Data center and IAB crawlers specifically

      * 12 hours: Other advanced General IVT (GIVT) and Sophisticated Invalid Traffic (SIVT)

    * In terms of publishing the data:

      * Real-time: IVT for GIVT (data center and IAB crawlers specifically) is available in the Fraud API

      * Hourly: Estimated IVT is published hourly in the dashboard and reports

      * Daily after 6:00 AM UTC: Estimated hourly IVT is reconciled into actual IVT and published in the dashboard and reports

    * To account for longer data processing times, it is recommended to pull the previous day's data 1 or 2 hours after 6:00AM UTC.

  * **What is the range of data that can be retrieved from the pre-set reports vs. advanced reports?**
    * For pre-set reports, the date range for data that can be retrieved is 12 months. The pre-set reports contain a streamlined list of dimensions and metrics available and is optimized for speed.
    * For advanced reports, the date range for data that can be retrieved is 60 days. Advanced reports contain a more comprehensive list of dimensions and metrics for in-depth data analysis.
    * If the data required is outside of these supported windows, reach out to your Customer Success representative to initiate a custom data pull, which may incur additional cost. 
  * **When comparing data between the "By Domains" report in the "Pre-Set Reports" group vs. "Domains" report in the "Reports" group, why is there a discrepancy in gross ad counts when all other filters and date range are the same?**
    * The **By Domain** report in the **Pre-Set Reports** does not include "not set" or null (empty) domain values.

This is in contrast with the **Domains** report in the**Reports** section in the Analytics dashboard where it includes domain values that are _"not set"_ or  _null._

This can cause discrepancies in reporting on comparison if _null_ values exists in the domain data set measured. 

### Supply Path Optimization (SPO) Reports and SCO IVT Types

  * **How often does Pixalate's crawler data refresh to account for updates made to 'ads.txt' and 'sellers.json' files and mitigate SCO-related IVT types?**
    * In case of an **SCOunauthorizedDirectSeller** error, the ads.txt and app-ads.txt files will be retried for crawling on the next day.
    * In case of an **SCOunauthorizedDirectSellerPublisherMissing** error, the sellers.json file will be retried for crawling on the next day.
  * **What is Pixalate's General Crawling Policy?**
    * All our ads.txt and app-ads.txt files are crawled within a rolling 30-day window.
    * All our sellers.json files are crawled within a rolling 7-day window.

### Viewability

  * **Do Pixalate viewability numbers include IVT?**
    * Pixalate Net Viewability numbers exclude IVT.

  * **Can viewability be recorded if a 1x1 pixel is used?**
    * No.

  * **Do you provide video viewability?**
    * No. However, we are in the process of supporting video viewability with a target window of Q2 2025. 

### Ad Types

  * **Do you support the delivery of image banners (e.g. 320x50)?**
    * Yes, we have a 1x1 pixel and a JavaScript tag that can support this.

  * **Do you support the delivery of image animation creatives (e.g. expandable banners)?**
    * Yes, we have a 1x1 pixel and a JavaScript tag that can support this.

  * **Do you support the delivery of video interstitials?**
    * Yes, we have a 1x1 pixel that can support this.

  * **Do you support the delivery of native ads?**
    * Yes, we have a 1x1 pixel and a JavaScript tag that can support this.

  * **Do you support the delivery of custom creative templates?**
    * Yes, we have a 1x1 pixel and a JavaScript tag that can support this.

### Click-Tracking

  * **What does highCTR IVT type mean?**

    * The “highCTR” IVT type characterizes traffic associated with domains or apps demonstrating high Click Through Rates (CTR) at the creative level. In other words, for a given publisher, only the creatives that generate anomalous CTRs will be flagged as IVT. This can flag user-side IVT such as crawlers clicking on a given creative repeatedly, or publisher-side IVT such as creative manipulation with the intent to inflate click through rates. 

  * **How is highCTR IVT type identified?**

    * For a given client, highCTR is identified as the proportion of traffic that belongs to a given creative that has been manipulated publisher-side or being targeted user-size in order to generate very large click through rates, either intentionally or as a byproduct of some other invalid activity. The main precondition for such determination is that both click and impression tracking have been enabled at the creative level. The thresholds used correspond to a combination of dynamic thresholds within a range of acceptable values (i.e. 2% - 10%). Creatives with less than 2% are not considered for analysis by this IVT type and creatives with more than 10% will be flagged deterministically. The region in between will be flagged depending on the dynamic baselines detected for that given client.

When sampling is used to decide what traffic to send to Pixalate, it is highly recommended that the same sampling method is used for both impressions and clicks in order to avoid false classifications. For example, if 10% of the impressions are sampled for the given publisher+creative while 20% of the clicks are sampled for the same publisher+creative, the perceived CTR can be twice as much compared to the real one, since the sampling rate of clicks is double the sampling rate of impressions.

### DElisted From the App StorE (DEFASE)

  * **What is the defaseApp IVT Type?**

    * The IVT type called “defasedApp” characterizes traffic seen from apps that were available for download through one of the two major app stores (namely Google Play and iTunes) over the last 12 months but got delisted and currently are not available any more. 

  * **What does DEFASE stand for?**

    * DEFASE stands for DElisted From the App StorE. 

  * **Why is a defasedApp IVT?**

    * In general, apps can be delisted for various reasons, including publisher level fraud, malware, adware, availability of backdoors for fraudsters to leverage bad SDKs, or simply because the developer decided to delist an app. In addition, it is also possible for an app to be delisted for other reasons such as copyright violations. So, clearly, not all delisted apps generate necessarily IVT. For this, Pixalate collects information about the behavior of a delisted app prior of it being delisted, and based on that, decides if an app should be flagged as IVT because it poses significant risks to the advertising ecosystem. 

  * **Can a DEFASED apps be flagged for other IVT reasons?**

    * Yes. Pixalate analyzes the traffic seen from an app using various models that check for certain types of IVT patterns. An app does not have to be flagged as 100% defasedApp if it gets delisted. On the contrary, Pixalate will try to label the traffic behind a delisted app using its other IVT types first (i.e. using higher IVT priorities) such that more light is shed on the invalid activity generated by the app. 

  * **Are there any data feeds that can protect us from “defasedApps”?**

    * Yes. Pixalate has developed two datafeeds related to delisted apps:

      * A data feed containing all the removed apps from Google Play and iTunes store within the last 6 months. The friendly name for this data feed is “Defase App List”.

      * A data feed containing all the apps removed from Google Play and iTunes store within the last 6 months, which have generated impressions in the last 2 weeks and which also have shown evidence of suspicious or invalid behavior. The friendly name for this data feed is “Defase App Blocklist”.

    * Based on the above definitions, the first list can contain apps that do not have ads or do not have impressions at all, but nevertheless they can be useful if proactively blocked to avoid being manipulated for IVT in the future. 

    * The second list contains apps that have been seen generating impressions and in general should be treated as IVT and be blocked. Note: Pixalate has developed algorithms to detect and exclude from the second list potential cases of removed apps that should not be blocked and treated as IVT because their removal was likely not related to IVT. Examples of such apps include cases removed temporarily due to legal issues, that are usually put back in the app store a few days or weeks later.

  * **For how long an app can be delisted from the app stores?**

    * An app can be delisted for various reasons, and in many cases some removals are permanent. However, there are cases of apps that have been added back a few weeks after their removal (e.g. due to a malicious SDK causing problems to the app until it gets uninstalled). This means that when someone uses a DEFASE data feed, he/she needs to make sure that the latest daily copy has been downloaded, since Pixalate’s backend has been designed to check on a daily basis if delisted apps are still delisted, and if new apps have been delisted, and update the data feeds accordingly. 

### Pre-caching:

  * **What are the current trends we are seeing and issues with pre-caching?**
    * Pre-caching is a quite common tactic in mobile, especially for certain types of creatives. Pixalate works with its partners to ensure that the measurement pixel is integrated properly and fired at the “SHOW” phase (actual impression) and not at the “LOAD” phase (pre-caching phase). If this is not the case, Pixalate has adopted the MRC recommendations of preventing pre-rendering of the measurement pixel (whenever possible; e.g. in Javascript), or if this is not possible, merge the consecutive impressions. If this is also not possible, traffic might be reported as duplicate impression if impression ID is passed (kv11) for further debugging. Duplicate impression is not an IVT type that can cause any type of blocking (e.g. at the datafeeds). It is an informative metric. [](https://developers.mopub.com/docs/marketplace/pre-caching/)

  * **How does this translate to IVT stats? What are the false positive risks?**
    * There might be instances where a duplicate call of the measurement pixel can be flagged as duplicate impression
  * **How common of a practice is this?**
    * The practice is getting more and more popular.

### General Questions:

  * **Why do IVT rates for websites and apps sometimes differ when viewing from the Analytics dashboard vs. the Media Ratings Terminal (MRT)?**
    * The difference in IVT rates and other metrics between the Analytics dashboard vs. the MRT depends primarily on the source of data being measured. 
      * Analytics measures your first-party traffic and the IVT rates as well as other metrics you see are specific to your platform's traffic quality. This allows for more targeted optimization strategies by identifying potential problem areas and IVT types that are present in your traffic in order to take steps to mitigate your risk. 
      * MRT measures the entirety of Pixalate's global data pool. The data source is more expansive and can give our clients insights into an app or website's traffic quality and other metrics prior to working with them. Due to the scope of data analyzed, this often times leads to a variance when compared against Analytics results. 
  * **How does Blocking relate to the first-party data measured in Analytics and the representation in the MRT?**
    * It is important to note that there are differences on how IVT is being presented depending on what platform and data set is being reviewed:  
  
\- The first party data in a client's Analytics dashboard and the level of IVT in that context  
\- MRT IVT data and how that is based on Pixalate's global data pool and not just a client's measured first-party data  
\- How apps are flagged in the the Pixalate blocklists  
  
Not all the IVT types we identify and measure using a client's first-party data via the Analytics dashboard goes into the MRT for a combination of reasons. Likewise, not all IVT types flagged in a client’s first-party data leads to the app to being flagged in the blocklist.  
  
IVT can be a product of compromised devices, bot farms, or behavior observed from the app themselves.   
  
When evaluating IVT, we take all of this into consideration and behavioral correlations in order to determine whether the flagged impressions show a stronger association to the app itself or the devices generating the impressions.   
  
This is in order to avoid penalizing an app for misrepresented traffic or bad devices.   
  
In addition, this is why we advise clients to work directly with the seller or publisher in order to figure out where the sources of these problematic devices are coming from. **  
**
  * Does Pixalate measure attention metrics (time on creative, etc.)? Advertisers are requesting this more and more since it shows that not only was the ad viewable, but viewable for x amount of time. 
    * The following reported metrics most closely align with the industry's definitions of attention related metrics: 
      * Ad Exposure Time (adExposureTime) = The amount of time Ad is visible to the user on the web page. Ad exposure is measured in minutes and seconds.
      * Ad Exposure (adExposure) = The percentage of total time spent on a web page in which the Ad was visible to the user.
    * There are also other attention-related metrics which may be of relevance such as 'Ad Hover' and 'Time Spent on Page'.
