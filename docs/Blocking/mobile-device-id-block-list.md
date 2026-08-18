---
title: "Mobile Device ID Block List"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

A smartphone device ID enables advertisers to individually target towards or against specific devices that correspond to all the major mobile device vendors in the market (i.e. Apple, Google, Windows, and others). This Data Feed contains IDs that have been used for performing some kind of nefarious or malicious activity(ies). This feed enables platforms to avoid serving or bidding on devices that are part of this feed. This feed consists of data collected by Pixalate through its vast network of partners that serve ads on mobile in-app globally. Since there are various types of device identifiers currently in use, Pixalate has included additional columns that show exactly what type of identifier each ID corresponds to (e.g. Apple IDFA, etc) as well as what type of fraudulent activity was initiated behind a given ID. The Device ID probability is a score from 0.5 to 1 that represents the likelihood a given Device ID is compromised or performing a malicious activity.

### Mobile Device ID Block List Details

Update Interval: Twice per day (estimated availability 8:00 AM and 8:00 PM UTC)

File Format: CSV

Naming convention in FTP folder: DeviceIdBlacklist_YYYYMMDD

Schema: deviceID | fraudType | os (ex: Android) | idType (ex: ADID) | probability (0.5-1)

#### Schema Details

**Column Name** |  **Type** |  **Description**  
---|---|---  
deviceID |  STRING |  The device ID that has shown suspicious traffic characteristics or is potentially malicious.  
fraudType |  STRING |  The mnemonic name that characterizes the type of invalid traffic associated with a given device ID (e.g. “datacenter”). Please see Reported Invalid Traffic (IVT) Types for the full list of invalid traffic types.   
os | STRING | The Operating System (OS) name that is associated with a given device ID.  
idType | STRING | The source of the given device ID (e.g. "ADID", "IDFA").   
probability |  FLOAT |  A number between 0.5 and 1 that characterizes the likelihood that the given device ID is associated with a specific risk type (e.g 0.7 is 70% probability). The higher the probability number, the higher the specific risk.  
  
### Mobile Device ID Block List Best Practices

Below is a list of best practices specific to implementing the Device ID block list. Please see Blocking for general best practices that apply to all lists.

### Probabilities

  * Pixalate purposely classifies the Mobile Device ID Block List with probabilities allowing the client to set their own thresholds based on the quality and scale of their supply inventory. In order for an entry to be included on a block list, it should be associated with a probability of at least 0.5 (as it is calculated by Pixalate’s proprietary machine learning algorithm). However, the determination of threshold is held by the client.

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

    curl --silent --head ftp://login:password@ftp.pixalate.com/deviceidblacklistv2/DeviceIdBlacklist_20180725.csv | grep "Last-Modified"  
  
---
