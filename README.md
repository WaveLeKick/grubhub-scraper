[Grubhub Scraper](https://apify.com/natanielsantos/grubhub-scraper?fpr=data)

## 🔍 What does GrubHub Scraper do?

This actor scrapes GrubHub for restaurant data. It extracts comprehensive data, enabling you to analyze restaurant offerings, pricing, and more.

## ✨ Features

- 📊 Extracts detailed restaurant information including name, address, phone number, menu items and more
- 🚀 High-performance with built-in proxy rotation
- 📅 Supports pagination to scrape multiple pages from search results
- 🔄 Automatically handles retries for failed requests
- 📦 Outputs data in JSON format for easy integration with other tools

## 🎯 Use Cases

- **Market Research**: Analyze restaurant offerings and pricing in specific areas
- **Competitive Analysis**: Compare restaurant menus and prices
- **Data Enrichment**: Enhance your datasets with detailed restaurant information
- **Business Intelligence**: Gain insights into restaurant trends and customer preferences
- **Academic Research**: Study food industry trends and consumer behavior

## 💡 Input Parameters

The actor accepts the following input parameters:

- `urls` (Required): A list of URLs to scrape. It can be multiple **restaurant URLs** or a single **search results** page URL
- `maxItems` (Optional): The maximum number of resturants to scrape from the provided URLs. Default is 100
- `scrapeMenu` (Optional): Whether to scrape menu items for each restaurant. It raises the run time significantly, so use it only if necessary. Default is `true`
- `scrapeAvailableHours` (Optional): Whether to scrape available hours for each restaurant. Default is `true`

## 📦 Output Format

The output is a JSON array containing objects with the following fields:

- `logoUrl`: URL of the restaurant's logo
- `url`: GrubHub URL of the restaurant
- `name`: Name of the restaurant
- `id`: Unique identifier for the restaurant
- `description`: Description of the restaurant
- `phoneNumber`: Phone number of the restaurant
- `cuisines`: List of cuisines offered by the restaurant
- `deliveryInfo`: Object containing delivery information

- `fee`: Delivery fee
- `timeEstimate`: Estimated delivery time (min and max)
- `available`: Whether delivery is available
- `location`: Object containing location details

- `address`: Street address of the restaurant
- `city`: City where the restaurant is located
- `postalCode`: Postal code of the restaurant's location
- `country`: Country of the restaurant (if available)
- `latitude`: Latitude coordinate of the restaurant
- `longitude`: Longitude coordinate of the restaurant
- `currencyCode`: Currency code used by the restaurant
- `rating`: Average rating of the restaurant
- `ratingCount`: Number of ratings the restaurant has received
- `priceRating`: Price rating of the restaurant (1-4 scale)
- `menuItems`: Array of menu items (if `scrapeMenu` is true)

- `id`: Unique identifier for the menu item
- `name`: Name of the menu item
- `description`: Description of the menu item
- `price`: Object containing prices for pickup and delivery

- `pickup`: Price for pickup
- `delivery`: Price for delivery
- `imageUrl`: URL of the menu item's image (if available)
- `availableHours`: Array of available hours for the restaurant (if `scrapeAvailableHours` is true)

 

## 📥 Input Example 1 (scraping by restaurant URL)

```
{
  "urls": [
    "https://www.grubhub.com/restaurant/20-dollar-pizza-642-9th-ave-new-york/1172686"
  ],
  "scrapeMenu": true,
  "scrapeAvailableHours": true
}
```

## 📥 Input Example 2 (scraping by search results URL)

```
{
  "urls": [
    "https://www.grubhub.com/search?orderMethod=delivery&locationMode=DELIVERY&facetSet=umamiV6&pageSize=36&hideHateos=true&searchMetrics=true&queryText=pizza&latitude=40.71277618&longitude=-74.00597382&geohash=dr5regw3pgd3&sorts=price&includeOffers=true&featureControl=fastTagBadges%3Atrue&sortSetId=umamiv3&countOmittingTimes=true&tab=all"
  ],
  "maxItems": 100,
  "scrapeMenu": false,
  "scrapeAvailableHours": false
}
```

 

## 📤 Output Example

This is an example of the output you can expect from this actor. You can choose in which format to download your data: JSON, JSONL, Excel spreadsheet, HTML table, CSV, or XML.

```
[
    {
        "logoUrl": "https://res.cloudinary.com/grubhub/image/upload/k4ew096v2bajcbkhzbda.jpg",
        "url": "https://www.grubhub.com/restaurant/20-dollar-pizza-642-9th-ave-new-york/1172686",
        "name": "20 Dollar Pizza",
        "id": "1172686",
        "description": "",
        "phoneNumber": "2122456260",
        "cuisines": [
            "Pizza"
        ],
        "deliveryInfo": {
            "fee": 0,
            "timeEstimate": {
                "min": 35,
                "max": 50
            },
            "available": true
        },
        "location": {
            "address": "642 9th Ave",
            "city": "New York",
            "postalCode": "10036",
            "country": "",
            "latitude": 40.7603302,
            "longitude": -73.99082947
        },
        "currencyCode": "USD",
        "rating": "3",
        "ratingCount": 27,
        "priceRating": 2,
        "menuItems": [
            {
                "id": "49249629",
                "name": "Mozzarella Sticks",
                "description": "Served with marinara sauce.",
                "price": {
                    "pickup": 9.95,
                    "delivery": 9.95
                },
                "imageUrl": "https://media-cdn.grubhub.com/image/upload/ucywmpm8etd4xfpfmfre.jpg"
		    },
            ...
        ],
        "availableHours": [
            {
                "dayOfWeek": 1,
                "timeRanges": [
                    "13:30-08:00"
                ]
            },
            ...
        ]
    },
    ...
]
```

## Integrations and GrubHub Scraper

Last but not least, GrubHub Scraper can be connected with almost any cloud service or web app thanks to [integrations on the Apify platform](https://apify.com/integrations). You can integrate with Make, Zapier, Slack, Airbyte, GitHub, Google Sheets, Google Drive, [and more](https://docs.apify.com/integrations). Or you can use [webhooks](https://docs.apify.com/integrations/webhooks) to carry out an action whenever an event occurs, e.g. get a notification whenever GrubHub Scraper successfully finishes a run.

## Using GrubHub Scraper with the Apify API

The Apify API gives you programmatic access to the Apify platform. The API is organized around RESTful HTTP endpoints that enable you to manage, schedule, and run Apify actors. The API also lets you access any datasets, monitor actor performance, fetch results, create and update versions, and more.

To access the API using Node.js, use the apify-client NPM package. To access the API using Python, use the apify-client PyPI package.

Check out the [Apify API reference](https://docs.apify.com/api/v2) docs for full details.

## Giving feedback

If you have any feature requests or bug reports, please create an issue on the [Issues page](https://console.apify.com/actors/Dk45auvk9CiglEduQ/issues).

If you need a custom solution of this actor, reach out to me through my email: [nathan.santos159@hotmail.com](mailto:nathan.santos159@hotmail.com)