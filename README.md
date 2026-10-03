# TidyTools for AI agents (remote MCP)

Six pay-per-use web data tools that any MCP client (Claude, Cursor, VS Code, n8n AI Agent, ...) can call through Apify's hosted MCP server. Nothing to install: add one URL.

```
https://mcp.apify.com/?tools=tidytools/company-website-enrichment,tidytools/website-contact-extractor,tidytools/website-markdown-crawler,tidytools/document-to-markdown,tidytools/audio-transcriber,tidytools/ai-crawler-access-checker
```

## Tools

| Tool | Ask your agent something like | Price (Apify, Sept 2026) |
|---|---|---|
| [Lead Enrichment (Google Maps emails & company data)](https://apify.com/tidytools/company-website-enrichment) | "What do these 20 companies do, and how do I contact them?" | $6 per 1,000 websites; unreachable sites free |
| [Website Contact Extractor](https://apify.com/tidytools/website-contact-extractor) | "Find the email and Instagram of these 50 cafés." | $2 per 1,000 websites; nothing found = free |
| [Website to Markdown Crawler](https://apify.com/tidytools/website-markdown-crawler) | "Load the FastAPI docs into context as Markdown." | $1 per 1,000 pages ($2.50 when a page needs a browser) |
| [PDF, Word & Excel to Markdown](https://apify.com/tidytools/document-to-markdown) | "Turn this PDF into Markdown chunks." | $2 per 1,000 documents |
| [Audio & Video Transcriber](https://apify.com/tidytools/audio-transcriber) | "Transcribe the latest episode of this podcast and summarize it." | $0.006 per audio minute |
| [AI Crawler Access Checker](https://apify.com/tidytools/ai-crawler-access-checker) | "Does nytimes.com block GPTBot or ClaudeBot?" | $2 per 1,000 sites |

## Connect

**OAuth (recommended):** add the URL above as a remote MCP server; your client opens an Apify sign-in the first time.

**API token:**

```json
{
  "mcpServers": {
    "tidytools": {
      "url": "https://mcp.apify.com/?tools=tidytools/company-website-enrichment,tidytools/website-contact-extractor,tidytools/website-markdown-crawler,tidytools/document-to-markdown,tidytools/audio-transcriber,tidytools/ai-crawler-access-checker",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

You need a free Apify account; runs are billed to it per result (no subscription). Only want one tool? Keep just that one in `?tools=`.

Besides the six tools, the server adds Apify's standard helpers (`get-actor-run`, `get-dataset-items`, `get-key-value-store-record`, `abort-actor-run`) so the agent can fetch results of longer runs.

## How it works

The server is Apify's official MCP server (`com.apify/apify-mcp-server`). The `tools` parameter limits it to these six Actors, so the agent sees six focused tools instead of thousands. Each Actor's behaviour, limits and output fields are documented on its Apify page.

## Listing

Published to the official MCP Registry as `io.github.tidytools/tidytools-apify-tools` (see [`server.json`](server.json)). Search: https://registry.modelcontextprotocol.io/v0/servers?search=tidytools

Source of this repo: https://github.com/tidytools/tidytools-apify-mcp

## License

MIT (this README and `server.json`, see [LICENSE](LICENSE)). The Actors themselves are paid services on Apify.
