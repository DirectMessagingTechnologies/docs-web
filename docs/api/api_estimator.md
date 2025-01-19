---

id: api-estimator
title: Channel Estimator (deprecated)
sidebar_position: 3
description: Channel estimator API endpoint
keywords:
    - Creator data
    - API
    - Custom DMT integrations
    - projection creator performance
---

:::danger [Deprecation Alert!]
For the future-forward version of this endpoint, please see the [Channel Estimate](./api-estimate) page.

This endpoint is approaching End of Life scheduled for 2025-12-21, after which this endpoint will be completely unsupported and unavailable to incoming requests.
:::


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

```js title="cURL Channel Estimate" showLineNumbers
--request GET
--url 'https://stg.directmessage.tech/api/v0/analytics/creators/estimate?channelName=@JohnCooganPlus&channelType=youtube'
--header 'Authorization: Bearer {{YOUR_API_KEY}}
```

### Endpoint parameters

You will notice there are two parameters in the request to the endpoint:

- `channelName` - this is the @username of the channel you are requesting data for, in this case "@JohnCooganPlus" in the exmaple
- `channelType` - the social media platform that the channel you are requesting data for publishes on. In this case "youtube"

There is also a *third* parameter
- `channelId` - the channel ID of the channel in question, this would be a large integer number for tiktok and twitch channels, and a 24 character text ID like *UChQl2YkLt3dj-KDyGUBzcHw* for YouTube channels

:::warning
Use **either** the `channelId` OR the `channelName` query parameter, but **one** of those parameters is required for a successful response.
:::


## Response example

### 200 Status

```js title="Channel Estimate response" showLineNumbers
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

:::info
The `type` property nested in the projection response indicates if a broader (or "expanded") slice of the channel's dataset was used to generate this view performance projection.
:::


This is a sample _successful_ request response payload. Note the `data` object in which all _other_ objects will be nested in as standard formatting with any DMT API endpoint.

### 422 Error Status

The `422 Unprocessable Content` error status code is expected to return if you attempted to submit an **invalid** body *or* query param request to the Estimator API endpoint.

```js title="Channel Estimate 422 Error response" showLineNumbers
{
	"error": {
		"message": "Invalid user input.\n
		Please reference docs for how to submit requests to the API:\n
		https://docs.directmessage.tech/api/api-estimator#422-error-status",
		"statusCode": 422
		}
}
```