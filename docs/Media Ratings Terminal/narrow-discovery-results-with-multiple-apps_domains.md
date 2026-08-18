---
title: "Narrow Discovery Results with Multiple Apps/Domains"
excerpt: "Narrow down Discovery results using Device and Region filters to only display one entry per app/domain."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

When generating discovery reports or importing domains/apps lists, the results often include what looks to be multiple entries (rows) of the same app/domain name. This is caused by separate entries for different regions and devices. This guide will show you how to narrow down the results so that these lists do not include multiple entries of the same app/domain.

### Step 1: Determine your preferred device filter

The App and Domain Discovery reports include a filter for Device type with the following options:

#### Available for Apps

  * **Smartphone** \- Only reports data that has been detected as coming from smartphones such as iPhone, Samsung Galaxy, or Google Pixel.

  * **Tablet** \- Only reports data that has been detected as coming from a tablet such as iPad, Samsung Galaxy Tab, or Google Pixel Slate.

  * **Smartphone & Tablet** \- Selecting this filter will report entries from both Smartphones and Tablets separately.

  * **All** \- Selecting ‘All’ reports all data for a specific application’s identifier within one entry, regardless of OS or device it was detected on.

#### Available for Domain

  * **Desktop** \- Only reports data that has been detected coming from devices known to run desktop operating systems (OS) such as Windows, MacOS, and Linux.

  * **Mobile** \- Only reports data that has been detected coming from devices known to run mobile operating systems (OS) such as iOS, Android, and Windows 10 Mobile.

  * **Desktop & Mobile** \- Selecting this filter will report entries from both Desktop and Mobile devices separately.

  * **All** \- Selecting ‘All’ reports all data for a specific domain within one entry, regardless of OS or device it was detected on.

Examples of data included in ‘All’ but not the other filter categories include CTV and other data where the device/OS was unknown.

#### Deciding which Device filter is best

When determining which filter category to select, consider whether your media buy will restrict delivery to specific devices. If your partners are contractually obligated to only deliver to apps on smartphones, then selecting ‘Smartphone’ would be the most representative of the data. However, it is not uncommon for purchase agreements to not specify device restrictions. In addition, it is possible for devices to be misrepresented by inventory providers. With this in mind, it is recommended to select ‘All’ for the most comprehensive data that will show all signs of risk.

Selecting a combined filter (i.e. Smartphone & Tablet or Desktop & Mobile) will still report a separate entry for the same app/domain for each device type.

#### Step 2: Determine your preferred region filter

The App and Domain Discovery reports include a filter for Region type with the following options:

#### Available for Apps

  * **North America** \- Reports data that has been detected as coming from Canada or United States. For Mexico: see LATAM.

  * **EMEA** \- Reports data that has been detected as coming from Europe, Middle East, and Africa.

  * **LATAM** \- Reports data that has been detected as coming from Latin America, which includes Mexico as well as other countries within Central and South America.

  * **APAC** \- Reports data that has been detected as coming from Asia Pacific countries.

  * **GLOBAL** \- Selecting ‘GLOBAL’ reports all data for a specific application’s identifier, regardless of detected country/region.

#### Available for Domain

  * **US** \- Only reports data that has been detected coming from the United States.

  * **International** \- Reports data for all locations other than the United States.

  * **GLOBAL** \- Selecting ‘GLOBAL’ reports all data for a specific domain, regardless of detected country/region.

#### Deciding which Region filter is best

When determining which filter category to select, consider whether your media buy will restrict delivery to specific locations. If your partners are contractually obligated to only deliver to specific locations, selecting those regions would be most representative of the data. However, keep in mind reviewing data globally will provide the most comprehensive data on all signs of risk.
