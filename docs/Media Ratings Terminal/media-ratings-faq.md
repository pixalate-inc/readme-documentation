---
title: "Media Ratings FAQ"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### Media Ratings Terminal

  * **What KPIs and metrics can I search for via the MRT?**

IVT estimates  
Most common IVT types broken down by GIVT vs. SIVT  
Viewability estimates  
Ads.txt checker  
Overall site risk  
Overall brand safety risk  
Overall traffic quality risk  
Site category  
Domain category

IAB categories  
Estimated reach  
Global and category ranking based on volume  
Estimated available programmatic inventory  
Split between video and display inventory  
Split between desktop and mobile inventory  
Available inventory by region, country, U.S. state, and DMA  
Available inventory by ad size  
Viewability by ad size  
Top trusted sellers  
Estimated CTR  
Top traffic sources  
Top subdomains  
Split between desktop OS and mobile OS  
Estimated DAU and MAU

  * **If I have a list of my own sites or apps, can I upload them in bulk to look at the results of just those sites or apps?**
    * Yes. We have a bulk upload feature which enables clients to look up custom groups of domains and apps. You can also create a Custom Discovery Dashboard within the MRT.

  * **Can I export app or domain information via the MRT?**
    * Yes.

  * **Is reporting in the MRT customizable?**
    * Yes. Our Analytics and Media Ratings Terminal products are highly customizable. Additionally, the Media Ratings Terminal offers an entirely customizable Custom Discovery Dashboard, where you can upload any list of apps or domains and then apply filters to your custom list. This custom dashboard allows you to quickly assess the quality ratings specific to any custom selection of apps or domains.

  * **How many domains are searchable in the MRT?**
    * Over 200 million domains

  * **How many apps are searchable in the MRT?**
    * Over 10+ million mobile apps and over 60,000 CTV apps.

  * **Why are some apps or domains labeled as 'High Risk' and on a blocklist even if the MRT shows that they have relatively low IVT levels?**
    * Apps or domains are sometimes labeled 'High Risk' for reasons other than IVT. For example, we measure adult advisories and content ratings, which are related to Brand Safety but not IVT. Whether on the block list or not, you may wish to make note of these advisories when considering running advertising on specific publishers.
  * **How should I interpret the Traffic Overlap Trends report?**
    * This report shows the relationship based off all devices linked between both apps - the app being looked up and the app in a particular row in the table. Depending on the nature of the apps being compared, the relationship between impression / inventory and user may be disproportionate and it usually implies "inorganic" relationships. In this case, this relationship would insinuate there are devices linked between these apps that disproportionately generates impressions for both apps.
    * The relation is App A Uniques Devices/ (A|B) Unique Devices

  * **How is CTR calculated for Domains?**
    * We aggregate it from clients using our tracking Analytics pixel with the impression tracker.

  * **How do I make sure that my 'ads.txt' or 'app-ads.txt' files are detected and flagged as available in the MRT?**
    * Confirm that the 'ads.txt' file or 'app-ads.txt' file can be reached from the root domain
    * Check your URL. Do you need to include "www" to access your site (e.g., www.domain.com)?

    * Ads.txt crawling will start at the root domain, and the root domain needs to return from, or redirect to, the ads.txt file.

      * An ads.txt file on www.domain.com/ads.txt will only be crawled if domain.com/ads.txt redirects to it.

    * If you need to include “www” to access your site, then you need to set up a redirect from domain.com/ads.txt to www.domain.com/ads.txt.

    * For more helpful information on setting up your 'ads.txt' files, refer to the IAB spec available [here](https://iabtechlab.com/wp-content/uploads/2022/04/Ads.txt-1.1.pdf) (current as of FAQ publish date)
  * **What buckets/themes are used in determining the ultimate quality? Low Risk – Medium Risk – High Risk? Or something different?**

    * For some metrics and overall risk, we use the "Low – Medium – High" theme while others use "true or false". Our filters also take in account numeric values for ranges. For the final risk score determination of an app or a domain which uses “Low – Medium – High" theme, our AI engine reviews use several metrics (e.g. programmatic transactional data, IVT rates (MRC accredited), ad viewability, registration data, app store data, authorized sellers, brand safety information and more) and a complex algorithm that decides how risky a combination of metrics is. Not all metrics have equal importance, but some of them in conjunction with others can be signs of high risk behavior. Below is a list of metrics shown in the Insight section and what buckets / themes they use. 
      * “Low / Medium / High” theme 
        * Overall site risk
        * Overall brand safety risk
        * Overall traffic quality risk
        * Social Media Presence: 
          * Facebook
          * LinkedIn 
          * Twitter
      * Percentage and “Low / Medium / High” theme 
        * IVT estimates 
          * The ranges for flagging high, medium, low are dynamic and varies depending on the IVT monitored for apps each time the MRT is updated. In general, the following ranges apply: 
            * Connected TV:

              * Low: 0.00% - 8.00%

              * Medium: 8.00% - 15.00%

              * High: 15.00% - 100.00%

            * Domain:

              * Low: 0.00% - 3.00%

              * Medium: 3.00% - 10.00%

              * High: 10.00% - 100.00%

            * Mobile:

              * Low: 0.00% - 5.00%

              * Medium: 5.00% - 10.00%

              * High: 10.01% - 100.00%

        * Viewability estimates
      * Percentage / Numeric 
        * Estimated available programmatic inventory
        * Split between video and display inventory
        * Split between desktop and mobile inventory
        * Available inventory by region, country, U.S. state, and DMA
        * Available inventory by ad size
        * Estimated reach
        * Viewability by ad size
        * Estimated CTR
        * Split between desktop OS and mobile OS
        * Estimated DAU and MAU
      * “True / False” theme 
        * Ads.txt checker
        * App store availability
        * Blocklist state
        * Incentivized activity
        * Private Domain
        * Terms and Conditions
        * Privacy Policy
        * Ads detected
      * Lists / Text 
        * Most common IVT types broken down by GIVT vs. SIVT
        * Site category
        * Domain category
        * Top trusted sellers
        * Top traffic sources
        * Top subdomains
        * Global and category ranking based on volume
  * **How is brand safety risk determined?**
    * The brand safety assessment runs through a proprietary sensitivity scanner where certain characteristics of an app or domain are analyzed for potential violations.

    * On apps, we perform image analysis on screenshots to identify potential adult and violence content not just on the images themselves but the extracted text within the images when available. We also use natural language processing (NLP) on the app title, app description, and advisory data to scan for the following:

      * Adult content

      * Drug Content

      * Alcohol Content

      * Hate Speech

      * Offensive Content

      * Gambling Content

      * Violence Content

Each category has their own set of text and context relationships that are taken into account when assessing their respective risks and the MRT exposes these discrete layers. An overall brand safety risk score is also calculated based on the blending of the facets specified above.

  * **What is Ad Density?**

    * Ad Density is the frequency in which video ads are played in CTV in a 10-minute period. Unlike video pre-roll in mobile and desktop, video ads in CTV are played after periods of content viewing, similar to traditional television. During these ad slots, multiple 15- or 30-second ads are played, typically ranging from one to five ads. The time for content viewing and the number of ads per ad slot varies widely across apps.

  * **Why does Ad Density matter?**

    * Certain app developers have content breaks too often and/or play a high number of video ads to take advantage of high CTV video ad CPMs. Ads on these apps are less likely to be viewed by an engaged user, reducing the effectiveness of an advertiser’s ad spend. Our aim is to provide a deeper insight to advertisers and programmatic buyers regarding apps that may harm the user experience with too many video ads.

  * **How is Ad Density defined and determined?**

    * Pixalate defines Ad Density as the number of video ads per 10 minutes in a given app. The 10 minute increment was determined as sufficient time to measure a standard ad break. This time frame was established through significant analysis using actual live video recordings of CTV apps. 

  * **Is there a limit to the number of apps or websites I can submit at one time via the MRT Discovery CSV upload?**
    * We recommend capping the number of apps or websites to 10,000 records at a time to ensure a quicker response.
  * **Some of the apps or domains I submitted to the MRT Discovery lookup or to the API request were not found, do those count towards the API or CSV upload limit?**
    * Only successful lookups with data returned are counted against the quota.
  * **When does the quota for app or website lookups via the API or MRT Discovery CSV upload refresh?**
    * The quota refreshes every 30 days. 
  * **What are the versions supported by the IAB Primary and Secondary Categories?**
    * Apps are aligned with [IAB Taxonomy v2.2](https://iabtechlab.com/standards/content-taxonomy/). Domains are aligned with v1 at the time of this update.
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
  
In addition, this is why we advise clients to work directly with the seller or publisher in order to figure out where the sources of these problematic devices are coming from. 
  * **Does the "Authorized Seller" section in the MRT translate to 100% of the impressions measured by Pixalate?**  

    * The total overall IVT percentage for an app is based on the global data pool Pixalate monitors, while the Trusted Sellers section is based on specific sellers that have mappings available. The percentages in the "Trusted Sellers" section shows a subset of traffic of the overall app rather than the traffic in its entirety. The percentages under Trusted Seller add up to 100% of the subset of data, rather than the entirety of the impressions that we are analyzing across the ecosystem.  

  * **Using the MRT Discovery search bar, I've searched by app title - why am I not seeing the app show in results?**

    * The Discovery search results are sorted by inventory volume, based on the impressions Pixalate captures in our data set. It is possible that the result you are looking for is in the results but further down & not in-view on the first few pages. We recommend downloading the results to confirm and find the full app list that matches your search terms. Otherwise, it might be better to search by app or bundle ID for your intended result to be at the top of the list. 
  * **For a blocklisted app, why could the "Advertising IVT Risk" be other than "High"?**
    * It's possible that an app could be on the blocklist for reasons other than IVT.  
  
In the case of an app that is on the blocklist, historically have had high IVT levels, and more recently have IVT % trending downwards significantly, we generally see this as potentially posing medium IVT risk. If this decreasing IVT rate trend continues and there are no other reasons for the app to be on any of our blocklists, the app should age off the list/s over time. 
  * **As a publisher, how can I use the MRT effectively?**
    * Publishers can leverage the MRT for insight into how their app or website is performing from a traffic quality, compliance, and brand safety perspective then take steps to improve potential problem areas, particularly when it comes to IVT risk mitigation. 
      * The MRT displays the IVT types present along with their definitions so that publishers can work with their Pixalate representatives on reducing risk. 
      * The MRT breaks down which inventory sources and sellers may present higher risk and can be used to optimize partnerships for better IVT mitigation strategies. 
    * Publishers can also use the MRT for competitive review because the platform shows other apps that users of your app go to, along with device and impression overlaps. 
    * Publishers can also breakdown the insights geographically at the region and country levels to have a better understanding of which markets present better opportunities for growth and which ones are more prone to risk for planning purposes.
  * **What is "True Reach" in the website insights page of the MRT?**
    * "True Reach" is the estimated ratio of unique visitors to the total visitors that Pixalate observed visiting this domain per 1M total visitors over the span of 30 days. This metric is updated weekly. 

### **CTV App Data: Roku, Amazon Fire TV, Samsung Smart TV Apps**

  * **Which CTV app stores does MRT have data for currently?**
    * The MRT provides data for Samsung Smart TV (as of May 2023), Roku, and Amazon Fire TV app stores. One thing to note is that each app store has different data structure and thus may present slightly differently in the MRT. 
  * **How much app data do we have and what is our visibility?**
    * The various CTV platforms are constantly adding and removing apps from their stores, we refresh our data in the MRT on a weekly basis. We tend to see increases in the number of apps over the course of time as content proliferates. We tend to have more data on North America as it leads in market share for CTV, but global data continues to increase YoY.
  * **What are skinny bundles?**
    * The term refers to how new OTT streaming services are able to bundle together different channels more efficiently compared to old cable TV bundles which forced people interested in only a few channels to then pay for a bunch of channels that they didn’t care about. Hence, skinny bundles are more efficiently bundled and therefore “skinnier” bundles and are represented by something like a SlingTV.
  * **What does the ads.txt reports mean?**
    * It appears that the industry is leaning towards using app-ads.txt for OTT apps as well and it will be the official supported name. 
  * **What does the “in store” flag mean?**
    * If we see the store is returning any data, we will note that it is “In Roku Store”. For the most part, apps should always be available but there are some edge cases such as apps that users can install but are not listed in stores, such as pirated movie apps. “Category” is from Roku’s own categories and the “developer” is from the Roku store.
  * **What does the IVT, SSAI, and CVAA mean?**
    * IVT is the overall IVT % we see for that app which includes bad SSAI. The SSAI % includes both good and bad SSAI and that % therefore does not correspond to the IVT % in any way. CVAA refers to the Communications & Video Accessibility Act which is designed to make sure digital media is more accessible to persons with disabilities such as via closed captioning for hearing loss individuals. CVAA compliance indicates that the app has features to support that. 
  * **What does the App Age Risk mean?**
    * We can track how old the app is based on the published date. Newer less established apps may be riskier from an advertising perspective so we have developed an algorithm that evaluates this threshold and assigns a Low or High Risk. This may in turn be a part of the overall App Risk though that metric takes into account a lot of other larger factors.
  * **What does the bundle ID’s section mean?**
    * This provides information about all the associated bundle ID’s with that particular app and is not typically information that is available and requires us to do a lot of data science work to properly map them together. Note that this report may not be enabled to everyone since it potentially opens up our methodology in OTT app data collection.
  * **How is the SOV report compiled?**
    * We are reading the app-ads.txt file. Initially we reviewed both the app-ads.txt file as well as the ads.txt file but since finding out that the app-ads.txt was going to be the industry standard, we started relying on that exclusively. When we report on the spoofing %, we are saying that waver spoofing % it is, that is the amount of spoofed inventory for that particular app a buyer may encounter when buying from that particular SSP. In other words, that % is specific to each SSP and the app in question, and is not a general across the board SSP spoofing %.
  * **What does Transparent SSAI mean?**
    * Transparent SSAI is a terminology that we developed and is referring to the fact that Pixalate is able to see more data getting passed to us which allows us to identify that the SSAI is legitimate. It is a good thing, so the higher the Transparent SSAI, the better. The additional data points we are seeing to verify legitimate SSAI is specifically through the X-Forwarded For as well as the X Device IP. Something to note is that if there is no Transparent SSAI, then we know for sure that they are not leveraging Vast 4.0 and later. Inferences can be drawn - for example if a provider has 100% SSAI but none of it is Transparent SSAI, then it likely doesn’t reflect as well on the partners since they may be using an outdated Vast version.

### Seller Trust Indexes

  * **How does a seller get ranked?**
    * Pixalate analyzes data gathered from billions of programmatic advertising transactions. Sellers identified by this data are scored in each category, and if enough data exists, they are ranked against other platforms.

  * **Where do you get your data?**
    * Pixalate collects advertising data from multiple sources across the entire advertising stack, including everyone from ad agencies and DSPs, to SSPs, exchanges, and publishers.

  * **Are the sources providing the data for all your clients?**
    * Many of our clients deploy our data analytics solution in order to gain valuable insights about the advertising opportunities and impressions trafficked by them or to them. While individual client data is restricted for use to that customer only, the data in aggregate helps to create our ratings

  * **Everyone knows that a given seller has more fraud than us, but they are ranked higher. How?**
    * Unfortunately, not all definitions and measurements of ad fraud are created equal. Company reputations may also be prone to hearsay and commentary. Pixalate works with other companies in the industry and participates with the IAB and MRC to move toward and employ a rigorous common definition of invalid traffic. As standards and measurement are still evolving, though, Pixalate may simply measure invalid traffic differently than another source. We’ve learned a lot from our data over time, and have made corrections where we’ve been wrong. As a result, we believe our measurements are as solid as you will find in the business.

  * **How does Pixalate deal with arbitragers?**
    * In our experience, arbitrage as a business model in programmatic advertising invites ad fraud. Low scores for viewability, domain masking, GIVT, and SIVT will track most arbitragers. Additionally, we expect to add arbitrage as a dimension to our indexes at some point in the future.

  * **How do we increase our score?**
    * The score is a blend of positive inputs such as volume of unique users, domains, and apps, and negative inputs such as suspicious web traffic, MFA (Made For Advertising) traffic, data center IP addresses, and low viewability. Your score may be increased by improving your positives by adding more unique inventory and traffic sources and by lowering your negatives - preventing ad fraud and improving ad viewability, lowering exposure to high-risk MFA sites/apps.

  * **Are these scores weighted?**
    * Yes. Each metric contributing to a Final Score carries a specific weight. The unique scoring algorithm is machine-learning tested to ensure that a seller’s score is fairly and consistently represented.

  * **What criteria is Pixalate applying to the ads.txt score on the Seller Trust Indexes?**
    * The portion of the Seller Trust Index scoring system that Pixalate labels "Ads.txt" takes into account, among other things, whether the partnership is a direct or indirect partnership, if the partnership is a "trusted seller" partnership (aka the main buyer/seller relationship); overall reach of the domain in the entire demand ecosystem; and relevancy of the domain within the entire ecosystem (is this a domain that people know and trust/how long has it been established). Again, this is a portion of what makes up the overall score.
  * **What criteria is Pixalate applying to the MFA Risk score on the Seller Trust Indexes?**
    * The portion of the Seller Trust Index scoring system that Pixalate labels "MFA Risk Score" takes into account, among other things, the amount of traffic that were deemed to be high or medium risk of being "Made For Advertising" (MFA) by Pixalate's [MFA detection methodology](https://www.pixalate.com/knowledgebase/pixalate-mfa-detection-product-overview). This score for sellers is marked as Low, Medium, High or Critical. Again, this is a portion of what makes up the overall score. This score was added starting with Q4 2023 Web Seller Trust Index (WSTI).

  * **How do we measure "user interaction" for the Engagement metric? Are we including video completions in there and viewability? In general, would Pixalate consider brand safety as another metric for STI?**  

    * The engagement score is more indicative to non-ivt user engagement with an ad. Instead of video completion which could mean the video is playing to an unnoticed screen, we use interactions with the ad to judge engagement like clicks. Currently brand safety is not a metric that is currently within scope, because we are more performance-focused. However, this is something we can entertain in the future.
