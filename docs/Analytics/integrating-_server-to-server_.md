---
title: "Integrating \"server-to-server"
excerpt: "This section provides information on how to pass data to Pixalate via a \"server-to-server\" integration. The URI for the INGEST function process\u00a0will be provided during the integration process by your Customer Success representative."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please login to access [this page](https://www.pixalate.com/knowledgebase/integrating-server-to-server) with additional information.

### Required Parameters

The following parameters are required and reach out to your Customer Success representative for the parameter name.

**Parameter** | **Description**  
---|---  
Browser Agent |  Browser agent string as provided in the HTTP User-Agent header  
Client ID |  Pixalate supplied client identifier  
Visitor IP Address |  Visitor’s IP address  
Page URI |  The URI of the page  
Session ID |  A unique number for each browser session occurrence that is between 0 and 9,223,372,036,854,775,807 inclusive. This is normally stored as a browser session cookie.  
Session Time |  The UNIX time that the session identifier was created in milliseconds. This is normally stored as a browser session cookie.  
Visitor ID |  A unique number for each browser visitor occurrence that is between 0 and 9,223,372,036,854,775,807 inclusive. This is normally stored as a browser persistent cookie.  
Visitor Time |  The UNIX time that the visitor identifier was created in milliseconds. This is normally stored as a browser persistent cookie.  
Session Identifier | A unique number for each event occurrence that is between 0 and 9,223,372,036,854,775,807 inclusive. This is for InApp only.  
Ad Event Time | Ad Event Time: The UNIX time that the event identifier was created in milliseconds. This is for InApp only.  
Partner ID | Partner identifier: Ask Pixalate for this ID.  
Supply type | Desktop / Mobile_Web / Mobile_InApp / OTT  
  
Please make sure that the Visitor IP address contains a valid visitor’s IP address. Do not supply local or private IP addresses.

### **Required Mobile Parameters**

The following parameters may be added to the required parameters for mobile applications. Please contact your Customer Success representative for the key value parameter. 

**Parameter** | **Description**  
---|---  
Mobile Latitude | The latitude of the user's location, when GPS data is available from a mobile device. Expressed in the format "snn.ddd,snn.ddd" (e.g., +12.345 or -45.123), where South is represented as negative. In order to comply with privacy standards, there can be a maximum of 3 decimal places of precision.  
Mobile Longitude | The longitude of the user's location, when GPS data is available from a mobile device. Expressed in the format "snn.ddd,snn.ddd" (e.g., +12.345 or -45.123), where West is represented as negative. In order to comply with privacy standards, there can be a maximum of 3 decimal places of precision.  
App ID | The identifier for the application requesting the impression. This is useful only for impressions from mobile apps.  
Device ID |  Apple IDA / IFA / Mobile Device ID (Android/iOS/Microsoft)  
  
### **Additional Parameters**

The following parameters can be used as needed:

**Parameter** | **Description**  
---|---  
Click |  Add this parameter to track click  
Conversion | Add this parameter to track conversion  
Page Referrer | URI of page referrer  
Partner ID | Partner identifier  
Publisher ID | Publisher identifier  
Seller ID | Seller identifier  
Site ID | Site identifier  
  
### Optional Parameters

The following parameters are optional:

**Parameter** | **Description**  
---|---  
MD5 | Device MD5  
UDID | Device Open UDID   
ODIN | Device ODIN  
Carrier ID | Carrier ID / Mobile Brand Name  
App Name | App type / App name / SDK versio  
OS | Device OS  
Device Make / Model | Mobile Make/Model  
  
For sample impression, click, and conversion trackers, please contact your Customer Success representative.
