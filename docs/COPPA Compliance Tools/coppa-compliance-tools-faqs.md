---
title: "COPPA Compliance Tools FAQs"
excerpt: "Answers to commonly asked questions about COPPA compliance & Pixalate's COPPA Compliance Tools"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

* **What is COPPA?**

  *     * The Children's Online Privacy Protection Act ("COPPA") is a United States federal law passed by Congress in 1998 to protect children’s online privacy. COPPA requires the Federal Trade Commission (FTC) to issue and enforce a rule implementing the law. The FTC’s COPPA Rule (“the COPPA Rule” or “the Rule”) became effective in 2000, and it was amended in 2013. The FTC is presently in the process of reviewing the Rule again. COPPA is enforced by the FTC and by state Attorneys General, who have the authority to seek civil penalties from companies that violate the law.
  * **What does child-directed mean?**
    * Directed to children is defined in the COPPA Rule as a commercial website or online service, or portion thereof, that is targeted to children.
  * **How do you assess if an app is likely directed to children or general audience**
    * Detailed guides are provided in our methodology documentation, found here:   
Pixalate's COPPA methodolog**y**
  * **What is the relationship between child-directed and mixed audience?**
    * Mixed audience online services are a subset of the child-directed category of online services. Any app designated as intended for a mixed audience would also be considered child-directed under COPPA. Hence, we refer to both of these groups as simply child-directed or directed to children in our data & reports. 
  * **The MRT labels sites/services that are mixed audience in the likely child-directed category. Is there a way of identifying which sites/services fall into the mixed audience subcategory of child-directed within the MRT?  
**
    * A mixed audience site/service falls under the child-directed category because it targets children under 13 as a portion of its audience. There are some carve-outs in the COPPA Rule for mixed audience sites. For example, these sites can implement a neutral age gate and screen users who indicate they are 13 or older and only collect information from children under 13 after obtaining verified parental consent. However, Pixalate does not have visibility into whether apps are implementing age gates and obtaining verified parental consent in a compliant manner.   
  
At this time, our AI tool does not distinguish mixed audience apps from sites that are purely child-directed. However, the educators on our Trust and Safety Advisory Board are able to make this assessment when they manually review apps. Pixalate is considering making this information available within the MRT for apps that have been manually reviewed.**  
**
  * **How does COPPA apply to advertising and the ad tech ecosystem?**
    * In addition to publishers whose content is directed to children or who have actual knowledge of a child using their service, any company that handles persistent identifiers of an online service it knows to be directed to children is subject to COPPA. This includes demand-side platforms (DSPs), supply-side platforms (SSPs), ad networks, data management platforms (DMPs), customer data platforms (CDPs), measurement providers and all of the other advertising technologies.
  * **Does COPPA restrict advertising in child-directed apps?**
    * COPPA does not prohibit advertising to children. However, the Rule prohibits the collection of personal information (including cookies and other persistent identifiers) from children under 13 without verifiable parental consent. Contextual advertising is permissible under COPPA. In practice, this means contextually-based advertising that does not track the user over time and across online services. 
  * **Does COPPA only apply in the United States?**
    * No, operators in other countries must also comply with COPPA.
    * Although COPPA is a U.S. law, foreign online service operators must comply with COPPA if they are directed to children in the U.S. or if they have actual knowledge that they collect information from children in the U.S. Relatedly, U.S. online service operators that collect information from foreign children are also subject to COPPA.

For additional insight into COPPA, visit [Pixalate's detailed methodology](https://www.pixalate.com/coppa-compliance-tools-methodology)

  * **How does Pixalate handle the likely target audience for channel aggregators?**
    * Pixalate does not designate likely-general audience streaming TV or channel aggregator apps like YouTube, SlingTV and Hulu as likely child-directed. However, certain channels within those apps may be child-directed. For example, the FTC’s complaint against YouTube does not characterize YouTube as child-directed. Rather, it states that “YouTube hosts numerous channels that are “directed to children” under the COPPA Rule.” Our methodology does not currently allow us to designate channels within an app as “likely child-directed” or “likely general audience.” If you are serving ads on these types of apps, please work with the apps so they appropriately flag child-directed channels or content for which targeted advertising will be prohibited under COPPA.

**  
**  

  * **What are the COPPA Compliance Tools?**
    * The COPPA compliance tools consist of products which provide transparency, analysis, and action in accordance with COPPA regulations across +8.5MM mobile apps. It includes: 
      * Real-time monitoring using our **Analytics’ COPPA Compliance reports**
      * **COPPA Audience data feed** to classify an app's likely intended audience & enable automated workflows
      * **COPPA Violation Risk data feed** to designate apps which carry a high or critical risk based on our methodology & enable automated workflows
      * Publisher level**COPPA Audience badge** for +8.5MM apps reveals Pixalate's assessment as likely child-directed (including mixed audience) or likely general audience. 
      * **COPPA violation risk planner** within our Media Ratings Terminal (Discovery) enables targeting (or exclusion) list building with COPPA data points in combination with the numerous other existing data points from Pixalate such as an app’s IVT%, Viewability, Brand Safety, Risk Advisories, app-ads.txt detected, app category info, etc.
      * **Keyword search for app content** to find apps likely intended for children
      * **Keyword search over 1MM app privacy policies** to make manual policy reviewing efficient
      * **API’s** for Analytics & Media Ratings Terminal COPPA Violation Risk reports & lookups to enable automated workflows 
  * **How can I access the COPPA Compliance Tools?**
    * Anyone can visit our Media Ratings Terminal <https://ratings.pixalate.com/> to view insights about an app including our COPPA Audience assessment.
    * To learn more, please visit __

<https://www.pixalate.com/coppa-compliance-tools>

  * **What methodology is used across the COPPA Compliance Tools?**
    * Our methodology was established by a team of COPPA experts, data scientists, and ad tech industry experts. You can read more about our [methodology here](https://www.pixalate.com/coppa-compliance-tools-methodology). 
  * **Do you have COPPA insights for CTV or domains?**
    * At this time we offer COPPA insights for mobile apps only. COPPA applies to any covered online service, regardless of the device on which it is accessed, including Connected Television (CTV). Accordingly, Pixalate is developing a methodology for CTV.

  * **​​What is considered, or what are the definitions for critical, high, medium, and low risk for COPPA Compliance?**
    * Pixalate analyzes multiple signals and produces a risk score (low, medium, high, or critical) that captures the potential COPPA violation risk. Check out [Pixalate's COPPA methodology](https://www.pixalate.com/coppa-compliance-tools-methodology) for more info on COPPA violation risk assessment.

  * **Can the status of an app’s COPPA Violation Risk Rating and COPPA Audience assessment change over time & if so, how is it handled?**
    * Yes, as Pixalate continuously monitors the data points, a mobile app’s COPPA Risk Rating can change between low, medium, high and critical over time.
    * Similarly, the COPPA Audience assessment can change from being likely child-directed (including mixed audience) to general audience over any period of time, or vice versa. Additionally, an app's audience assessment can be changed as the result of manual review by [Pixalate's Trust & Safety Advisory Board.](https://www.pixalate.com/trust-and-safety-advisory-board)
      * Pixalate offers a report about an app’s change history within our Media Ratings Terminal Change Log feature, which goes back 5 weeks.
  * **Why would the COPPA Audience reason code description include “iOS” when I’m filtered to view the Google Play store version of the app?**

  *     * Per Pixalate’s methodology both app stores are leveraged to classify the likely audience of an app because app stores provide different types of information on each app. 
      * For example, if an app is assessed as likely child-directed in Apple’s app store only, Pixalate’s methodology automatically designates it as likely child-directed in Google Play as well. In this scenario the reason code within Google Play will display the iOS signals that caused the app to be assessed as likely child-directed.

  * **If Pixalate manually reviews an app in one store, do we apply the same results to the app in both stores?**
    * Yes, during Pixalate's manual review process if we find an app in either app store is likely directed to children we will associate that app as likely child-directed in both app stores.

**How can an advertiser or ad tech partner act upon this COPPA information?**  

  * There are 2 areas to be considered - the first is to ensure that child directed apps are being correctly identified in your systems (both during onboarding, and during ad transactions). With that secured, the second part is to ensure that COPPA regulations are being followed in the traffic that is flowing through your systems, and the traffic is privacy safe. 
    * _Recommendations to Implementers_
      * OpenRTB Exchanges and Bidders should:
      * Provide a facility for sites to be declared as “child directed”.
      * Implement the regulations object extension.
      * Provide facilities within campaigns to adapt the targeting practices based on this signal.
      * Degrade the Geographic information to be less exact prior to logging or transmission.
      * Suppress the assignment and synchronization of identifiers, depending on usage
    * It is recommended that when regs.coppa = 1, the exchange should additionally manipulate the OpenRTB bid request object as follows:  

      * Device Object 
        * Suppress didmd5 and didsha1 device ID fields.
        * Truncate ip field - remove lowest 8 bits.
        * Truncate ipv6 field - remove lowest 32 bits.
      * Geo Object 
        * Suppress lat and lon fields.
        * Suppress metro, city, and zip fields.
      * User Object 
        * Suppress id, buyeruid, yob, and gender fields  
For example, in OpenRTB 2.5, confirm that the regs.coppa=1 for all child directed apps - even if it had not been set as such upstream. In addition, follow the guidance in section 7.5: 
  * **If Pixalate designates an app as “likely general audience,” am I safe in serving targeted ads on that app?**
    * Not necessarily. Pixalate’s tool helps ad networks assess risk, but cannot serve as a legal conclusion. The best entity to ascertain the child-directed nature of the app is the publisher of the app. If the publisher of the app signals to you that it is child-directed or that portions of the app are child-directed, that is the most reliable indicator, and you should not serve targeted ads on that app without parental consent. Similarly, if you or your employees notice that an app appears child-directed, you may have liability under COPPA if you serve targeted ads on that app without parental consent. If you learn that an app Pixalate has designated as “likely general audience” is child-directed, please let us know by using the Suggest Edit button, located next to the COPPA Audience assessment field in the Media Ratings Terminal App Insights page, pictured below:  
![Screen Shot 2022-06-15 at 6.46.33 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202022-06-15%20at%206.46.33%20PM.png)
  * **What is your manual review process and sampling method like?**
    * Pixalate has formed a [Trust and Safety Advisory Board](https://www.pixalate.com/trust-and-safety-advisory-board), helmed by a former FTC enforcer and composed of qualified educators, to review and assess whether apps are likely child-directed.
    * App review is an ongoing process, Pixalate prioritizes apps for review based on the popularity of the app measured by the number of downloads in Google Play and the number of reviews in Apple’s App store.
  * **How many apps are analyzed in the COPPA related data set?**
    * Pixalate assesses over 8.5MM apps for COPPA Audience and Violation Risk Ratings. Pixalate analyzes any new apps that are listed in the Apple App Store or Google Play Store.
  * **How often is our COPPA Violation Risk Rating updated?**
    * Pixalate updates the COPPA Violation Risk on a weekly cadence.
  * **How often is COPPA Audience assessment updated?**
    * Pixalate updates the COPPA Audience assessment on a weekly cadence, but few components used in the assessment, like Content Rating, Category or App description, are only refreshed on a monthly cadence.
    * The data points in the MRT including COPPA risk assessment and COPPA Audience (likely child-directed or likely general audience) are refreshed weekly, though some specific data points like Content Rating, Category or App description, are refreshed monthly.**When are the COPPA Compliance Data Feed products refreshed?**
      * Pixalate refreshes the COPPA Violation risk (high & critical risk apps list) and COPPA Audience (likely child-directed app list) data feeds on a monthly basis.
  * **Are there any examples of apps that are likely general audience that would get a medium, high or critical COPPA violation risk score?**
    * No. If an app is assessed to be likely general audience, it will get a low COPPA risk violation score. The rationale is that a site that is likely not targeting children as any portion of the audience is a low risk from a COPPA compliance perspective.
  * **Does Pixalate's COPPA AI-tool label gaming apps like solitaire, trivia crack, gin rummy and others as being likely child-directed?**
    * Some of these apps are labeled as likely child-directed. If the app is in the Games category and it has a certain content rating (Everyone, Everyone 10+ on Android and 4+ or 9+ on Apple) and it contains child-related keywords in the app title or description, it will be labeled as likely child-directed. Additionally, when Pixalate’s educators on the Trust and Safety Advisory Board are reviewing apps like these, they are applying the subjective factors set forth in the COPPA Rule such as the subject matter, visual content, language, and use of animated characters or child-oriented activities and incentives. There are certain versions of games like solitaire that would fall under the child-directed category when assessed under these factors.  

  * **If an app is flagged as child directed based on manual review, does Pixalate provide an explanation of how that assessment was made?**

The educators on Pixalate’s [Trust and Safety Advisory Board](https://www.pixalate.com/trust-and-safety-advisory-board?hsLang=en) make assessments of the likely target audience of apps based on the child-directed factors outlined in the [COPPA Rule](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa). The factors include the subject matter; visual content; use of animated characters or child-oriented activities and incentives; language or other characteristics of the website or online service; and evidence regarding audience composition. A full list of the child-directed factors in the COPPA Rule can be found in Pixalate’s [COPPA Compliance Tools Methodology](https://www.pixalate.com/coppa-compliance-tools-methodology). Any number of these factors could come into play during the manual review process. For apps that are manually reviewed, Pixalate indicates that the app is likely general audience or child-directed based on manual review. However, Pixalate does not list the specific factors that the manual reviewer relied on in making the assessment.

  * **How often does your automated system flag something differently from your manual reviewers", How accurate is your automated assessment vs. the manual review?**
    * According to a sample analysis of a magnitude sufficiently large to provide confidence in the results from a statistical perspective, Pixalate's AI assessment has resulted in the same outcome as a manual review more than 85% of the time. This correlation is, however, expected to vary with different sample analyses. For example, where manual review targets categories that over index for false negatives or false positives, we expect manual assessment to be somewhat divergent from the corresponding AI assessment. In such circumstances, manual assessments will be incorporated into our ML algorithms to improve future AI assessments.
  * **What if myself or my company disagrees with how an app has been labeled or presented in the COPPA related analysis?**
    * Pixalate offers a "Suggest Edit" button next to the COPPA Audience assessment result on our App Insights page, see visual below. Pixalate will review your request & get back to you with our assessment as soon as possible.   
![Screen Shot 2022-06-15 at 6.46.33 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202022-06-15%20at%206.46.33%20PM.png)

Can't find something? Send additional questions to your customer success representative or [schedule a demo here.](https://www.pixalate.com/coppa-compliance-tools)

Disclaimer:

Pixalate’s COPPA Compliance Tools render opinions that Pixalate believes may be useful to our clients and others in the digital media industry. It is important to note, however, that the mere fact that an app appears to be directed to children (e.g., data subjects under 13 years of age, as defined by the COPPA Rule) does not mean that any such app, or its operator, is failing to comply with the COPPA Rule. Further, with respect to apps that appear to be child-directed and have characteristics that, in Pixalate’s opinion, may trigger related privacy obligations and/or risk, such assertions reflect Pixalate’s opinions (i.e., they are neither facts nor guarantees); and, although Pixalate’s methodologies used to render such opinions are derived from a combination of automated processing coupled with significant human intervention, no assurances can be – or are – given by Pixalate with respect to the accuracy of any such opinions.
