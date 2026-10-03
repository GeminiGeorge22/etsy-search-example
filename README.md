# etsy-search-example

One-command example for [`publicrecords/etsy-search-scraper`](https://apify.com/publicrecords/etsy-search-scraper) **0.2.3** (sort + price filters).

## Pricing

- Actor-start: **$0.005**
- Listing row: **$0.006** per delivered listing
- Do not quote listing-row-bulk $0.004

## One command

Requires [Apify CLI](https://docs.apify.com/cli) and `APIFY_TOKEN`.

```bash
apify call publicrecords/etsy-search-scraper --input '{
  "queries": ["ceramic mug"],
  "sort": "price_asc",
  "minPrice": 10,
  "maxPrice": 40,
  "maxItems": 10,
  "maxPages": 1,
  "fillLazyCards": true,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": ["RESIDENTIAL"],
    "apifyProxyCountry": "US"
  }
}'
```

Same input is in `input.json`. Sample output (`sample-output.json`) is the **10** dataset items from Store-page run `fB8Y28DNUy5kJ9xfg` (origin WEB, build 0.2.3).

## Fields used (from that Store run)

| Field | Value |
|---|---|
| `sort` | `price_asc` |
| `minPrice` | `10` |
| `maxPrice` | `40` |
| `maxItems` | `10` |
| row count | **10** |

Disclosure: I maintain these Actors on Apify Store (publicrecords).
