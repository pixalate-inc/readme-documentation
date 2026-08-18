---
title: "Discovery"
excerpt: "A Guide to Supply Vetting Across Mobile Apps, CTV Apps, and Websites"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### What Is MRT Discovery?

The **Discovery** section of Pixalate's Media Ratings Terminal (MRT) is the primary workspace for supply vetting at scale. It gives buyers, sellers, and platform teams a filtered, searchable view into millions of properties across Connected TV (CTV), Mobile Apps, and Websites to surface privacy, compliance, risk, traffic, and brand safety signals in one place.

Whether you're building an exclusion list before a campaign launches, vetting a new publisher relationship, or running a bulk quality check against your existing supply, Discovery is where that work begins.

###   
Accessing Discovery: Three Inventory Channels

Discovery is organized into three parallel workspaces, each tailored to the signals and metadata most relevant to that inventory type:

**Mobile Apps** covers iOS (App Store) and Android (Google Play) inventory. 

**CTV Apps** covers streaming applications across major platforms including Roku, Fire TV, Samsung, LG TV, and tvOS. CTV apps carry some unique data points not present on mobile, including app spoofing signals and channel-level data for MVPD apps. 

**Websites** covers open web domains, with signals oriented toward desktop and mobile web traffic, including ads.txt status, MFA risk, brand safety, and domain age.

All three channels share a common filtering framework and export workflow, making it straightforward to apply consistent vetting standards across inventory types.

###   
The Filter Panel: Narrowing Results 

The left-hand filter panel is where most active vetting happens. Discovery lets you build lists by filtering across hundreds of metrics, including app details, traffic, and brand safety.   
  
Filters operate across several categories: 

**Risk & IVT.** The overall risk rating (Low / Medium / High) is a composite score which is comprised of programmatic transactional data, IVT rates (MRC accredited), ad viewability, registration data, app store data, authorized sellers, brand safety information, and more. Users can filter directly on the composite risk score or on individual IVT sub-signals. 

**Brand Safety.** Discrete filters are available for each advisory category - adult content, gambling, violence, offensive content, hate speech, alcohol/drug content - allowing teams to build exclusion lists calibrated to a specific advertiser's requirements rather than applying a single blanket brand safety threshold.

**Compliance.** Filters include COPPA Violation Risk Rating, COPPA Audience Assessment (child-directed vs. general audience), privacy policy presence, terms and conditions presence, app-ads.txt or ads.txt detection, and age gate detection.

**Made for Advertising (MFA).** For domains, a "Made For Advertising Risk" filter appears in the left sidebar alongside an MFA Risk column in the main grid, allowing users to filter based on Pixalate's MFA risk designations of low, medium, or high. MFA detection for websites breaks down into sub-components including ad load, ad density, social media traffic sourcing, and paid traffic sourcing. [Pixalate](https://www.pixalate.com/knowledgebase/identifying-made-for-ads-websites-using-the-mrt)

**Traffic & Audience.** Filters are available on Daily Active Users, Monthly Active Users, inventory volume, download ranges, average user ratings, content rating, and top device type.

**Supply Chain & Compliance.** Users can filter on Trusted Seller status, app-ads.txt / ads.txt presence, and the Owner Domain field. These are available as a filter and useful for identifying all properties owned by a single business entity, a key signal for Supply Path Optimization.

**Region and Device.** Region options for apps include North America, EMEA, LATAM, APAC, and Global. Device options depend on the selected supply type. 

For CTV specifically, Discovery also includes a **Spoofing toggle** that lets users view their list results with or without spoofed inventory incorporated into IVT percentages. This is useful when analyzing whether an app's risk profile is driven by legitimate traffic or fraudulent bundle spoofing.

###   
Bulk Upload and Custom Discovery

One of Discovery's most operationally useful features is the ability to upload large lists for bulk evaluation. Discovery lets you upload thousands of publishers at a time to determine overall risk and download all associated data insights. [Pixalate](https://www.pixalate.com/discovery)

Users submit lists as CSV files containing bundle IDs (mobile/CTV) or domains (websites). The MRT runs each identifier against its database and returns a row of data for every matched property. 

The Discovery Dashboard extends this further, allowing teams to apply the full filter panel to a custom-uploaded list rather than the full indexed universe. This is useful for evaluating a specific partner's app portfolio or a curated supply list against Pixalate's data.

#### **Mobile Apps - CSV Upload output**

# | Parameter | Description  
---|---|---  
1 | App Id | Unique identifier for the app in the Pixalate database  
2 | Region | Geographic region of the data (Global, NA, EMEA, LATAM, APAC)  
3 | Device | Device type filter applied (Smartphone, Tablet, All)  
4 | Title | App display name as listed in the app store  
5 | Bundle Id | Bundle ID app identifier (e.g. com.example.app)  
6 | Track Id | Apple App Store numeric track identifier (iOS only)  
7 | App Store | Store the app is distributed through (iOS App Store or Google Play)  
8 | Category | App store content category (e.g. Games, News)  
9 | Risk | Composite overall risk rating: Low / Medium / High  
10 | App Store Page Url | Direct URL to the app's listing on its app store  
11 | IVT (%) | Percentage of observed impressions classified as invalid traffic   
12 | Viewability (%) | Percentage of measured ad impressions that met the viewability threshold  
13 | Trusted Seller | Primary authorized seller with the highest impression share in app-ads.txt  
14 | Downloads | App store download range (e.g. 100M–500M)  
15 | Average User Rating | Average star rating as shown in the app store  
16 | Content Rating | App store age/content rating (e.g. Everyone, 17+)  
17 | Developer Name | Name of the app developer or publishing company  
18 | Developer Email | Contact email listed by the developer in the app store  
19 | Developer Country | Country of the developer as registered in the app store  
20 | Private Domain | Whether the app's owner domain is registered privately (true/false)  
21 | Terms and Conditions | Whether a detectable Terms and Conditions page is present (true/false)  
22 | Privacy Policy | Whether a detectable Privacy Policy is present (true/false)  
23 | Spoofing Risk | Risk level that the bundle ID is being spoofed on open RTB (Low/Medium/High)  
24 | Location Masking Risk | Risk level that location data is being masked or manipulated (Low/Medium/High)  
25 | Advertising IVT Risk | Risk level of SIVT patterns in observed advertising traffic (Low/Medium/High)  
26 | Click IVT Risk | Risk level of invalid click activity detected (Low/Medium/High)  
27 | Viewability Risk | Risk level based on display viewability performance relative to benchmarks (Low/Medium/High)  
28 | Daily Active Users | Estimated number of daily active users observed in the data  
29 | Monthly Active Users | Estimated number of monthly active users observed in the data  
30 | Top Device | Most frequently detected device model for this app's ad traffic  
31 | Top Display AdSize | Most common display ad unit size detected (e.g. 320x50)  
32 | Top Video AdSize | Most common video ad unit size detected (e.g. 320x480)  
33 | Display Contribution (%) | Share of total observed inventory that is display format  
34 | Video Contribution (%) | Share of total observed inventory that is video format  
35 | Hyper Location Availability (%) | Share of bid requests that include precise geolocation signals  
36 | Mraid Version | MRAID version detected in the app's ad environment  
37 | Clean Programmatic Ads Detected | Whether non-fraudulent programmatic ads have been observed (true/false)  
38 | Brand Safety Risk | Overall brand safety risk rating based on content analysis (Low/Medium/High)  
39 | Content Brand Safety Rating | Brand safety risk derived from in-app content signals  
40 | Brand Safety Description Advisories Risk | Overall advisory risk from textual analysis of the app store description  
41 | Brand Safety Description Adult Content Risk | Adult content signal detected in app store description (Low/Medium/High)  
42 | Brand Safety Description Drug Content Risk | Drug-related content signal in app store description (Low/Medium/High)  
43 | Brand Safety Description Alcohol Content Risk | Alcohol-related content signal in app store description (Low/Medium/High)  
44 | Brand Safety Description Hate Speech Risk | Hate speech signal in app store description (Low/Medium/High)  
45 | Brand Safety Description Offensive Content Risk | Offensive content signal in app store description (Low/Medium/High)  
46 | Brand Safety Description Gambling Content Risk | Gambling-related content signal in app store description (Low/Medium/High)  
47 | Brand Safety Description Violence Content Risk | Violence-related content signal in app store description (Low/Medium/High)  
48 | User Generated Content | Whether the app contains user-generated content (true/false)  
49 | Delisted Date | Date the app was removed from its app store, if applicable  
50 | App-Ads.Txt | Whether an app-ads.txt file was detected for this app (true/false)  
51 | IAB Primary Category | IAB primary content category for the app  
52 | IAB Sub Category | IAB secondary/sub content category for the app  
53 | COPPA Violation Risk Rating | Risk rating of COPPA regulatory violation based on observed signals (Low/Medium/High)  
54 | COPPA Audience Assessment | Pixalate's independent audience classification: Child Directed or General Audience  
55 | MFA Risk | Made for Advertising risk designation (Low/Medium/High)  
56 | Owner Domain | Business domain of the entity that owns the app, per app-ads.txt ownerdomain directive  
57 | Ad Refresh Rate | Average number of ad refreshes per session detected in the app  
58 | Age Gate Detected | Whether an age verification gate is present in the app (true/false)  
59 | VPC Detected | Whether a Verifiable Parental Consent check is detected (true/false)  
  
#### **Websites - CSV Upload output**

# | Parameter | Description  
---|---|---  
1 | Domain | The website domain being evaluated (e.g. example.com)  
2 | Region | Geographic region of the data  
3 | Device | Device type filter applied (Desktop, Mobile Web, All)  
4 | Risk | Composite overall risk rating: Low / Medium / High  
5 | Ads.txt | Ads.txt status for the domain (Enabled, Disabled, or Not Found)  
6 | Industry | Industry classification for the domain (e.g. News and Media)  
7 | Site Category | Content category within the industry (e.g. Blogs, Sports)  
8 | Reach | Estimated relative audience reach score for the domain  
9 | Desktop (%) | Share of observed traffic originating from desktop devices  
10 | Mobile (%) | Share of observed traffic originating from mobile devices  
11 | Video (%) | Share of observed ad inventory that is video format  
12 | Family Of Sites | Number of related properties under the same owner domain  
13 | Bid Range Low ($) | Low end of the observed CPM bid range for this domain  
14 | Bid Range High ($) | High end of the observed CPM bid range for this domain  
15 | Trusted Seller | Primary authorized seller with the highest impression share in ads.txt  
16 | IVT Risk | Categorical IVT risk level derived from observed invalid traffic (Low/Medium/High)  
17 | IVT (%) | Percentage of observed impressions classified as invalid traffic   
18 | Click Fraud Risk | Risk level of invalid click activity detected on the domain (Low/Medium/High)  
19 | Viewability Risk | Risk level based on viewability performance relative to benchmarks (Low/Medium/High)  
20 | Viewability (%) | Percentage of measured ad impressions that met the viewability threshold  
21 | Major Traffic Source | Primary channel driving traffic to the domain (e.g. Search, Direct, Discovery)  
22 | Domain Age (Years) | Number of years the domain has been registered  
23 | Privacy Policy | Whether a detectable Privacy Policy is present (true/false)  
24 | Terms and Conditions | Whether a detectable Terms and Conditions page is present (true/false)  
25 | Private Domain | Whether the domain registration is private/anonymized (true/false)  
26 | Corporate Email | Whether a corporate (non-free-provider) email is associated with the domain (true/false)  
27 | Ad Injection Risk | Risk level of unauthorized ad injection detected on the domain (Low/Medium/High)  
28 | Adult Content Risk | Risk level of adult content present on the domain (Low/Medium/High)  
29 | Alcohol Content Risk | Risk level of alcohol-related content on the domain (Low/Medium/High)  
30 | Drug Content Risk | Risk level of drug-related content on the domain (Low/Medium/High)  
31 | Hate Speech Risk | Risk level of hate speech content on the domain (Low/Medium/High)  
32 | Phishing Risk | Risk level of phishing activity detected on the domain (Low/Medium/High)  
33 | Malware Risk | Risk level of malware distribution detected on the domain (Low/Medium/High)  
34 | IAB Primary Category | IAB primary content category for the domain  
35 | IAB Sub Category | IAB secondary/sub content category for the domain  
36 | Brand Safety Risk | Overall brand safety risk rating based on content analysis (Low/Medium/High)  
37 | MFA Risk | Made for Advertising risk designation (Low/Medium/High)  
38 | Owner Domain | Business domain of the entity that owns the site, per ads.txt ownerdomain directive  
39 | Ad Refresh Rate | Average frequency of ad refreshes per session detected on the domain  
40 | Ad Density | Ratio of ad slots to content; a key MFA sub-signal for websites  
41 | Social Traffic Rate | Share of inbound traffic attributable to social media referrals; a key MFA sub-signal  
42 | Paid Traffic Rate | Share of inbound traffic attributable to paid sources; a key MFA sub-signal  
  
#### **CTV Apps - CSV Upload output**

# | Parameter | Description  
---|---|---  
1 | App Id | Unique identifier for the CTV app in the Pixalate database  
2 | Region | Geographic region of the data (Global, NA, EMEA, LATAM, APAC)  
3 | Device | CTV platform the app runs on (e.g. Roku, Fire TV, Samsung, tvOS)  
4 | Title | App display name as listed on the CTV platform  
5 | Category | Content category of the CTV app (e.g. Entertainment, News)  
6 | Risk | Composite overall risk rating: Low / Medium / High  
7 | IVT (%) | Percentage of observed impressions classified as invalid traffic   
8 | SSAI (%) | Share of observed inventory delivered via Server-Side Ad Insertion  
9 | Transparent SSAI (%) | Share of SSAI inventory with transparent, measurable delivery signals  
10 | Brand Safety Risk | Overall brand safety risk rating based on content analysis (Low/Medium/High)  
11 | Trusted Seller | Primary authorized seller with the highest impression share in app-ads.txt  
12 | Developer Name | Name of the CTV app developer or publishing company  
13 | Developer Website | Developer's registered website URL  
14 | Developer Total Apps | Total number of apps published by this developer across Pixalate's CTV index  
15 | App Age Risk | Risk signal based on how recently the app was published or updated (Low/Medium/High)  
16 | CVAA Compliant | Whether the app meets Communications and Video Accessibility Act requirements (true/false)  
17 | App-Ads.Txt | Whether an app-ads.txt file was detected for this CTV app (true/false)  
18 | Top 5 Bundle IDs | The five most common bundle IDs observed mapping to this CTV app title  
19 | Include Spoofing | Toggle controlling whether spoofed bundle ID traffic is included in IVT metrics  
20 | COPPA Violation Risk Rating | Risk rating of COPPA regulatory violation based on observed signals (Low/Medium/High)  
21 | COPPA Audience Assessment | Pixalate's independent audience classification: Child Directed or General Audience  
22 | MFA Risk | Made for Advertising risk designation (Low/Medium/High)  
23 | Owner Domain | Business domain of the entity that owns the CTV app, per app-ads.txt ownerdomain directive  
24 | Ad Refresh Rate | Average number of ad refreshes per session detected in the CTV app  
  
###   
Related Resources

  * [MRT Discovery FAQ](https://www.pixalate.com/knowledgebase/media-ratings-faq)
  * [Narrowing Discovery Results with Device & Region Filters](https://www.pixalate.com/knowledgebase/narrow-discovery-results-with-multiple-apps/domains)
  * [Owner Domain Filtering](https://www.pixalate.com/knowledgebase/leverage-adstxt-ownerdomain)
  * [MFA Identification in the MRT](https://www.pixalate.com/knowledgebase/identifying-made-for-ads-websites-using-the-mrt)
  * [Insights for Mobile Apps, CTV Apps, and Domains](https://www.pixalate.com/knowledgebase/insight)
  * [MRT API Documentation](https://developer.pixalate.com/?version=latest#00fd50c1-93b7-40ce-a45f-dfc73a8318d2)
