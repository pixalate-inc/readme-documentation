---
title: "Blocking for Websites"
excerpt: "How the Pixalate Tag Server intercepts browser ad requests and suppresses them when real-time and historical signals point to non-human traffic."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please login to access [this page](https://www.pixalate.com/knowledgebase/blocking-for-dfp) with additional information.

### Get Started with Pixalate Tag Server

Pixalate Tag Server specifically designed to intercept ad requests from the browser and test them against Pixalate’s proprietary fraud detection system before releasing javascript and HTML code to the browser. If the ad request seems suspicious or fraudulent, the Tag server suppresses the ad request and none of the ads load on the domain. 

### How does it work?

Pixalate’s Tag Server is a real time system that uses both historical and real time data in order to prevent ads from being served to non-humans. This technique is called machine anti-targeting since it aims to target away of machine (i.e. bots, malware, crawlers, etc) visitors in a seamless fashion that does interfere with the user served the ad, and also without introducing any significant delay

In order for the Tag Server to make a decision to serve or not serve the ad requests, historical and real time data are used in order to train an artificial intelligence system that makes serving decision in real time. Some examples of the data points used are:

  * IP address, 

  * UserId, 

  * VisitorId (i.e. cookie), 

  * User Agent string, 

  * Geographical Location, 

  * Frequency of Requests over different time ranges, 

  * Overall traffic characteristics of the given IP (e.g. is it originating from a gateway, public proxy, company network or home router)

### Assumptions

Pixalate will provide a **Client ID** and **Box ID** for use.

### Tagging for DFP

### Page Header Implementation

This implementation requires the least amount of changes on a domains web pages. 

Find the existing google gpt header script block (usually located in the html page header):

Replace the entire GPT script block with the script tag to be provided by Pixalate Ad Ops team. Please contact your Customer Success representative for sample code.

### Testing Implementation

The ef flag has two additional options available for testing an implementation

ef=1 |  Fraud Detection Algorithm (default)  
---|---  
ef=2 |  Testing Blocked Case - This is used to test cases where an impression is determined to be blocked. Forces any code in {?block} tag to be rendered, and any code in {^block} tag to omitted.  
ef=3 |  Testing Not Blocked Case - This is used to test cases where an impression is not blocked. Forces any code in {?block} tag to be omitted, and any code in {^block} tag to rendered.  
  
In addition to the ef flag, we also offer a self service page to perform specific actions on the current IP address.

  1. URL will be provided by your Customer Success representative

  2. Login with your username and password (supplied by Pixalate)

  3. Select from one of the three options.

Selecting any of the available options will perform that specific action on the user’s current IP address as detected by our system, that action will only be valid for 1 hour, after which the IP is returned to its original state.

**Available Options**

Block Me |  Testing Blocked Case - This is used to test cases where an impression is determined to be blocked. Forces any code in {?block} tag to be rendered, and any code in {^block} tag  
---|---  
Unblock Me |  Testing Not Blocked Case - This is used to test cases where an impression is not blocked. Forces any code in {?block} tag to be omitted, and any code in {^block} tag to rendered.  
Whitelist Me |  This will whitelist your IP and bypass the fraud checks.  
  
All options expire after 1 hour, and the IP is reverted back to its original state.
