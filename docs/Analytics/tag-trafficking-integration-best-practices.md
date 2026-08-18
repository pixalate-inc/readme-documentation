---
title: "Tag Trafficking & Integration Best Practices"
excerpt: "This page provides information on how to traffic and integrate Pixalate's tags."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### Client Responsibilities

  * Provide all the necessary information needed to generate the tag.
  * Traffic the tag following the instructions provided during the Client Onboarding process.
  * Reconcile any issues noted by Pixalate's Solutions team during Quality Assurance (QA) process.

The Pixalate tag only supports IE6 and above. For older versions please make sure the code snippets below are added.

The Pixalate tag also supports both GET and POST methods. For any questions, reach out to your Customer Success representative. 

For HTML5 use:

For HTML4 use:  

---  
  
For iframe use:  

---  
  
IE9/IE10 adds border to any linked images. Most websites have a reset.css file that turns this off: **(img {text-decoration: none; border: 0px}).**

There are two possible solutions:

  * To disable border add this to the styles:

    img {text-decoration: none; border: 0px}  
  
---  
  
  * If border is required, explicitly set the size of the image: ****width="160" height="600"src="<http://placehold.it/160x600>">**

#### Impression Tag Best Practices

Depending on the client, the impression tag can be trafficked through the following ways:

  * Directly on the Publishers site/App 
    * Implement the tag directly on the page/App at the placement level. The tag should be trafficked in the same div as the creative/placement. If that is not possible then it should be as close to the div as possible.

  * In the Publisher SDK 
    * The impression tag should be fired when the creative is loaded. In the case of video, the tag is fired at an impression even level. Depending on the Publisher’s partner SDK the callbacks can be labeled differently to indicate creative load and impression.

  * Ad server Implementation 
    * Every ad server has a field to traffic impression tag. While trafficking the tag please make sure that the correct Tag type is selected (JS/Image/etc.)

#### Begin To Render Best Practices

  * Attempt to ensure that the tag is within the same iframe as the creative. 
    * Failing that, attempt to ensure that the iframe containing the creative follows the same-origin policy with regards to the iframe the creative is in.
    * Failing that, ensure that the iframe containing the creative is of correct standard ad size and that its size matches the same correct standard ad size of its parent iframe.
    * The tag will attempt to determine a valid render state for cross-domain iframes that match IAB-defined ad sizes but due to same-origin policy restrictions, this detection will fail if the iframe loads before the tag does. It is highly recommended not to rely on this detection or if no alternative exists, ensure that the tag loads before rendering the iframe.

  * Ensure that the creative and/or its container is within a tolerable margin of correct standard ad size. 
    * The tag will attempt to match ads that are of improper size, but only within a cumulative (width + height) error of up to 15 pixels (inclusive).
    * Any placement that is larger than 15 pixels off of a correct standard ad size will fail to be detected entirely.

  * In direct placements, ensure that the tag is placed within a common parent of the creative. 
    * Due to the discrete nature of the tag’s detection, it will not detect any elements that are outside of what it detects as the placement’s parent container.

**Warning:** Failing to adhere to the guidelines above may result in lower than anticipated 'Rendered Display Impression' and 'Rendered Impression' metric counts; thus limiting viewability insights in Analytics data-sets.
