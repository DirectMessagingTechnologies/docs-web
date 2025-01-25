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

The Channel Finder API generates a list of related channels simply from the required channelType and url query params in an http GET request.

:::warning
The DMT API is current in pre-alpha. This means you should not rely on its availability, and that it may change without warning, although we will certainly make a best effort to contact you in advance.
:::


### Get early access!

If you wish to get early access, sign up using this [**form here**](https://airtable.com/appzETVKT8y3nFxsx/shrEEvRQTq3tXfmgR)

## Request examples

### Requesting with the URL param

The `url` parameter is _exclusive_ to the YouTube channelType param and will accept either a youtube video _or_ channel url

```js title="cURL Channel Finder: URL"
--request GET
--url 'https://stg.directmessage.tech/api/v0/analytics/creators/find?url={{URL}}&channelType=youtube'
--header 'Authorization: Bearer {{YOUR_API_KEY}}
```

### Requesting with the Keywords param

The `keywords` parameter is currently _exclusive_ to the YouTube channelType param

```js title="cURL Channel Finder: Keywords"
--request GET
--url 'https://stg.directmessage.tech/api/v0/analytics/creators/find&keywords=snacks,health+snacks,fitness,lifestyle&channelType=youtube'
--header 'Authorization: Bearer {{YOUR_API_KEY}}
```

### Requesting with the ChannelName param

Use the `channelName` param to identify similar Instagram and Tiktok channels

```js title="cURL Channel Finder: channelName"
curl -H 'Authorization: Bearer {{YOUR_API_KEY}}' \
-X GET \
'https://stg.directmessage.tech/api/v0/analytics/creators/find?channelName={{channelName}}&channelType=tiktok'
```

:::warn Input validation
The `channelType` query param is required. Any **one** (and only one) of these params is **also** required:
- url - expects the url of a (currently only YouTube) channel for identifying "look alikes" of that channel
- channelName - expects the @channelName of a channel for identifying "look alikes" of that channel
- keywords - expects comma separated keywords for returning channels related to the keywords
:::

### Paginating with this iteration

<!-- Flesh out here -->


## Response example

### 200 status

```js title="Channel Finder response" showLineNumbers
{
	"data": {
		"channels": [
                {
				"id": "UCLMuXbUwSMiQrkouXTc0lNA",
				"name": "ethanolodj",
				"username": "@ethanolodj",
				"type": "youtube",
				"url": "https://www.youtube.com/channel/UCLMuXbUwSMiQrkouXTc0lNA",
				"followers": 198000,
				"totalViews": 55664590,
				"totalPosts": 227,
				"description": "my views/sub ratio so bad HELP ME SUBSCRIBE\n\n\nI upload whenever I want.\n",
				"createdDate": "2019-10-15T15:30:19.450342Z",
				"categoryName": "Gaming",
				"sampleVideo": "https://www.youtube.com/watch?v=Vq0b-6Zir88",
				"country": "FR",
				"profileImg": "https://yt3.ggpht.com/ytc/AIdro_nVICEDEtYaOIRjeVCtNx-CgR9oHk4FFDoZUKue=s88-c-k-c0x00ffffff-no-rj"
			},
			{
				"id": "UCTVleVqZ2YKv0hFyFOddY1w",
				"name": "Ache",
				"username": "@ache00",
				"type": "youtube",
				"url": "https://www.youtube.com/channel/UCTVleVqZ2YKv0hFyFOddY1w",
				"followers": 5440,
				"totalViews": 1849552,
				"totalPosts": 221,
				"description": "fr'",
				"createdDate": "2023-02-07T23:59:10.608777Z",
				"categoryName": "Gaming",
				"sampleVideo": "https://www.youtube.com/watch?v=vTsk953_8qs",
				"country": null,
				"profileImg": "https://yt3.ggpht.com/A9bfxK_IhSbW7YpZo2Ny2HIHPlWmiKSOBIKvQUUjzfh6MFhFtpInnToU3Xm6_XUjDh4obQYAdA=s88-c-k-c0x00ffffff-no-rj"
			},			
		],
		"find": {
			"url": null,
			"keywords": "jackfrags|fps|battlefield%202",
			"source": {
				"videoId": null,
				"channelId": null
			}
		}
	}
}
```
:::info
The `find` nested object within the "data" payload contains information about the keywords and other related parameters that informed the search results
:::

### 422 Error Status

The `422 Unprocessable Content` error status code is expected to return if you attempted to submit an **invalid** body *or* query param request to the Estimator API endpoint.

```js title="Channel Finder 422 Error response" showLineNumbers
{
	"error": {
		"message": "Invalid user input.\n
		Please reference docs for how to submit requests to the API:\n
		https://docs.directmessage.tech/api/api-finder#422-error-status",
		"statusCode": 422
		}
}
```