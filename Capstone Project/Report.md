# Comparing Central America Cities

## Introduction/Business Problem

A very big company called *Fiction Sales* is looking to invest in Central America,  because they see it as a very potential market for the future. Their problem is that they need help deciding where exactly to begin and what kind of business they want, based on this the following questions are formulated:
* What is the most prolific business in that city?
* What are the most suitable cities for selected business?

To answer them, the following process will be followed:
* Identify important cities in Central American Countries.
* Identify trending venues categories in those cities.
* Cluster cities with similar categories.

At the end, the groups will give the company information about similar cities across the countries with similar consumption patterns and trends. And also what business will be more adequate for each group. Analyzing that information, recommendations can be made about the potential cities and type of business.


## Data

The data sources are the Foursquare API and Wikipedia.

### Wikipedia
It will be used to get the most important cities of each country, the most populous cities of each country are going to be chosen.

Example:

Costa Rica ([Wikipedia URL](https://en.wikipedia.org/wiki/Costa_Rica#Largest_cities))
From the URL, the following will be scraped.
![alt text](/home/diego/GitHub/Coursera_Capstone/Capstone Project/images/costa_rica_example.png)

### FourSquare API

It will be used to get information about the trending venue and their category from each city. The endpoint that is going to be used is: [venues/trending/](https://developer.foursquare.com/docs/api-reference/venues/trending/), it will provide information about trending venues in the given city and their respective category.

Example:

```
{
  "meta": {
    "code": 200,
    "requestId": "5ac51dde351e3d4df64064f8"
  },
  "response": {
    "venues": [
      {
        "id": "5735dc3f498e1ac6a088f324",
        "name": "Union Fare",
        "location": {
          "address": "5 E 17th St",
          "crossStreet": "btwn 5th Ave & Union Sq W",
          "lat": 40.737697,
          "lng": -73.991402,
          "labeledLatLngs": [
            {
              "label": "display",
              "lat": 40.737697,
              "lng": -73.991402
            }
          ],
          "distance": 1802,
          "postalCode": "10003",
          "cc": "US",
          "city": "New York",
          "state": "NY",
          "country": "United States",
          "formattedAddress": [
            "5 E 17th St (btwn 5th Ave & Union Sq W)",
            "New York, NY 10003",
            "United States"
          ]
        },
        "categories": [
          {
            "id": "4bf58dd8d48988d157941735",
            "name": "New American Restaurant",
            "pluralName": "New American Restaurants",
            "shortName": "New American",
            "icon": {
              "prefix": "https://ss3.4sqi.net/img/categories_v2/food/newamerican_",
              "suffix": ".png"
            },
            "primary": true
          }
        ]
      }
    ]
  }
}
```

In the response from the API, the names of the venue are obtained (in the example: *Union Fare*) and their corresponding category (in the example: *New American Restaurant*)





