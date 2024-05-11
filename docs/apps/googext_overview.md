---

id: gsheets-overview
title: Overview
sidebar_position: 1
description: Overview on the DMT Creator Data for Google Sheets™ extension
hide_table_of_contents: false 
keywords:
    - Creator data
    - Custom functions overview
---

# Overview

The DMT Creator Data app is an extension for Google Sheets™ that puts all of your influencer and creator data gathering workflows back in google sheets so you can get back to focusing on planning and executing great campaigns!

This quick overview includes the major components of the extension that is generally available.

### Find and install us from the Google Workspace Marketplace!

Our Creator Data extension for Google Sheets is listed on the official Google Workspace Marketplace™, you can view (and install!) by clicking this button:

<a href="https://workspace.google.com/marketplace/app/dmt_creator_data/752840059650" style={{ display:'flex', "justify-content": 'center', "align-items":'center',  width: '380px', height: '50px', "max-width": '420px', margin: '2rem 0rem .5rem', "background-color": '#1C93D9', border: '1px solid white', "border-radius":'7px', color: '#f9fafa', "font-weight":'bold' }} target="_blank" >Get Creator Data for Google Sheets™</a>


## Installing & Setup

There is minimal installation and setup needed to start working with creator data directly in your spreadsheets!

Simply click the **install** button in the [Google Workspace Marketplace™ listing](https://workspace.google.com/marketplace/app/dmt_creator_data/752840059650) and proceed through the installation flow and grant the DMT Creator Data extension the Google™ Account permissions it needs to work as expected. 



And that's it! Once it is successfully installed, the extension install will be associated with your Google Workspace account (either a personal gmail _or_ a professional custom domain) that you used to install the application into your workspace.

## Components

The current implementation includes two major components: the custom functions that you can invoke directly in the cells of your google spreadhsheets, and there is also a basic settings panel that is included for understanding who the managing user of the extension in the working document is.

### Custom Functions

The custom DMT functions are prefixed with `DMT` and can be directly invoked in your google sheets document of your choice as your workflow and analytics needs demand. We are always thinking about more functions to include and each function effectively packages the DMT API and makes it "readable" by Google Sheets for your convenience.

#### DMTChannelEstimate()

The `DMTChannelEstimate()` function takes in the the `channelName` as well as a few optional parameters and returns a projected viewcount of how _a video_ from that given channel will perform in its first 30 days.

This is helpful for understanding how to project performance for a given channel you might be considering for collaboration in a media campaign or just for general understanding of how they might perform relative to their follower counts.

##### Parameters

- `channelName` - the username of the channel, prefixed with an `@` symbol, for example the channel name of Mr Beast's YouTube channel is `@mrbeast`. The function will return an error if the prefix `@` symbol is missing.

- `channelType` (optional) - The platform of the channel that you requesting analytics for. For example, for requesting this function for the `@mrbeast` YouTube channel, you would input `"youtube"`. The default value is "youtube". You can assume all channelType values are lowercase, for example, Tiktok is "tiktok", Instagram is "instagram", Twitch is "twitch".

- `refreshData` (optional) - The default value is `false` and does not need to be changed or input. Only change the value to `true` if you want to force a recalcuation on the channel. However, please see the warning below.

:::warning
We recommend keeping the `refreshData` value default as **false**, otherwise this will increase your usage consumption of the DMT platform and could lead to getting throttled or billed additionally. The **Best Practice** here is to use the `true` value to force a recalculation and then change the value back to `false` to be safe.
:::

#### DMTChannelFinder()

The `DMTChannelFinder` function returns a list of channels that are "look alikes" of either a youtube video or channel that you pass in _or_ keywords that surface channels related to those keywords.

##### Parameters

- `url` - The url of the channel or the video that you intend to use to find lookalike channels

:::warning
Currently, the channel or video url **needs to match** the `channelType` value, in other words, YouTube videos can only be used to generate lookalike YouTube channels
:::

- `keywords` - (optional) use the keywords that are comma-separated wrapped in double quotes to find channels that are semantically related to the keywords you input. Currently, keywords is only supported for the "youtube" `channelType`.

- `channelType` (optional) - The platform of the channel that you requesting analytics for. For example, for requesting this function for the `@mrbeast` YouTube channel, you would input `"youtube"`. The default value is "youtube". You can assume all channelType values are lowercase, for example, Tiktok is "tiktok", Instagram is "instagram", Twitch is "twitch".

:::info 
To use the `keywords` parameter without providing a channel or video url, you can simply pass in `Null()` into the `url` parameter.
:::

### Settings Panel

The Settings panel is accessed through the `Settings` option in the `Extensions -> DMT Creator Data` dropdown. This is a basic but informative UI sidebar that shows you the managing user for the DMT Creator Data extension in the Google Sheets™ document you are operating in.
