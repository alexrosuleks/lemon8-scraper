# Lemon8 Scraper: Lemon8-app Scraper API for Python & Node.js (2026)

Scrape Lemon8 posts and profiles: likes, comments, saves, views, hashtags, images and creator stats by username, feed or keyword. No login needed. JSON, CSV.

**[▶ Try the Lemon8 Scraper free on Scrapely](https://scrape.ly/store/echofield/lemon8-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Lemon8-app data with the [Lemon8 Scraper](https://scrape.ly/store/echofield/lemon8-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the lemon8-app scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Lemon8-app scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/lemon8-scraper) or from your code with the SDK.
- **Structured lemon8-app data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $2.50 per 1,000 post results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Lemon8-app changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Lemon8-app data can you extract?

Scrape Lemon8 posts and profiles: likes, comments, saves, views, hashtags, images and creator stats by username, feed or keyword. No login needed. JSON, CSV.

| Output field |
|---|
| `coverImage` |
| `title` |
| `content` |
| `likes` |
| `comments` |
| `saves` |
| `views` |
| `publishedAt` |
| `type` |
| `authorUsername` |
| `authorFollowers` |
| `hashtags` |
| `source` |
| `url` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/lemon8-scraper').call({"usernames": ["frankiealeron"], "maxItems": 20, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/lemon8-scraper').call(run_input={ "usernames": [ "frankiealeron" ], "maxItems": 20, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~lemon8-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "usernames": [
    "frankiealeron"
  ],
  "maxItems": 20,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Lemon8 Scraper page](https://scrape.ly/store/echofield/lemon8-scraper).

## Pricing

**$2.50 per 1,000 post results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/lemon8-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Lemon8-app with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Lemon8-app with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a lemon8-app scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~lemon8-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Lemon8-app legal?** This scraper collects publicly available data. Check Lemon8-app's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** lemon8 scraper, lemon8-app scraper, lemon8-app scraper api, lemon8-app scraper python, lemon8-app scraper node.js,
scrape lemon8-app, lemon8-app data extraction, lemon8-app crawler, lemon8-app api, export lemon8-app data to csv, lemon8-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/lemon8-scraper).
