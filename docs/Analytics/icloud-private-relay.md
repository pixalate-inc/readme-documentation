---
title: "iCloud Private Relay"
excerpt: "iCloud Private Relay traffic and IVT"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### **What is iCloud Private Relay?**

iCloud Private Relay (iCPR) is a [privacy offering from Apple](https://support.apple.com/en-us/HT212614) that is intended to protect users' privacy by hiding their IP addresses. This is only available to paid subscribers of iCloud+,

Note - HideMyIP is a different (free) feature from Apple which uses the iCloud Private Relay infrastructure and IP ranges, but only obfuscates the client IP address from "known trackers".0

### Why is it important?

When [Pixalate conducted a study](https://www.pixalate.com/blog/icloud-private-relay-ad-fraud-study) of iCloud Private Relay traffic, we described the general findings related to iCPR traffic, and the potential exploit. A [second report in November 2022](https://www.pixalate.com/blog/ip64-ad-fraud-exploit-apple-icloud-private-relay) dove deeper into the suspicious behavior we saw in the traffic, which we dubbed iP64.

### How does Pixalate's Analytics Dashboard help with iCPR?

Pixalate has introduced two features to help analyze your ad traffic.

  1. **New iCPR IVT Type**  
A new iCPR-specific IVT type called “maskediCloudRelayIP” to cover this form of IVT where the declared IP lies in the iCloud Private Relay range, and demonstrates suspicious behavior, including  

     * Traffic originating from an invalid data center IP range;
     * Traffic that has inappropriate device types associated with it, and;
     * Traffic featuring suspicious patterns and associations.  

  2. **New iCPR Report**  
A new iCPR pre-set report in the Analytics dashboard that distinguishes your valid and invalid iCloud Private Relay traffic in one place.

**Impact of maskediCloudRelayIP IVT on total IVT**  
The new “maskediCloudRelayIP” IVT subtype, is a carve out of the "maskedIP" IVT type, and so will not increase the total IVT rate.The overall rate might decrease because we are only marking a subset of the iCPR mismatch traffic as maskediCloudRelayIP IVT, based on demonstrated suspicious behavior.

Note - Even though the total IVT will not significatnly change, the amount of “maskedIP” IVT will decrease proportionally.

**New pre-set report - "iCPR Traffic Report"**

This new report will take all your iOS and MacOS Safari traffic and give you the ability to break it down by domain, seller, iCPR type, and more.

![](https://lh3.googleusercontent.com/2rXxWWFhKp8mdq_bnbQL10rdOFwdJhC3u3-GXXU8jNul4V7lGt5yD6jvpdPcn8RIi7y0GbCKi_Z7aMUdbPDFiAr4nd6rEKqwFZrxQh6-x3fna8QYwbNpzEJf9N2PIEHJGwNTUkNvVhp_qSGBwCMMiL9E6_c46dpFc0ph66DUeQC3FeDZHR-GOU6JEJ2n5g)

_Sample Screenshot_

The dimension “iCPR type” lists all the forms in which iCloud Private Relay IPs have been seen in your traffic with the following possible values:

Declared only | Declared in the bid request to be iCPR, but when checked by Pixalate, found to not be an iCPR IP address  
---|---  
Detected only | Not declared in the bid request to be iCPR, but when checked by Pixalate, found to be an iCPR IP address   
True iCPR | Both declared and detected to be iCPR (Note - this does not automatically mean "free from IVT")  
Non iCloud Relay | Neither declared not detected to be an iCPR IP Address
