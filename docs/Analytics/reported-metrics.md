---
title: Reported Metrics
excerpt: >-
  Definitions of the metrics available in Analytics reports, organised by gross,
  GIVT-filtered and IVT-filtered reporting tiers.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---
#### Dashboard Analytics - Reported Metrics/Definitions

The table below represents metrics available and common among basic reports. Specialized reports such as Supply Path Optimization, Compliance, Brand Safety, Geolocation and others have specialized metrics available.

Combined metrics including specialized reports equal roughly 250+ data points available for granular reporting.

**Video Viewability(Beta) & Video Engagement Metrics (Beta):** For the complete metric definitions for the Video Viewability and Video Engagement pre-set reports (54 metrics across 3 IVT-filtering tiers), see the dedicated [Video Viewability & Video Engagement Metrics](/knowledgebase/video-viewability-video-engagement-metrics) page.

| Gross: Pre-Removal of Invalid Traffic (IVT) - General Invalid Traffic (GIVT) or Sophisticated Invalid Traffic (SIVT) |
| -------------------------------------------------------------------------------------------------------------------- |

<Table>
  <thead>
    <tr>
      <th>
        **Metric Name**
      </th>

      <th>
        **Metric Definition**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Gross Ad Counts
      </td>

      <td>
        The total number of Ad Counts before removal of invalid traffic (IVT). This metric aligns with the MRC's definition of 'Gross Tracked Ads' and includes 1x1 pixel and JS traffic recorded via a 'Count on Download' approach (before removal of IVT). This metric may also include server-side-ad-insertion (SSAI) traffic which is unable to be identified - deterministically - as being recorded via a client-side, 'Count on Download' approach.

        This metric reflects the following counts:

        1x1 pixel display traffic recorded in a manner consistent with the MRC's definition of a "Count on Download" measurement approach (before removal of IVT);
        JavaScript-tagged display traffic recorded in a manner consistent with the MRC's definition of a "Count on Download" measurement approach (before removal of IVT);
        Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); before removal of IVT.
        Notes

        Due to the inherent nature of 1x1 pixel display traffic, such traffic is unable to be evaluated on the basis of the MRC's definition of a "Begin to Render" impression measurement approach;
        JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach, will be reflected in the 'Rendered Display Impressions' and 'Rendered Impressions' metric sets accordingly.
        Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame) will be reflected in the 'Rendered Video Impressions' and 'Rendered Impressions' metric sets accordingly.
      </td>
    </tr>

    <tr>
      <td>
        Gross Rendered Impressions
      </td>

      <td>
        The total number of Rendered Ad Impressions (Display & Video); before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Rendered Display Impressions
      </td>

      <td>
        The total number of Rendered Display Impressions recorded from Pixalate’s enhanced script technology (excludes 1x1 pixel impressions); before removal of IVT. This metric set reflects the following counts:

        JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach (before removal of IVT);
        Notes

        This metric set excludes video, 1x1 pixel display Impressions and JavaScript-tagged display traffic not determined to have rendered via Pixalate's enhanced JS solution.
        JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach, will be reflected in the 'Rendered Display Impressions' and 'Rendered Impressions' metric sets accordingly.
      </td>
    </tr>

    <tr>
      <td>
        Gross Rendered Video Impressions
      </td>

      <td>
        <br />The total number of Rendered Video Impressions; before removal of IVT. This metric set reflects the following counts:

        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Share of Gross Ad Counts %
      </td>

      <td>
        The percentage distribution of Ad Counts in relation to total Ad Counts; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross SSAI Ad Counts
      </td>

      <td>
        Estimated total SSAI Ad Counts, before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross SSAI Transparent Ad Counts
      </td>

      <td>
        Estimated total SSAI Ad Counts that come from proxies passing X-Device-User-Agent headers for more transparency, before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross SSAI Ad Counts %
      </td>

      <td>
        Estimated percentage of Ad Counts that correspond to SSAI proxies, before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross SSAI Transparent Ad Counts %
      </td>

      <td>
        Estimated percentage of Ad Counts that correspond to SSAI and come from proxies passing X-Device-User-Agent headers for more transparency, before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross IPv6 Ad Counts
      </td>

      <td>
        The total number of IPv6 Ad Counts before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross IPv6 Ad Counts %
      </td>

      <td>
        The percentage of IPv6 Ad Counts from total Ad Counts before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Clicks
      </td>

      <td>
        The total number of measured Clicks; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross CTR
      </td>

      <td>
        The percentage of measured Clicks divided by Ad Counts; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Matched Clicks
      </td>

      <td>
        The total number of measured Clicks that were matched to an Ad Count; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Conversions
      </td>

      <td>
        The total number of measured Actions (e.g., purchasing an item) related to Ads; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Conversion Rate
      </td>

      <td>
        The percentage of measured Actions (e.g., purchasing an item) related to Ads; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Matched Conversions
      </td>

      <td>
        The total number of Conversions that were matched to an Ad Count; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Matched C-Convs
      </td>

      <td>
        Click-through Conversions. The total number of matched Conversions in which users clicked on the Ad, visited the website and performed an action (e.g., purchasing an item); before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Matched V-Convs
      </td>

      <td>
        View-through Conversions. The total number of matched Conversions in which users took action at a later time after seeing a viewable impression; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Gross Reach
      </td>

      <td>
        The total number of uniquely identified browser cookies; before removal of IVT.
      </td>
    </tr>

    <tr>
      <td>
        Ad Exposure Time
      </td>

      <td>
        The amount of time Ad is visible to the user on the web page. Ad exposure is measured in minutes and seconds.
      </td>
    </tr>

    <tr>
      <td>
        Ad Exposure
      </td>

      <td>
        The percentage of total time spent on a web page in which the Ad was visible to the user.
      </td>
    </tr>

    <tr>
      <td>
        Ad Hover
      </td>

      <td>
        The average amount of time that users hovered over the Ad with the mouse cursor (expressed in minutes:seconds.milliseconds).
      </td>
    </tr>

    <tr>
      <td>
        Ads Above the Fold
      </td>

      <td>
        The total number of Ad Counts that were determined to be served within the user’s browser viewport.
      </td>
    </tr>

    <tr>
      <td>
        Bid Price
      </td>

      <td>
        The average bid price for Ad Counts.
      </td>
    </tr>

    <tr>
      <td>
        Media Spend
      </td>

      <td>
        The total media spend of all Ad Counts is based on the recorded price paid.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

| **Net of GIVT** |
| --------------- |

<Table>
  <thead>
    <tr>
      <th>
        **Metric Name**
      </th>

      <th>
        **Metric Definition**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Ad Counts
      </td>

      <td>
        The total number of Ad Counts after removal of General Invalid traffic (GIVT). This metric aligns with the MRC's definition of 'Net Tracked Ads' and includes 1x1 pixel and JS traffic recorded via a 'Count on Download' approach (after the removal of GIVT). This metric may also include server-side-ad-insertion (SSAI) traffic which is unable to be identified - deterministically - as being recorded via a client-side, 'Count on Download' approach.

        This metric reflects the following counts:

        - 1x1 pixel display traffic recorded in a manner consistent with the MRC's definition of a "Count on Download" measurement approach (net of GIVT);
        - JavaScript-tagged display traffic recorded in a manner consistent with the MRC's definition of a "Count on Download" measurement approach (net of GIVT);
        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); net of GIVT.

        Notes

        - Due to the inherent nature of 1x1 pixel display traffic, such traffic is unable to be evaluated on the basis of the MRC's definition of a "Begin to Render" impression measurement approach;
        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach, will be reflected in the 'Rendered Display Impressions' and 'Rendered Impressions' metric sets accordingly.
        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame) will be reflected in the 'Rendered Video Impressions' and 'Rendered Impressions' metric sets accordingly.
      </td>
    </tr>

    <tr>
      <td>
        Rendered Impressions
      </td>

      <td>
        The total number of Rendered Impressions (Display & Video); after removal of GIVT. This metric set reflects the following counts:

        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach (net of GIVT);
        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Rendered Display Impressions
      </td>

      <td>
        The total number of Rendered Display Impressions recorded from Pixalate’s enhanced script technology (excludes 1x1 pixel impressions); after removal of GIVT. This metric set reflects the following counts:

        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach (net of GIVT);

        Notes

        - This metric set excludes video, 1x1 pixel display Impressions and JavaScript-tagged display traffic not determined to have rendered via Pixalate's enhanced JS solution.
        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach, will be reflected in the 'Rendered Display Impressions' and 'Rendered Impressions' metric sets accordingly.
      </td>
    </tr>

    <tr>
      <td>
        Rendered Video Impressions
      </td>

      <td>
        The total number of Rendered Video Impressions; after removal of GIVT. This metric set reflects the following counts:

        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Share of Ad Counts %
      </td>

      <td>
        The percentage of Ad Counts after the removal of General Invalid Traffic in relation to total Ad Counts; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Ad Counts
      </td>

      <td>
        Estimated total SSAI Ad Counts, excluding GIVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Transparent Ad Counts
      </td>

      <td>
        Estimated total SSAI Ad Counts that come from proxies passing X-Device-User-Agent headers for more transparency, excluding GIVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Ad Counts %
      </td>

      <td>
        Estimated percentage of Ad Counts that correspond to SSAI proxies, excluding GIVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Transparent Ad Counts %
      </td>

      <td>
        Estimated percentage of Ad Counts that correspond to SSAI and come from proxies passing X-Device-User-Agent headers for more transparency, excluding GIVT.
      </td>
    </tr>

    <tr>
      <td>
        IPv6 Ad Counts
      </td>

      <td>
        The total number of IPv6 Ad Counts, excluding GIVT.
      </td>
    </tr>

    <tr>
      <td>
        IPv6 Ad Counts %
      </td>

      <td>
        The percentage of IPv6 Ad Counts from total Ad Counts, excluding GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Measured Impressions
      </td>

      <td>
        The total number of Rendered Display Impressions in which Pixalate’s technology was capable of measuring for Viewability; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Measured Rate %
      </td>

      <td>
        The percentage of Rendered Display Impressions in which Pixalate’s technology was capable of measuring for Viewability; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Views
      </td>

      <td>
        The total number of Measured Impressions that were determined to be Viewable Impressions; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Viewability %
      </td>

      <td>
        The percentage of Measured Impressions that were determined to be Viewable Impressions; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Non Views
      </td>

      <td>
        The total number of Measured Impressions that were determined to not meet the requirements of a Viewable Impression; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Undetermined Imps
      </td>

      <td>
        The total number of Rendered Display Impressions in which Pixalate’s technology was NOT able to determine if the Ad Impression met the requirements of a Viewable Impression; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Views %
      </td>

      <td>
        The percentage of Rendered Display Impressions that were determined to be Viewable Impressions; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Non Views %
      </td>

      <td>
        The percentage of Rendered Display Impressions that were determined to not meet the requirements of a Viewable Impression; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Undetermined Imps %
      </td>

      <td>
        The percentage of Rendered Display Impressions in which Pixalate’s technology was NOT able to determine if the Ad Impression met the requirements of a Viewable Impression; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Clicks
      </td>

      <td>
        The total number of measured clicks; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        CTR
      </td>

      <td>
        The percentage of matched clicks divided by Ad Counts; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Matched Clicks
      </td>

      <td>
        The total number of measured clicks that were matched to an Ad Count; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Conversions
      </td>

      <td>
        The total number of measured actions (e.g., purchasing an item) related to Ads; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Matched Conversions
      </td>

      <td>
        The total number of conversions that were matched to an Ad Count; net of GIVT.
      </td>
    </tr>

    <tr>
      <td>
        Reach
      </td>

      <td>
        The total number of uniquely identified visitors; net of GIVT.
      </td>
    </tr>
  </tbody>
</Table>

| **Net of all IVT - (GIVT & SIVT)** |
| ---------------------------------- |

<Table>
  <thead>
    <tr>
      <th>
        **Metric Name**
      </th>

      <th>
        **Metric Definition**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Net Ad Counts
      </td>

      <td>
        The total number of Ad Counts after removal of all Invalid traffic (IVT). This metrics' aligns with the MRC's definition of 'Total Net Tracked Ads' and includes 1x1 pixel and JS traffic recorded via a 'Count on Download' approach (net of all IVT). This metric may also include server-side-ad-insertion (SSAI) traffic which is unable to be identified - deterministically - as being recorded via a client-side, 'Count on Download' approach.

        This metric set reflects the following counts:

        - 1x1 pixel display traffic recorded in a manner consistent with the MRC's definition of a "Count on Download" measurement approach (net of all IVT);
        - JavaScript-tagged display traffic recorded in a manner consistent with the MRC's definition of a "Count on Download" measurement approach (net of all IVT);
        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); net of all IVT.

        Notes

        - Due to the inherent nature of 1x1 pixel display traffic, such traffic is unable to be evaluated on the basis of the MRC's definition of a "Begin to Render" impression measurement approach;
        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach, will be reflected in the 'Rendered Display Impressions' and 'Rendered Impressions' metric sets accordingly.
        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame) will be reflected in the 'Rendered Video Impressions' and 'Rendered Impressions' metric sets accordingly.
      </td>
    </tr>

    <tr>
      <td>
        Net Rendered Impressions
      </td>

      <td>
        The total number of Rendered Impressions (Display & Video); after removal of all IVT. This metric set reflects the following counts:

        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach (net of all IVT);
        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Rendered Display Impressions
      </td>

      <td>
        The total number of Rendered Display Impressions recorded from Pixalate’s enhanced script technology (excludes 1x1 pixel impressions); after removal of all IVT. This metric set reflects the following counts:

        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach (net of all IVT);

        Notes

        - This metric set excludes video, 1x1 pixel display Impressions and JavaScript-tagged display traffic not determined to have rendered via Pixalate's enhanced JS solution.
        - JavaScript-tagged display traffic determined to have begun to render in a manner consistent with the MRC's definition of a "Begin to Render" impression recording approach, will be reflected in the 'Rendered Display Impressions' and 'Rendered Impressions' metric sets accordingly.
      </td>
    </tr>

    <tr>
      <td>
        Net Rendered Video Impressions
      </td>

      <td>
        The total number of Rendered Video Impressions; net of all IVT. This metric set reflects the following counts:

        - Video traffic recorded in a manner consistent with the MRC's definition of a video impression (post-buffer/render of first video frame); net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Share of Net Ad Counts %
      </td>

      <td>
        The percentage of Ad Counts after the removal of all Invalid Traffic in relation to total Net Ad Counts; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Net Ad Counts
      </td>

      <td>
        Estimated total SSAI Ad Counts, excluding IVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Net Transparent Ad Counts
      </td>

      <td>
        Estimated total SSAI Ad Counts that come from proxies passing X-Device-User-Agent headers for more transparency, excluding IVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Net Ad Counts %
      </td>

      <td>
        Estimated percentage of Ad Counts that correspond to SSAI proxies, excluding IVT.
      </td>
    </tr>

    <tr>
      <td>
        SSAI Net Transparent Ad Counts %
      </td>

      <td>
        Estimated percentage of Ad Counts that correspond to SSAI and come from proxies passing X-Device-User-Agent headers for more transparency, excluding IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net IPv6 Ad Counts
      </td>

      <td>
        The total number of IPv6 Ad Counts, excluding IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net IPv6 Ad Counts %
      </td>

      <td>
        The percentage of IPv6 Ad Counts from total Ad Counts, excluding IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Measured Impressions
      </td>

      <td>
        The total number of Rendered Display Impressions in which Pixalate’s technology was capable of measuring for Viewability; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Measured Rate %
      </td>

      <td>
        The percentage of Rendered Display Impressions in which Pixalate’s technology was capable of measuring for Viewability; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Views
      </td>

      <td>
        The total number of Measured Impressions that were determined to be Viewable Impressions; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Viewability %
      </td>

      <td>
        The percentage of Measured Impressions that were determined to be Viewable Impressions; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Non Views %
      </td>

      <td>
        The percentage of Rendered Display Impressions that were determined to not meet the requirements of a Viewable Impression; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Non Views
      </td>

      <td>
        The total number of Measured Impressions that were determined to not meet the requirements of a Viewable Impression; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Undetermined Imps
      </td>

      <td>
        The total number of Rendered Display Impressions in which Pixalate’s technology was NOT able to determine if the Ad Impression met the requirements of a Viewable Impression; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Views %
      </td>

      <td>
        The percentage of Rendered Display Impressions that were determined to be Viewable Impressions; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Undetermined Imps %
      </td>

      <td>
        The percentage of Rendered Display Impressions in which Pixalate’s technology was NOT able to determine if the Ad Impression met the requirements of a Viewable Impression; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Clicks
      </td>

      <td>
        The number of measured Clicks; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net CTR
      </td>

      <td>
        The percentage of matched Clicks divided by Ad Counts; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Matched Clicks
      </td>

      <td>
        The number of measured Clicks that were matched to an Ad Count; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        Net Conversions
      </td>

      <td>
        The total number of measured Actions (e.g., purchasing an item) related to Ads; net of all IVT
      </td>
    </tr>

    <tr>
      <td>
        Net Matched Conversions
      </td>

      <td>
        The total number of Conversions that were matched to an Ad Count; net of all IVT
      </td>
    </tr>

    <tr>
      <td>
        Net Matched V-Conversions
      </td>

      <td>
        View-through Conversions. The total number of matched conversions in which users took action at a later time after seeing a viewable impression; net of all IVT.
      </td>
    </tr>

    <tr>
      <td>
        TruReach
      </td>

      <td>
        The number of uniquely identified visitors; net of all IVT.
      </td>
    </tr>
  </tbody>
</Table>

| **Filtered for GIVT** |
| --------------------- |

| **Metric Name**            | **Metric Definition**                                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------- |
| GIVT Ad Counts             | The number of Gross Ad Counts that were filtered as General Invalid Traffic (GIVT).                  |
| GIVT Ad Counts %           | The percentage of Gross Ad Counts that were filtered as GIVT.                                        |
| Share of GIVT Ad Counts %  | The percentage of Gross Ad Counts that were filtered as GIVT; in relation to total GIVT filtered.    |
| GIVT Traffic               | The total number of Gross Ad Counts, Gross Clicks, and Gross Conversions that were filtered as GIVT. |
| GIVT %                     | The percentage of Gross Ad Counts, Gross Clicks, and Gross Conversions that were filtered as GIVT.   |
| IPv6 GIVT Ad Counts        | The total number of IPv6 Ad Counts that were filtered as GIVT.                                       |
| IPv6 GIVT Ad Counts %      | The percentage of the total number of IPv6 Ad Counts that were filtered as GIVT.                     |
| Malware Traffic            | The number of Gross Ad Counts that were determined to be generated by Malware.                       |
| Phishing Traffic           | The number of Gross Ad Counts that were determined to be generated by Phishing activity.             |
| GIVT Clicks                | The total number of Gross Clicks that were filtered as GIVT.                                         |
| GIVT Clicks %              | The percentage of Gross Clicks that were filtered as GIVT.                                           |
| GIVT Matched Clicks        | The number of Gross Matched Clicks that were filtered as GIVT.                                       |
| GIVT Matched Clicks %      | The percentage of Gross Matched Clicks that were filtered as GIVT.                                   |
| GIVT Conversions           | The number of Gross Conversions that were filtered as GIVT.                                          |
| GIVT Conversions %         | The percentage of Gross Conversions that were filtered as GIVT.                                      |
| GIVT Matched Conversions   | The number of Gross Matched Conversions that were filtered as GIVT.                                  |
| GIVT Matched Conversions % | The percentage of Gross Matched Conversions that were filtered as GIVT.                              |

| **Filtered for SIVT** |
| --------------------- |

| **Metric Name**            | **Metric Definition**                                                                                             |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| SIVT Ad Counts             | The number of Gross Ad Counts that were filtered as Sophisticated Invalid Traffic (SIVT).                         |
| SIVT Ad Counts %           | The percentage of Gross Ad Counts that were filtered as SIVT.                                                     |
| Share of SIVT Ad Counts %  | The percentage of Gross Ad Counts that were filtered as SIVT; in relation to total SIVT filtered.                 |
| SIVT Traffic               | The total number of Gross Ad Counts, Gross Clicks, and Gross Conversions that were filtered as SIVT.              |
| SIVT %                     | The percentage of Gross Ad Counts, Gross Clicks, and Gross Conversions that were filtered as SIVT.                |
| IPv6 SIVT Ad Counts        | The total number of IPv6 Ad Counts that were filtered as SIVT.                                                    |
| IPv6 IVT Ad Counts         | The total number of IPv6 Ad Counts that were filtered as IVT.                                                     |
| IPv6 SIVT Ad Counts %      | The percentage of the total number of IPv6 Ad Counts that were filtered as SIVT.                                  |
| IPv6 IVT Ad Counts %       | The percentage of IPv6 Ad Counts that were filtered as IVT.                                                       |
| SIVT Clicks                | The number of Gross Clicks that were filtered as SIVT.                                                            |
| SIVT Clicks %              | The percentage of Gross Clicks that were filtered as SIVT.                                                        |
| SIVT Matched Clicks        | The number of Gross Matched Clicks that were filtered as SIVT.                                                    |
| SIVT Matched Clicks %      | The percentage of Gross Matched Clicks that were filtered as SIVT.                                                |
| SIVT Conversions           | The number of Gross Conversions that were filtered as SIVT.                                                       |
| SIVT Conversions %         | The percentage of Gross Conversions that were filtered as SIVT.                                                   |
| SIVT Matched Conversions   | The number of Gross Matched Conversions that were filtered as SIVT.                                               |
| SIVT Matched Conversions % | The percentage of Gross Matched Conversions that were filtered as SIVT.                                           |
| IVT %                      | The total percentage of General Invalid Traffic (GIVT) and Sophisticated Invalid Traffic (SIVT).                  |
| Share of IVT Ad Counts %   | The percentage of Gross Ad Counts that were filtered as Invalid Traffic (IVT); in relation to total IVT filtered. |
