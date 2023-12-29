---

id: gsheets-overview
title: Overview
sidebar_position: 1
description: Overview on the DMT Creator Data Google sheets extension
hide_table_of_contents: false 
keywords:
    - Creator data
    - Custom functions overview
---

# Overview

The DMT Creator Data app is an extension for Google Sheets that puts all of your influencer and creator data gathering workflows back in google sheets so you can get back to focusing on planning and executing great campaigns!

This quick overview includes the major components of the extension that is generally available.

## Components

The current implementation includes two major components: the custom functions that you can invoke directly in the cells of your google spreadhsheets, and there is also a basic settings panel that is included for understanding who the managing user of the extension in the working document is.

### Custom Functions

The custom DMT functions are prefixed with `DMT` and can be directly invoked in your google sheets document of your choice as your workflow and analytics needs demand. We are always thinking about more functions to include and each function effectively packages the DMT API and makes it "readable" by Google Sheets for your convenience.

#### DMTChannelEstimator()

The `DMTChannelEstimator` function takes in the the `channelName` as well as a few optional parameters and returns a projected viewcount of how _a video_ from that given channel will perform in its first 30 days.

This is helpful for understanding how to project performance for a given channel you might be considering for collaboration in a media campaign or just for general understanding of how they might perform relative to their follower counts.

#### DMTChannelFinder()

The `DMTChannelFinder` function returns a list of channels that are "look alikes" of either a youtube video or channel that you pass in _or_ keywords that surface channels related to those keywords

:::info 
To use the `keywords` parameter without providing a channel or video url, you can simply pass in `Null()` into the `url` parameter.
:::


### Settings Panel

The Settings panel is accessed through the `Settings` option in the `Extensions -> DMT Creator Data` dropdown. This is a basic but informative UI sidebar that shows you the managing user for the DMT Creator Data extension in the Google Sheets document you are operating in.
