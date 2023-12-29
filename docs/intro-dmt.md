---
sidebar_position: 1
---

# Intro

If you've spent any time in the 'influencer marketing' or 'creator economy' space you will notice that most of these services provide an API as an afterthought or so severely marked up in price as to be non-viable to any developer or savvier growth marketer just starting out with their own venture.
With DMT, our mission is to make creator marketing a viable and productive activity for anyone, regardless of their stage in the market, and we've found that APIs are a great way to start opening up those insights to new and more people.

## How to use this resource

Any new DMT API services that we provide will be documented in this section as an item in a given section and as a sub-page for a more detailed explanation of what and how that endpoint will return data to you.

## Anatomy of DMT Endpoints

The DMT Endpoints tend to conform to this pattern:

`baseUrl/:version/:service/:group/:app`

The :string refers to a dynamic parameter that depends on the service and child group and app being requested. The Endpoints are organized this way with the goal of being intuitive of what kind of response and service they will provide in the response payload.