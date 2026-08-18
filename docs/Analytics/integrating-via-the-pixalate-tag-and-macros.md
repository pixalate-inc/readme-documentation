---
title: "Integrating via the Pixalate tag and macros"
excerpt: "A guide on how to pass data to Pixalate via macros in a URL query string.\u00a0A macro is an ad server's placeholder for a specific value type, placed inside the tag URL query string, that allows an ad server to dynamically insert the desired value."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The Pixalate tag supports both GET and POST methods. For any questions, reach out to your Customer Success representative.

### Generic example instructions on developing/testing macros for two different key parameters.

#### Advertiser ID

  * An advertiser ID key parameter is provided in the Tag (1x1 pixel or JS) URL labeled avid=.
  * After this avid= parameter is a placeholder labeled [ADVERTISER_ID]
  * Replace the [ADVERTISER_ID] placeholder with your ad server's macro for advertiser ID (For this example, lets say the ad server macro is {advertiserId}. The URL should now instead include avid={advertiserId}).
  * Traffic the Tag (1x1 pixel or JS) in the ad server inside the test campaign/creative.
  * Open the browser, run the browser's dev tools or Charles Proxy, and load test page/tag.
  * In the dev tools/proxy, search for Pixalate's pixel URL **(The URL will be provided during the integration process).**
  * Check the URL's query string and confirm the value after avid= is no longer displaying the macro, but rather the expected advertiser ID (such as avid=28374)

#### Device ID (UDID, IDFA, WIN ID, AAID)

  * A Device ID key parameter is provided in the Tag (1x1 pixel or JS) URL labeled kv19=.
  * After this kv19= parameter is a placeholder labeled [DEVICE_ID]
  * Replace the [DEVICE_ID] placeholder with your ad server's macro for device ID (For this example, lets say the ad server macro is {deviceId}. The URL should now instead include kv19={deviceId}).
  * Traffic theTag (1x1 pixel or JS) in the ad server inside the test campaign/creative.
  * Open the test app, run the webview's dev tools (chrome or safari) or Charles Proxy, and load test ID/Page.
  * In the dev tools/proxy, search for Pixalate's pixel URL **(The URL will be provided during the integration process).**
  * Check the URL's query string and confirm the value after kv19= is no longer displaying the macro, but rather the expected Device ID (such as kv19=002ebf12-a125-5ddf-a739-67c3c5d20177)

#### Measuring viewability for the IAB non-standard ad sizes

To measure the viewability for the IAB non-standard ad sizes (e.g. native ads), the client can pass the "div_id" of the ad placement in the Pixalate tag using the parameter "divid=". This can be either hardcoded or passed via a macro.

If the div provided in the tag is not found then the tag will default back to its original method of measuring viewability. If the div_id is hardcoded then please be sure to add the correct div_id in the tag for the IAB non-standard placements so the viewability is measured for the respective ad slot/placement.

If the same div_id is used for all the placements, the Pixalate tag will search for that div_id only and viewability measurement can be misleading. It is recommended to traffic this on a test page first and provide it to Pixalate for QA before pushing to production.
