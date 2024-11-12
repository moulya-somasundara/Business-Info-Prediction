# Yelp Restaurant Business Info Prediction

## Overview

This project aims to scrape business information of restaurants listed on Yelp, focusing on key details such as restaurant names, URLs, and usernames. The data is scraped and saved in a text file for further analysis and prediction tasks. The project is designed to help build a dataset for predicting the performance of restaurants based on various features.

## Requirements

The following libraries are required to run this project:

- `beautifulsoup4`
- `requests`
- `lxml`
- `re`
- `math`
- `time`

You can install the necessary libraries using pip:
pip install beautifulsoup4 requests lxml

Data Scraping
Module 1: Data Collection
This module fetches a list of restaurant names, unique business IDs, and URLs. The process is as follows:

The script scrapes restaurant details from Yelp using web scraping techniques.
It generates a .txt file (restaurantList.txt) that contains restaurant names, business IDs, and URLs.
The script handles pagination to gather data from multiple Yelp pages.
Key Functions
isAd(restaurantBlock): Checks if the restaurant block is an advertisement.
getRestaurantName(restaurantBlock): Extracts the restaurant name.
getRestaurantHref(restaurantBlock): Retrieves the URL of the restaurant.
getRestaurantUsername(restaurantUrl): Extracts the restaurant's username from its URL.
restaurantsListScrapper(restaurantCount, domain, cuisine, location): Main scraping function to gather restaurant details and write them to a file.
Example
To run the scraping process, simply call the restaurantsListScrapper function with the required parameters:

python
Copy code
restaurantCount = 10  # Number of restaurants to scrape
domain = "https://www.yelp.com"  # Website domain
cuisine = "Food+-+Korean"  # Type of cuisine
location = "Manhattan%2C+NY"  # Location

restaurantsListScrapper(restaurantCount, domain, cuisine, location)
This will scrape 10 restaurants that offer Korean food in Manhattan and save the data to a text file.

Future Work
The next steps involve processing the collected data and building prediction models to analyze the business performance of these restaurants. This could include predicting metrics like customer engagement, revenue, or popularity based on the scraped data.

License
This project is licensed under the MIT License - see the LICENSE file for details.




