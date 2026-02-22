Yellow Pages Web Scraping Script (Anti-Bot Ready)
Overview

This script is designed to scrape business data from the Yellow Pages website, which employs strong anti-bot protections.
To avoid bot detection, the script uses human-like behavior simulation and advanced Selenium stealth techniques.

The workflow consists of:

Safely navigating business category listings

Extracting basic business information

Visiting individual business pages in parallel to collect detailed data

Handling errors gracefully

Producing a clean, structured dataset for export

Key Features
1. Selenium with Advanced Anti-Bot Techniques

Since Yellow Pages actively detects automated scraping, the script mimics real human browsing behavior using:

Random delays (human-like interaction timing)

User-Agent rotation

Random screen and viewport sizes

Session rotation

Multi-agent browser pool (parallel browsers)

Mouse movement simulation

Request fingerprint randomization

Stealth mode using selenium-stealth (Python 3.14 compatible)

JavaScript and WebGL fingerprint masking

2. Business Category Listing Scraping

The script navigates business category listing pages page-by-page to collect basic information.

From each listing page:

Basic business data is extracted

Business detail page URLs are collected for deeper scraping

Steps:

Retrieve total number of businesses from search results

Count items per page

Calculate total number of pages

Extract basic listing data:

Business name

Business URL

Category

3. Parallel Scraping of Business Detail Pages

Because a large number of business pages must be visited, the script uses multi-threading with a multi-agent browser pool.

Each agent:

Uses a unique browser fingerprint

Visits business detail pages in parallel

Simulates human interaction on every page

Extracted details include:

Address

Phone number(s)

This approach significantly improves performance compared to sequential page visits.

4. Error Handling

The script is designed to be resilient and stable:

Detects Cloudflare challenges and bot blocks

Handles HTTP 403, CAPTCHA, and rate limiting

Automatically retries failed requests

Rotates sessions and agents when limits are reached

5. Clean Data Output

All collected data is:

Cleaned and normalized

Combined into a single Pandas DataFrame

Exported in a format suitable for analytics and reporting

Workflow Instructions
1. Install Required Packages
selenium
webdriver-manager
pandas
openpyxl
tqdm
fake-useragent        # User-Agent rotation
selenium-stealth      # Fingerprint protection
2. Import Required Libraries

All scraping, browser control, data handling, and concurrency libraries are initialized at startup.

3. Configure Anti-Bot Settings

3.1 Setup User-Agent rotation
3.2 Define random screen sizes (11 resolutions)
3.3 Configure human-like delays
3.4 Setup session rotation rules

4. Human-Like Behavior Functions

4.1 Random delay generator
4.2 Human-like scrolling (random distance and pauses)
4.3 Mouse movement simulation
4.4 Randomized mouse movement patterns

5. Stealth WebDriver Setup

5.1 Random screen size selection
5.2 Chrome anti-detection options
5.3 Random User-Agent injection
5.4 Apply selenium-stealth fingerprint protection
5.5 Inject advanced JavaScript stealth via CDP
5.6 Randomize WebGL and hardware fingerprints

6. Bot Detection & Handling

6.1 Detect Cloudflare challenges
6.2 Detect bot blocks (403, CAPTCHA, rate limits)
6.3 Safe navigation with auto-retry

7. Scrape Business Listings with Anti-Bot Measures

7.1 Navigate to search URL using stealth driver
7.2 Wait for Cloudflare challenges if detected
7.3 Simulate human behavior (scrolling and mouse movement)
7.4 Extract total business count
7.5 Count items per page
7.6 Calculate total pages
7.7 Extract listing data:

Name

URL

Address

Description

Category

Google Maps link

7.8 Handle pagination with human-like delays
7.9 Rotate browser sessions after N requests

8. Visit Business Pages in Parallel (Multi-Agent Pool)

8.1 Initialize multiple browser agents with unique fingerprints
8.2 Extract phone number(s)
8.3 Extract full address
8.4 Simulate human behavior on each page
8.5 Rotate agents after N requests
8.6 Retry and recover from errors automatically

9. Data Cleaning & Export

9.1 Combine all collected data
9.2 Reorder and standardize columns
9.3 Export to CSV (UTF-8 with BOM, suitable for Thai text)
