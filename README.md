# Parallel Web Scraping with Selenium and ThreadPoolExecutor

This is an example of parallel web scraping using Selenium and ThreadPoolExecutor to fetch match data from a sports website.

## Overview

This script demonstrates how to use the ThreadPoolExecutor from the concurrent.futures module in Python to fetch match data from multiple URLs concurrently using Selenium WebDriver. The script is designed to scrape match data from a sports website and save it to CSV files.

## Prerequisites

Before running the script, make sure you have the following prerequisites installed:

- Python (>= 3.6)
- Selenium (install using `pip install selenium`)
- Chrome WebDriver (ensure compatibility with your Chrome browser version)
- Chromedriver (download from https://sites.google.com/chromium.org/driver/)

## Usage

1. Clone this repository to your local machine.

2. Install the required Python packages:

3. Download the appropriate Chromedriver executable and place it in the same directory as the script.

4. Open the script file `web_scraping.py` and modify the following variables as needed:

- `start_date`: The start date for the web scraping (e.g., datetime(2022, 10, 9))
- `end_date`: The end date for the web scraping (e.g., datetime(2023, 8, 12))
- `max_workers`: The number of worker threads in the ThreadPoolExecutor

5. Run the script:

## How It Works

1. The script defines a `fetch` function that fetches match data from a list of URLs. It uses Selenium WebDriver to navigate to each URL and extract the required data.

2. The `generate_urls` function generates a list of URLs based on the specified date range.

3. The script creates two lists of URLs: one for normal date order and another for reverse date order.

4. It initializes a `ThreadPoolExecutor` with a specified number of worker threads.

5. The script submits tasks to the executor using the `executor.submit()` method, passing the `fetch` function and the list of URLs as arguments.

6. The script waits for the submitted tasks to complete using the `future.result()` method.

7. The fetched match data is saved to CSV files, with each file named after the corresponding date.

## Notes

- The script uses headless mode to run the Chrome WebDriver without a visible browser window. You can modify the options in the `fetch` function if needed.

- Make sure to adjust the path to the Chromedriver executable in the `fetch` function.

- The script checks if a CSV file for a URL's date already exists and skips fetching if it does.

- You may need to adjust the timeout values in the `fetch` function based on your internet connection and website responsiveness.

- This example uses the sports website "https://www.goal.com" for demonstration purposes. Modify the selectors and data extraction logic to match the structure of your target website.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
