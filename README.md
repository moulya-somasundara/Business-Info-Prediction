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

Modules Overview
Module 1: Data Scraping
This module is responsible for scraping the restaurant details from Yelp and saving them to a .txt file.

Key Functions:
isAd(restaurantBlock): Checks if the restaurant block is an advertisement.
getRestaurantName(restaurantBlock): Extracts the name of the restaurant.
getRestaurantHref(restaurantBlock): Retrieves the URL of the restaurant.
getRestaurantUsername(restaurantUrl): Extracts the username of the restaurant from its URL.
restaurantsListScrapper(restaurantCount, domain, cuisine, location): Main scraping function that processes multiple Yelp pages, fetches the restaurant information, and writes the data to a text file.
Example:
To run the scraper, call the restaurantsListScrapper function with the required parameters:

python
Copy code
restaurantCount = 10  # Number of restaurants to scrape
domain = "https://www.yelp.com"  # Website domain
cuisine = "Food+-+Korean"  # Type of cuisine
location = "Manhattan%2C+NY"  # Location

restaurantsListScrapper(restaurantCount, domain, cuisine, location)
This will scrape 10 restaurants offering Korean food in Manhattan and save the data to restaurantsList.txt

Module 2: Data Cleaning and Processing
This module involves tasks as follows;

Removing duplicates
Handling missing or incomplete data
Normalizing restaurant names and other attributes
It will prepare the data for predictive modeling and analysis.

Module 3: Prediction Modeling
This module involves tasks as follows;

Analyze the data to identify key factors affecting restaurant success.
Build prediction models using algorithms like linear regression, decision trees, or machine learning techniques.
The goal will be to predict customer engagement, revenue, or other key performance indicators.
Future Work
Once the data is collected and processed, the next step is to build and evaluate predictive models. These models will analyze the restaurant data to identify patterns and predict outcomes such as business success or customer engagement.

License
This project is licensed under the MIT License - see the LICENSE file for details.




