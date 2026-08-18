---
title: "Reporting Dimensions"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### Dashboard Analytics - Reporting Dimensions/Definitions

**Note:** The table below represents dimensions available and common among basic reports. Specialized reports such as Supply Path Optimization, Compliance, Brand Safety, Geolocation and others have specialized dimensions available. 

Combined dimensions including specialized reports equal roughly 100+ data points available for granular reporting.

**Reporting Dimension** | **Definition**  
---|---  
**Ad Server**  
Advertiser | The advertiser ID associated to measured campaign ad traffic.  
Campaign | The advertising campaign ID associated to measured ad traffic.  
Tag Type | The tag integration type associated to measured Analytics traffic.  
Ad Platform | A third-party network that allows advertisers to publish text, graphics or animated advertisements on the web.  
Ad Size | The size of the placement, measured in pixels.  
Line Item | Line item reporting set/passed at discretion of client, to facilitate reporting on a discrete level.  
Site | The site ID associated to measured campaign ad traffic.  
Publisher | The publisher ID associated to measured campaign ad traffic.  
Creative | The creative ID associated to the advertising creative measured.  
Seller | The seller ID associated to ad traffic, set/passed at an individual client level.  
Traffic Source | The search engine or referring domain from which traffic to your site originated. For example, google (search engine) or [google.com](http://google.com) (domain). Direct traffic, that does not originate from searching-engine results or a referring link in a domain is identified as (direct).  
Site Placement | The site placement ID associated to ad traffic, set/passed at an individual client level.  
Supply Type | The type of inventory/supply (e.g., desktop display, mobile web video, mobile app video, OTT video, etc.), set/passed at a creative/placement level.  
Fraud Type | The fraud types are calculated based on the worst fraudulent activity that each IP has performed globally. This might product cases where click fraud is evident, without the client having implemented any Pixalate click trackers.  
Creative Type | The type of ad creative measured (i.e., display, video).  
Video Play Status | The type of video player configuration/integration (i.e., auto-play, click-to-play, continuous play), set/passed at a creative/video player level.  
IPv6 Type | The type of IPv6 associated to measured ad traffic. Refer to the [IPv6 Types](http://pixalate.atlassian.net/wiki/spaces/CSP/pages/652738591/IPv6+Types) page for additional information.  
**User Location**  
City | The name of the city associated to measured ad traffic at a user level.  
Country Name | The name of the country associated to measured ad traffic at a user level.  
Country Code | Country codes are short alphabetic or numeric geographical codes developed to represent countries and dependent areas, for use in data processing and communications.  
Postal Code | A postal code (known in various countries as a post code, postcode, or ZIP code) is a series of letters and/or digits appended to a postal address for the purpose of sorting mail.  
Region Code | An area or division, esp. part of a country or the world having definable characteristics but not always fixed boundaries.  
DMA | The identified designated market area associated to measured ad traffic at a user level.  
**Device**  
Device Brand Name | The manufacturer or branded name of the device.  
Device Marketing Name | The name of the device model.  
Device Model ID | The model ID associated to the respective device.  
Device Type | The type of device used to interact with the site.  
Operating System | The user's operating system where the ad was served.  
Browser | Also called web browser, is a program with a graphical user interface for displaying HTML files, used to navigate the World Wide Web.  
Device Traffic Type | The traffic breakdown by app or web per device type.  
App ID | The identifier associated to the application measured.  
**Publisher**  
Auto Refresh | Denotes the presence of either site/app or publisher/developer specific automatic-refresh configurations. This is based on client-passed identifiers for purposes of separately reporting such traffic in a manner consistent with the applicable _MRC/IAB Guidelines_.  
Sourced Traffic | Denotes the applicable traffic which has been purchased or acquired as part of routine supply chain transactions. This is based on client-passed identifiers for purposes of separately reporting such traffic in a manner consistent with the _MRC IVT Guidelines_.  
URL | The location of a webpage or file on the internet  
Domain | The core part of a website's URL (its internet address). In the URL "[www.pixalate.com/fraud](http://www.pixalate.com/fraud)", the domain name is "[pixalate.com](http://pixalate.com)".  
True Domain | True Domain is the actual domain the impression was served on regardless of the number of nested iFrames. This is detected by proprietary Pixalate technology and is available 75-85% of all impressions.  
**User**  
Segment | The user segment ID associated to ad traffic, set/passed at an individual client level.  
User ID | A unique sequence of characters used to identify a user.  
Organization | The name of the organization associated to the respective IP address.  
**Time**  
Day | The day of the week when the ad was served.
