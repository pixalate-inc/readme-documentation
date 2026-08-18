---
title: "Analytics Updates: High Risk Domains 2.0 (Beta)"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

#### **What's Changing**

With the release of _[High Risk Domains 2.0(Beta)](https://www.pixalate.com/knowledgebase/high-risk-domains-v2)_, impressions from high-risk domains will no longer be classified under the `highRiskDomain` IVT type. Two new data points will be available on Analytics to indicate traffic originating from high-risk domains, reflecting the separation between domain-level structural risk and impression-level IVT detection.

#### **New Data Points**

To understand how much of your traffic originates from domains on the blocklist, Analytics will surface two new data points:

  * **Traffic from High Risk Domains (%)**  
The percentage of your total traffic originating from domains on the list.
  * **High Risk Domain (Yes/No)**   
A boolean indicator available in domain-specific reports identifying whether a domain appears on the list.

This approach separates domain-level risk signals from impression-level IVT classification, giving you visibility into high-risk inventory sources while preserving granular IVT reporting.

#### **Why This Change**

Standard IVT measurement operates at the impression level. It does not always capture risk that is structural, persistent, or rooted in domain-level behaviour or compliance status.

The High Risk Domains 2.0 (Beta) blocklist is designed to identify domains and subdomains where risk cannot be reliably isolated or mitigated through impression-level filtering alone. Analytics now reflects this distinction.

In line with the MRC’s _Invalid Traffic Detection and Filtration Interim Update Memo_ , impressions are no longer automatically classified as IVT solely because a domain or subdomain appears on the High Risk Domains 2.0 (Beta) list.

With this update, you gain:

  * IVT reporting that reflects impression-level invalid traffic measurement
  * Dedicated visibility into traffic originating from high-risk domains
  * The ability to make independent decisions about domain-level blocking and impression-level filtering

#### **Timeline**

  * April 30, 2026: Analytics updates go live

If you have any questions, please contact your Customer Success representative.
