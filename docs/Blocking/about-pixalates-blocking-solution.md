---
title: "About Pixalate's Blocking Solution"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Hackers use compromised machines under their control to make profit either through advertising channels, by stealing personal information that can be used to hack user financial accounts, or perform DDOS attacks. Pixalate has spent years integrating with and acquiring data from unparalleled advertising channels as well as many other proprietary and third party sources explained later in the document.

### Pixalate Approach

Pixalate’s unique approach allows us to touch a billion users by gathering data directly from compromised machines and isolate the most malicious IP addresses, Device IDs, Apps and Domains. In addition, we also use traffic patterns from our honeypots that we have set up across the Internet and have access to ghost sites which only a non-humans will visit. Using our proprietary technology, Pixalate is able to determine if the device or machine has been compromised without installing any native code. These are the same devices that end up becoming part of an extensive network of botnets such as Zeus or Zero-Access and are then are used to carry out many malicious and criminal tasks such as stealing advertiser dollars, credit card information, and staging DDOS attacks.

Pixalate advocates a combination of threat intelligence and analytics tags as a best practice. Adding Pixalate’s tag based solution creates a feedback loop that collects intelligence on new fraud attack vectors as they happen.

![](https://f.hubspotusercontent40.net/hubfs/2364596/About_Cube-png.png)

The Data Feeds are comprised of seven separate feeds: IP Block List (IPv4 and IPv6), Datacenter List, UserAgent Block List, Domain Block Lists, Device ID Block List and App ID Block list. These lists make up the most comprehensive real time solution to blocking suspicious traffic at the user, domain and infrastructure levels.

### Block List Implementation

Pixalate's block lists are provided in CSV format and can be downloaded from the provided FTP server location, which allows subscribers to host the list's data on the same programmatic server making delivery decisions to reduce costs and latency. When an ad or bid is requested, check the request's corresponding details reject the request if any request details (IP, device ID, App ID, etc) are on the block list.

### Implementation Best Practices

  * Ping FTP server every hour checking for new file 
    * Example: curl --silent --head
    * Ensures delayed or additional lists are implemented
    * The file should **only** be downloaded if it is new
  * Replace entire file contents (do not append)
  * Support for X-Forwarded-For IPs (where applicable)

### Downloading Block Lists via HTTP/S

Using the WEBDAV propfind command you can get an XML document that contains the complete directory listing with file metadata:

    curl -i -X PROPFIND https://:@ftp.pixalate.com// --upload-file - -H "Depth: 1" <  

    end  
  
---  
  
Once you know the path to the file, download the file:

    curl https://:@ftp.pixalate.com/ ---remote-name  
  
---  
  
An alternative WEBDAV method to try if you are using a Mac is to use the "Go>>Connect to Server" menu in your Mac's Finder menubar and put "<https://ftp.pixalate.com>" into the server address. When prompted, put in the ftp.pixalate.com username and password. This will open the specified user's ftp.pixalate.com directory as a folder on the desktop. You should be able to perform the file transfer by dragging the file out of the window and on to your desktop.
