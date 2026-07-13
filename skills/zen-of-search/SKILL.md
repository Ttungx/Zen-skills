---
name: zen-of-search
description: Route and combine Anysearch, Exa, Firecrawl, and Tavily MCP tools for external information work. Use for current facts, daily search, scientific and academic research, market and competitor research, knowledge discovery, blogs and community discussions, GitHub and project research, fact-checking, URL reading, website extraction, crawling, and deep multi-source research. Select the smallest useful provider set, verify important claims against original sources, and conserve Tavily quota.
---

# Zen of Search

Choose tools by information need, not by habit. Start with one primary provider; add a complementary provider only when coverage, confidence, or source diversity materially improves. Do not call all four by default.

## Route Providers

| Provider | Prefer for | Key behavior |
| --- | --- | --- |
| Anysearch | Fast general lookup, current facts, news, structured verticals, multi-angle batches | Use general search directly. For academic, finance, legal, health, security, code, or other structured verticals, call `get_sub_domains` before passing a domain. Use `batch_search` for 2-5 related queries and `extract` for HTML pages. |
| Exa | Semantic discovery, technical blogs, hard-to-name sources, companies/people, research and project discovery | Describe the ideal result in natural language. Use search to find high-relevance sources, then batch-fetch the best URLs when snippets are insufficient. |
| Firecrawl | Web extraction, dynamic pages, PDFs, site mapping/crawling, structured extraction, GitHub, papers, monitoring, or interactive pages | Use search for discovery, scrape for a known page, map before a targeted crawl, and dedicated paper/GitHub tools when applicable. Submit search feedback after consuming search results. |
| Tavily | Independent second opinion, quick current search, or finished cited synthesis when other tools are insufficient | Conserve quota. Default to at most one Tavily call per task. Prefer `basic` or `fast` search; use research only when a decision-ready multi-source report justifies the cost. |

## Match Common Scenarios

- **Daily or current lookup:** start with Anysearch. Add Exa when the likely source is a specific article, company page, or technical document.
- **Scientific research:** combine Firecrawl paper search with Anysearch academic verticals. Use Exa for semantic recall and related terminology. Read original papers before making load-bearing claims.
- **Market or competitor research:** use Anysearch business/finance verticals for structured facts, Exa for companies, people, and narrative sources, and Firecrawl for official sites, pricing, changelogs, and structured extraction.
- **Blogs and community research:** use Exa for semantic discovery and Anysearch for broad/current coverage. Use Firecrawl to read selected posts or difficult pages.
- **GitHub and project research:** start with Firecrawl GitHub search or GitHub-category search; add Exa for project discovery and Anysearch code verticals for structured lookup.
- **Knowledge-base ingestion:** use Firecrawl map, crawl, and scrape to preserve source structure. Use Exa fetch for a small known URL set. Keep source URLs and retrieval dates.
- **Deep research:** search independent angles with Anysearch, Exa, and Firecrawl; deduplicate, read primary sources, reconcile conflicts, and synthesize. Use Tavily only as a scarce independent check or when its research output is specifically valuable.

## Follow the Search Loop

1. Identify freshness, breadth, source type, structured fields, page complexity, and decision stakes.
2. Pick one primary provider and, when justified, one complementary provider with a different retrieval strength.
3. Split broad questions into distinct query angles. Use provider-native filters rather than stuffing every constraint into one query.
4. Deduplicate by canonical URL and source identity. Prefer official documentation, papers, filings, repositories, and first-party statements.
5. Open the strongest sources. Treat search snippets as discovery evidence, not final evidence.
6. Cross-check consequential or disputed claims with an independent source or provider.
7. Report source dates, conflicting evidence, uncertainty, and missing information. Cite the pages actually read.

## Control Cost and Noise

- Keep exploratory result sets small, usually 5-8 results per query.
- Do not repeat an unchanged query across providers. Change the angle or use the second provider for verification.
- Do not crawl an entire site when map plus targeted scrape is enough.
- Reserve Firecrawl Agent and Tavily Research for genuinely multi-step tasks.
- If a provider is unavailable or returns weak results, reformulate once, then switch providers instead of retrying blindly.
- Never invent source contents, publication details, or unavailable facts.
