---
title: "Trafficking the 1x1 Video Tag"
excerpt: "How to insert the Pixalate 1x1 tracking pixel into VAST XML for video measurement, plus notes on VPAID."
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
    			  
    http://demo.tremormedia.com/proddev/vast/vast_inline_linear.xml  
      
    			http://myErrorURL/wrapper/error  
    			{PIXALATE TRACKING PIXEL}  

    							http://myTrackingURL/wrapper/creativeView  
    							http://myTrackingURL/wrapper/start  
    							http://myTrackingURL/wrapper/midpoint  
    							http://myTrackingURL/wrapper/firstQuartile  
    							http://myTrackingURL/wrapper/thirdQuartile  
    							http://myTrackingURL/wrapper/complete  
    							http://myTrackingURL/wrapper/mute  
    							http://myTrackingURL/wrapper/unmute  
    							http://myTrackingURL/wrapper/pause  
    							http://myTrackingURL/wrapper/resume  
    							http://myTrackingURL/wrapper/fullscreen  

    							http://myTrackingURL/wrapper/click  

---  
  
### VPAID

The IAB’s Video Player Ad-Serving Interface Definition (VPAID) establishes a common interface between video players and ad units, enabling a rich interactive in-stream ad experience.

#### Pixalate 1x1 Pixel

Pixalate provides a VPAID compatible 1x1 pixel to track video impressions. Pixalate registers an impression on the client side when the video is loaded on the browser. The Pixalate pixel is capable of ingesting up to 60 different macros out of which up to 30 of them can be custom.

#### Sample VPAID tag within VAST Tag with Pixalate 1x1 (for custom platform integrations)

The Pixalate 1x1 tracking pixel, which will be provided during the integration process, needs to be injected into the third party impression tag of the VAST XML containing the VPAID tag as shown below:

Example Non-Linear VPAID

    	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="vast.xsd" version="3.0">  

    			NonLinear VPAID JS  
    			Vpaid Linear Video Ad  
    			http://www.example.com/error  
    			{PIXALATE TRACKING PIXEL}  

    							http://www.example.com/start  
    							http://www.example.com/firstQuartile  
    							http://www.example.com/midpoint  
    							http://www.example.com/thirdQuartile  
    							http://www.example.com/complete  
    							http://www.example.com/mute  
    							http://www.example.com/rewind  
    							http://www.example.com/pause  
    							http://www.example.com/resume  
    							http://www.example.com/fullscreen  
    							http://www.example.com/creativeView  
    							http://www.example.com/acceptInvitation  

---  
  
Example Linear VPAID

    	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="vast.xsd" version="3.0">  

    			GDFP  
    			Linear VPAID  
    			Vpaid Linear Video Ad  
    			http://www.example.com/error  
    			{PIXALATE TRACKING PIXEL}  

    						00:00:13  
    						  
    							http://www.example.com/start  
    							http://www.example.com/firstQuartile  
    							http://www.example.com/midpoint  
    							http://www.example.com/thirdQuartile  
    							http://www.example.com/complete  
    							http://www.example.com/mute  
    							http://www.example.com/unmute  
    							http://www.example.com/rewind  
    							http://www.example.com/pause  
    							http://www.example.com/resume  
    							http://www.example.com/fullscreen  
    							http://www.example.com/creativeView  
    							http://www.example.com/acceptInvitation  

    							http://wikipedia.com  
    							http://www.example.com/click  

    http://ryanthompson591.github.io/vpaidExamples/examples/VpaidCallbackAd.js  

---  
  
Example of VAST XML Response

    			Column6  
    			Column6  
    			Column6  

    						00:00:20  

---  
  
Please see [IAB VAST 4.1 documentation](https://iabtechlab.com/wp-content/uploads/2018/11/VAST4.1-final-Nov-8-2018.pdf) for more information on supporting VAST's standardized macros.
