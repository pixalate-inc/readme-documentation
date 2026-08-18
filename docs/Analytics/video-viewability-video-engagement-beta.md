---
title: "Video Viewability & Video Engagement (Beta)"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

For Pixalate clients and users, please log in to access [this page](/knowledgebase/video-viewability-video-engagement) with additional information.

### **Overview**

Pixalate delivers Video Viewability (VV) and Video Engagement (VE) measurement across programmatic and direct-sold video. Methodology is informed by the MRC Video Viewable Impression Measurement Guidelines (50% of the video player’s pixels visible on-screen for at least 2 continuous seconds while the video is playing), with audibility detection powered by Open Measurement SDK (OM SDK) signals.

Two preset reports provide 54 metrics across three IVT-filtering tiers covering video ad delivery, viewability outcomes, and engagement performance.

**Beta designation.** VV and VE are currently in Beta status, reflecting the initial rollout phase. Metrics methodology is stable; Beta status will be lifted upon completion of the launch validation cycle. Beta does not indicate any limitation in measurement accuracy.

### **Integration**

### What you need

Pixalate’s standard JavaScript verification tag is referenced in the video ad’s VAST AdVerifications node. The script runs alongside the video creative, collecting OM SDK viewability and audibility signals, and reports them to Pixalate for measurement and reporting in your Analytics dashboard.

Pixalate is **not** a VAST wrapper server. The verification script is configured as a verification provider within your existing VAST chain (via the publisher, SSP, or ad server). No SDK is installed, and no changes are made to the ad-serving path itself.

### Two integration prerequisites

Both must be in place for VV/VE measurement to populate:

  1. **OM SDK–compliant delivery chain.** The publisher, SSP, or ad-server software in your delivery chain must support Open Measurement SDK.
  2. **VAST AdVerifications reference.** Pixalate’s JavaScript verification script must be referenced in the VAST AdVerifications node of the response.

### VAST version support

**VV/VE measurement requires VAST 3.0 or 4.0+ in practice.** The measurement chain depends on the video player executing Pixalate’s verification JavaScript via Open Measurement SDK. VAST 4.0+ supports this natively; VAST 3.0 supports it via the Extensions wrapper described below. VAST 2.0 predates the IAB Open Measurement specification — most VAST 2.0 players will not execute verification JavaScript at all, so VV/VE measurement is not achievable on VAST 2.0 inventory without upgrading the response chain.

VAST version |  Status |  AdVerifications placement |  Notes  
---|---|---|---  
**VAST 4.x** (4.0, 4.1, 4.2, 4.3) |  Recommended |  Native  element inside  or  |  Recommended path for new and upgradeable inventory. VAST 4.1 introduced the standardized AdVerifications node aligned with OM SDK; 4.2 and 4.3 maintain this.  
**VAST 3.0** |  Supported, with caveats |  Wrapped: … |  Player must implement OM SDK and correctly parse the typed Extension. A validation pass per player environment is recommended before broad rollout.  
**VAST 2.0** |  Not supported in practice |  No mechanism in spec |  Pre-dates IAB Open Measurement. Most VAST 2.0 players will not execute verification JavaScript. Upgrade the VAST response chain to 3.0 or 4.x to enable VV/VE on the affected inventory.  
**VPAID** |  Industry-deprecated |  Creative-wrapper delivery is possible |  We recommend planning a migration to VAST 4.x + OM SDK for new integration work.  
  
IAB Tech Lab’s VAST progression is 3.0 → 4.0 → 4.1 → 4.2 → 4.3; there is no intermediate VAST 3.1 release. The integration path is the same for any 3.x context (the Extensions wrapper) and the same for any 4.x context (native AdVerifications).

### Sample VAST snippet — VAST 4.x (recommended path)

<**InLine** >  
__  
<**AdVerifications** >  
<**Verification** vendor="pixalate.com-omid">  
<**JavaScriptResource** apiFramework="omid" browserOptional="true">  
  
JavaScriptResource**>  
Verification**>  
AdVerifications**>  
InLine**>

### Sample VAST snippet — VAST 3.0 (Extensions wrapper)

<**InLine** >  
__  
<**Extensions** >  
<**Extension** type="AdVerifications">  
<**AdVerifications** >  
<**Verification** vendor="pixalate.com-omid">  
<**JavaScriptResource** apiFramework="omid" browserOptional="true">  
  
JavaScriptResource**>  
Verification**>  
AdVerifications**>  
Extension**>  
Extensions**>  
InLine**>

**Required attributes (each must be exact):** vendor="pixalate.com-omid" (case-sensitive); apiFramework="omid";  wrapper around the URL; # unencoded as a real URI fragment. For VAST 3.0, type="AdVerifications" on  is case-sensitive.

### Macro substitution

The standard Pixalate verification tag contains template macros that your ad server must substitute at the moment the VAST response is generated (e.g., $!{…} for Apache Velocity, ${…}, %%…%%, depending on your ad-server templating engine). The macros carry per-impression context — campaign ID, creative ID, publisher ID, IP, device, supply type, geo, video length, and others — which are required for IVT classification, reporting breakouts, and measurement bucketing.

Macros left as literal template strings cannot be read by the verification runtime; impressions in this state will classify as Undetermined and will not contribute to viewability or engagement metrics. **If your dashboard shows zero across VV/VE metrics after a structurally correct integration, the first thing to confirm is whether ad-server-side macro substitution is firing before VAST delivery.**

Two macro families work together in the script URL.

#### _(a) Ad-server-side macros — substituted by your ad server before VAST delivery_

#### _Full version link:<https://www.pixalate.com/knowledgebase/video-viewability-video-engagement>_

#### The exact macro set reflected in your tag template may include additional kv slots for onboarding-specific signals. For tag-template-specific questions, contact your Pixalate Customer Success team.

#### _(b) IAB VAST bracketed macros — substituted by the player at runtime_

These are part of the IAB VAST specification (formally standardized in VAST 4.1) and are substituted by a VAST-compliant player when the script loads. Your ad server should leave them as literal bracket-text — the player fills them in.

The highest-impact macros for VV/VE measurement specifically are [IFA] (uniqueness and IVT), [CONTENTPLAYHEAD] / [ADPLAYHEAD] (quartile detection driving every VE metric), and [PLAYERSIZE] (viewability geometry). The remaining macros enrich reporting dimensions but are not measurement-gating.

Macro |  Purpose  
---|---  
[ERRORCODE] |  Verification error reporting  
[CONTENTPLAYHEAD] and [ADPLAYHEAD] |  Quartile detection (drives First Quartile, Midpoint, Third Quartile, Completion VE metrics)  
[ASSETURI] |  Creative identification  
[VASTVERSIONS] |  Player’s declared VAST version  
[IFATYPE] and [IFA] |  Advertising identifier  
[CLIENTUA] / [SERVERUA] / [DEVICEUA] |  User-agent strings  
[DEVICEIP] |  Device IP  
[LATLONG] |  Geo  
[DOMAIN] / [PAGEURL] |  Web context  
[PLAYERSIZE] |  Player dimensions  
[REGULATIONS] |  GDPR / CCPA / COPPA signals  
[ADTYPE] |  Linear / non-linear  
[TRANSACTIONID] |  Unique impression identifier  
[BREAKPOSITION] |  Pre-roll / mid-roll / post-roll  
[APPNAME] |  App name (in-app)  
[PLACEMENTTYPE] |  Outstream / instream / CTV  
  
If the player does not honor IAB VAST 4.1+ macro substitution (older or non-compliant players), bracketed macros flow through as literals. The impression will still register if the ad-server-side macros are correct, but quartile, geo, and identifier breakdowns will be incomplete for that subset.

### Player capability requirements

For VV/VE measurement to populate, the video player must:

  1. Implement Open Measurement SDK at a current build (OMID 1.4.x or later recommended).
  2. Parse the AdVerifications node (native at VAST 4.x; Extensions-wrapped at VAST 3.0) and route the JavaScriptResource to the OM SDK runtime.
  3. Instantiate an OM SDK ad session and emit viewability state observer events.
  4. Emit OM SDK video events (start, first-quartile, midpoint, third-quartile, complete) for engagement measurement.
  5. Emit OM SDK volume-change signals for audibility measurement.
  6. Permit loading of the Pixalate script under the player’s Content Security Policy and sandbox configuration.

A publisher or player vendor declaring “OMID support” in their integration documentation is a metadata claim, not proof of correct end-to-end behavior. Common gaps observed in production include the AdVerifications block being parsed but never instantiated as an OM SDK session, OM SDK version mismatches between the player and the verification script, and Content Security Policy restrictions silently blocking the script load. A brief validation pass per player environment is strongly recommended before broad rollout.

* * *

Measurement Methodology

### Video impressions

Recorded post-buffer as Rendered Video Impressions per MRC Video Impression Guidelines — only impressions where video playback has begun.

### Viewability

A video impression is classified as **Viewable** when 50% or more of the video ad player’s pixels are visible on-screen for at least 2 continuous seconds while the video is playing, consistent with MRC Video Viewable Impression Measurement Guidelines.

Each Measured Video Impression is classified as one of: - **Viewable Video Impression** — Measured Video Impression meeting the 50%/2-continuous-second standard - **Non-Viewable Video Impression** — Measured Video Impression that did not meet the viewability standard - **Undetermined Video Impression** — Rendered Video Impression for which Pixalate’s technology was unable to collect sufficient OM SDK signal to decision viewability

### Engagement

Measured at four VAST quartile milestones (First Quartile, Midpoint, Third Quartile, Completion) plus Average Playback Duration and Audibility Rate.

### Audibility

Detected via OM SDK signals, reflecting whether audio was enabled during video ad playback.

### IVT filtering

All VV/VE metrics are reported at three IVT-filtering tiers, consistent with Pixalate’s broader reporting framework:

  * **Gross** — Prior to removal of Invalid Traffic
  * **Net of GIVT** — Following removal of General Invalid Traffic
  * **Net of All IVT** — Following removal of both General and Sophisticated Invalid Traffic

* * *

Known Limitations

  * **Server-Side Ad Insertion (SSAI):** Video Viewability and Video Engagement measurement are not currently available for SSAI traffic. SSAI delivery chains do not carry the client-side OM SDK signals required for viewability decisioning. SSAI video impressions continue to be measured and reported via Pixalate’s existing SSAI metric set. Extension of VV/VE coverage to SSAI traffic is a potential area of future enhancement and may be explored on request.
  * **Historical backfill:** VV/VE reports populate from the enablement date forward only. There is no backfill of historical traffic.
  * **Player capability dependency:** VV/VE measurement requires the video player to support Open Measurement SDK (OM SDK) and to correctly instantiate an OMID ad session. A publisher or player vendor declaring “OMID support” is a metadata claim, not proof of correct end-to-end behavior — a brief validation pass per player environment is recommended before broad rollout.
  * **VPAID:** Supported via creative-wrapper delivery, but industry-deprecated. For new integration work, VAST 4.x + OM SDK is the recommended path.
  * **VAST 2.0:** VV/VE measurement is not achievable on VAST 2.0 inventory in practice. VAST 2.0 pre-dates the IAB Open Measurement specification, and most VAST 2.0 players will not execute verification JavaScript at all. To enable VV/VE on this inventory, the VAST response chain must be upgraded to 3.0 or 4.x.

* * *

Troubleshooting — Common Pitfalls

Symptom |  Likely cause |  Resolution  
---|---|---  
Dashboard shows zero across every VV metric |  Ad-server macros not substituted (script URL contains literal $!{…} strings); or dvid=v not set |  Verify ad-server templating engine is resolving the macros before VAST delivery; confirm dvid=v literal is present  
Script loads, but Measured % is very low |  Player does not fully support OM SDK |  Confirm player vendor’s OM SDK support documentation; player update may be required  
Audibility Rate stays at 0% |  OM SDK audio signals not emitted by the player |  Some players support viewability but not audibility — confirm player capability  
High Undetermined classification |  Player executes the script but cannot determine viewport state (older player, embedded WebView, CSP restriction) |  Environment-specific; isolate by inventory subset and validate per environment  
Wrong URL hostname |  URL pointing at a non-production Pixalate hostname |  Switch to the production URL provided by your Pixalate Customer Success contact  
Impressions counted twice |  A 1×1 tracking pixel is firing alongside the JS verification tag on the same VV-measured ad |  Remove the 1×1  node from VV-measured ad-server traffic templates; the JS verification tag carries both the impression and the measurement  
Historical data missing for the first weeks after enablement |  Reports populate from the enablement date forward only |  By design — no backfill is available  
Average Playback Duration does not match player-side playback time |  APD is derived from highest quartile milestone × creative duration, not exact playback time |  Align methodologies; see Video Engagement metric definitions  
  
For any symptom not listed above, contact your Pixalate Customer Success team with a representative test impression URL and a description of the observed vs. expected behavior.

* * *

Available Reports

Tier |  VV Metrics |  VE Metrics |  Total  
---|---|---|---  
Gross |  4 |  10 |  14  
Net of GIVT |  10 |  10 |  20  
Net of All IVT |  10 |  10 |  20  
**Total** |  **24** |  **30** |  **54**  
  
**Video Viewability Report — 24 metrics** measuring video ad delivery and viewability outcomes across the three IVT-filtering tiers.

**Video Engagement Report — 30 metrics** measuring quartile completion (First Quartile, Midpoint, Third Quartile, Completion), Average Playback Duration, and Audibility Rate across the three IVT-filtering tiers.

For complete metric definitions, see [**Video Viewability & Video Engagement Metrics**](https://www.pixalate.com/knowledgebase/video-viewability-video-engagement-metrics).

* * *

Related Resources

  * [Video Viewability & Video Engagement Metrics](https://www.pixalate.com/knowledgebase/video-viewability-video-engagement-metrics) — full metric-by-metric definitions
  * Pixalate’s Description of Methodology (request via your Pixalate contact for the current version)
  * IAB Tech Lab — [VAST specifications](https://iabtechlab.com/standards/vast/)
  * IAB Tech Lab — [Open Measurement SDK (OM SDK)](https://iabtechlab.com/standards/open-measurement-sdk/)
  * Media Rating Council — [Video Viewable Impression Measurement Guidelines](https://www.mediaratingcouncil.org/)

* * *

_Last updated: 2026-06-02 | Version 2.0_
