# Yellow Pages Web Scraping Script (Anti-Bot Ready)

## Overview

This project is a Selenium-based web scraping script designed to collect business information from the Yellow Pages website, which employs strong anti-bot protections.

To avoid detection, the script simulates real human browsing behavior and applies advanced Selenium stealth and fingerprint-randomization techniques.

The workflow includes:

* Navigating business category listing pages
* Extracting basic business data
* Visiting individual business pages in parallel to collect detailed information
* Handling errors and bot challenges gracefully
* Exporting clean, structured data for further use

---

## Key Features

### 1. Selenium with Advanced Anti-Bot Techniques

Because Yellow Pages actively blocks automated traffic, the script uses multiple evasion strategies:

* Random delays (human-like timing)
* User-Agent rotation
* Random screen and viewport sizes
* Session rotation
* Multi-agent browser pool (parallel browsers)
* Mouse movement simulation
* Request fingerprint randomization
* Selenium stealth mode (Python 3.14 compatible)
* JavaScript, WebGL, and hardware fingerprint masking

---

### 2. Business Category Listing Scraping

The script navigates category listing pages page-by-page to collect basic business information and URLs for detail pages.

**Process:**

1. Retrieve total business count from search results
2. Count items per page
3. Calculate total pages to scrape
4. Extract basic listing data:

   * Business name
   * Business URL
   * Category

---

### 3. Parallel Scraping of Business Detail Pages

To handle a large number of business pages efficiently, the script uses multi-threading with a multi-agent browser pool.

Each agent:

* Uses a unique browser fingerprint
* Simulates human behavior
* Visits detail pages in parallel

**Extracted details:**

* Address
* Phone number(s)

This significantly improves scraping speed compared to sequential processing.

---

### 4. Error Handling & Bot Detection

The script is designed to be resilient:

* Detects Cloudflare challenges
* Detects HTTP 403, CAPTCHA, and rate limiting
* Automatically retries failed requests
* Rotates sessions and browser agents when limits are reached

---

### 5. Clean Data Output

All collected data is:

* Cleaned and normalized
* Combined into a single Pandas DataFrame
* Exported for analytics and reporting use

---

## Workflow Instructions

### 1. Install Required Packages

```bash
pip install selenium webdriver-manager pandas openpyxl tqdm fake-useragent selenium-stealth
```

**Packages used:**

* selenium
* webdriver-manager
* pandas
* openpyxl
* tqdm
* fake-useragent (User-Agent rotation)
* selenium-stealth (Fingerprint protection)

---

### 2. Import Required Libraries

All browser control, scraping logic, concurrency handling, and data processing libraries are initialized at startup.

---

### 3. Configure Anti-Bot Settings

* User-Agent rotation
* Random screen sizes (11 predefined resolutions)
* Human-like delay configuration
* Session rotation rules

---

### 4. Human-Like Behavior Functions

* Random delay generator
* Human-like scrolling (random distance and pauses)
* Mouse movement simulation
* Randomized mouse movement patterns

---

### 5. Stealth WebDriver Setup

* Random screen size selection
* Chrome anti-detection options
* Random User-Agent injection
* Selenium-stealth fingerprint protection
* Advanced JavaScript stealth injection (CDP)
* WebGL and hardware fingerprint randomization

---

### 6. Bot Detection & Safe Navigation

* Detect Cloudflare challenges
* Detect general bot blocks (403, CAPTCHA, rate limits)
* Auto-retry with safe navigation logic

---

### 7. Scrape Business Listings

1. Navigate to search URL using stealth driver
2. Wait for Cloudflare challenges if detected
3. Simulate human behavior (scrolling and mouse movement)
4. Extract total business count
5. Count items per page
6. Calculate total pages
7. Extract listing data:

   * Name
   * URL
   * Address
   * Description
   * Category
   * Google Maps link
8. Handle pagination with human-like delays
9. Rotate browser sessions after N requests

---

### 8. Parallel Scraping of Business Pages (Multi-Agent Pool)

* Initialize multiple browser agents with unique fingerprints
* Extract phone number(s)
* Extract full address
* Simulate human behavior on each page
* Rotate agents after N requests
* Retry and recover from errors automatically

---

### 9. Data Cleaning & Export

* Combine all collected data
* Reorder and standardize columns
* Export to CSV (UTF-8 with BOM, suitable for Thai text)

---

## Notes

* This script is intended for **educational and internal research purposes only**.
* Always review and comply with website terms of service and local laws before scraping.

---

## License

MIT License
