# TidyTools for AI agents (remote MCP)

Twenty-six pay-per-use web data tools that any MCP client (Claude, Cursor, VS Code, n8n AI Agent, ...) can call through Apify's hosted MCP server. Nothing to install: add one URL.

```
https://mcp.apify.com/?tools=tidytools/company-website-enrichment,tidytools/website-contact-extractor,tidytools/website-markdown-crawler,tidytools/document-to-markdown,tidytools/audio-transcriber,tidytools/ai-crawler-access-checker,tidytools/smart-fetch,tidytools/regional-price-check,tidytools/places-database,tidytools/ats-job-search,tidytools/ads-transparency,tidytools/domain-authority,tidytools/youtube-transcript,tidytools/google-trends-scraper,tidytools/amazon-product-scraper,tidytools/product-price-tracker,tidytools/pagespeed-insights-bulk,tidytools/website-traffic-rank,tidytools/domain-overview,tidytools/backlink-gap,tidytools/sec-form-d-scraper,tidytools/polymarket-kalshi-scraper,tidytools/y-combinator-scraper,tidytools/eventbrite-luma-events,tidytools/ai-web-data-extractor,tidytools/image-to-text-ocr
```

## Tools

| Tool | Ask your agent something like | Price (Apify, Oct 2026) |
|---|---|---|
| [Lead Enrichment (Google Maps emails & company data)](https://apify.com/tidytools/company-website-enrichment) | "What do these 20 companies do, and how do I contact them?" | $6 per 1,000 websites; unreachable sites free |
| [Website Contact Extractor](https://apify.com/tidytools/website-contact-extractor) | "Find the email and Instagram of these 50 cafés." | $2 per 1,000 websites; nothing found = free |
| [Website to Markdown Crawler](https://apify.com/tidytools/website-markdown-crawler) | "Load the FastAPI docs into context as Markdown." | $1 per 1,000 pages ($2.50 when a page needs a browser) |
| [PDF, Word & Excel to Markdown](https://apify.com/tidytools/document-to-markdown) | "Turn this PDF into Markdown chunks." | $2 per 1,000 documents |
| [AI Web Scraper (URL to JSON)](https://apify.com/tidytools/ai-web-data-extractor) | "Pull name, price and address from these 30 property pages as JSON." | $10 per 1,000 extracted pages; blocked or empty pages free |
| [Image to Text OCR](https://apify.com/tidytools/image-to-text-ocr) | "Read the text on these 100 receipt images." | $3 per 1,000 images; images with no text free |
| [Audio & Video Transcriber](https://apify.com/tidytools/audio-transcriber) | "Transcribe the latest episode of this podcast and summarize it." | $0.006 per audio minute |
| [AI Crawler Access Checker](https://apify.com/tidytools/ai-crawler-access-checker) | "Does nytimes.com block GPTBot or ClaudeBot?" | $2 per 1,000 sites |
| [Smart Fetch](https://apify.com/tidytools/smart-fetch) | "Fetch these 30 URLs as clean Markdown, including the ones that block simple requests." | from $1 per 1,000 pages; regions and browser cost more |
| [Regional Price Checker](https://apify.com/tidytools/regional-price-check) | "What does spotify.com/premium cost in the US, Singapore, the UK and Taiwan?" | per region checked, failed regions free (see the Store page) |
| [Places Database](https://apify.com/tidytools/places-database) | "List dentists in Berlin with websites and emails." | $1 per 1,000 places; contact enrichment $3 per 1,000 websites with a contact found |
| [Job Search (ATS Jobs Index)](https://apify.com/tidytools/ats-job-search) | "Which companies are hiring data engineers in the US this week?" | $1.50 per 1,000 jobs |
| [Google Ads Transparency Scraper](https://apify.com/tidytools/ads-transparency) | "What Google ads is Zapier running in Germany this month?" | $1.50 per 1,000 ads; ad text and details optional |
| [Domain Authority Checker](https://apify.com/tidytools/domain-authority) | "Which of these 50 sites has the most referring domains?" | $3 per 1,000 domains; unknown domains free |
| [YouTube Transcript Scraper](https://apify.com/tidytools/youtube-transcript) | "Get the transcript of this YouTube video and summarize it." | $2 per 1,000 transcripts; videos without one free |
| [Google Trends Scraper](https://apify.com/tidytools/google-trends-scraper) | "Compare search interest for 'ai agents' vs 'chatbots' in the US over 5 years." | $2 per 1,000 term reports; trending searches $0.50 per 1,000 |
| [Amazon Scraper](https://apify.com/tidytools/amazon-product-scraper) | "What are the top 10 Best Sellers in Electronics and their prices?" | $3 per 1,000 products; search and list rows $1 per 1,000; failed pages free |
| [E-commerce Price Tracker](https://apify.com/tidytools/product-price-tracker) | "Has the price of these 20 products changed since yesterday?" | $2 per 1,000 products; unchanged re-checks $1 per 1,000 |
| [Bulk PageSpeed Insights](https://apify.com/tidytools/pagespeed-insights-bulk) | "Check Core Web Vitals for these 30 URLs on mobile." | $2 per 1,000 measurements; failed ones free |
| [Website Traffic Rank Checker](https://apify.com/tidytools/website-traffic-rank) | "Rank these 100 domains by traffic." | $2 per 1,000 domains; unlisted free |
| [Domain Overview](https://apify.com/tidytools/domain-overview) | "Give me tech stack and hiring signals for these 50 company sites." | $10 per 1,000 domains |
| [Backlink Checker & Link Gap](https://apify.com/tidytools/backlink-gap) | "Which sites link to my competitors but not to me?" | $1-2 per 1,000 rows |
| [SEC Form D Scraper](https://apify.com/tidytools/sec-form-d-scraper) | "Which startups filed a Form D in the last 3 days?" | $5 per 1,000 filings |
| [Polymarket & Kalshi Scraper](https://apify.com/tidytools/polymarket-kalshi-scraper) | "Top 20 prediction markets by 24h volume with current odds." | $1 per 1,000 markets |
| [Y Combinator Scraper](https://apify.com/tidytools/y-combinator-scraper) | "List YC Fall 2026 companies hiring engineers." | $2 per 1,000 companies; jobs $1 per 1,000 |
| [Eventbrite & Luma Events](https://apify.com/tidytools/eventbrite-luma-events) | "Find AI meetups in San Francisco in the next 30 days." | $2 per 1,000 events |

## Connect

**OAuth (recommended):** add the URL above as a remote MCP server; your client opens an Apify sign-in the first time.

**API token:**

```json
{
  "mcpServers": {
    "tidytools": {
      "url": "https://mcp.apify.com/?tools=tidytools/company-website-enrichment,tidytools/website-contact-extractor,tidytools/website-markdown-crawler,tidytools/document-to-markdown,tidytools/audio-transcriber,tidytools/ai-crawler-access-checker,tidytools/smart-fetch,tidytools/regional-price-check,tidytools/places-database,tidytools/ats-job-search,tidytools/ads-transparency,tidytools/domain-authority,tidytools/youtube-transcript,tidytools/google-trends-scraper,tidytools/amazon-product-scraper,tidytools/product-price-tracker,tidytools/pagespeed-insights-bulk,tidytools/website-traffic-rank,tidytools/domain-overview,tidytools/backlink-gap,tidytools/sec-form-d-scraper,tidytools/polymarket-kalshi-scraper,tidytools/y-combinator-scraper,tidytools/eventbrite-luma-events,tidytools/ai-web-data-extractor,tidytools/image-to-text-ocr",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

You need a free Apify account; runs are billed to it per result (no subscription). Only want a few tools? Keep just those in `?tools=`.

Besides the twenty-six tools, the server adds Apify's standard helpers (`get-actor-run`, `get-dataset-items`, `get-key-value-store-record`, `abort-actor-run`) so the agent can fetch results of longer runs.

## How it works

The server is Apify's official MCP server (`com.apify/apify-mcp-server`). The `tools` parameter limits it to these twenty-six Actors, so the agent sees twenty-six focused tools instead of thousands. Each Actor's behaviour, limits and output fields are documented on its Apify page.

## Listing

Published to the official MCP Registry as `io.github.tidytools/tidytools-apify-tools` (see [`server.json`](server.json)). Search: https://registry.modelcontextprotocol.io/v0/servers?search=tidytools

Source of this repo: https://github.com/tidytools/tidytools-apify-mcp

## License

MIT (this README and `server.json`, see [LICENSE](LICENSE)). The Actors themselves are paid services on Apify.
