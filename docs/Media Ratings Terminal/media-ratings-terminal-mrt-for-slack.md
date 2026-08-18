---
title: "Media Ratings Terminal (MRT) for Slack"
excerpt: "The Media Ratings Terminal (MRT) for Slack Plugin allows you to access MRT data directly within Slack, as well as keep track of your top follows."
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

### [ ](https://github.com/pixalate-inc/mrt-slack-guide#installation)

### Installation

You can install the [**Media Ratings Terminal (MRT) for Slack**](https://github.com/pixalate-inc/mrt-slack-guide#installation) to your workspace by clicking the below button and following the prompts:

[![Add to Slack](https://camo.githubusercontent.com/f4f5c59f7014665e334ab12219c9b8339e6cc53eb2b24691901afa638ecbbf69/68747470733a2f2f706c6174666f726d2e736c61636b2d656467652e636f6d2f696d672f6164645f746f5f736c61636b2e706e67)](https://slack.com/oauth/v2/authorize?client_id=4596232674.1734105936803&scope=commands,links:read,links:write)

### [](https://github.com/pixalate-inc/mrt-slack-guide#account-linking)Account Linking

You can either link your account using the /mrt account command and clicking "Login", or by click the "Log In" button on the Home page. From there, the linking process will continue in your browser. Follow the on-screen prompts to link your MRT account to Slack.

### [](https://github.com/pixalate-inc/mrt-slack-guide#commands)Commands

### [](https://github.com/pixalate-inc/mrt-slack-guide#help)Help

The help command displays all available commands along with a condensed description of their functionality.

#### [](https://github.com/pixalate-inc/mrt-slack-guide#usage)Usage

    /mrt help

#### [](https://github.com/pixalate-inc/mrt-slack-guide#sample-output)Sample Output

    /mrt help                           displays this help dialog  
    /mrt app     retrieve details about an app    
    /mrt ctv                        retrieve details about a ctv app    
    /mrt domain                 retrieve details about a domain    
    /mrt account                        manage the connection with your MRT account

### [](https://github.com/pixalate-inc/mrt-slack-guide#app-search)App Search

The App Search command allows you to retrieve general information about an App Store or Google Play app from within Slack. It also includes a link to view the app within the MRT, as well as the ability to follow the app from within Slack.

The details provided in the output are a brief overview of key metrics associated with the app. These cannot be customized at this time.

You may pass either the app name, the bundle id, or the app id to retrieve the associated app. Partial titles may be used, but for best results provide explicit app names or complete app/bundle ids.

#### [](https://github.com/pixalate-inc/mrt-slack-guide#usage-1)Usage

    /mrt app 

#### [](https://github.com/pixalate-inc/mrt-slack-guide#sample-output-1)Sample Output

![mrt_app_preview](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_app_preview.png)

### [](https://github.com/pixalate-inc/mrt-slack-guide#ctv-search)CTV Search

The CTV Search command allows you to retrieve general information about a Roku or Fire TV app from within Slack. It also includes a link to view the app within the MRT, as well as the ability to follow the app from within Slack.

The details provided in the output are a brief overview of key metrics associated with the app. These cannot be customized at this time.

CTV search only supports passing explicit app ids to retrieve the associated app at this time.

#### [](https://github.com/pixalate-inc/mrt-slack-guide#usage-2)Usage

    /mrt ctv 

#### [](https://github.com/pixalate-inc/mrt-slack-guide#sample-output-2)Sample Output

![mrt_ctv_preview](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_ctv_preview.png)

### [](https://github.com/pixalate-inc/mrt-slack-guide#website-search)Website Search

The Website Search command allows you to retrieve general information about a website from within Slack. It also includes a link to view the domain within the MRT, as well as the ability to follow the domain from within Slack.

The details provided in the output are a brief overview of key metrics associated with the domain. These cannot be customized at this time.

#### [](https://github.com/pixalate-inc/mrt-slack-guide#usage-3)Usage

    /mrt domain   
    /mrt website 

#### [](https://github.com/pixalate-inc/mrt-slack-guide#sample-output-3)Sample Output

![mrt_domain_preview](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_domain_preview.png)

### [](https://github.com/pixalate-inc/mrt-slack-guide#account)Account

The Account command allows you to manage your connection between the MRT and Slack.

#### [](https://github.com/pixalate-inc/mrt-slack-guide#usage-4)Usage

    /mrt account  
    /mrt login  
    /mrt logout

#### [](https://github.com/pixalate-inc/mrt-slack-guide#sample-output-4)Sample Output

![mrt_account_logged_out](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_account_logged_out.png) ![mrt_account_logged_in](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_account_logged_in.png)

### [](https://github.com/pixalate-inc/mrt-slack-guide#home)Home

Your MRT Slack home page can show you a summary of your top follows, as well as convenient links to view them in the MRT console when you've connected your account.

Home will always show your top three follows from each category. Currently, this is not configurable.

#### [](https://github.com/pixalate-inc/mrt-slack-guide#configuring-your-home)Configuring your Home

By pressing the Configure button at the top of the page, you are able to reorder or hide the sections you see in Home.

![mrt_configure_btn](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_configure_btn.png)

![mrt_configure_window](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_configure_window.png)

You can reorder or hide each section by pressing the ... menu to the right of each row. From there, you can see options to move or hide the section.

![mrt_reorder_dropdown](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_reorder_dropdown.png)

If you've hidden a section, you can restore it via the "Add a section..." dropdown.

![mrt_restore_section](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_restore_section.png)

Additionally, you can reset the layout to default using the Reset Layout button.

![mrt_reset_layout](https://2364596.fs1.hubspotusercontent-na1.net/hubfs/2364596/mrt_reset_layout.png)

Once you're satisfied, you can save your new layout by pressing the Save button. You can also discard any changes you've made with the Cancel button, or by clicking the X button in the upper right.
