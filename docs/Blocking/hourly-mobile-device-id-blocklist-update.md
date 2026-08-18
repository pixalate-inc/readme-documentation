---
title: "Hourly Mobile Device ID Blocklist Update"
excerpt: "Effective December 2, 2025, Pixalate introduced hourly updates to our Mobile Device ID blocklist, delivering enhanced precision in SIVT detection with an optimized datafeed architecture for faster ingestion and processing."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

**What Changed?**

**Hourly Blocklist Updates****  
**Our Mobile Device ID blocklist now refreshes every hour (enhanced from twice daily), enabling faster response to emerging invalid traffic patterns and significantly reducing exposure windows to new IVT threats.

**Enhanced Detection Logic****  
**Updated algorithms provide superior accuracy by prioritizing device IDs with demonstrated high-impact IVT contribution, resulting in a more targeted and efficient blocklist.

**Optimized File****  
**The refined datafeed maintains comprehensive IVT coverage while reducing file size, streamlining ingestion without compromising protection efficacy. This optimization enables faster processing within your existing blocking workflows.

#### **What's the Anticipated Impact?**

**Enhanced Protection Timeline****  
**High-risk device IDs can now be identified and blocked within hours rather than half a day, improving your proactive defense against sophisticated invalid traffic patterns.

**Streamlined Integration****  
**Smaller file sizes enable faster downloads and processing, reducing ingestion overhead while maintaining the same comprehensive IVT coverage you rely on today.

**Seamless Transition****  
**The file naming convention and data schema remain unchanged, ensuring zero disruption to your existing pre-bid blocking workflows.

#### **What Do You Need To Do?**

**For Clients Using Hourly Polling (Recommended)****  
**If you currently poll Pixalate's FTP server every hour, no action is required. Your system will automatically receive the new hourly updates. Continue to reference the "last modified date" to determine when new files are available.

**For Clients Polling Less Frequently****  
**If you poll less than hourly, you'll automatically benefit from more current data without any integration changes. However, to maximize the value of hourly updates, consider increasing your polling frequency.

**Processing Differential Updates****  
**For optimal bandwidth and processing efficiency, we recommend implementing differential update logic:

  * Compare the "last modified date" on the FTP server before downloading
  * Process only net-new device ID additions since your last ingestion
  * This approach minimizes bandwidth usage while ensuring real-time protection

**Infrastructure Considerations****  
**To prepare for the new hourly cadence:

  * Ensure sufficient bandwidth to accommodate hourly updates
  * Verify storage capacity can handle the increased refresh frequency
  * Confirm your ingestion systems support hourly scheduling (if not already configured)

**Additional Information**

**Expanding Your Pre-Bid Protection****  
**If you'd like to explore additional coverage options or discuss how Pixalate's pre-bid blocking solutions can further enhance your traffic quality strategy, please contact your dedicated Customer Success Manager or Sales Representative.

**CTV Device ID Blocklist****  
**These enhancements are specific to Mobile Device ID datafeeds. Connected TV Device ID blocklist updates follow their existing schedule. Please contact your Customer Success Manager if you'd like to discuss CTV Device ID coverage expansion.

#### **Questions or Need Assistance?**

For technical implementation guidance or to discuss how hourly updates can enhance your specific pre-bid blocking workflow, please contact your dedicated Customer Success Manager.

We're here to ensure a seamless transition and help you maximize the value of these enhancements.
