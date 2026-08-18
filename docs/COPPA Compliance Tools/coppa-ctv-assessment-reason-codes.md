---
title: "COPPA CTV Assessment Reason Codes"
excerpt: "Pixalate's COPPA Audience assessment and Violation Risk Rating are based on various attributes of the CTV app. The information below captures the various reasons for each potential assessment result."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

**COPPA CTV Audience Assessment Reason Codes**

**CTV App** | **Likely Directed to Children Reason Codes**  
---|---  
Fire | This app is likely directed to children (including mixed audience) based on manual review.  
Roku | This app is likely directed to children (including mixed audience) based on manual review.  
  
**CTV App** | **Likely General Audience Reason Codes**  
---|---  
Fire | This app is likely general audience based on manual review.  
Fire |  This app has not yet been reviewed under Pixlate’s automated or manual methodology. The default likely target audience for this app is General Audience.  
Roku |  This app is likely general audience based on manual review.  
Roku |  This app has not yet been reviewed under Pixlate’s automated or manual methodology. The default likely target audience for this app is General Audience.  
  
|  **Directed to Children** |  **Privacy Policy Detected** |  **Passes Residential IP in the bidstream** |  **Passes Location in the bidstream** |  **COPPA RISK**  
---|---|---|---|---|---  
1 |  No |  - |  - |  - |  **Low**  
2 |  Yes |  Yes |  No |  No |  **Medium**  
3 |  Yes |  Yes |  Yes |  Yes |  **High**  
4 |  Yes |  Yes |  No |  Yes |  **High**  
5 |  Yes |  Yes |  Yes |  No |  **High**  
6 |  Yes |  No |  - |  - |  **Critical**  
  
### COPPA Violation Risk Assessment Reason Codes (CTV)

The reason code descriptions below correspond to each numbered row in grid above.

  1. The COPPA risk is **low** because the app is likely not directed to children under 13.

  2. The COPPA risk is **medium** because the app is likely directed to children under 13, and it is not passing residential IP or location information. It has a privacy policy as required by the COPPA Rule.

  3. The COPPA risk is **high** because the app is likely directed to children under 13, and it passes residential IP and location information. It has a privacy policy as required by the COPPA Rule.

  4. The COPPA risk is **high** because the app is likely directed to children under 13, and it passes location information. It has a privacy policy as required by the COPPA Rule.

  5. The COPPA risk is **high** because the app is likely directed to children under 13, and it passes residential IP. It has a privacy policy as required by the COPPA Rule.

  6. The COPPA risk is **critical** because the app is likely directed to children under 13, and it does not have a privacy policy as required by the COPPA Rule.

Learn more about Pixalate's CTV COPPA assessment [methodology here.](https://www.pixalate.com/coppa-ctv-methodology)

Disclaimer:

Pixalate’s COPPA Compliance Tools render opinions that Pixalate believes may be useful to our clients and others in the digital media industry. It is important to note, however, that the mere fact that an app appears to be directed to children (e.g., data subjects under 13 years of age, as defined by the COPPA Rule) does not mean that any such app, or its operator, is failing to comply with the COPPA Rule. Further, with respect to apps that appear to be child-directed and have characteristics that, in Pixalate’s opinion, may trigger related privacy obligations and/or risk, such assertions reflect Pixalate’s opinions (i.e., they are neither facts nor guarantees); and, although Pixalate’s methodologies used to render such opinions are derived from a combination of automated processing coupled with significant human intervention, no assurances can be – or are – given by Pixalate with respect to the accuracy of any such opinions
