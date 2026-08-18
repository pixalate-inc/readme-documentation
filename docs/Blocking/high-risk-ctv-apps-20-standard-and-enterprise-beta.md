---
title: "High Risk CTV Apps 2.0 Standard and Enterprise (Beta)"
excerpt: "Effective March 11, 2026, Pixalate is introducing High Risk CTV Apps 2.0 Standard and Enterprise (Beta), Connected TV app blocklists designed to give buyers deterministic, explainable control over app-level risk where impression-level IVT filtering is insufficient."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

High Risk CTV Apps 2.0 Standard and Enterprise (Beta) identify known dangerous and fraudulent apps across 9 CTV operating systems — Android, FireOS, Linux, Roku, Samsung, Sony, tvOS (Apple TV), LG webOS, and Windows — and more than hundreds of CTV platforms. The lists combine persistent IVT signals, app store compliance indicators, app-ads.txt authorization checks, and privacy risk signals into a single, unified feed with transparent risk reason codes. Each app is included based on defined inclusion thresholds, not probabilistic scoring.

This approach aligns with the property-level reporting requirements outlined in the MRC’s Invalid Traffic Detection and Filtration Interim Update Memo and reflects Pixalate’s continued evolution of app-level risk intelligence based on client feedback.

#### Why This Matters

Standard IVT measurement operates at the impression level. It does not always capture risk that is structural, persistent, or rooted in app-level behaviour or compliance status.

High Risk CTV Apps 2.0 Standard and Enterprise (Beta) complement impression-level IVT detection by identifying CTV apps where risk cannot be reliably isolated or mitigated through impression-level filtering alone. These risks can expose buyers to compliance violations, brand safety issues, and wasted spend, even when impressions appear valid in isolation.

#### What's Included

High Risk CTV Apps 2.0 Standard and Enterprise (Beta) provide app-level risk coverage across the following dimensions:

  * **Invalid traffic** based on sustained GIVT and SIVT thresholds
  * **App store compliance** , including privacy policy and listing status
  * **Supply chain authorisation** , via app-ads.txt validation
  * **Child privacy compliance** , including Verifiable Parental Consent (VPC) risk
  * **Inventory quality** , including Made for Advertising (MFA) indicators

Every app is tagged with explicit risk reason codes, providing transparency into why an app is flagged and enabling informed blocking decisions.

#### Risk Types

**Risk Type** |  **Code** |  **Description**  
---|---|---  
High GIVT |  `highGivt` |  Apps with General Invalid Traffic rates exceeding Pixalate's thresholds  
High SIVT |  `highSivt` |  Apps with Sophisticated Invalid Traffic rates exceeding Pixalate's thresholds  
Missing Privacy Policy |  `missingPrivacyPolicy` |  Apps missing privacy policies  
Abandoned App |  `abandonedApp` |  Apps that have not been updated by developers and may be unmaintained, insecure, or non-compliant with current app store requirements  
Missing app-ads.txt |  `noAdsTxt` |  Apps generating ad impressions without a valid app-ads.txt file, indicating unauthorized inventory  
VPC Bypass Risk |  `vpcBypass` |  Child-directed apps transmitting personal data without Verifiable Parental Consent, creating COPPA compliance exposure  
Developer Anonymity |  `developerAnonymity` |  Apps where the developer has missing or unverifiable contact information  
Delisted App |  `delistedApp` |  Apps removed from app stores that continue to generate ad traffic  
Made for Advertising |  `mfaApp` |  Apps designed primarily to generate ad impressions rather than deliver genuine user value, including apps exhibiting ad stacking and other manipulative ad placement tactics  
  
**NOTE:** RiskType coverage differs across CTV operating systems based on each platform’s level of transparency and metadata availability.

#### Schema

High Risk CTV Apps 2.0 Standard and Enterprise (Beta) evaluate each app against nine risk dimensions. An app can be flagged for multiple risk types simultaneously — for example, an app may be both abandoned and missing a privacy policy.

In High Risk CTV Apps 2.0 Standard (Beta) version, when an app has multiple risk types, the riskType field displays the string value “various”. If you require visibility into all applicable risk types for each app, High Risk CTV Apps 2.0 Enterprise (Beta) version is available that lists each risk type individually.

The probability field is set to 1 for all entries. High Risk CTV Apps 2.0 Standard and Enterprise (Beta) use deterministic inclusion criteria — an app either meets the threshold for a risk type or it does not.

### High Risk CTV Apps 2.0 Standard (Beta)

**Column** |  **Type** |  **Description**  
---|---|---  
osName |  STRING |  The Operating System (OS) name that is associated with a given app.  
platformName |  STRING |  The platform where the CTV app is available  
appId |  STRING |  The actual ID that characterizes a CTV app, if available  
bundleId |  STRING |  The bundle ID associated with the app  
riskType |  STRING |  Risk type code; displays the string value “various” when multiple risk types apply  
probability |  FLOAT |  Value of 1.0 for all entries  
  
File Format: CSV

Delivery: FTP or S3 Bucket

Naming Convention: CtvHighRiskApps_YYYYMMDD

Update Frequency: Daily

### High Risk CTV Apps 2.0 Enterprise (Beta)

High Risk CTV Apps 2.0 Enterprise (Beta) includes all features from the Standard version, plus the following:

  * **Full risk type granularity:** All applicable risk types are listed as comma-separated values (e.g., highSivt,abandonedApp,missingPrivacyPolicy) instead of displaying various, enabling you to build custom blocking logic based on specific risk type combinations.
  * **New HRA data points:** Access additional High Risk App data points in scheduled reports via Analytics Dashboard and Analytics API.

Contact your Customer Success representative to upgrade to High Risk CTV Apps 2.0 Enterprise (Beta).

#### Access and Pricing

High Risk CTV Apps 2.0 Standard (Beta) is included at no additional cost for the remainder of your current subscription term, subject to acceptance of the updated Master Subscription Terms (MST). Ongoing pricing will be addressed at renewal.

High Risk CTV Apps 2.0 Enterprise (Beta) is available for clients who require full visibility into all applicable risk types per app. Enterprise exposes each risk type individually, enabling selective and differentiated blocking strategies rather than uniform app-level exclusions.

Contact your Customer Success representative to discuss upgrade options.

#### Deployment and Integration

After acceptance of the updated MST, Pixalate will enable access and provide delivery details for your FTP folder or S3 bucket. High Risk CTV Apps 2.0 Lists are now also available through AWS RTB Fabric and APIs. Most integrations will continue to function without change. Action is required only if:

  * Your integration relies on hard-coded legacy risk type names. These must be updated or removed.
  * Your blocking logic uses probability thresholds. All apps now have a probability value of 1, so filtering should be based on risk types instead.

Your Customer Success representative will confirm MST acceptance, access enablement, and next steps.

#### Timeline

  * March 11, 2026: Production rollout begins for clients who have accepted the updated MST

Clients with custom integrations or internal review requirements are encouraged to engage with Customer Success ahead of the rollout date to ensure continuity and avoid unintended blocking behaviour.
