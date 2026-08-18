---
title: "Data Center Block List"
excerpt: "Describes the weekly data center IP block list, its CIDR schema and naming convention, and best practices such as checking X-Forwarded-For addresses."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The Datacenter Block List enables security products to block (or alert on) all communications associated with all known data center IP addresses, including IP addresses related to malicious or compromised devices at the data center level.

#### Data Center Block List Details

Update Interval: Once per week (estimated availability Fridays 12:00 AM UTC)

  * Check once every hour on Friday
  * Download only when a new file is available
  * Stop pinging once the new file is found

File Format: CSV

Naming convention in FTP folder: DatacenterSubnetsWeek[WeekNum]. With every new year, the week number in the naming convention will restart from week1. It means that from weeks 1-9, the week number will be a single-digit, and from week 10 and onwards, it will be two digits.

Examples: DatacenterSubnetsWeek1, DatacenterSubnetsWeek2, DatacenterSubnetsWeek10, DatacenterSubnetsWeek11 

Schema: CIDR Range (no header)

#### Data Center List Example

159.8.15.48/28  
---  
31.3.242.48/28  
5.153.35.128/25  
31.3.234.160/29  
148.251.136.0/22  
80.243.179.58/31  
199.167.42.152/31  
199.38.116.243/32  
  
#### Data Center Block List Best Practices

Below is a list of best practices specific to implementing the Data Center block list. 

#### Blocking X-Forwarded-For IP Addresses

_Most effective against proxy, datacenterProxy, IPObfuscation, MaskedIP IVT Types_

Proxying internet traffic through a server, gateway or peer to peer connection has become an increasingly common phenomenon on the web. However, when the internet protocol was initially designed, no standard method was implemented to capture all the IP addresses involved in proxied transactions. As a result, a de facto standard has emerged known as “X-Forwarded-For.” The term “X-Forwarded-For” is added to an internet transaction to display the list of all IP Addresses involved in a given transaction.

In the example web transaction below, this browser is using a proxy to reach its destination ([www.pixalate.com](http://www.pixalate.com/)). It is using the de facto X-Forwarded-For standard to send both the originating client IP address and the proxy IP address to the destination.

    Source: 87.143.57.85  
    Destination: 216.239.32.21  
    ...  
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8  
    Accept-Encoding: gzip, deflate  
    Accept-Language: en-US,en;q=0.8  
    Connection: keep-alive  
    Cookie: km_ai=O%2FgZcPGNRBsRp6jz3Bmb5I0wOTQ%3D; km_lv=x; PRUM_EPISODES=s=1489509030430&r;=http%3A//www.pixalate.com/%23welcome; __atuvc=0%7C31%2C0%7C32%2C0%7C33%2C0%7C34%2C1%7C35; optimizelyEndUserId=oeu1496439449508r0.15055014440449055; _ga=GA1.2.1299395571.1489163698; __ar_v4=DBJXNZQFNRHYZMMXUKUUPQ%3A20170902%3A3%7C4C74BBE5ONGGFOUG745GWA%3A20170902%3A3%7C5BQD2CMYB5DNBF3JWVPUSC%3A20170902%3A3; km_uq=; ajs_group_id=null; ajs_user_id=%22http%3A%2F%2Fidp.pixalate.com%2Fsession%2Fftv%22; ajs_anonymous_id=%224613c846-bbc7-4e5c-922d-96d8707155f4%22; __hstc=90197253.9d31d9eedd1a50bb560b593f98348baa.1487356139030.1505417044047.1505534305589.200; __hssrc=1; hubspotutk=9d31d9eedd1a50bb560b593f98348baa; mp_d0b88c4d966db9e8487b7f58f92ff61f_mixpanel=%7B%22distinct_id%22%3A%20%2215a4e5941536f1-02add994dfea95-1d396853-13c680-15a4e59415464d%22%2C%22%24initial_referrer%22%3A%20%22http%3A%2F%2Fdashboard.pixalate.com%2F%22%2C%22%24initial_referring_domain%22%3A%20%22dashboard.pixalate.com%22%2C%22mp_name_tag%22%3A%20%22ftv%22%7D; kvcd=1505534344315  
    Host: www.pixalate.com  
    Upgrade-Insecure-Requests: 1  
    User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.113 Safari/537.36  
    X-Forwarded-For: 98.37.87.163, 87.143.57.85  
  
---  
  
#### Below is a list of cases on what to do for each scenario

#### Case #1 - When the X-Forwarded-For header exists

Always use the furthest left IP Address in the X-Forwarded-For header (98.37.87.163) as the client IP address in your subsequent transactions. If this IP Address is present on the IP Blocklist, filter the transaction according to your thresholds. When the X-Forwarded-For header is present, you should check all other IP values for inclusion on the IP Blocklist and filter the transaction according to your thresholds - even if the client IP address is “clean”. When flagged for IVT, these proxy IP addresses will most commonly match the proxy IVT type but can be found in other IVT types as well, such as datacenterProxy, IPObfuscation and MaskedIP.

#### Case #2 - When the X-Forwarded-For Header is absent

The source IP Address (87.143.57.85) from the transaction should be used in the transaction, matched against the IP Blocklist and filtered according to your thresholds.

#### Case #3 - No access to the HTTP Header

If you are not a direct party to the transaction and do not have access to HTTP header info, you should ensure that your partners are making this information available to you for every transaction in order to make your IP filtration more effective.
