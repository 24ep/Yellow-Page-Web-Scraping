=============================================================

Explain script work
1 - Use selenium libraly with anti-bot technical included

as exploed the yellowpages website, it have the anti bot for webscraping , so I need to implement the humen similate to avoid each bot detech

Random delays (human-like behavior)
User-Agent rotation
Random screen/viewport sizes
Session rotation
Multi-agent pool (parallel browsers)
Mouse movement simulation
Request fingerprint randomization
Stealth mode with selenium-stealth (Python 3.14 compatible)
2 - Go business categories list page and go page by page to get present information

the listing page is showibg basic information, so I extract url to business detail page and basic information , the get another information like phone,address from detail page instend

1 Get total shop count from search results
2 Count items per page
3 Calculate total pages to scrape
4 Extract basic data from each listing (name, URL, category)
3 - Visit each shop URL in parallel to get detailed info

regrading to alot of shop page need to visit, i implement multitheard working to visit each page in parraler instend do one by one to handel more information

1 Extract address
2 Extract phone number(s)
4 Handle errors gracefully
4 - Create clean dataframe

=============================================================

=============================================================

Workflow instrution
Install required packages

selenium, webdriver-manager, pandas, openpyxl, tqdm
fake-useragent (User-Agent rotation)
selenium-stealth (fingerprint protection)
Import required libraries
Configure anti-bot settings

3.1 Setup User-Agent rotator
3.2 Define random screen sizes (11 resolutions)
3.3 Configure human-like delays
3.4 Setup session rotation settings
Setup human-like behavior functions

4.1 Random delay generator
4.2 Human-like scrolling (random amounts, pauses)
4.3 Mouse movement simulation
4.4 Random mouse movements
Setup stealth webdriver

5.1 Random screen size selection
5.2 Anti-detection Chrome options
5.3 Random User-Agent injection
5.4 Apply selenium-stealth fingerprint protection
5.5 Inject advanced JavaScript stealth (CDP)
5.6 Random WebGL/hardware fingerprint
Setup bot detection & handling

6.1 Detect Cloudflare challenges
6.2 Detect general bot blocks (403, CAPTCHA, rate limit)
6.3 Safe navigation with auto-retry
Get shop listings with anti-bot measures

7.1 Navigate to search URL with stealth driver
7.2 Wait for Cloudflare if detected
7.3 Simulate human behavior (scroll, mouse move)
7.4 Get total shop count from search results
7.5 Count items per page
7.6 Calculate total pages to scrape
7.7 Extract basic data from each listing (name, URL, address, description, category, Google Maps)
7.8 Handle pagination with human-like delays
7.9 Rotate session after N requests
Visit each shop URL in parallel with multi-agent pool

8.1 Initialize agent pool (multiple browsers with different fingerprints)
8.2 Extract phone number(s)
8.3 Extract detailed address
8.4 Human-like behavior on each page
8.5 Auto-rotate agents after N requests
8.6 Handle errors gracefully with retry
Create clean dataframe & export

9.1 Combine all collected data
9.2 Reorder columns
9.3 Export to CSV (UTF-8 with BOM for Thai)
