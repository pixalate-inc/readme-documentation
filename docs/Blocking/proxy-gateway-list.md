---
title: "Proxy Gateway List"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The Proxy Gateway feed provides a list of proxies, TOR nodes, and network gateways that malicious users use in order to hide their real IP address. The vast majority of suspicious activities (including botnet distribution and control) take place behind these proxy nodes. In addition, Pixalate’s proxy/gateway detection methodology estimates the number of users behind an IP, in order to better decide if an IP should be blocked without blocking a large subnet from accessing your services. 

Naming convention: Gateways_YYYYMMDD

Schema : IP, user_bucket

**Purpose:** The purpose of Gateway IP list is to surface gateway IP addresses. It contains individual IP addresses associated with the average number of visitors/users behind the IP address.

The CSV format contains where UserBucket has possible values of "2-5", "6-10", "10-20", "20-50" and so on. The interpretation is **lowerbound_upperbound** where for example "2-5" means the average users behind the IP address are between 2 and 5 (inclusive boundaries). Similarly 10-20 means the average users behind the IP address are between 10 and 20.

AVG(users) > 5 AND AVG(users) <= 10 THEN "6-10"  
AVG(users) > 10 AND AVG(users) <= 20 THEN "10-20"  
AVG(users) > 20 AND AVG(users) <= 50 THEN "20-50"  
AVG(users) > 50 AND AVG(users) <= 100 THEN "50-100"  
AVG(users) > 100 AND AVG(users) <= 500 THEN "100-500"  
ELSE "500+"

_Also please note that Gateways will always have more than 1 user_. That is why buckets start from 2 onwards.
