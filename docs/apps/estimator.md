---
id: estimator
title: Channel Estimator
description: Overview on the Channel Estimator application
keywords:
    - channel performance
    - predictive analytics
    - performance marketing
---

# Intro

Use the Creator Estimator app as the entry point in discovering how much a creator might realistic price a brand integration with a video because the performance is projected (tested within 10% margin of error) for a how a hypothetical video will perform in the first 30 days of that video's life.

# Walkthrough

Using the Creator Estimator can be distilled into 3 easy steps

## Step 1: Get your DMT API key
For starters, make sure you have your DMT API key handy otherwise you will not be able to use the Estimator tool.
You can retrieve your existing key or request a new API key at this link.

## Step 2: Look up the Channel using the Name or Id
Platforms like YouTube and Twitch have several ways of identifying each channel in a unique way to that channel. Depending on the platform, that 'identifier' may be very easy for you to retrieve, but it can get complicated.

For YouTube

Channel Name - the channel name can be confusing for YouTube because, there is the "Display Name" (called the channel.title in the DMT response payload) that YouTube does not consider a valid way to look up the channel. 

If a channel does not have an alias in the channel url (especially after clicking around the "About" or "Videos" tabs on the channel page) you will need to use the channel Id.
Channel ID - YouTube has a unique way of creating their own unique identifier for each channel. This ID will be a 32 character mix of letters and numbers, all prefixed with the letters UC (Unique Channel? We think?)
If a YouTube channel does not have a username configured (newer YouTube channels are less likely to have this) you will need to use the provided Channel Id to lookup a projection. The good news is that getting the Channel Id is just as easy as referencing the url for the Channel Name:


# Missing something? Tell us!
Is there something you don't like? Results are not what you are expecting?
Feel free to drop us a line and share your thoughts at this [link](https://airtable.com/appzETVKT8y3nFxsx/shreeZck44tUeKVqf).