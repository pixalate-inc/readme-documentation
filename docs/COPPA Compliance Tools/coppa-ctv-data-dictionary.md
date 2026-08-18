---
title: "COPPA CTV Data Dictionary"
excerpt: "Information about the data points used within our COPPA CTV compliance tools & methodology."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The following data points are featured within the COPPA CTV section of the Media Ratings Terminal for Connected TV (CTV) apps, Analytics Compliance reports for CTV apps, and associated APIs - with consideration of paid product subscription access & permissions. Each of these data points are relevant to our COPPA CTV insights, and further explained within our methodology.

**Field Name** |  **Definition** |  **Expected/Sample Result**  
---|---|---  
COPPA Audience - Mobile Apps |  Assesses the likely intended audience of an app based on a variety of factors including app store categories, content ratings, and keywords, etc. according to Pixalate’s methodology. |  Likely Child Directed including mixed audiences, or Likely General Audience  
COPPA Audience Reason Code |  Describes the specific variables considered when making the audience assessment. |  “This app is likely child-directed because…"  
Store Categories |  The associated categories of an app according to the Roku and Amazon Stores.  |  Examples include: Education, Health & Fitness, Kids, Lifestyle, Movies & TV, Music & Audio, News, Religious, Screensavers  
Age Rating |  The recommended age rating defined by Amazon’s app store or the Parental Hint provided by the Roku store. |  Roku: Content Not Rated, Content Rated, All Ages, Adult Fire: Guidance Suggested, All Ages, Adult, Mature   
COPPA Risk Rating - CTV Apps |  Pixalate analyzes multiple signals and produces a risk score (low, medium, or high) that captures the potential COPPA risk. See chart below. |  High, medium, low  
COPPA Risk Rating Reason Code |  Describes the specific variables considered when making the overall COPPA risk rating assessment. |  “The COPPA risk is high because the app…”   
Privacy Policy Detected |  Pixalate determines whether an app has a privacy policy based on information provided in the app stores. Additionally, Pixalate uses crawlers to scan developer websites for privacy policies. |  Yes or No  
Transmits Residential IP |  Pixalate examines the traffic associated with an app and determines if the end-user IP is transmitted through the advertising pipeline that can expose granular information about the user’s location. |  Yes or No  
Passes Location |  Pixalate examines the traffic associated with an app and determines if the end-users’ GPS coordinates are being transmitted through the advertising pipeline that exposes granular information about the user’s location. |  Yes or No  
  
Learn more about these data points & our [methodology](https://www.pixalate.com/coppa-ctv-methodology).

Learn more about[ Pixalate's COPPA Compliance Tools here.](https://www.pixalate.com/coppa-compliance-tools)

Disclaimer:

Pixalate’s COPPA Compliance Tools render opinions that Pixalate believes may be useful to our clients and others in the digital media industry. It is important to note, however, that the mere fact that an app appears to be directed to children (e.g., data subjects under 13 years of age, as defined by the COPPA Rule) does not mean that any such app, or its operator, is failing to comply with the COPPA Rule. Further, with respect to apps that appear to be child-directed and have characteristics that, in Pixalate’s opinion, may trigger related privacy obligations and/or risk, such assertions reflect Pixalate’s opinions (i.e., they are neither facts nor guarantees); and, although Pixalate’s methodologies used to render such opinions are derived from a combination of automated processing coupled with significant human intervention, no assurances can be – or are – given by Pixalate with respect to the accuracy of any such opinions.
