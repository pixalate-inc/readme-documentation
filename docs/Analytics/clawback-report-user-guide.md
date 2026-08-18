---
title: "Clawback Report User Guide"
excerpt: "The Clawback Report feature in the Pixalate Analytics Dashboard enables users to generate\u00a0 official Invalid Traffic (IVT) reports for both Apps and Domains."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### **Introduction**

These reports can assist Publishers, Sellers, and Advertisers with identifying IVT, documenting findings, and supporting with financial clawback processes, saving teams hours of extensive manual analysis.

It’s important to note that Clawback Report can only be used for impressions that have been measured by Pixalate. 

Clawback Reports are generated as PDFs with all relevant information:

  * Comprehensive IVT data (GIVT, SIVT, Total IVT)
  * Report metadata (filters, date ranges, timestamps)
  * Document authentication 
  * Accompanying legal disclaimers and requisite compliance statements

**When to Use the Clawback Report**

Use the Clawback Report if you need to:

  * Provide **evidence** of IVT to support clawback discussions with partners.
  * Compare **App vs. Domain** traffic quality for clawback processes. 
  * Identify **Publishers/Sellers** contributing to high IVT.
  * Generate a **PDF report** to share internally or with external partners.

**Accessing the Clawback Report**

  1. Log in to the Pixalate Analytics Dashboard using your account. 
  2. In the left navigation section, under **Reports** , select **Clawback Report**.

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/undefined-Oct-07-2025-08-31-02-4611-PM.png)

_Figure 1: Analytics Dashboard – Clawback Section Access_

### **Report Types**

Pixalate supports the following two types: 

#### **App Clawback Report**

  * **Dimensions:** App ID, Seller ID, Publisher ID, Campaign ID, and Advertiser ID
  * **Metrics:** Gross Ad Counts, IVT Ad Count, SIVT Ad Count, GIVT Ad Count
  * **Filters:** App ID, Seller ID, Publisher ID, Campaign ID, Advertiser ID, and Fraud Type
  * (Optional) Filter by IVT Ad Count, SIVT Ad Count, and GIVT Ad Count. 

#### **Domain Clawback Report**

  * **Dimensions:** Domain (URL), Seller ID, Publisher ID, Campaign ID, and Advertiser ID
  * **Metrics:** Gross Ad Counts, IVT Ad Count, SIVT Ad Count, GIVT Ad Count (substituting Domain for App ID)
  * **Filters:** Domain, Publisher ID, Seller ID, Campaign ID, Advertiser ID, and Fraud Type
  * (Optional) Filter by IVT Ad Count, SIVT Ad Count, and GIVT Ad Count. 

### **Generating a Clawback Report**

#### **Step 1: Select Report Type**

  * Choose **App Report** or **Domain Report**.

**![Screenshot 2025-10-07 at 13.34.49](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202025-10-07%20at%2013.34.49.png)**

_Figure 2: Clawback Report – Select Report Type_

#### **Step 2: Apply Filters**

  * **Publisher ID** – Select or enter the ID.
  * **Seller ID** – Select or enter the ID.
  * (Optional) Filter by IVT Ad Count, SIVT Ad Count, and GIVT Ad Count. 

#### **Step 3: Select Date Range**

  * Presets: **Yesterday** , **Last 7 Days** , **Last 30 Days, Last 90 Days**
  * Custom Range: Up to one (1) year. 

**![Screenshot 2025-10-07 at 13.36.03](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/Screenshot%202025-10-07%20at%2013.36.03.png)**_Figure 3: Clawback Report – Select Filters, Select Date Range_

#### **Step 4: Generate & Download Report**

  * Click **Apply Filters**. 
  * A preview will display: 
    * Gross Ad Counts
    * IVT % breakdown
  * To generate the PDF report, click on **Generate Clawback Report**. 
  * A PDF report will be generated that is timestamped and digitally signed. 

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/undefined-Oct-07-2025-08-31-02-0697-PM.png)

_Figure 4: Clawback Report – Apply Filters, Preview Report, Download PDF_

### **Understanding the Report**

#### **Executive Summary**

  * **Total Ad Counts** – Total Ads analyzed
  * **Overall IVT** – Total Invalid Traffic
  * **Overall SIVT** – Total Sophisticated Invalid Traffic
  * **Overall GIVT** – Total General Invalid Traffic

#### **Detailed Data Table**

Each row includes:

  * Identifier (App ID or Domain)
  * Publisher ID
  * Seller ID
  * Gross Ad Counts
  * IVT Ad Count ( and %) with SIVT Ad Count (%) and GIVT Ad Count (%)

#### **Data Limits**

Each Clawback Report displays up to 500 rows by default. If users see a data limitation message on the screen, they should apply filters by IVT% directly in the main reports screen to focus on entities with the highest levels of Invalid Traffic.

If the current data limit does not meet their needs, users should **contact Pixalate Support** for assistance.

#### **Accessing Past Reports**

Previously generated Clawback Reports can be accessed anytime from the Recently Generated Reports section within the Clawback section. 

Reports are automatically organized by date, entity type (App or Domain), and report name for easy retrieval and verification.

#### **Document Authentication**

Each PDF includes:

  * **Verification Link**
  * **Document Hash (SHA-256)**
  * **Digital Signature**

This ensures reports are tamper-proof and verifiable.

![](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/undefined-Oct-07-2025-08-31-01-6351-PM.png)

_Figure 5: PDF Version of the Clawback Report_

### **Frequently Asked Questions (FAQ)**

**Q: Can I store historical reports?****  
**A: Yes. Reports can be downloaded and stored internally. The retention policy is up to one year.

**Q: Can reports be emailed automatically?****  
**A: Currently, reports must be downloaded manually. Email delivery may be added in future versions.

**Q: What’s the maximum timeframe for lookback?****  
**A: Up to a year.

**Q: Can I customize the metrics?****  
**A: No. Metrics are standardized for compliance integrity.

#### **Disclaimer**

The content of this Clawback Report User Guide reflects Pixalate’s opinions with respect to the factors that Pixalate believes can be useful to the digital media industry. Any proprietary data, including images and figures shared are grounded in Pixalate’s proprietary technology and analytics, which Pixalate is continuously evaluating and updating. Any references to outside sources should not be construed as endorsements. Pixalate’s opinions are just that - opinions, not facts or guarantees.

Per the [MRC](http://www.mediaratingcouncil.org/063014%20Viewable%20Ad%20Impression%20Guideline_Final.pdf), “'Fraud' is not intended to represent fraud as defined in various laws, statutes and ordinances or as conventionally used in U.S. Court or other legal proceedings, but rather a custom definition strictly for advertising measurement purposes. Also per the [MRC](http://mediaratingcouncil.org/101515_IVT%20Addendum%20FINAL%20\(Version%201.0\).pdf), “‘Invalid Traffic’ is defined generally as traffic that does not meet certain ad serving quality or completeness criteria, or otherwise does not represent legitimate ad traffic that should be included in measurement counts. Among the reasons why ad traffic may be deemed invalid is it is a result of non-human traffic (spiders, bots, etc.), or activity designed to produce fraudulent traffic.”

#### **Support**

For questions about Clawback Reports, contact: **support@pixalate.com**

Pixalate Analytics Platform © 2025 – All Rights Reserved.
