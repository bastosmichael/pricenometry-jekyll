---
layout: post
title: Pricels Realtime API launches today
---

After nearly a year of research and development we are happy and proud to anounce the <a href="http://developers.pricels.com" target="_blank">Pricels API</a> launch.

As of yesterday we soft launched a working API with full documentation at <a href="http://developers.pricels.com" target="_blank">http://developers.pricels.com</a> and so far the reception has been very exciting.

Over the past few days we've been handing out free API keys for anyone wanting to test it out (rate limiting them to 100 requests per day).

I wanted to highlight a few of the main features of the current working API that are already documented in the link above.

A few months ago we sat down with the former division head of a large fortune 500 company and he showed us three things we needed to focus on in order to succeed in the market intelligence space.

### Speed of Data

The first piece of advice was already the cornerstone of what we were building, we needed to build a system that is effectively real time and faster at gathering and collecting data than anything else on the market today.

When you run the below API request you'll see that we are constantly collecting data, we never stop indexing which allows us to give you the fastest possible search and most up to date pricing on everything you are following.

<a href="http://developers.pricels.com/#get-status-in-json" target="_blank">http://api.pricels.com/v1/?access_token=YOUR-API-KEY</a>

```json
{
    "response": {
        "status": 200
    },
    "active": true,
    "api_usage_cap": 100,
    "api_last_used": "2015-02-25",
    "api_daily_usage": 2,
    "available": {
        "amazon-offers": "3.1M",
        "walmart-offers": "170.3K",
        "costco-offers": "83K",
        "target-offers": "38.4K"
    },
    "indexing": "1.1M",
    "processing": "440.4K",
    "pending": "947.2M"
}
```

When a customer makes an API request like the one below, our system immediately uses it's scalability and speed to gather the most recent changes right away.

<a href="http://developers.pricels.com/#get-product-in-json" target="_blank">http://api.pricels.com/v1/amazon-offers/B00DR0PDNE?access_token=YOUR-API-KEY</a>

```json
{
    "response": {
        "status": 200
    },
    "url": "http://www.amazon.com/Google-Chromecast-Streaming-Media-Player/dp/B00DR0PDNE",
    "date": "2015-02-25",
    "id": "B00DR0PDNE",
    "tags": [
        "Google",
        "Chromecast",
        "HDMI",
        "Streaming",
        "Media",
        "Player",
        "Inc.",
        "H2G2-42",
        "86002596-01"
    ],
    "name": "Google Chromecast HDMI Streaming Media Player",
    "description": "Amazon.com: Google Chromecast HDMI Streaming Media Player: Electronics",
    "type": "Offer",
    "image": "http://ecx.images-amazon.com/images/I/811nvG%2BLgML._SL1500_.jpg",
    "sku": "B00DR0PDNE",
    "screenshot": "B00DR0PDNE/2015-02-24.jpg",
    "price": "30.07",
    "original_price": "35.00",
    "facebook_shares": 48466,
    "google_shares": 5776,
    "twitter_shares": 177,
    "reddit_shares": 149,
    "linkedin_shares": 364,
    "pinterest_shares": 106,
    "stumbleupon_shares": 23,
    "total_shares": 55061
}
```

Our data is analyzed and processed faster than anyone else, this is how we are able to process data on a daily basis, no more waiting a month or a week for accurate and large scale calculations.

### Accuracy of Data

The second part of the advice we got was on being able to prove that our data is accurate, we have done this by documenting every change across a multitude of data points, indexing them in our search api and keeping them around for the long term.

<a href="http://developers.pricels.com/#get-product-history-in-json" target="_blank">http://api.pricels.com/v1/amazon-offers/B00DR0PDNE/history?access_token=YOUR-API-KEY</a>

```json
{
    "response": {
        "status": 200
    },
    "id": "B00DR0PDNE",
    "name": "Google Chromecast HDMI Streaming Media Player",
    "sku": {
        "2015-02-09": "B00DR0PDNE"
    },
    "screenshot": {
        "2015-02-09": "B00DR0PDNE/2015-02-09.jpg",
        "2015-02-10": "B00DR0PDNE/2015-02-10.jpg",
        "2015-02-21": "B00DR0PDNE/2015-02-21.jpg",
        "2015-02-24": "B00DR0PDNE/2015-02-24.jpg"
    },
    "price": {
        "2015-02-09": "32.49",
        "2015-02-10": "31.78",
        "2015-02-21": "30.07"
    },
    "original_price": {
        "2015-02-09": "35.00"
    },
    "facebook_shares": {
        "2015-02-09": 48466
    },
    "google_shares": {
        "2015-02-09": 5803,
        "2015-02-24": 5776
    },
    "twitter_shares": {
        "2015-02-09": 174,
        "2015-02-24": 177
    },
    "reddit_shares": {
        "2015-02-09": 146,
        "2015-02-10": 144,
        "2015-02-24": 149
    },
    "linkedin_shares": {
        "2015-02-09": 351,
        "2015-02-10": 358,
        "2015-02-24": 364
    },
    "pinterest_shares": {
        "2015-02-09": 106
    },
    "stumbleupon_shares": {
        "2015-02-09": 23
    },
    "total_shares": {
        "2015-02-09": 55075,
        "2015-02-10": 55074,
        "2015-02-24": 55061
    }
}
```

Apart from tracking every change that occurs we also take a screenshot of every time we hit a website, this allows us to both find discrepancies if any exist as well as prove to our cusotmers that our pricing data is more accurate that of anyone else on the market.

<a href="http://developers.pricels.com/#get-product-screenshot-image" target="_blank">http://api.pricels.com/v1/amazon-offers/B00DR0PDNE/2015-02-24.jpg?access_token=YOUR-API-KEY</a>

<img src="/public/images/anouncing-the-price-tracking-api-launch-product-screenshot.jpg"/>

By following this approach, we ensure that if any of our competitors present our customers with conflicting data, we can contradict with cold hard truth and not outdated spreadsheets.

### Simplicity of Data

Finally the last bit of advice we got was that we had to make it stupid simple, this was the most important part of our customer experience.

The below example shows how easy our <a href="http://developers.pricels.com/#search-all-products-in-json" target="_blank">search</a> and <a href="http://developers.pricels.com/#match-all-products-in-json" target="_blank">match API endpoints</a> are, by using <a href="http://en.wikipedia.org/wiki/Fuzzy_matching_%28computer-assisted_translation%29" target="_blank">fuzzy matching</a> and <a href="http://en.wikipedia.org/wiki/Incremental_search" target="_blank">incremental product search</a> we are able to provide <a href="http://en.wikipedia.org/wiki/Real-time_data" target="_blank">real time availability and pricing data</a> from multiple sites and sources.

<a href="http://developers.pricels.com/#search-all-products-in-json" target="_blank">http://api.pricels.com/v1/search/chromecast?access_token=YOUR-API-KEY</a>

```json
{
    "response": {
        "status": 200
    },
    "results": [
        {
            "id": "B00DR0PDNE",
            "name": "Google Chromecast HDMI Streaming Media Player",
            "container": "amazon-offers"
        },
        {
            "id": "811571013579",
            "name": "Google Chromecast HDMI Streaming Media Player",
            "container": "walmart-offers"
        },
        {
            "name": "Google Chromecast HDMI Streaming Media Player",
            "id": "15460778",
            "container": "target-offers"
        },
        {
            "id": "945132",
            "name": "Google Chromecast HDMI Streaming Media Player with $10 Google Play Credit",
            "container": "costco-offers"
        }
    ]
}
```

A simple search for the name 'chromecast' will return the above results or our matcher service will allow you to pass something in like a Manufacturer Part Number or Part ID and find the identical ID's on other sites almost immediately, fuzzy matching allows the product numbers not to be exact for them to match perfectly which makes it super easy to track the same product across hundreds of sites instantaneously.

So if you're interested in <a href="/get-access/">Getting API Access</a> then we'd love to have you take our system for a spin, we know that once you've started using Pricels, you won't want to use anything else.
