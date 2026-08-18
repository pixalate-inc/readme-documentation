---
title: "Direct Mobile SDK Implementation"
excerpt: "The following documentation outlines the steps to integration Pixalate's 1x1 pixel tags as impression event callbacks for mobile app publishers that do not currently use an ad server for ad delivery management."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The following documentation outlines the steps to integration Pixalate's 1x1 pixel tags as impression event callbacks for mobile app publishers that do not currently use an ad server for ad delivery management. 

For Pixalate clients and users, please login to access [this page](https://www.pixalate.com/knowledgebase/direct-mobile-sdk-implementation) with additional information.

#### Integration Details

  1. Identify the SDKs implemented within the application that will be returning advertisements. 
  2. Review each SDKs documentation for the supported events where callbacks can be implemented. 
  3. Establish which event would fire at the ad impression, or closest to as possible, for each SDK. 
     1. An Impression is defined by the IAB as "a measurement recorded at a point as late as possible in the process of delivery of the creative material to the user's browser — therefore closest to actual opportunity to see by the user."
     2. The ad should be fully rendered and on screen (or available to be scrolled to if loaded below the fold) at the point when an impression is counted. 
  4. Implement a callback to the impression event which will load a network request to Pixalate's 1x1 Tag (example sample tag below) with all applicable data points populated in the query string. 

#### Required Data Points

Pixalate requires numerous data point values to be dynamically populated and sent within the 1x1 pixel tag's query string. Below is a list of those data points required for direct mobile SDK integrations and the parameter key assigned for each. Please contact your Customer Success representative for the specific parameters. 

  * Ad Size: Creative size (width x height)

  * IP: IP of the user

  * Auction/Impression ID: Random ID that is unique per impression.

  * Placement ID: ID for each ad slot on a given page or screen. Each ad slot on the page/screen must be unique.

  * Latitude: Latitude location value of the user if available.

  * Longitude: Longitude location value of the user if available.

  * App/BundeID: Play or iTunes store ID

  * Device ID: User Identifier such as IFA, Advertising ID, etc.

  * Supply Type: Type of the supply environment, in this case 'Mobile_InApp' or 'Mobile_InApp_Video'

  * OS: Operating System

  * User Agent: User Agent of the device.

  * All relevant demand side IDs:

    * Use these parameters for demand identifiers if the impression event callback provides creative/demand side information.

    * It is important to capture demand side identifiers to monitor or investigate any demand side inquiries into IVT

#### Next Steps

  1. Start the integration with 1 app (or one placement within 1 app) in a non live test environment.

  2. Remove any placeholders with square brackets within the tag of parameters that will not be populating any values.
  3. Send over a test environment (Xcode project, APK, etc) to your customer success representative for the Pixalate team to review.
  4. Once Pixalate confirms a successful SDK integration, set the integration live on one app (or one placement within the app).
  5. Once 10,000 impressions have registered, Pixalate will be begin a data QA to ensure the values provided in the tag are populating correctly.
  6. Once both QAs are complete, you can start replicating the integration across the other apps and SDK networks.

No data will be captured with the sample tag until a client & platform ID is assigned and provided by Pixalate.
