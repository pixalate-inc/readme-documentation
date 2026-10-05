---
title: Trafficking the 1x1 Video Tag
excerpt: >-
  How to insert the Pixalate 1x1 tracking pixel into VAST XML for video
  measurement, plus notes on VPAID.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---
For Pixalate clients and users, please log in to access [this page](https://www.pixalate.com/knowledgebase/trafficking-the-1x1-video-tag) with additional information.

#### Sample VAST Tag with the Pixalate 1x1 tracking pixel for custom platform integrations

The Pixalate 1x1 tracking pixel, which will be provided during the integration process, needs to be injected into the third party impression tag of the VAST XML as shown below:

Acudeo Compatible

![](https://files.readme.io/f3fb3b3db01e7395d3718af2e19bd3af4e9b1bf024d0ee796b2bbfe75ecc6488-Screenshot_2026-10-05_at_5.24.40_PM.png)

<br />

<br />

***

### VPAID

The IAB’s Video Player Ad-Serving Interface Definition (VPAID) establishes a common interface between video players and ad units, enabling a rich interactive in-stream ad experience.

#### Pixalate 1x1 Pixel

Pixalate provides a VPAID compatible 1x1 pixel to track video impressions. Pixalate registers an impression on the client side when the video is loaded on the browser. The Pixalate pixel is capable of ingesting up to 60 different macros out of which up to 30 of them can be custom.

#### Sample VPAID tag within VAST Tag with Pixalate 1x1 (for custom platform integrations)

The Pixalate 1x1 tracking pixel, which will be provided during the integration process, needs to be injected into the third party impression tag of the VAST XML containing the VPAID tag as shown below:

Example Non-Linear VPAID

![](https://files.readme.io/90a5baca358941d753f103ec1cc648a483a5ba1b1aaaf06eae0be6cb040b8865-Screenshot_2026-10-05_at_5.31.02_PM.png)

<br />

NonLinear VPAID JS

![](https://files.readme.io/9225669660847079a78279c978334b099dfa71bc2f89374bf629161936522b69-Screenshot_2026-10-05_at_5.36.51_PM.png)

<br />

***

[http://ryanthompson591.github.io/vpaidExamples/examples/VpaidCallbackAd.js](http://ryanthompson591.github.io/vpaidExamples/examples/VpaidCallbackAd.js)

***

Please see [IAB VAST 4.1 documentation](https://iabtechlab.com/wp-content/uploads/2018/11/VAST4.1-final-Nov-8-2018.pdf) for more information on supporting VAST's standardized macros.

<br />
