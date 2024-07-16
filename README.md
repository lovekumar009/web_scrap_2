# Y Combinator Companies Web Scraper API

This project provides a web scraping API to extract data from Y Combinator's publicly listed companies. The API allows users to scrape a specified number of companies and apply various filters.

## Features

- Scrapes company information from Y Combinator's website
- Supports pagination to handle multiple pages of data
- Extracts detailed company and founder information
- Allows filtering based on batch, industry, region, tags, company size, and boolean attributes
- Outputs the scraped data in CSV format

## Requirements

- Ruby 3.1.0
- Rails 6.1
- SQLite database

## API Endpoint

### `/y_combinator/scrape`

#### Method: POST

#### Input

```json
{
  "n": 10,
  "filters": {
    "batch": "W21",
    "industry": "Healthcare",
    "region": "United States",
    "tag": "Top Companies",
    "company_size": "1-10",
    "is_hiring": true,
    "nonprofit": false,
    "black_founded": true,
    "hispanic_latino_founded": false,
    "women_founded": true
  }
}

n: Number of companies to scrape
filters: (Optional) Object containing filter criteria

#Output
CSV file with the following columns:
Company name
Company location
Short description
YC batch (e.g., W09, W12)
Website
Founder names
LinkedIn URLs of founders

Setup
1. Clone the repository:
git clone <repository_url>
cd <repository_directory>

2.Install dependencies:
bundle install

3.Setup the database:
rails db:create
rails db:migrate

4.Run the server:
rails server

```
