---
title: "Analytics Updates: High Risk Mobile Apps 2.0 Standard and Enterprise (Beta)"
excerpt: "What changes in Analytics with High Risk Mobile Apps 2.0: two new high risk app data points and the retirement of the highRiskApp IVT type."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### **What's Changing**

Effective February 5, 2026 with the release of [High Risk Mobile Apps 2.0 Standard and Enterprise (Beta)](https://www.pixalate.com/knowledgebase/high-risk-mobile-app-lists-v2), impressions from apps on the High Risk Mobile Apps 2.0 Standard and Enterprise (Beta) list will no longer be classified under the highRiskApp IVT type. As a result, you may see a reduction in reported IVT rates.  
  
This change reflects a separation between app-level structural risk and impression-level IVT detection.

### **New Data Points**

To understand how much of your traffic originates from apps on the blocklist, Analytics will surface two new data points:

  * **Traffic from High Risk Apps (%)**  
The percentage of your total traffic originating from apps on the list.
  * **High Risk App (Yes/No)**   
A boolean indicator available in app-specific reports identifying whether an app appears on the list.

This approach separates app-level risk signals from impression-level IVT classification, giving you visibility into high-risk inventory sources while preserving granular IVT reporting.

### **Why This Change**

Standard IVT measurement operates at the impression level. It does not always capture risk that is structural, persistent, or rooted in app-level behaviour or compliance status.

High Risk Mobile Apps 2.0 Standard and Enterprise (Beta) are designed to identify apps where risk cannot be reliably isolated or mitigated through impression-level filtering alone. Analytics now reflects this distinction.

In line with the MRC’s _Invalid Traffic Detection and Filtration Interim Update Memo_ , impressions are no longer automatically classified as IVT solely because an app appears on the High Risk Mobile Apps list.

With this update, you gain:

  * IVT reporting that reflects impression-level invalid traffic measurement
  * Dedicated visibility into traffic originating from high-risk app sources
  * The ability to make independent decisions about app-level blocking and impression-level filtering

### **Anticipated IVT Impact**

As a result of these enhancements, we anticipate a material reduction in overall IVT and SIVT percentages, typically greater than 5%.

This reduction reflects more precise classification, not reduced detection of invalid traffic.

For projected impact, refer to your Analytics dashboard and the notification therein.

### **Timeline**

  * February 5, 2026: Analytics updates go live

If you have any questions, please contact your Customer Success representative.
