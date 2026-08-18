---
title: "COPPA Mobile App Data Dictionary"
excerpt: "Information about the data points used within our COPPA compliance tools & methodology"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The following data points are featured within the COPPA section of the Media Ratings Terminal for mobile apps, Analytics Compliance reports for mobile apps, and associated APIs - with consideration of paid product subscription access & permissions. Each of these data points are relevant to our COPPA insights, and further explained within our methodology.

**Field Name** |  **Definition** |  **Expected/Sample Result**  
---|---|---  
COPPA Audience - Mobile Apps |  Assesses the likely intended audience of an app based on a variety of factors including app store categories, content ratings, and keywords, etc. according to Pixalate’s methodology |  Likely Child Directed including mixed audiences, or Likely General Audience  
COPPA Audience Reason Code |  Describes the specific variables considered when making the audience assessment |  “This app is likely child-directed because…   
iOS, Content Rating |  Pixalate's term Content Rating for Apple refers to their "Age Rating". According to the [Apple developer website](https://help.apple.com/app-store-connect/#/dev599d50efb), “An age rating is a required app information property used by the parental controls on the App Store.” |  See [App Store age rating](https://help.apple.com/app-store-connect/#/dev269f11291).  
Google, Content Rating |  Pixalate’s term Content Rating for Google refers to the content ratings provided by the Google Play Store. Google explains that, “Ratings are the responsibility of the app developers and the International Age Rating Coalition (IARC).”  |  See [Apps & Games content ratings on Google Play](https://support.google.com/googleplay/answer/6209544?hl=en).   
Store Category |  The associated category of an app according to the Google Play Store & Apple’s App Store. There can be multiple assigned to one app. |  “Application, Education”, or  “Entertainment”, or “Games, Casual” etc.   
Store Subcategory |  The associated subcategory from Google Play Store & Apple’s App Store. There can be multiple assigned to one app. |  “Music”, or “Family Ages 9 & Up”, or “Sports”  
Google Teacher Approved |  Google Play’s [program](https://play.google.com/console/about/teacherapproved/) in which apps are evaluated by teachers and other specialists and for age and content appropriateness.  |  Yes or No  
COPPA Risk Rating - Mobile Apps |  Pixalate analyzes multiple signals and produces a risk score (low, medium, or high) that captures the potential COPPA risk. See chart below. |  High, medium, low  
COPPA Risk Rating Reason Code |  Describes the specific variables considered when making the overall COPPA risk rating assessment |  “The COPPA risk is high because the app…”   
Privacy Policy Detected |  Pixlate determines whether an app has a privacy policy based on information provided in the app stores. Additionally, Pixalate uses crawlers to scan developer websites for privacy policies. |  Yes or No  
Sensitive Permissions:  |  Detects mobile device permissions granted to the app such as camera, microphone, contacts, etc. which allow for sensitive personal information collection |  Yes or No  
Transmits Residential IP |  Pixalate examines the traffic associated with an app and determines if the end-user IP is transmitted through the advertising pipeline that can expose granular information about the user’s location. |  Yes or No  
Passes Location |  Pixalate examines the traffic associated with an app and determines if the end-users’ GPS coordinates are being transmitted through the advertising pipeline that exposes granular information about the user’s location |  Yes or No  
Permission |  Lists the device permissions granted to the app, reports those considered sensitive permissions related to COPPA |  Lists the permissions by name, e.g. “RECORD_AUDIO”  
Description |  Text which describes the mobile app permission indicated |  e.g. “Allows an application to record audio.”  
  
Learn more about these data points & our[ methodology here](https://www.pixalate.com/coppa-compliance-tools-methodology).

* * *

### **App Store Content Category Information:**

Pixalate uses app store categories, not IAB categories, as part of its assessment of the likely intended audience.  

  *     * IAB categories are available in the Media Ratings Terminal, the Analytics reports, and our free app search tool as an additional or alternative filter to sort and find apps’. 

#### **Google Play Store Content Categories**

Google Play organizes apps into various genres, including “Application”, “Games”, and “Family”. Developers can assign a category and add ‘keys’ to their apps indicating the type of content or purpose of the app. 

**Applications** are categorized as:

_Auto & Vehicles, Beauty, Books & Reference, Business, Comics, Communication, Dating, _**_Education,_**_**Entertainment** , Events, Finance, Food & Drink, Health & Fitness, House & Home, Lifestyle, Maps & Navigation, Medical, Music & Audio, News & Magazines, Parenting, Personalization, Photography, Productivity, Shopping, Social, Sports, Tools, Travel & Local, Video Players & Editors, Weather, Libraries & Demo_

  * Pixalate’s COPPA methodology analyzes all apps in the **Education** and **Entertainment** categories for additional indicators that it is child directed by either keywords in the description or the presence of family subcategories.

**Games** are categorized as: 

_Arcade, Puzzle, Cards, Casual, Racing, Sport Games, Action, Adventure, Board, Casino, Educational, Music Games, Role Playing, Simulation, Strategy, Trivia, Word Games_

  * Pixalate’s COPPA methodology looks at every app within the “Games” category for additional indicators that it is child directed, either keywords in the description or the presence of family subcategories.

**Applications and Games** can also be designated with the category key “Family”, where a Game or an Application is identified by the developer as intended for Family use, and indicated for specific age appropriateness. Pixalate considers all apps which carry the key “Family” as likely child-directed. The Family genre, or key, consists of app age ratings to help users find appropriate applications & games: 

_Family All Ages, Family Ages 5 & Under, Family Ages 6-8, Family Ages 9 & Up, Family Action, Family Brain Games, Family Create, Family Education, Family Music & Video, Family Pretend Play_

  * Note, some **Games** may not be designated with the additional Family subfilter, but could still be considered likely intended for children if the app description contains child-directed keywords. 

Here are some examples as to how the Media Ratings Terminal COPPA module will display the “Store Category” and “Store SubCategory”:

**Example A:**

If “Application” → “Education” → “Family”: _Family Ages 6-8_

Category = “Application”, “Family”

Subcategory = “Education”, “Family Ages 6-8”

**Example B:**

If “Games” → “Casual” → “Family”: “ _Family Music & Video”_

Category = “Games”, “Family”

Subcategory = “Casual”, “Family Music & Video”

**Example C:**

If “Games” → “Role Playing” → “null” (Family key is not identified)

Category = Games

Subcategory = Role Playing

#### **Apple App Store Content Categories**

Pixalate’s methodology uses the **Kids** category and the **Family** subcategory as an indicator that an app is likely child-directed. Pixalate also evaluates any apps within the **Games** and **Entertainment** categories or subcategories for additional indicators, like content ratings and child keywords, as indicators that an app is likely child-directed.

* * *

#### **Age Ratings**

Age Ratings applicable to Pixalate’s COPPA methodology include:

**Device Type** | ***Age Rating**  
---|---  
[Android](https://support.google.com/googleplay/answer/6209544?hl=en) |  North and South America (ESRB) - Everyone 10+, Everyone Europe and Middle East (PEGI) - PEGI 3+, PEGI 7+,  Germany (USK) - USK: All ages, USK: Ages 6+,  Australia (ACB) - General, Parental Guidance  Brazil (ClassInd) - All ages, Rated 10+ South Korea (GRAC): Rated for 7+, Rated for 3+   
[iOS](https://apps.apple.com/kh/story/id1440847896) | +4, +9  
  
* * *

#### **Sensitive Data Permissions**

Sensitive Data Permissions applicable to Pixalate’s COPPA methodology include:

**Device Type** |  **Permission Name** |  **Description**  
---|---|---  
Android |  Camera |  Allows App To Take Video  
Android |  Callphone |  Allows App to Make Phone Calls  
Android |  Add_voicemail |  Allows App To Have Access to Voicemail  
Android |  Read_calendar |  Allows App Access to your Calendar and Data within Calendar  
Android |  Read_call_log |  Allows App Access to your Call Logs  
Android |  Read_contacts |  Allows App Access to Your Contacts and information included (PII)  
Android |  Access_fine_location |  Allows App Access to GPS coordinates  
Android |  Access_background_location |  Allows App Access to your location as it operates in the background  
Android |  Read_phone_numbers |  Allows read access to the device's phone number  
Android |  Read_phone_state |  Allows read only access to phone state, including the phone number of the device, current cellular network info  
Android |  Read_sms |  Allows an application to read SMS messages.  
Android |  Read_voicemail |  Allows an application to read voicemails in the system.  
Android |  Access_coarse_location |  Allows an app to access an approximate location.  
iOS |  NSCameraUsageDescription |  Allows App To Take Video  
iOS |  NSLocationWhenInUseUsageDescription |  Allows an app to approximate location.  
iOS |  NSLocationAlwaysUsageDescription |  Allows an app to access location at all times.  
iOS |  NSMicrophoneUsageDescription |  Allows an app to access the device’s microphone.  
iOS |  NSCalendarsUsageDescription |  Allows App Access to your Calendar and Data within Calendar  
  
Find out more about Pixalate's COPPA[ Methodology here.](https://www.pixalate.com/coppa-compliance-tools-methodology)

Learn more about [Pixalate's COPPA Compliance Tools here.](https://www.pixalate.com/coppa-compliance-tools)

Disclaimer:

Pixalate’s COPPA Compliance Tools render opinions that Pixalate believes may be useful to our clients and others in the digital media industry. It is important to note, however, that the mere fact that an app appears to be directed to children (e.g., data subjects under 13 years of age, as defined by the COPPA Rule) does not mean that any such app, or its operator, is failing to comply with the COPPA Rule. Further, with respect to apps that appear to be child-directed and have characteristics that, in Pixalate’s opinion, may trigger related privacy obligations and/or risk, such assertions reflect Pixalate’s opinions (i.e., they are neither facts nor guarantees); and, although Pixalate’s methodologies used to render such opinions are derived from a combination of automated processing coupled with significant human intervention, no assurances can be – or are – given by Pixalate with respect to the accuracy of any such opinions.
