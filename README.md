# TidyTools for AI agents (remote MCP)

Twelve pay-per-use web data tools that any MCP client (Claude, Cursor, VS Code, n8n AI Agent, ...) can call through Apify's hosted MCP server. Nothing to install: add one URL.

```
https://mcp.apify.com/?tools=tidytools/company-website-enrichment,tidytools/website-contact-extractor,tidytools/website-markdown-crawler,tidytools/document-to-markdown,tidytools/audio-transcriber,tidytools/ai-crawler-access-checker,tidytools/smart-fetch,tidytools/regional-price-check,tidytools/places-database,tidytools/ats-job-search,tidytools/ads-transparency,tidytools/domain-authority
```

## Tools

| Tool | Ask your agent something like | Price (Apify, Oct 2026) |
|---|---|---|
| [Lead Enrichment (Google Maps emails & company data)](https://apify.com/tidytools/company-website-enrichment) | "What do these 20 companies do, and how do I contact them?" | $6 per 1,000 websites; unreachable sites free |
| [Website Contact Extractor](https://apify.com/tidytools/website-contact-extractor) | "Find the email and Instagram of these 50 cafés." | $2 per 1,000 websites; nothing found = free |
| [Website to Markdown Crawler](https://apify.com/tidytools/website-markdown-crawler) | "Load the FastAPI docs into context as Markdown." | $1 per 1,000 pages ($2.50 when a page needs a browser) |
| [PDF, Word & Excel to Markdown](https://apify.com/tidytools/document-to-markdown) | "Turn this PDF into Markdown chunks." | $2 per 1,000 documents |
| [Audio & Video Transcriber](https://apify.com/tidytools/audio-transcriber) | "Transcribe the latest episode of this podcast and summarize it." | $0.006 per audio minute |
| [AI Crawler Access Checker](https://apify.com/tidytools/ai-crawler-access-checker) | "Does nytimes.com block GPTBot or ClaudeBot?" | $2 per 1,000 sites |
| [Smart Fetch](https://apify.com/tidytools/smart-fetch) | "Fetch these 30 URLs as clean Markdown, including the ones that block simple requests." | from $1 per 1,000 pages; regions and browser cost more |
| [Regional Price Checker](https://apify.com/tidytools/regional-price-check) | "What does spotify.com/premium cost in the US, Singapore, the UK and Taiwan?" | $4 per 1,000 regions checked ($6 for Taiwan via browser); failed regions free |
| [Places Database](https://apify.com/tidytools/places-database) | "List dentists in Berlin with websites and emails." | $1 per 1,000 places; contact enrichment $3 per 1,000 websites with a contact found |
| [Job Search (ATS Jobs Index)](https://apify.com/tidytools/ats-job-search) | "Which companies are hiring data engineers in the US this week?" | $1.50 per 1,000 jobs |
| [Google Ads Transparency Scraper](https://apify.com/tidytools/ads-transparency) | "What Google ads is Zapier running in Germany this month?" | $1.50 per 1,000 ads; ad text and details optional |
| [Domain Authority Checker](https://apify.com/tidytools/domain-authority) | "Which of these 50 sites has the most referring domains?" | $3 per 1,000 domains; unknown domains free |

## Connect

**OAuth (recommended):** add the URL above as a remote MCP server; your client opens an Apify sign-in the first time.

**API token:**

```json
{
  "mcpServers": {
    "tidytools": {
      "url": "https://mcp.apify.com/?tools=tidytools/company-website-enrichment,tidytools/website-contact-extractor,tidytools/website-markdown-crawler,tidytools/document-to-markdown,tidytools/audio-transcriber,tidytools/ai-crawler-access-checker,tidytools/smart-fetch,tidytools/regional-price-check,tidytools/places-database,tidytools/ats-job-search,tidytools/ads-transparency,tidytools/domain-authority",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

You need a free Apify account; runs are billed to it per result (no subscription). Only want a few tools? Keep just those in `?tools=`.

Besides the twelve tools, the server adds Apify's standard helpers (`get-actor-run`, `get-dataset-items`, `get-key-value-store-record`, `abort-actor-run`) so the agent can fetch results of longer runs.

## How it works

The server is Apify's official MCP server (`com.apify/apify-mcp-server`). The `tools` parameter limits it to these twelve Actors, so the agent sees twelve focused tools instead of thousands. Each Actor's behaviour, limits and output fields are documented on its Apify page.

## Listing

Published to the official MCP Registry as `io.github.tidytools/tidytools-apify-tools` (see [`server.json`](server.json)). Search: https://registry.modelcontextprotocol.io/v0/servers?search=tidytools

Source of this repo: https://github.com/tidytools/tidytools-apify-mcp

## License

MIT (this README and `server.json`, see [LICENSE](LICENSE)). The Actors themselves are paid services on Apify.
