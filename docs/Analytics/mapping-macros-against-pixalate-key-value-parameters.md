---
title: "Mapping macros against Pixalate Key Value parameters"
excerpt: "The macro mapping process for ad server integrations and the key-value parameters Pixalate tags support in each environment."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please log in to access [this page](https://www.pixalate.com/knowledgebase/mapping-macros-against-pixalate-key-value-parameters) with additional information.

During the integrating process, your Customer Success representative will provide a macro mapping form that needs to be filled out for each ad serving platform. The appropriate ad server macro must be provided then submitted to Pixalate for review. Once macros are finalized, Pixalate will generate and provide tags with the macros already inserted for each parameter.

#### Supported Macro Parameters for Publishers (No AdServer)

Name | **Dashboard Name** | **Definition** | **Recommended / Required**  
---|---|---|---  
**All Environments**  
Pixalate Client ID | N/A | Supplied client identifier | Hard coded by Pixalate  
Platform ID | Ad Platform | ID of the platform or ad server the tags will be implemented in | Hard coded by Pixalate  
Creative size | Ad Unit Size | The width and height of the creative unit. (width x height) | Recommended (Domain, InApp) Required for Viewability measurement.  
**User IP** | _(API Only)_ | Client/user IP address (this should include X-Forward-For client IPs - <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For>) | **Required (domain,InApp)**  
**Auction ID/Impression ID** | _(API Only)_ | Also can be considered an impression ID, in the case of direct page and InApp integration a random unique. number can be generated that can identify each impression. At least 16 characters long (Alphanumeric preferred) | **Required (domain,InApp)**  
**Placement ID*** | Site Placement | Ad server ID of the placement/adslot/tag as implemented on a website. Each placement on a page should have a unique ID. For example, a website with a 300x250 above the fold should have a different placement ID than the a 300x250 below the fold on the same page. | **Required (domain,InApp)**  
Supply Type | Supply Type |  The type of supply generating the impression (Display, Mobile web, Mobile In App) for both Display and Video. This can be passed dynamically or hardcoded in the tag | **Required (domain,InApp)**  
Device OS | _(API Only)_ | Operating System of the device. | Recommended (Domain, InApp)  
User-Agent | _(API Only)_ | User Agent of the device  | Recommended (Domain, InApp)  
Cachebuster | Not Available | Unique alphanumeric value that prevents a browser from reusing a file it has already seen and cached, or saved, to a temporary memory file (or use the IAB VAST 4.1 [CACHEBUSTING] macro where supported). | **Required for JS implementation.**  
**Domain Environment**  
Page URL | URL | Page URL the ad loaded on. | **Required for web (desktop / mobile web)**  
**App Environment**  
**APP ID/Bundle ID** | App ID |  The bundle/app ID that is unique to its relative App Store (iTunes, Google Play). This can also be hardcoded in the tag for direct InApp integration. Example: App ID: 1207472156 (iOS & tvOS), G18012010833 (Samsung smart TV). Bundle ID: com.foxsports.videogo (mobile & CTV) | **Required (InApp)**  
**Device ID** | _(API Only)_ | User Identifier such as UDID, IDFA, WIN ID, AAID, RIDA, AFAI. | **Required (InApp)**  
  
#### Supported Macro Parameters (All)

**Name** | **Dashboard Name** | **Definition** | **Recommended / Required**  
---|---|---|---  
**All Environments**  
Pixalate Client ID | N/A | Supplied client identifier | Hard coded by Pixalate  
Platform ID | Ad Platform | ID of the platform or ad server the tags will be implemented in | Hard coded by Pixalate  
Advertiser ID* | Advertiser | Ad server ID for the top level advertiser/demand partner | Recommended  
Campaign ID* | Campaign | Ad server ID for the campaign (group of tags) provided by an advertiser | Recommended  
Creative ID* | Creative | Ad server ID for the individual demand side creative or tag. | Recommended  
Publisher ID* | Publisher | Ad server ID for the publisher organization that owns a group of websites. This can sometimes be the same as the SellerID if you have a direct relation with the publisher. | Recommended  
Site ID* | Site | Ad server ID for the website. | Recommended  
Line Item ID* | Line Item | Ad server ID for the line item | Recommended  
Bid price | Bid Price | The price that was offered. | Recommended  
Clear Price | _(API Only)_ | The price at which the auction is cleared. | Recommended  
Creative size | Ad Unit Size | The width and height of the creative unit. (width x height) | Recommended  
Page URL | URL | Page URL the ad loaded on. | Required for web (desktop / mobile web)  
User ID | _(API Only)_ | This is an ID that identifies a specific user. This is different than a UDID/IDFA device ID. For example, one might want to pass in here the cookie ID | **Required**  
**User IP** | _(API Only)_ | Client/user IP address (this should include X-Forward-For client IPs - <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For>) | **Required**  
Custom | _(API Only)_ | Reserved for custom values. Data passed for kv5 can be displayed in the Pixalate dashboard.  |   
Seller ID* | Seller | Ad server ID for the organization directly purchasing the inventory through. An SSP for example. | Recommended  
aDomain | _(API Only)_ | The adomain field is used to identify the domain of the advertiser's landing page.  | Recommended  
ISP | _(API Only)_ | Name or ID of the Internet Service Provider | Recommended  
**Auction ID/Impression ID** | _(API Only)_ | Also can be considered an impression ID, this ID is to specify each individual impression or request. Per the IAB's Open RTB V2 guidelines, the auction ID is a required top-level globally unique bid request object attribute (or use the IAB VAST 4.1 [TRANSACTIONID] macro where supported). | **Required (minimum character limit is 16 and alphanumeric value is recommended)**  
**Placement ID*** | Site Placement | Ad server ID of the placement/adslot/tag as implemented on a website. Each placement on a page should have a unique ID. For example, a website with a 300x250 above the fold should have a different placement ID than the a 300x250 below the fold on the same page. | **Required**  
Geographic Region | _(API Only)_ |  Country or Geographic Region of the originating user location | Recommended  
Supply Type | Supply Type |  The type of supply generating the impression (Display, Mobile web, Mobile In App) for both Display and Video. This can be passed dynamically or hardcoded in the tag | Hard coded by Pixalate or can be passed by client macro  
Device OS | _(API Only)_ | Operating System of the device. | Recommended  
User-Agent | _(API Only)_ |  User Agent of the device (or use the IAB VAST 4.1 [DEVICEUA] macro where supported). | Recommended  
Supply chain object | _(API Only)_ | Serialized supply chain object as shown in this [spec page](https://github.com/InteractiveAdvertisingBureau/openrtb/blob/master/supplychainobject.md#supplychain-for-non-openrtb-requests) |  Recommended  
Cachebuster | Not Available | Unique alphanumeric value that prevents a browser from reusing a file it has already seen and cached, or saved, to a temporary memory file (or use the IAB VAST 4.1 [CACHEBUSTING] macro where supported). | Recommended  
SDK User ID | Not Available | Unique user ID assigned by the SDK | Recommended  
IDFV | Not Available | Identifier for Vendor.It is unique ID for all the App running on a given device from one Developer. | Recommended  
"Do not track" indicator | Not Available | A flag to determine if the user set the "do not track" option on their device to true or false (values accepted are "1" for true or "0" for false | Recommended  
**Mobile and CTV Environments**  
MRAID Version | _(API Only)_ | Version of the MRAID API used to deliver the ad (mobile only) | Recommended  
**Latitude** | _(API Only)_ |  Latitude location value of the user if available. | **Required**  
**Longitude** | _(API Only)_ | Longitude location value of the user if available. | **Required**  
**APP ID/Bundle ID** | App ID |  The bundle/app ID that is unique to its relative App Store (iTunes, Google Play). If a separate macro is available for App ID then kv32 will be used for that and kv18 will be reserved for Bundle ID.  Example: App ID: 1207472156 (iOS & tvOS), G18012010833 (Samsung smart TV). Bundle ID: com.foxsports.videogo (mobile & CTV) | **Required**  
**Device ID** | _(API Only)_ | User Identifier such as UDID, IDFA, WIN ID, AAID, RIDA, AFAI. Can be passed through one macro or multiple macros. | **Required**  
Carrier ID | _(API Only)_ | ID of the mobile carrier  | Recommended  
App Name | _(API Only)_ | App Name (separate from app/bundle ID) as listed by the platform or ad server | Recommended  
Device manufacturer/model | _(API Only)_ | The manufacturer and/or model of the device | Recommended  
SSAI Integration | _(API Only)_ | Declares if this impression came from an SSAI integration (0=no, 1=yes) | Recommended  
App version | _(API Only)_ | Version of the app that fired the ad impression | Recommended for mobile  
**Video Environments**  
Video Length | _(API Only)_ | Duration of the video ad.  | Recommended  
Content ID | _(API Only)_ | ID of the video content.  | Recommended  
**Video Play Status** | Video Play Status | Indicates the current state of the player, such as whether or not the video is Auto-Play or Click-to-Play | **Required / Hard coded by Pixalate**  
  
_* IDs which are represented in the ad server. Ad server values must be provided in order to identify and optimize against data as represented in the ad server._

Failing to pass values marked as required may prevent certain Invalid Traffic types from being detected.

#### VAST 4.1 Standardized Macros

The following is a list of IAB VAT 4.1 standardized macros supported by Pixalate. 

For more information about VAST 4.X macros, please see [here](http://interactiveadvertisingbureau.github.io/vast/vast4macros/vast4-macros-latest.html).

This page contains the latest/current list of the "official" macros defined by the IAB Tech Lab's Digital Video Technical Working Group. The purpose of this page is to allow new Macros to be added to the supported list without requiring a new version of VAST to be released. 

**Macro** | **Type** | **Example Value**  
---|---|---  
[ERRORCODE] | integer  | 12345678   
[MEDIAPLAYHEAD] or [ADPLAYHEAD]  | timecode | Encoded: 00%3A05%3A21.123   
[ASSETURI] | string | Encoded:  
https%3A%2F%[2Fmyadserver.com](http://2Fmyadserver.com)%2Fvideo.mp4  
[VASTVERSIONS] | Array | 2,3,5,6,7,8,310  
[IFATYPE] | string  | rida   
[IFA] |  uuid | 123e4567-e89b-12d3-a456-426655440000  
[CLIENTUA] | string  | Encoded: MyPlayer%2F7.1%20MyPlayerVastPlugin%2F1.1.2  
[SERVERUA] | string  | Encoded:  
AdsBot-  
Google%20(%2Bhttp%3A%2F%[2Fwww.google.com](http://2Fwww.google.com)%2Fadsbot.h  
tml)  
[DEVICEUA] | string | Encoded: Mozilla%2F5.0%20(X11%3B%20Linux%20x86_64)%20AppleWe bKit%2F537.36%20(KHTML%2C%20like%20Gecko)%20Chrome% 2F51.0.2704.103%20Safari%2F537.36  
[DEVICEIP] | string  |  IPv4: 8.8.8.8 IPv6 encoded:  
2001%3A0db8%3A85a3%3A0000%3A0000%3A8a2e%3A0370%3A73  
34  
[LATLONG] | number,number | 51.004703,3.754806  
[DOMAIN] | string | [www.mydomain.com](http://www.mydomain.com)  
[PAGEURL] | string | Encoded:  
https%3A%2F%[2Fwww.mydomain.com](http://2Fwww.mydomain.com)%2Farticle%2Fpage  
[VIDEOPLAYSTATUS] |  string |  Indicates the current state of the player, such as whether or not the video is Auto-Play or Click-to-Play  
[PLAYERSIZE] | integer,integer | 640,360   
[REGULATIONS] | Array | gdpr  
[ADTYPE] | string | video   
[TRANSACTIONID] | uuid | 123e4567-e89b-12d3-a456-426655440000  
[BREAKPOSITION] | integer  | 2  
[APPNAME] | string | com.example.myapp  
[PLACEMENTTYPE] | integer | 1  
[AUTOREFRESH] |  string |  Self-reported by publishers for purposes of delineating activity derived from page or site-level auto-refresh.  
[PLAYERSTATE] | string | autoplayed,fullscreen  
Purchased/Acquired Traffic | string | purchased,acquired  
  
#### Supply Chain Object in KV55

The value for the Supply Chain Object (SCO) in serialized form can be passed in "kv55". If kv55 is not already in the tag provided by Pixalate, please add it in as follows

> kv55=[SupplyChainObject]

For examples of Pixalate tags with KV55, please see [this page](https://www.pixalate.com/knowledgebase/mapping-macros-against-pixalate-key-value-parameters#KV55-Tag-Example) with additional information.

For more information about the IAB's OpenRTB SCO specifications, please visit[ this page](https://github.com/InteractiveAdvertisingBureau/openrtb/blob/master/supplychainobject.md).

**  
Format**

  * [SupplyChainObject] should be replaced by a serialized value

The serialization value is composed of two items; 

  *     * The SupplyChainObject properties
    * SupplyChainNode array

These two items are separated by a bang (“!”) character:

> SupplyChainObject}!{SupplyChainNode array}

**Properties**

  * There are two properties: 
    * Version
    * Complete

These two values must be included and separated by ‘,’:

> ver,complete

**Order Of Node Properties**  

  * If there are more than one node then each node is also separated by bang (‘!’) character.

> asi,sid,hp,rid,name,domain,ext

**Example of Multiple Hops with all the properties supplied**

    **"schain" : {**  
      
    **"ver": "1.0",**  
      
    **"complete" : 1,**  
      
    **"nodes" : [**  
      
    **{**  
      
    **"asi":"exchange1.com",**  
      
    **"sid":"1234",**  
      
    **"hp":1,**  
      
    **"rid":"bid-request-1",**  
      
    **"name":"publisher",**  
      
    **"domain":"publisher.com"**  
      
    **},**  
      
    **{**  
      
    **"asi":"exchange2.com",**  
      
    **"sid":"abcd",**  
      
    **"hp":1,**  
      
    **"rid":"bid-request-2",**  
      
    **"name":"intermediary",**  
      
    **"domain":"intermediary.com"**  
      
    **}**  
      
    **]**  
      
    **}**

**Serialized value:**

1.0,1!exchange1.com,1234,1,bid-request-1,publisher,publisher.com!exchange2.com,abcd,1,bid-request2,intermediary,intermediary.com

The last node should be the client’s ID/info and is expected to be added before passing in kv55, if not already in the serialized value.
