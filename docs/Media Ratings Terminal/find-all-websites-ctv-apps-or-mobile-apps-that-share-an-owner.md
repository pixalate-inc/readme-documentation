---
title: "Find all Websites, CTV apps, or Mobile apps that share an owner"
excerpt: "Leverage ads.txt \"ownerdomain\" to find all websites, CTV apps, or Mobile apps that share an owner"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

In many cases, a single business entity may own many websites (or CTV apps or Mobile apps). In the ad tech ecosystem, this shared business entity gets paid across all these websites/apps, making the knowledge about this business entity an important piece of information from a Supply Path Optimization (SPO) point of view. To make this data easily accessible, the IAB TechLab's ads.txt standard [introduced a new directive ("**ownerdomain** ") in 2022](https://iabtechlab.com/blog/why-ownerdomain-managerdomain-fields-are-important-additions-to-ads-txt/).

**"** Ownerdomain**"** is defined as the business domain of the owner of the site or app that is being monetized. For example, Disney owns ESPN, ABC, and other properties, and so the ads.txt files for those properties have an entry that indicates that disney.com is the "ownerdomain" for those properties.

Pixalate has crawled millions of ads.txt and app-ads.txt files and enables clients to use the "ownerdomain" information within the Media Ratings Terminal.

### **Use Cases / Key Benefits -**

The MRT enables clients to   

  * Understand ownership of a specific website or app.
  * Look up all the websites (or CTV apps or Mobile apps) that have the same owner. This can be useful in both blocking or inclusion scenarios where a client may be looking to block (or target) all websites or apps from a particular business entity, for any reason.

### **MRT Discovery Page**

"Owner Domain" is available as a filter in the MRT discovery page for all 3 platforms (Mobile Apps, CTV Apps, and websites) 

#### Apps:

![](https://lh7-us.googleusercontent.com/45evC9uk7i2D0QLrTER1W34mh7AizftLEqgsSaCo9cVoSToywjjUw_cpVlVzj1VTbqyrm4GVj_JH1Gy72w1eLSXbfnXy4QkhjWruU3-cCo_nMzV6RhQqTDx7qeD0NjuhPQrhjeLh9Y908YSO0qkQUuQ)

![](https://lh7-us.googleusercontent.com/i7e6AnnjmftMp6p_Rl--O_G_9WNml9WWuNXSCEhrzq48tAjyocYxTOYx0rmQppy-8tIcXaBjnAUjXLUglBGPresJj0M1Rf09fMd_P1gjXA0C_enBLKV9aJx4rUCvgKIxWOIpnuU-WNBcxsxoPBu7Eik)

#### Websites:

![](https://lh7-us.googleusercontent.com/YPupadljP1sq6dw82fp2cWr5M2Ye0RdJw5vlwCKtJAjoYSAWXXxTYaGZzMcTrR5KbW94BDwm-lpxwrlqi4vSqgMT3_9a5DAxCUCGfA60IAwovD2x3OkuNQIjtXH0VxVu4i_JiJZdb0Bn4bWH5tSYChA)

![](https://lh7-us.googleusercontent.com/P-utx7zCHs9dP4slba6twhzuX_yyvZ4FOLiPC9mtanZuiFbDJ5A08w5H8keRHq76lw_m1jKxUDZp9i3S-6ORTWMuzNQDSS_ihgFDrCT18Z5Z07sHRE13thZR2n6no9YyWX9xic3Bk1JSVb7uKioitGw)

### MRT Insights Page

The "Owner Domain" information is available in the MRT insights pages, as a field in the “App Information” section for apps, and in “Domain Details” section for websites.

![](https://lh7-us.googleusercontent.com/GrRiPxiBTdhkKc-20BR-kaUaVRgwG4FIDXO5aHxF-EFDm9yDPznjcVorHo7lmQTi2rONqZBYNNhu9zjMte9zYIanlrSUWHFhIVxLg85QJC6aXg5QEsR_-D-9F8_FhsJsDvI2yX65N7EFTsLhWL41T4Y)  

![](https://lh7-us.googleusercontent.com/AYFNrdD8ipL-247EeiN23XRHfeuuSDMhEAJWXgBzA_o72dpYjHfcwGN1ZrzkWFUOglays5-3VAo57W6A1Ba1gzSniMu7ykAMNi6iQMreeZ5HX53_c0hlrBTf0eyuRl1WOrqqMxC7jMq5atZxI9-VUFI)
