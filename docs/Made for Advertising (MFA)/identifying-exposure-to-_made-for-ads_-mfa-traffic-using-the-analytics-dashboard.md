---
title: "Identifying exposure to \"Made For Ads\" (MFA) traffic using the Analytics Dashboard"
excerpt: "How can I use the Analytics Dashboard to combat MFA Inventory?"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Pixalate has updated the Analytics Dashboard with reports for MFA websites. These features are available to all Analytics Dashboard subscribers as a beta program. With these reports, a user can identify traffic that has been labeled with an MFA risk, ranging from low to high, and see the impact on overall performance. 

For a full description of Pixalate's methodology and MFA solutions, please see [here](https://www.pixalate.com/knowledgebase/pixalate-mfa-detection-product-overview) and for all MFA related definitions, see [here](https://www.pixalate.com/knowledgebase/mfa-made-for-advertising-definitions). From these reports, a number of actions can be taken, including blocking certain supply, working with the publisher or increasing spend where MFA risk is low. 

**Domain Data Set**

Although the number of websites marked as MFA makes up 2% of all websites, the global ad spend tied to MFA sites makes up 9%, per Pixalate's Q1 2024 MFA Websites Report. The MFA Analytics report allows clients to view their web/domain traffic by MFA Risk levels, as well as by the various MFA metrics. These MFA metrics can be broken down individually or in combination to yield a custom list of domains that a user wishes to act on. Additionally, other metrics, such as IVT, can be leveraged for further insights. 

**View the MFA Domains Report and Sort by Default Values**

This provides a snapshot of total traffic accompanied by the amount of MFA impressions and MFA Traffic rate, so a user has a better understanding of current impact. Should any spikes in MFA traffic occur, this day over day view can pinpoint when that occurred and what/if new supply was introduced. 

**![Screen Shot 2024-05-23 at 3.02.17 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.02.17%20PM.png)**

![Screen Shot 2024-05-23 at 3.02.58 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.02.58%20PM.png)

![](https://lh7-us.googleusercontent.com/wYdmmZz11kwRxnF4KcIDtkreK7INd-zikZqAyuavtI5-vTrpkavHUhMyGGzwjt8_jmsyDm9a2HARPNIzU305wRk64iGVmd7rkLog6rzagXqrgxuaCi0JzAxFwN89Egcfo9iHhTm397-3sJa2vk2_XBg)

  * By sorting by MFA risk from high to low, you are given an immediate list of the top outlier sites with MFA risk. If you are concerned with the source coming from either social or paid traffic, these columns would be helpful to sort by as well. With the domains that meet upper quantile performance, a user can decide to block that site or the publisher altogether. Additionally, a user can leverage this data to work with a supply source and improve areas such as omitting certain sources of traffic.
  * If you're concerned with user experience and how a web page is operating its ad placements, a user can sort by Ad Density and Ad Refresh Rate. By focusing on the worst offenders, you can take this data to sellers and/or publishers to work on either decreasing the ad placement activity or blocking the site due to continued poor user experience. If there is an ad refresh limit in place based on the partnership, then this data can be used for potential clawbacks as well. 

**Filter by MFA Dimensions/Metrics & Adding Other Metrics**

![Screen Shot 2024-05-23 at 3.15.34 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.15.34%20PM.png)

![Screen Shot 2024-05-23 at 3.24.19 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.24.19%20PM.png)

![Screen Shot 2024-05-23 at 3.27.44 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.27.44%20PM.png)

  * By layering different MFA related dimensions and metrics, a user can create a custom allow or block list based on the thresholds input. This can allow for a more nuanced method of blocking based on post bid data. Note, without touching any IVT related metrics/dimensions, the score increased as scope was tightened to medium MFA risk and ad density of greater than 3. Pixalate's 2024 research shows there's a 23% higher risk of invalid traffic (IVT), including ad fraud, on MFA websites compared to non-MFA websites.
  * Introducing specific fraud types can help identify overlap with MFA and fraudulent activity as well. For instance, if a site demonstrated high ad density and high ad refresh rate AND was also being flagged for display impression fraud, a buyer may infer that the two behaviors are possibly correlated. This will not always be the case, but in this situation, there's signals pointing to ad placement saturation and possibly background or non viewable ads, which warrant clawbacks. 
  * If you'd like to flip the view to the demand side to track how advertisers and campaigns are exposed to MFA sites, these dimensions can be added as well. This is helpful to monitoring performance at a more granular level for the buy side. In addition, reports can be saved and scheduled to keep different partnerships separate. On that note, if different buyers have varying thresholds for MFA risk, this can help to monitor different quality levels of inventory by demand preferences. 

**Splice the Data by a Specific Publisher or Seller**

**![Screen Shot 2024-05-23 at 3.32.17 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.32.17%20PM.png)**

**![Screen Shot 2024-05-23 at 3.33.54 PM](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screen%20Shot%202024-05-23%20at%203.33.54%20PM.png)**

  * By isolating a specific seller, this exposes an overall MFA health tied to that supply source. Instead of blocking altogether, a user can reference this post bid data to make note of sites that do not meet expectations when considering MFA. With the exported report, you can claim which sites are in the high performing range for MFA risk and deem which impressions are billable vs not. By referencing specific data points, such as an ad refresh rate of 48, this will help bolster an argument for why this traffic is devalued.
  * Publishers can own/create a wide array of sites and that number is growing every day, which makes monitoring a tricky situation. Based on Q1 2024 data, one root domain ([iwastesomuchmoney.com](http://www.iwastesomuchmoney.com/reflect/why-these-dog-breeds-may-be-the-best-fit-for-seniors/?utm_source=fc&utm_campaign=120206067612440523-120206067613230523-fc&utm_medium=dbg-all-w3-c-sv2-app.0-240306-im-fc-e5_adgroup-fc&utm_content=120206067615010523-fc&utm_term=120206067613230523&fbclid=PAAaaaYux9j4zVJh2f9bWEg9nfnjLsv2NJ9n4P8Kb84QVNZlzT2_nCxfVPfM4_aem_AZne8S-WBj5kS8stu6OkJ4PTW-WX_EcVBI7DMmyIGcCyi9wbPYaNVa0Ci6uHxZrrKvHLzbCl2bEsX07Xgxw9BDu8)) was linked to 771,742 unique urls. Being able parse out all the data can be cumbersome but by adding in pub ID, a user can evaluate all inventory under a given publisher. If there's a direct partnership in place, a user can reference the data to no longer buy on certain sites or block the publisher altogether if the majority of inventory is high MFA risk. This can also act as a decision making tool when comparing two publishers or even sellers for that matter. By tracking performance side by side, you can repurpose spend with publishers that align with quality expectations in place. 

**Key Benefits of Pixalate’s MFA Analytics Dashboard Report**

  * **Understand exposure based on actual traffic** : The report provides insights into your specific traffic and associated exposure from MFA websites.
  * **Filter by MFA Risk level:** The report filters can be used to view by specific risk level (low/high/medium).
  * **Granular insights with MFA factors** : The dimensions or MFA filters can be used to view traffic by the various MFA factors (ad density, ad refresh rate, etc) that are a part of Pixalate’s MFA detection methodology.
  * **Reduce SOV tied to MFA inventory** : By utilizing the data and flagging for supply partners, the MFA impact can be reduced while wasted spend also goes down. At the same time, demand partners and advertisers are please with more premium and brand suitable sites/apps.

### **How can I block MFA traffic?**

Pixalate's MFA data feeds can be used to block traffic on websites, mobile apps, or CTV apps deemed to be high or medium for MFA Risk. For more information, please visit [the knowledge base ](https://www.pixalate.com/knowledgebase/how-to-use-pixalates-mfa-datafeeds-to-block-mfa-traffic)article.

### **Where can I learn about MFA, Pixalate's MFA detection methodology, and products?**

For more information, please visit Pixalate's [Made For Advertising Solutions](https://www.pixalate.com/knowledgebase/made-for-advertising-mfa) knowledge base articles.

####
