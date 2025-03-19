# MarketMapper

<img src="screenshots/MarketMapper-1.png" alt="MarketMapper_logo" width="300">

## Overview
**MarketMapper** is a Python-based tool consisting of two scripts: one for downloading historical stock data from [Yahoo Finance](https://finance.yahoo.com/) using Selenium and another for scraping currency conversion rates from [x-rates](https://www.x-rates.com/calculator/) website using BeautifulSoup. The stock data downloader allows users to specify a stock ticker symbol along with start and end dates to download historical stock data in CSV format. The currency converter prompts users to input currency symbols for conversion and then fetches the current conversion rate between the specified currencies.

---

## Features
- **Stock Data Downloader**: Downloads historical stock data from Yahoo Finance API using Selenium.
- **Currency Converter**: Scrapes currency conversion rates from x-rates website using BeautifulSoup.

---

## Technologies Used
- **Selenium**: Web automation tool used for interacting with `Yahoo Finance` website.
- **BeautifulSoup**: Python library for parsing HTML and extracting data from `x-rates` website.
- **requests**: Python library for making HTTP requests, used for fetching data from `x-rates` website.

---

## Setup
1. Clone the repository.
2. Ensure Python 3.x is installed.
3. Install the required dependencies using `pip install -r requirements.txt`.
4. Configure the necessary parameters such as `STOCK_DATA_DIR`, `YAHOO_FINANCE_API_ENDPOINT`, and `X_RATES_ENDPOINT` in `constants.py`.
5. Run the script using `python download_stock_data.py` for stock data downloader or `python scrape_currency_rate.py` for currency converter.

---

## Usage
1. Run the main script using `python main.py` to select and run either the `stock data downloader.py` or the `currency converter.py` script.
   - You will be prompted to enter the number corresponding to your choice.
2. Run the stock data downloader script using `python download_stock_data.py`.
   - You will be prompted to enter the stock `ticker symbol`, `start date`, and `end date`.
3. Run the currency converter script using `python scrape_currency_rate.py`.
   - You will be prompted to enter the currency symbols you want to convert from and to.
4. Follow the instructions provided by each script to complete the respective tasks.

---

### ⬅ [🔗 Back to Premium Projects](../../../README.md#-application-development) 

