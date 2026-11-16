# GovDeals Scraper — MCP Server

Search GovDeals from your AI agent or MCP client — the marketplace where U.S. government agencies auction surplus property. Vehicles, equipment, and real-estate lots from federal, state, and local sellers, returned as structured records, with an only-new mode for watching fresh lots.

This repo is the MCP listing for the [GovDeals Scraper](https://apify.com/magnova/govdeals-scraper) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--govdeals-scraper** — Search surplus auction lots by keyword, category, and state. Returns structured records: lot title, current bid, bid count on category and browse searches, seller agency name, location, auction end time, and lot URL.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/govdeals-scraper
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "govdeals-scraper": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/govdeals-scraper"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "govdeals-scraper": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/govdeals-scraper"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/govdeals-scraper-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.005 per lot fetched — $5 per 1,000 lots**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/govdeals-scraper
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/govdeals-scraper

*Lot data comes from GovDeals' public marketplace listings. Seller agencies are named; no contact details are collected.*
