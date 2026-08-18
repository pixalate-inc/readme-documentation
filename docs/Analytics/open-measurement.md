---
title: "Open Measurement"
excerpt: "Open Measurement & Viewability"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Pixalate's script based viewability measurement includes support for Open Measurement.

Open Measurement is a [standard and an SDK](https://iabtechlab.com/standards/open-measurement-sdk/) developed by IAB Tech Lab, in response to the problem of publishers having to include multiple viewability measurement SDKs to support various advertisers. OMSDK is a trusted, single SDK that publishers can include, and that verification scripts can access for viewability and other signals. 

Pixalate's viewability script checks and prioritizes OMSDK (alongside MRAID and other mechanisms) as it is the most current standard. When OMSDK is not detected, we will default to other available mechanisms. 

FAQs -

1\. How do we take advantage of OM support?

A: There are no changes that need to be made with the tags. The updates are transparent, and we will pick up OM signals where available.

There are also no changes to the viewability report in the Pixalate Analytics Dashboard. OM viewability data will be used in the same manner other signals are used.

2\. Why is OM support useful?

A: Open Measurement has been gaining traction over the last few years, and is considered the main measurement standard. The SDK has been widely deployed. This means that Open measurement support in our scripts will make more inventory measureable. 

3\. What platforms are supported with OM?

A: Mobile platforms (Android, iOS) were the first platforms supported and most widely adopted. OM is now also supported for web and CTV platforms, but the adoption is still not very high. We will be tracking the OM roadmap and making updates as needed.
