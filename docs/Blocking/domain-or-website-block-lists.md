---
title: "Domain or Website Block Lists"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Pixalate has up to five website blocklists that are part of the domain or website intelligence feeds subscription. 

**Domain Data Intelligence Feeds (Domain Blocklists) - SIVT:** The blacklisted domain feeds provide a way to block domains that perform malicious activities. This can include domains that solely spread malware, perform advertisement fraud, serve malicious advertisements that force malware downloads, contain adult content, etc.. The data are generated based on the ad-analytics data collected by Pixalate, as well as data that are collected by the Pixalate crawler and where we assess their IVT probability score as greater than or equal to 60%

Naming convention: FraudBlist_YYYYMMDD.csv

Schema: Domain URL

**Anti-phishing/Malware URL Data Intelligence Feed (Malware/Phishing Blocklist) - SIVT:** The anti-phishing/malware data feed—when updated in real time throughout the day—enables security products to block (or alert on) malicious internet traffic associated with URLs serving malware executables or URLs performing phishing or spear phishing attacks. The feed consists of data collected by the Pixalate’s crawler, as well as data provided by Pixalate’s partners that collectively fight against the dissemination of malware/phishing URLs.

Naming convention: PhishingMalwareBlist_YYYYMMDD.csv

Schema: Domain URL

**Viewability Blocklist:** A blocklist generated from our universal data where viewability is less than 5%

Naming convention: ViewabilityBlist_YYYYMMDD.csv

Schema: Domain URL

**Domain Age Blocklist:** A blocklist of websites where we see the age as less than or equal to 6 months

Naming convention: DomainAgeBlist_YYYYMMDD.csv

Schema: Domain URL

**Brand Safety:** A blocklist of known adult websites

Naming convention: BrandsafetyBlist_YYYYMMDD.csv

Schema: Domain URL
