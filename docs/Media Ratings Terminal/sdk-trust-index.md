---
title: "SDK Trust Index"
excerpt: "SDK Trust Index"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

An independent, free, and public database that rates mobile advertising and data collection SDKs on the gap between what their code actually does with user location data and what their disclosures say they do — information that publishers, regulators, and platforms have no efficient way to verify on their own.

#### **In this article**

  * What is the SDK Trust Index?
  * How are SDKs rated?
  * Risk rating definitions
  * Underlying signal definitions
  * How ratings are determined
  * Coverage and ranking

### **What is the SDK Trust Index?**

The **SDK Trust Index** is a free, public reference that rates mobile advertising and analytics software development kits (SDKs) on the alignment between their disclosed data practices and their actual code-level behavior. The Index focuses on **precise location** as the measured data category, and surfaces two independent risk indicators for every SDK:

  * **FTC Section 5 Violation Risk** — exposure under the Federal Trade Commission's prohibition on unfair or deceptive acts or practices, driven by gaps between the SDK vendor's privacy policy and the SDK's actual code.
  * **App Store ToS Violation Risk** — exposure under the published guidelines of the Apple App Store and Google Play, driven by gaps between the SDK's manifest-file declarations and the SDK's actual code.

Pixalate evaluates each SDK by manually reviewing its privacy policy, parsing its manifest files (Apple PrivacyInfo.xcprivacy and the Android merged manifest), and running source-code analysis on the SDK's compiled distribution. Where collection is found in code, Pixalate also tests for off-device transmission via further code analysis. The Index covers SDKs distributed on both Android and iOS; the same SDK is rated separately on each operating system because disclosure surfaces and permission models differ.

The Index is accessible for free on Pixalate's website and is updated quarterly.

### **How are SDKs rated?**

Each SDK in the Index receives two independent risk ratings, each of which can resolve to one of two states:

  * **Critical Risk Detected** — a meaningful gap between disclosure and observed behavior was found.
  * **Not Detected** — no such gap was found in Pixalate's evaluation.

The two ratings are derived from a small set of observable signals about each SDK. Both ratings can resolve independently of each other: an SDK can carry serious exposure on one surface (consumer-facing privacy policy) while remaining clean on the other (platform-facing manifest), or vice versa. The dual rating surfaces both patterns separately so the right remediation reaches the right surface.

### **Risk rating definitions**

#### **FTC Section 5 Violation Risk**

Reflects exposure under the Federal Trade Commission Act, Section 5 — the federal statute prohibiting "unfair or deceptive acts or practices in or affecting commerce." Driven primarily by inconsistency between the SDK vendor's privacy policy (the consumer-facing surface) and the SDK's actual data behavior in code. An undisclosed collection or undisclosed off-device transmission constitutes a deceptive omission to consumers.

  * **Not Detected** → The SDK's privacy policy is consistent with what its code does, or no precise-location collection was found.
  * **Critical Risk Detected** → The SDK's code collects (or collects and transmits off-device) precise location, but the privacy policy does not disclose this — or no privacy policy was discoverable for the SDK at all.

#### **App Store ToS Violation Risk**

Reflects exposure under the published guidelines of the Apple App Store and Google Play, including Apple's Privacy Manifest requirements, App Store Review Guidelines 5.1.1 and 5.1.2, App Tracking Transparency rules, Google's Developer Program Policies, and Android manifest-permission requirements. Driven primarily by inconsistency between the SDK's manifest-file declarations (the platform-facing surface) and the SDK's actual data behavior.

  * **Not Detected** → The SDK's manifest is consistent with what its code does, or no off-device transmission of precise location was confirmed.
  * **Critical Risk Detected** → The SDK was observed transmitting precise location off-device without a matching manifest declaration (Apple PrivacyInfo.xcprivacy or Android ACCESS_FINE_LOCATION).

### **Underlying signal definitions**

Each SDK rating is derived from three observable signals. Each signal is binary or three-state, and is collected from a distinct technical source with distinct reliability characteristics.

#### **Declares Location Collection (Privacy Policy)**

Whether the SDK vendor's publicly accessible privacy policy contains language disclosing collection of location data. Pixalate manually reviews each SDK vendor's public website, identifies the operative privacy policy, and analyzes it for location-specific disclosure language.

  * **Detected** → Manual review of the policy found location-collection disclosure language.
  * **Not Detected** → Manual review of the policy did not find location-collection disclosure language, or precise-location collection was specifically disclaimed.
  * **Policy Not Found** → No privacy policy was discoverable for the SDK. Treated as the most severe disclosure failure, since the consumer cannot read what does not exist.

#### **Declares Precise Location (Manifest)**

Whether the SDK's distributed manifest file declares the location capability the platform requires it to declare. On iOS, an NSPrivacyCollectedDataTypes entry for precise location in PrivacyInfo.xcprivacy. On Android, an ACCESS_FINE_LOCATION permission in the merged manifest.

  * **Detected** → The manifest declares precise-location collection.
  * **Not Detected** → The manifest does not declare precise-location collection.

#### **Collects Precise Location (Code Analysis)**

Whether the SDK's compiled or source code contains a code path that reads precise location data from the device, detected through static analysis of API call sites, framework imports, and known location-collection patterns. Where collection is found, Pixalate runs additional code analysis to determine whether the collected data is in fact transmitted off the device.

  * **Not Detected** → No precise-location collection path was found in the code. Subject to detector coverage limits.
  * **Collects Only** → A location data collection path was found in the code, but off-device transmission found within the code base.
  * **Collects & Transmits Off-Device** → A location data collection path was found AND off-device transmission was confirmed via further code analysis.

### **How ratings are determined**

The two public ratings are derived from the three signals above to highlight **disclosure and code discrepancy detection.** Pixalate compares the privacy policy declaration, the manifest declaration, and the code behavior. Where the code shows collection and transmission but a disclosure surface (policy or manifest) is silent, a discrepancy is recorded. A privacy-policy discrepancy drives FTC Section 5 Violation Risk. A manifest discrepancy drives App Store ToS Violation Risk.

### **Coverage and ranking**

The Index covers mobile advertising and analytics SDKs detected by Pixalate across the Apple App Store and Google Play. SDKs in the public Index are grouped by operating system (Android, iOS) and by SDK type (Advertising, Analytics), and ordered within each bucket by **install base** — the number of distinct apps in which Pixalate has detected the SDK. Larger install base ranks first within each bucket, surfacing the SDKs that touch the largest share of the user base at the top of the public view.

OS is treated as a separate dimension. The same SDK package can carry different ratings on iOS and Android because the disclosure surfaces, manifest formats, and runtime permission models differ between the two platforms. This is not a contradiction; it reflects each platform's distinct requirements and the SDK's distinct runtime paths on each.

[**See Full Methodology Here.**](http://pixalate.com/sdk-trust-index-methodology)

* * *

#### **Disclaimer**

Pixalate’s SDK Trust Index Ratings (“SDK Index”) reflect Pixalate’s opinions that Pixalate believes may be useful to developers, regulators, platforms, advertisers, researchers, and others in the digital media industry. Any data shared is grounded in Pixalate’s proprietary technology and analytics, which Pixalate is continuously evaluating and updating. Any references to outside sources should not be construed as endorsements, affiliations, or associations with any third-parties. Pixalate is sharing this data not to impugn the standing or reputation of any entity, person or SDK, but, instead, to report research findings and trends pertaining to the period studied.

It is important to note however, that classification of a software development kit operator (“SDK operator”) within a particular risk tier does not mean that the SDK operator, its SDK(s), or any associated practices are in violation of any laws or regulations, including the Children’s Online Privacy Protection Act (COPPA) or any other global privacy framework. Further, the SDK(s) of an SDK operator(s) that appear(s) to present elevated risk signals does not mean that such SDK, or its operator, is failing to comply with applicable FTC Rules.

Pixalate’s determinations are based on a proprietary methodology that incorporates a combination of signals and automated processes. Additionally, with respect to SDK operators that appear to have characteristics that, in Pixalate’s opinion, may trigger related privacy law or regulatory compliance obligations and/or risk, such assertions reflect Pixalate’s opinions i.e., they are neither facts nor guarantees. While Pixalate endeavors to apply rigorous standards in compiling this SDK Index, no assurances or guarantees can be, or are, made as to the accuracy or completeness of any classification. This SDK Index, including all content set forth herein–constitutes Pixalate “Materials” under Pixalate’s Terms of Use, and is licensed subject to–and conditioned expressly upon–compliance with each of the applicable terms and conditions of such Pixalate Terms of Use.

Apple and the Apple logo are trademarks of Apple Inc; Google, Google Ad Exchange, the brand “Google Play,” its logos, and other Google logos are trademarks of Google LLC. These companies are not affiliated with, nor do they endorse or sponsor, any products, data, content, reports, materials or services associated with Pixalate. Any other brand logos, names, or trademarks not explicitly mentioned herein – but otherwise mentioned, displayed, or used in any of Pixalate’s materials, including this report – are the property of their respective owners.
