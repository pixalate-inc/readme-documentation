---
title: "Video Viewability & Video Engagement Metrics (Beta)"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Pixalate's Video Viewability (VV)(Beta) and Video Engagement (VE)(Beta) reports provide 54 metrics across three IVT-filtering tiers, delivering comprehensive visibility into video ad delivery, viewability outcomes, and engagement performance. Measurement is performed in accordance with MRC Video Impression Guidelines, with audibility detection powered by OM SDK signals.

Both reports are available under **Pre-Set Reports** in Pixalate Analytics, for general reported metrics across all Pixalate reports, see [Reported Metrics](about:blank).

* * *

### Video Viewability Report — 24 Metrics

The Video Viewability report measures video ad delivery and viewability outcomes: how many video impressions were rendered, how many could be measured, and whether they met MRC viewability requirements.

### Gross (Prior to Removal of IVT)

**#** |  **Metric** |  **Definition**  
---|---|---  
1 |  Gross Ad Counts (Video) |  The total number of recorded video ad content count-on-download events; prior to removal of IVT.  
2 |  Gross Rendered Video Impressions (VV) |  The total number of impressions eligible for video-viewability (VV) decisioning, recorded in a manner consistent with MRC Video Impression Guidelines, post-buffer/playback; prior to removal of IVT.  
3 |  Gross Measured Video Impressions |  The total number of Rendered Video Impressions (VV) in which Pixalate's technology was capable of measuring for Viewability; prior to removal of IVT.  
4 |  Gross Measured Video Impressions % |  The percentage of Rendered Video Impressions (VV) in which Pixalate's technology was capable of measuring for Viewability; prior to removal of IVT.  
  
### Net of GIVT

**#** |  **Metric** |  **Definition**  
---|---|---  
5 |  Ad Counts (Video) |  The total number of recorded video ad content count-on-download events; net of GIVT.  
6 |  Rendered Video Impressions (VV) |  The total number of impressions eligible for video-viewability (VV) decisioning, recorded in a manner consistent with MRC Video Impression Guidelines, post-buffer/playback; net of GIVT.  
7 |  Measured Video Impressions |  The total number of Rendered Video Impressions (VV) in which Pixalate's technology was capable of measuring for Video Viewability; net of GIVT.  
8 |  Measured Video Impressions % |  The percentage of Rendered Video Impressions (VV) in which Pixalate's technology was capable of measuring for Video Viewability; net of GIVT.  
9 |  Viewable Video Impressions |  The total number of Measured Video Impressions that were determined to be Viewable Video Impressions; net of GIVT.  
10 |  Non-Viewable Video Impressions |  The total number of Measured Video Impressions that were determined to not meet the requirements of a Viewable Video Impression; net of GIVT.  
11 |  Undetermined Video Impressions |  The total number of Rendered Video Impressions (VV) in which Pixalate's technology was NOT able to determine if the Video Ad Impression met the requirements of a Viewable Video Impression; net of GIVT.  
12 |  Undetermined Video Impressions % |  The percentage of Rendered Video Impressions (VV) in which Pixalate's technology was NOT able to determine if the Video Ad Impression met the requirements of a Viewable Video Impression; net of GIVT.  
13 |  Video Views % |  The percentage of Rendered Video Impressions (VV) that were determined to be Viewable Video Impressions; net of GIVT.  
14 |  Video Non-Views % |  The percentage of Rendered Video Impressions (VV) that were determined to not meet the requirements of a Viewable Video Impression; net of GIVT.  
  
### Net of All IVT

**#** |  **Metric** |  **Definition**  
---|---|---  
15 |  Net Ad Counts (Video) |  The total number of recorded video ad content count-on-download events; net of all IVT.  
16 |  Net Rendered Video Impressions (VV) |  The total number of impressions eligible for video-viewability (VV) decisioning, recorded in a manner consistent with MRC Video Impression Guidelines, post-buffer/playback; net of all IVT.  
17 |  Net Measured Video Impressions |  The total number of Rendered Video Impressions (VV) in which Pixalate's technology was capable of measuring for Video Viewability; net of all IVT.  
18 |  Net Measured Video Impressions % |  The percentage of Rendered Video Impressions (VV) in which Pixalate's technology was capable of measuring for Video Viewability; net of all IVT.  
19 |  Net Viewable Video Impressions |  The total number of Measured Video Impressions that were determined to be Viewable Video Impressions; net of all IVT.  
20 |  Net Non-Viewable Video Impressions |  The total number of Measured Video Impressions that were determined to not meet the requirements of a Viewable Video Impression; net of all IVT.  
21 |  Net Undetermined Video Impressions |  The total number of Rendered Video Impressions (VV) in which Pixalate's technology was NOT able to determine if the Video Ad Impression met the requirements of a Viewable Video Impression; net of all IVT.  
22 |  Net Undetermined Video Impressions % |  The percentage of Rendered Video Impressions (VV) in which Pixalate's technology was NOT able to determine if the Video Ad Impression met the requirements of a Viewable Video Impression; net of all IVT.  
23 |  Net Video Views % |  The percentage of Rendered Video Impressions (VV) that were determined to be Viewable Video Impressions; net of all IVT.  
24 |  Net Video Non-Views % |  The percentage of Rendered Video Impressions (VV) that were determined to not meet the requirements of a Viewable Video Impression; net of all IVT.  

* * *

#### Video Engagement Report — 30 Metrics

The Video Engagement report measures how users interact with video ad content: quartile completion, full playback, average duration, and audibility.

### Gross (Prior to Removal of IVT)

**#** |  **Metric** |  **Definition**  
---|---|---  
1 |  Gross First Quartile |  The total number of times the first quartile of video content has completed playback; prior to removal of IVT.  
2 |  Gross First Quartile % |  The percentage of times the first quartile of video content has completed playback; prior to removal of IVT.  
3 |  Gross Midpoint |  The total number of times the midpoint video content (quartile 2/4) has completed playback; prior to removal of IVT.  
4 |  Gross Midpoint % |  The percentage of times the midpoint video content (quartile 2/4) has completed playback; prior to removal of IVT.  
5 |  Gross Third Quartile |  The total number of times the third quartile of video content has completed playback; prior to removal of IVT.  
6 |  Gross Third Quartile % |  The percentage of times the third quartile of video content has completed playback; prior to removal of IVT.  
7 |  Gross Video Completions |  The total number of times video content has completed full video playback; prior to removal of IVT.  
8 |  Gross Video Completion % |  The percentage of times video content has completed full video playback; prior to removal of IVT.  
9 |  Gross Average Playback |  The average amount of playback time across video ad content; prior to removal of IVT.  
10 |  Gross Audibility Rate |  The percentage of video ad content determined to have audibility turned on, as signaled via OM SDK; prior to removal of IVT.  
  
### Net of GIVT

**#** |  **Metric** |  **Definition**  
---|---|---  
11 |  First Quartile |  The total number of times the first quartile of video content has completed playback; net of GIVT.  
12 |  First Quartile % |  The percentage of times the first quartile of video content has completed playback; net of GIVT.  
13 |  Midpoint |  The total number of times the midpoint video content (quartile 2/4) has completed playback; net of GIVT.  
14 |  Midpoint % |  The percentage of times the midpoint video content (quartile 2/4) has completed playback; net of GIVT.  
15 |  Third Quartile |  The total number of times the third quartile of video content has completed playback; net of GIVT.  
16 |  Third Quartile % |  The percentage of times the third quartile of video content has completed playback; net of GIVT.  
17 |  Video Completions |  The total number of times video content has completed full video playback; net of GIVT.  
18 |  Video Completion % |  The percentage of times video content has completed full video playback; net of GIVT.  
19 |  Average Playback |  The average amount of playback time across video ad content; net of GIVT.  
20 |  Audibility Rate |  The percentage of video ad content determined to have audibility turned on, as signaled via OM SDK; net of GIVT.  
  
### Net of All IVT

**#** |  **Metric** |  **Definition**  
---|---|---  
21 |  Net First Quartile |  The total number of times the first quartile of video content has completed playback; net of all IVT.  
22 |  Net First Quartile % |  The percentage of times the first quartile of video content has completed playback; net of all IVT.  
23 |  Net Midpoint |  The total number of times the midpoint video content (quartile 2/4) has completed playback; net of all IVT.  
24 |  Net Midpoint % |  The percentage of times the midpoint video content (quartile 2/4) has completed playback; net of all IVT.  
25 |  Net Third Quartile |  The total number of times the third quartile of video content has completed playback; net of all IVT.  
26 |  Net Third Quartile % |  The percentage of times the third quartile of video content has completed playback; net of all IVT.  
27 |  Net Video Completions |  The total number of times video content has completed full video playback; net of all IVT.  
28 |  Net Video Completion % |  The percentage of times video content has completed full video playback; net of all IVT.  
29 |  Net Average Playback |  The average amount of playback time across video ad content; net of all IVT.  
30 |  Net Audibility Rate |  The percentage of video ad content determined to have audibility turned on, as signaled via OM SDK; net of all IVT.  

* * *

#### Glossary

**Term** |  **Definition**  
---|---  
Rendered Video Impressions (VV) |  Video impressions eligible for viewability decisioning, recorded post-buffer/playback per MRC guidelines.  
Measured Video Impressions |  Rendered impressions where Pixalate's technology could measure viewability.  
Viewable Video Impressions |  Measured impressions meeting MRC viewability requirements.  
GIVT |  General Invalid Traffic  
SIVT |  Sophisticated Invalid Traffic  
IVT |  Invalid Traffic (includes both General and Sophisticated).  
OM SDK |  Open Measurement SDK — IAB Tech Lab standard for third-party viewability and verification measurement.  
VAST |  Video Ad Serving Template — IAB standard for serving video ads.  
MRC |  Media Rating Council, Inc.
