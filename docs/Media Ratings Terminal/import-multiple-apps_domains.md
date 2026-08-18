---
title: "Import Multiple Apps/Domains"
excerpt: "Retrieve ratings results for multiple domains or apps at the same time."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

The Importing feature will allow you to pull Pixalate’s category risk assessments for multiple domains or apps simultaneously within the Media Ratings Terminal (MRT) Insight report.The following guide walks you through creating a list of the apps/domains, importing the list, and customising the results, so you only see the categories you care most about.

The insight will need to process apps separately from domains. When creating lists and uploading, be sure you are only creating a list for apps OR domains, not both.

### Step 1: Creating the list

To begin, open your favorite spreadsheet software (ex: Excel, Google Sheets, LibreOffice Calc), create a new sheet, then enter the apps or domains you want information on. You may also open any existing CSV or spreadsheet file, but be sure to remove any additional headings or additional columns before importing, as only one column with the app/domain names is needed. Below is an example of a CSV looking up 5 apps.

![](https://f.hubspotusercontent40.net/hubfs/2364596/b263c525-679f-4e65-a8af-9a917e624d53-png.png)

App importing accepts lists with Android bundle IDs, Apple App IDs, and Apple Bundle IDs

Once you are finished adding the apps or domains, save the file in CSV format. To do this, you may need to go into your spreadsheet’s file menu and select ‘save as’ to ensure the file format is correct. There may be multiple CSV formats available with different encodings. If you are unsure which encoding to save the file in, select the option to encode as UTF-8.

![](https://f.hubspotusercontent40.net/hubfs/2364596/25e4c338-8a3f-40cb-bc7b-e5113670014d-png.png)

### Step 2: Importing the file

Now that your file is ready, go [ratings.pixalate.com](https://ratings.pixalate.com) and navigate to the Insight report at the top and select whether your list is made of domains or App IDs.

![](https://f.hubspotusercontent40.net/hubfs/2364596/d124b3fb-c449-43aa-a3f4-a7658df6267f-png.png)

Next, click the Import button on the right.

![](https://f.hubspotusercontent40.net/hubfs/2364596/7fd0ff94-7df3-4878-9593-b721ef483f68-png.png)

You will then be prompted to browse for the CSV file. Once selected, you will be met with a prompt letting you the report is being generated. Depending on the CSV size, it can take up to 20 minutes to complete the import.

![](https://f.hubspotusercontent40.net/hubfs/2364596/7d10060d-4bf9-4a74-9e42-dcbead2db7ae-png.png)

You may remain on the page or navigate elsewhere. The URL can be saved for later use (up to 7 days) and the report URL will also be emailed to the address on the account when the results are ready.

### Step 3: Refining the results

Once the report is ready, you will be presented with a discovery report of the apps or domains in the list.

![](https://f.hubspotusercontent40.net/hubfs/2364596/fe73c0f5-e788-44ed-99b5-c8e15c11f74b-png.png)

Any apps or domains found without any data will be listed at the top of the report with a link to download those values.

![](https://f.hubspotusercontent40.net/hubfs/2364596/a42d49e2-64d2-41bc-bc03-b1b6c6e74e5a-png.png)

Often, the list may contain what seems like multiple results of the same app or domain. This is the intent, as the results produce a separate row for each individual device type and region along with a row for all (all devices and global) data. To only view one row for each app or domain, narrow down the results by selecting the desired device and region under the detail filter:

![](https://f.hubspotusercontent40.net/hubfs/2364596/81261ee8-0568-4040-b710-a144d2502304-png.png)

‘All’ implies all data we have for the app or website regardless of device. Therefore, selecting ‘All’ devices and ‘Global’ region will provide the most comprehensive data.

At this point, you have the option to refine the list even further, such as if you wanted to determine which apps or domains should be removed from your list. The same filters that are provided in the discovery report are available for filtering. Below is a list of the most popular filters:

### Available for both Apps & Domains

  * **Category** \- The category classification of the app, such as news, travel, or social networking.

  * **Risk** \- Overall low/medium/high risk assessment determined by a review of risk across all comprehensive data points.

  * **IVT %** \- The IVT % threshold is determined by selecting a number between 0 and 100%. The higher the IVT % number, the more IVT detected by PIxalate.

  * **Adult Content Risk** \- Low/medium/high risk assessment of the likelihood the app or domain contains adult content.

### Apps Only

  * **Brand Safety Risk** \- Brand safety risk is determined by the risk of all high brand safety risk categories such as adult, drug, and violence content.

  * **Blocklisted** \- Whether the app’s bundle or app store ID is currently on Pixalate’s High Risk App blocklist.

  * **Viewability Risk** \- A low/medium/high risk assessment is based on the overall % of the application’s viewability performance.

### Domains Only

  * **Ads.txt** \- Whether the domain is hosting a valid ads.txt file.

  * **Viewability** \- The Viewability threshold determined by selecting a number between 0 and 100%. The lower the Viewability % number, the more ads Pixalate is detecting as not viewable.

### Step 4: Downloading the Results

Once the results are refined to your liking, you may download the list to CSV that can be sent to partners or imported into your internal systems. To download this report select download button at the top left, specify the fields you want the CSV to contain, and click ‘Download’.

![](https://f.hubspotusercontent40.net/hubfs/2364596/99ef3de2-fe18-4889-83c3-75bf37b91f9f-png.png)

### Troubleshooting

The list below are some common issues that occur when importing and how you may be able to resolve them.

#### Maximum Limit Error

If your upload maximum limit of apps or domains is reached, you will meet the following error:

![](https://f.hubspotusercontent40.net/hubfs/2364596/1be4e6e5-aa1c-4f5f-879e-49d2855e22bb-png.png)

To correct this error, reduce the number of apps/domains (rows) in the list to equal or below the limit number specified in error and try again.

Due to the amount of bandwidth it takes to generate the data in these lists, we must set a limit on the amount allowed to be uploaded. If you have any questions, please reach out to your [customer service representative](mailto:am@pixalate.com).

#### No Results Found

There may be a few different reasons why no results are returned. Below are a few things to help you get started to solving the issue.

#### Check the format of your CSV

The easiest way to ensure a CSV is encoded correctly is by opening it in code editing software such as Sublime Text, Text Wrangler, or Visual Studio Code and looking at its contents. The reason why we suggest a code editing software (many are free) rather than any text editing software is text editing software such as Notepad (Windows) and TextEdit (mac) may encode special characters. So what looks to be a comma actually isn’t as far as a web program is concerned.

#### Remove headings and columns

The importer only needs and expects one column of the apps or domains without any header. Including additional unexpected information may return empty results.

#### Using the right report type

Only the app importer can process app IDs, and only the domain importer can process URLs. Before importing, ensure you are selecting the list type the correlates with the values in your CSV.

![](https://f.hubspotusercontent40.net/hubfs/2364596/d124b3fb-c449-43aa-a3f4-a7658df6267f-png-3.png)

#### Multiple app or domain results listed

Seeing multiple app or domain results in a list is the intent. This is because the results produce a separate row for each individual device type and region along with a row for all (all devices and global) data. To only view one row for each app or domain, narrow down the results by selecting the desired device and region under the detail filter:

![](https://f.hubspotusercontent40.net/hubfs/2364596/81261ee8-0568-4040-b710-a144d2502304-png-1.png)

If you prefer seeing all data that Pixalate has on an app or domain, we recommend filtering the list by selecting ‘Device = All’ and ‘Region = Global’.
