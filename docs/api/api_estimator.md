---

id: api-estimator
title: Channel Estimator 
sidebar_position: 1
description: Channel estimator API endpoint
keywords:
    - Creator data
    - API
    - Custom DMT integrations
    - projection creator performance
---

# Creator Estimator 

:::warning
The DMT API is current in pre-alpha. This means you should not rely on its availability, and that it may change without warning, although we will certainly make a best effort to contact you in advance.

If you wish to get early access, [**sign up**](https://airtable.com/appzETVKT8y3nFxsx/shrEEvRQTq3tXfmgR) using this form (I promise we look at it!)
:::

The `/estimate` endpoint provided by DMT provides a viewership projection of _hypothetical video_ for a given YouTube, tiktok, Instagram, or Twitch channel, either by `channelId` or `channelName` - either one is optional, but at least one must be required for a successful request.

:::info
This **Creator Estimate** service is an exclusive service provided by DMT and the underlying calculations are the result of a need for something similar for the last 10 years of 'influencer marketing.' 

While these projections have been used with real clients and in production use-cases, we recommend thinking of them as a way to _benchmark_ a channel's performance and inform your pricing decisions, they are **not** a guarantee.
:::

## Request example

```js title="cURL Channel Estimator" showLineNumbers
--request GET
--url 'https://stg.directmessage.tech/api/v0/analytics/creators/estimate?channelName=@JohnCooganPlus&channelType=youtube'
--header 'Authorization: Bearer {{YOUR_API_KEY}}
```

## Response example

### 200 Status

```js
{
	"data": {
		"channel": {
			"id": "UC3_BakzLfadvFrsnClMFWmQ",
			"type": "youtube",
			"projection": {
				"views": 191271,
				"type": "expanded"
			}
		}
	}
}
```

This is a sample _successful_ request response payload. Note the `data` object in which all _other_ objects will be nested in as standard formatting with any DMT API endpoint.