---
title: "Analytics Updates: High Risk CTV Apps 2.0 Standard and Enterprise (Beta)"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### **What's Changing**

With the release of High Risk CTV Apps 2.0 Standard and Enterprise (Beta), impressions from apps on the Connected TV High Risk App list will no longer be classified under the highRiskApp IVT type. As a result, you may see a reduction in reported IVT rates.  
  
This change reflects a separation between app-level structural risk and impression-level IVT detection.

#### **New Data Points**

To understand how much of your traffic originates from CTV apps on the blocklist, you can use the two new High Risk App data points recently added to Analytics:

  * **Traffic from High Risk Apps (%)**  
The percentage of your total traffic originating from apps on the list.
  * **High Risk App (Yes/No)***   
A boolean indicator available in app-specific reports identifying whether an app appears on the list.

_*A subscription to the High Risk CTV Apps 2.0 Enterprise blocklist is required to export the HRA boolean via Analytics reports and API._

#### **Why This Change**

Standard IVT measurement operates at the impression level. It does not always capture risk that is structural, persistent, or rooted in app-level behaviour or compliance status.

High Risk CTV Apps 2.0 Standard and Enterprise (Beta) are designed to identify apps where risk cannot be reliably isolated or mitigated through impression-level filtering alone. Analytics now reflects this distinction.

In line with the MRC’s _Invalid Traffic Detection and Filtration Interim Update Memo_ , impressions are no longer automatically classified as IVT solely because an app appears on the High Risk CTV Apps list.

With this update, you gain:

  * IVT reporting that reflects impression-level invalid traffic measurement  

  * Dedicated visibility into traffic originating from high-risk app sources  

  * The ability to make independent decisions about app-level blocking and impression-level filtering

#### **Anticipated IVT Impact**

As a result of these enhancements, we anticipate a slight reduction in overall IVT and SIVT percentages, typically less than 5%.

This reduction reflects more precise classification, not reduced detection of invalid traffic.

For projected impact, refer to your Analytics dashboard and the notification therein.

#### **Timeline**

  * March 11, 2026: Analytics updates go live

If you have any questions, please contact your Customer Success representative.
