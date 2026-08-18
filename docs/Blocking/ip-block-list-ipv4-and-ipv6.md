---
title: "IP Block List (IPv4 and IPv6)"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The IP Block List enable security products to block (or alert on) all communications associated with known bad IP addresses that are related to malicious or compromised devices. The IP reputation is a score from 0.5 to 1 that represents the likelihood a given IP is compromised or performing a malicious activity.

### IP Block List Details

Update Interval: Twice per day (estimated availability 8:00 AM and 8:00 PM UTC)

File Format: CSV

Naming convention in FTP folder: 

  * IPv6: GenericIPv6Blacklisting_YYYYMMDD.csv
  * IPv4: GenericIPBlacklisting_YYYYMMDD.csv

Schema: 

  * IPv4: IP | fraudType | probability (0.5-1)
  * IPv6: IP | IP Type | fraudType | probability (0.5-1)

### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
ip |  STRING |  The IP that has shown suspicious traffic characteristics, is potentially malicious, or is registered as the IP of a data center.  
ipType (IPv6 feed only) |  STRING |  The type associated with the IPv6 address usually denoting their usage and infrastructure.   
fraudType |  STRING |  The mnemonic name that characterizes the type of invalid traffic associated with a given IP (e.g. “datacenter”). Please see [Reported Invalid Traffic (IVT) Types](https://www.pixalate.com/knowledgebase/reported-invalid-traffic-ivt-types) for the full list of invalid traffic types.   
probability |  FLOAT |  A number between 0.5 and 1 that characterizes the likelihood that the given IP is associated with a specific risk type (e.g 0.7 is 70% probability). The higher the probability number, the higher the specific risk.  
  
### IP Block List Best Practices

Below is a list of best practices specific to implementing the IP block list. 

### Probabilities

  * Pixalate purposely classifies the IP Block List with probabilities allowing the client to set their own thresholds based on the quality and scale of their supply inventory. In order for an entry to be included on a block list, it should be associated with a probability of at least 0.5 (as it is calculated by Pixalate’s proprietary machine learning algorithm). However, the determination of threshold is held by the client.

As a generic guideline, Pixalate recommends the following thresholds:

1) Probability equal to 1, for filtering out only the worst offender for blocking (deterministic).  
2) Probability greater than or equal to 0.90 for filtering out users that are fraudulent beyond reasonable doubt.  
3) Probability between 0.75 (inclusive) and 0.90 (exclusive), to filter out users that are associated with clear and convincing evidence that they are fraudulent.  
4) Probability between 0.5 (inclusive) and 0.75 (exclusive), to filter out users that it is more likely than not that they are fraudulent (also known as preponderance of the evidence standard).

  * When making adjustments to the probability threshold, Pixalate highly recommends regular checks-and-balances against impression delivery as lowering the probabilistic threshold can potentially impact the impression count.

### Implementing New Files

  * Do not use the file name to determine the latest file. 
    * The CSV files do not include a time or version in the file name, only a date.
    * The first file available in the day (estimate: 08:00 UTC) would have yesterday's date in the file name.
    * The second file available, released ~12 hrs later (estimate: 20:00 UTC) will have today's date in the file name.
    * Note: The last file uploaded for today will have the same file name as the first file uploaded tomorrow and will replace it.
  * Use the header information to determine the latest file

    curl --silent --head ftp://login:password@ftp.pixalate.com/ipblocklistv2/GenericIPBlacklisting_20180725.csv | grep "Last-Modified"  
  
---  
  
### Blocking X-Forwarded-For IP Addresses

_Most effective against proxy, datacenterProxy, IPObfuscation, MaskedIP IVT Types_

Proxying internet traffic through a server, gateway or peer to peer connection has become an increasingly common phenomenon on the web. However, when the internet protocol was originally designed, there was no standard method implemented to capture all the IP addresses involved in proxied transactions. As a result, a de facto standard has emerged known as “X-Forwarded-For.” The term “X-Forwarded-For” is added to an internet transaction to display the list of all IP Addresses involved in a given transaction.

In the example web transaction below, this browser is using a proxy to reach its destination ([www.pixalate.com](http://www.pixalate.com)). It is using the de facto X-Forwarded-For standard to send both the originating client IP address and the proxy IP address to the destination.

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

Always use the furthest left IP Address in the X-Forwarded-For header (98.37.87.163) as the client IP address in your subsequent transactions. If this IP Address is present on the IP Blocklist, filter the transaction according to your thresholds. When the X-Forwarded-For header is present you should also check all other IP values for inclusion on the IP Blocklist and filter the transaction according to your thresholds - even if the client IP address is “clean”. These proxy IP Addresses when flagged for IVT will most commonly match the proxy IVT type but can be found in other IVT types as well such as datacenterProxy, IPObfuscation and MaskedIP.

#### Case #2 - When the X-Forwarded-For Header is absent

The source IP Address (87.143.57.85) from the transaction should be used in the transaction, matched against the IP Blocklist and filtered according to your thresholds.

#### Case #3 - No access to the HTTP Header

If you are not a direct party to the transaction and do not have access to HTTP header info, you should ensure that your partners are making this information available to you for every transaction in order to make your IP filtration more effective.

**How to approach the last octet missing with respect to IP/DC data feeds**

Questions:

How should the Pixalate IP/DC data feeds be implemented in cases where the passed IP’s 4th octet is missing?

A small portion of IPs included in the IP/DC data feeds have a last octet of zero. How should these IPs be handled?

Answer:

In both cases mentioned, the main objective is to hide the true IP from the downstream partners. In such cases there are few things that can be done:

  * Leverage other data feeds such as deviceId blocklist, App blocklist , etc to block fraudulent traffic. It's possible for a fraudster to mask an IP address by removing the final octet, in which case using another user-based feed like device ID may still successfully block a particular source of IVT based on other associated identifiers that have been flagged.

  * Use frequency capping at IP level for residential IPs.
  * Work with trusted partners and publishers.

Note: The last octet being set as '0' is not alone indicative of invalid traffic. Pixalate recommends that when the last octet is not available to set it as a '0' rather than leaving blank.
