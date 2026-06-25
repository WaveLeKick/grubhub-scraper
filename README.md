[Grubhub Scraper](https://apify.com/alizarin_refrigerator-owner/grubhub-scraper?fpr=data)

# Grubhub Restaurant Scraper

Scrape Grubhub for restaurant listings, menus, prices, ratings, and delivery info. Extract restaurant data for food delivery market research. Built by John Rippy ([https://www.linkedin.com/in/johnrippy/](https://www.linkedin.com/in/johnrippy/)).

---

## Quick Start

### Test with Demo Mode (free, no API key needed)

```
{
  "demoMode": true,
  "restaurantUrl": "https://example.com"
}
```

### Run with real data

```
{
  "demoMode": false,
  "scrapeType": "search",
  "restaurantUrl": "https://example.com",
  "searchTerm": "pizza",
  "location": "Chicago, IL",
  "cuisineType": "all",
  "includeMenu": true,
  "maxResults": 50,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": [
      "RESIDENTIAL"
    ]
  }
}
```

---

## Input Parameters

| Parameter | Type | Default | Required | Description |
| --- | --- | --- | --- | --- |
| `scrapeType` | string | `"search"` | No | What type of data to scrape |
| `restaurantUrl` | string | - | No | Direct Grubhub restaurant page URL |
| `searchTerm` | string | `"pizza"` | No | Cuisine type or restaurant name |
| `location` | string | `"Chicago, IL"` | No | Delivery address or zip code |
| `cuisineType` | string | `"all"` | No | Filter by cuisine |
| `includeMenu` | boolean | `true` | No | Extract menu items and prices |
| `maxResults` | integer | `50` | No | Maximum number of restaurants to scrape |
| `proxyConfiguration` | object | `{"useApifyProxy":true,"apifyProxyGroups":["RESIDENTIAL"]}` | No | Proxy settings for web scraping |
| `demoMode` | boolean | `true` | No | Return sample data without actual scraping |
| `webhookUrl` | string | - | No | Optional webhook URL to receive data as it's scraped |

---

## Pricing

This actor uses **pay-per-event** billing:

| Event | Description | Price |
| --- | --- | --- |
| Restaurant Scraped | Each Grubhub restaurant scraped | $0.05 |

**Demo mode is free** -- no charges for sample data.

---

## Troubleshooting

### "API error 429" or "Rate limit"

Too many requests. Wait a minute and try again, or reduce the number of items per run.

### No results or empty dataset

Check the run log for error messages. Common causes:

- Invalid input format (check the examples above)
- The target data doesn't exist or is too small to track

### How do I test without an API key?

Enable **Demo Mode** in the input. This returns realistic sample data so you can verify the output format works for your workflow.

---

**Built by John Rippy | [Actor Arsenal](https://actorarsenal.com)**