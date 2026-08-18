---
title: "Over-The-Top\" vs. Connected TV Reporting"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

**What is OTT? What is CTV? How does Pixalate define OTT and CTV?**

At Pixalate, we monitor OTT advertising based on the device where the ad was shown. There are differences between content and the devices they are played on. Our definitions generally follow the same as those defined by the IAB Tech Lab [in their CTV vs. OTT definitions.](https://iabtechlab.com/blog/ott-vs-ctv-what-is-in-a-name/)

  * **OTT:** OTT stands for “over-the-top,” and it refers to the ability for users to access TV content without a regular TV set-top box. In OTT, content is delivered via an internet connection rather than through a traditional cable/broadcast provider.

  * **OTT content** : Content that can be consumed across multiple devices, including desktops, laptops, mobile devices, and CTV devices. An example is watching Sling TV on your smartphone. This is OTT content but _not_ on a CTV device — therefore, Pixalate would categorize this as mobile.
  * **CTV device** : Any device that is not desktop, laptop, or mobile but is used to consume OTT content. Examples include Smart TVs, Apple TVs, Chromecast, PlayStation, Xbox, Amazon Fire sticks, and other streaming devices. For example, if you watch Sling TV on your Apple TV, we’d categorize it as CTV.
  * In general, we try to avoid using the term "OTT device" because of the confusion that it could cause as seen by the above definitions.

Note - In cases of crossover — i.e. using an Apple TV to mirror your laptop while watching OTT content — we still rely on the device on which the ad was served (in this example, the laptop).

In some cases, streaming devices (such as Chromecast) have specific integrations with apps that are used to consume OTT content. For example, if you are watching YouTube on your laptop and press the “Cast” button to send the content to your Chromecast, then the Chromecast becomes the primary device, and any ads served would be categorized as a CTV device by Pixalate.

Pixalate also categorizes Smart TVs, sometimes referred to as Connected TV, as CTV devices.

The dynamic, growing OTT landscape can be confusing, but Pixalate keeps it simple by categorizing OTT ad inventory based solely on the device on which our measurement tags are fired.

**How does Pixalate distinguish between OTT and CTV?**

The difference here is CTV generally refers to the **device** that is connected to the internet. It could be either a TV with internet capabilities or a device that connects to the internet and uses a TV to display content. OTT refers to **content** delivered through the internet. However, OTT content can also be delivered to mobile devices and browsers. 

**What are the most popular CTV device types?**

Roku devices are by far the most common. After Roku, Amazon, Google, Apple, Vizio, LG, and Sony generally round out the list. We detect hundreds of CTV device types across over 57+ million unique devices each month.

**Is Pixalate Accredited for OTT / CTV?**

Yes, Pixalate is currently MRC accredited for OTT / CTV in the following areas:  
\- Display Served Impressions  
\- Video Served Impressions  
\- SIVT detection and filtration for both Display and Video Impressions

**What is server-side ad insertion (SSAI)?**

Server-side ad insertion (SSAI) — also known as “dynamic ad insertion” or “ad stitching” — is the process of delivering an ad from the server-side. Traditionally, video content comes from a content delivery network (CDN) on the server-side, while video ads come from a third-party ad server on the client-side. SSAI allows video providers to “stitch” the content and the ads together (both from the server-side) for a more seamless user experience.

However, impressions are typically tracked on the client-side. There is usually a tracking pixel included in the creative so that when the creative renders, so does the tracking pixel, which results in 1-to-1 counting only when the creative is rendered.

The challenge with SSAI is that it makes measurement and tracking more complex (depending on the exact implementation architecture) by outsourcing certain client-level functionality to the proxy server (e.g. firing the tracking pixels on behalf of the client). Additionally, when SSAI takes place, the standard HTTP headers used to identify a client (e.g. IP address and User Agent string) will correspond to the proxy server instead, and additional (currently optional) headers are needed in order to pass all the information for the user to any third party measurement entity.

**Are there legitimate use cases for SSAI?**

Yes. Video content providers may choose to utilize SSAI to create a more seamless user experience.

One of the promises of CTV is that it can replace the traditional TV viewing experience. However, if CTV ads are always buffering, then CTV isn’t living up to that promise, and consumers may move back to traditional TV for a better user experience. SSAI aims to solve that challenge by ensuring that the video content and the video ads are served without interruption.

**Can SSAI be used by ad fraudsters?**

Yes. Fraudsters know how SSAI looks in reporting data, and they use this fact to their advantage. One of the most accessible ways to change an IP address is via proxy servers. Mismatched IPs have traditionally been seen as a risk factor, but in the OTT/CTV space, there is a legitimate reason (SSAI). Fraudsters use SSAI to hide their real intentions, and they know that advertisers will look the other way because SSAI is accepted in the OTT/CTV industry.

Fraudsters hide behind SSAI to spoof or fake inventory by altering the information contained in the ad request. Because the ad request information comes from a proxy, it is difficult to verify if the information passed is legitimate.

**How does Pixalate detect SSAI?**

Depending on the exact SSAI architecture used, it is possible that the whole user activity is represented and communicated to third party measurement companies by an SSAI proxy server that is responsible for composing HTTP requests on behalf of the end-user seeing the ad content. This opens a big security backdoor to fraudsters and allows them to use machines that act like proxies and spoof the user request headers by faking all the associated HTTP header fields (i.e. X-Forwarded-For, X-Device-User-Agent, Forwarded HTTP extension etc), thus making SSAI detection that purely relies on X-Forwarded-For headers extremely error prone. 

However, since the industry is very far from providing a concrete and deterministic solution to the above problem, Pixalate has taken the initiative to be the leading innovator in the above space and develop algorithms that can differentiate between real and fake SSAI and estimate the overall reputation of a given SSAI server. To do this, Pixalate has created and extensively analyzed more than 30 composite signals that characterize the overall behavior of an SSAI server and its interactions with the publisher (e.g. apps) and the client (e.g. deviceID) and therefore is able to determine if an SSAI proxy generates valid or invalid traffic.

**Does Pixalate consider SSAI invalid traffic (IVT)?**

It depends on each individual transaction because SSAI is used for legitimate and fraudulent purposes.

When Pixalate detects SSAI, we take an additional step to determine if it’s invalid traffic or not. Specifically, Pixalate has created and extensively analyzed more than 30 composite signals that characterize the overall behavior of an SSAI proxy and its interactions with the publisher (e.g. apps) and the client (e.g. deviceID) and therefore is able to determine if an SSAI proxy generates valid or invalid traffic.

**What are some of the common fraud types seen in OTT / CTV?**

Ad fraud in OTT / CTV takes on several forms, but among the most common we see include:

  * Proxy IVT

Proxy IVT is when we detect SSAI that is invalid. For example, if the client’s IP doesn’t match the IP detected when the ad is rendered and if the proxy IP is determined to be invalid, then the traffic is flagged as Proxy IVT.

  * Video Impression Fraud

Video Impression Fraud is when we detect statistically significant outlier user behavior. Video Impression Fraud can occur on any device, including CTV. Pixalate’s algorithms and machine-learning models are used to detect anomalous behavior.

  * Data center

Data center traffic is any traffic with an IP address that is identified as a data center. For example, hundreds of jailbroken CTV devices can be set up to continually play content on a specific app or group of apps.

  * IP Obfuscation

IP obfuscation occurs when a proxy IP is discovered, but there exists a cookie that extends to a statistically significant inflated number of unique device IDs or IPs. This could be a sign that a fraudster is using a desktop device masquerading as a CTV device.

  * App Spoofing

Device behind traffic from apps that appear to be spoofed either at the impression level or at more macroscopic levels.

**What Products does Pixalate offer for OTT / CTV?**

  1. Blocking: Pixalate pre-bid Blocking solution protects our clients from threats in the OTT / CTV ecosystem Blocklists that cover OTT include:

  * Global CTV Device ID blocklist
  * Global IPv6 blocklist

Pixalate is also planning to launch a CTV-specific high risk app blocklist, as well as a CTV Delisted apps blocklist that will include additional information for marketers seeking to protect their growing OTT / CTV budgets.

2\. Analytics: Pixalate offers detection and monitoring of CTV IVT through our Analytics dashboard.
