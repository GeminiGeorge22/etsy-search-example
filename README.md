# etsy-search-example

One-command example for [`publicrecords/etsy-search-scraper`](https://apify.com/publicrecords/etsy-search-scraper) (sort + price filters).

## Pricing

As of Oct 28, 2026 ([Store pricing](https://apify.com/publicrecords/etsy-search-scraper/pricing)), pay per event:

- Listing row: **0.4¢** per complete listing delivered on the Free plan (0.38¢ Bronze, 0.36¢ Silver, 0.34¢ Gold and up)
- Actor start: **0.005¢** once per run, only when a complete listing is in hand
- A run that returns no rows charges nothing

This example (10 listings) comes to about 4¢ on the Free plan. Prices can change; the Store pricing page is the live source.

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

Same input is in `input.json`. Sample output (`sample-output.json`) is the **10** dataset items from one run of this input started from the Store page.

## Fields used (from that run)

| Field | Value |
|---|---|
| `sort` | `price_asc` |
| `minPrice` | `10` |
| `maxPrice` | `40` |
| `maxItems` | `10` |
| row count | **10** |

Disclosure: I maintain these Actors on Apify Store (publicrecords).
