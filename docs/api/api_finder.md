---

id: api-finder
title: Channel Finder
sidebar_position: 2
description: Find look-alike channels
keywords:
    - Creator data
    - API
    - look-alikes
---

# Channel Finder

:::warning
The DMT API is current in pre-alpha. This means you should not rely on its availability, and that it may change without warning, although we will certainly make a best effort to contact you in advance.
:::

If you wish to get early access, sign up using this [form](https://airtable.com/appzETVKT8y3nFxsx/shrEEvRQTq3tXfmgR) (I promise we look at it!)
The Channel Finder API generates a list of related channels simply from the required channelType and url query params in an http GET request.

## Request example

```js title="cURL Channel Finder"
--request GET
--url 'https://stg.directmessage.tech/api/v0/analytics/creators/find&url={{URL}}'
--header 'Authorization: Bearer {{YOUR_API_KEY}}
```