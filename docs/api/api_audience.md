---

id: api-audience
title: Channel Audience
sidebar_position: 3
description: Coverage on creator audience API
keywords:
    - Creator data
    - API
    - Custom DMT integrations
    - demographic & geolocation data
---

# Overview

:::warning 
The DMT API is currently in **pre-alpha**. This means you should not rely on its availability, and that it may change without warning, although we will certainly make a best effort to contact you in advance.

If you **wish to get early access**, sign up using this [form](https://airtable.com/appzETVKT8y3nFxsx/shrEEvRQTq3tXfmgR) (I promise we look at it!)
:::

## Authentication

There is currently one way to authenticate with DMT API v0: by providing an authentication token. You can obtain a token by signing up in our early access form.
This token can then be provided in the Authorization header of your HTTP request.
Here is a sample curl statement you can run in your terminal with your own API key:

```curl --request GET
--url 'https://stg.directmessage.tech/api/v0/analytics/creators/estimator?channelName=@JohnCooganPlus&channelType=youtube'
--header 'Authorization: Bearer {{YOUR_API_KEY}}
```

## Errors

DMT uses conventional HTTP response codes to indicate the success or failure of an API request.

As a general rule:
Codes in the 2xx range indicate success
Codes in the 4xx range indicate incorrect or incomplete parameters (e.g. a required parameter was omitted, or an operation failed with a 3rd party, etc.)
Codes in the 5xx range indicate an error with DMT's servers

## Rate limiting

The DMT APIs are in 'pre-alpha' so in general, the "be polite" MO is encouraged and bad actors will be isolated and blocked. Of course, we will reach out and attempt to understand your use-cases and usage model before doing anything drastic.

### Revoked API keys

If you find your API key no longer works, it is probably because we found your usage to be an existential edge-case that needed immediate addressing, although again, we will make a best effort to communicate decisions like this with you.
Another reason your API key was revoked might be because you did not respond to our outreach to better understand your usage model within a reasonable timeline (10 days). You can either submit a case through our Support Form or request help in our community Discord.