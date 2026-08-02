---
name: zen-of-search 
description: Select and combine Exa, Tavily, AnySearch, and Firecrawl for general-purpose external information retrieval. Use when a task requires current facts, web discovery, source finding, URL reading, fact verification, parallel lookup, or website exploration. Match the user's question to each MCP's retrieval strength, begin with one tool, and add another only when it improves discovery, acquisition, or verification. 
compatibility: Designed for MCP environments exposing some or all of Exa, Tavily, AnySearch, and Firecrawl. Treat the available tool schemas as authoritative.
---
# Zen of Search

Search is the reduction of uncertainty through evidence.

Before choosing a tool, ask:

1. Is the target precisely known or only semantically describable?
2. Does freshness or exact filtering matter?
3. Is the information structured or repeated across several entities?
4. Is finding the source difficult, or is acquiring its content difficult?

Use the shortest reliable path from the question to an inspected source.

## Know the Tools

### Exa — discover by meaning

Use Exa when the desired source is easier to describe than to name.

Best for unknown projects, similar products, niche articles, companies, people, technical approaches, and broad exploration before the correct terminology is known.

Describe the ideal source in natural language: what it discusses, what type of page it is, and what makes it relevant. Use search to form a candidate set, then fetch only the strongest ordinary pages.

Exa answers: **Where might the relevant knowledge be?**

### Tavily — retrieve with precision and freshness

Use Tavily when the target is clear and current relevance, dates, exact phrases, domains, or geographic filters matter.

Best for recent events, releases, prices, schedules, named facts, and queries that benefit from a continuous search–extract–map–crawl workflow.

Prefer native filters over long queries. After Tavily finds an ordinary page, continue with Tavily Extract unless another tool offers a concrete advantage.

Tavily answers: **What currently and precisely matches the question?**

### AnySearch — retrieve by structure and multiplicity

Use AnySearch when the question maps to a supported vertical domain or contains several independent lookups.

Best for identifiers and structured subjects such as CVEs, tickers, DOIs, patents, academic records, travel data, and comparisons across several entities.

Inspect the vertical schema before searching. Use batch search for two to five independent queries, but not when later queries depend on earlier results.

AnySearch answers: **Can this problem be expressed as structured or parallel queries?**

### Firecrawl — acquire the source itself

Use Firecrawl when obtaining usable page content is the difficult part.

Best for dynamic pages, PDFs, tables, screenshots, structured extraction, site mapping, and bounded crawling.

Use search when discovery and extraction should happen together, scrape for one known page, map when the relevant page inside a site is unknown, and crawl only when several pages are genuinely required.

Firecrawl answers: **How can the source be reliably acquired and transformed?**

## Route and Combine

Choose the primary tool according to the dominant difficulty:

| Need                                  | Start with |
| ------------------------------------- | ---------- |
| Unknown source or fuzzy concept       | Exa        |
| Current, exact, or filterable fact    | Tavily     |
| Structured record or several entities | AnySearch  |
| Difficult page or website structure   | Firecrawl  |

These tools overlap. Do not assign them rigid territories. Let the user's question determine the first tool, then let the remaining information gap determine whether another is needed.

Use these common combinations:

```text
Semantic discovery:
Exa → select URLs → Exa fetch or Firecrawl for difficult pages

Fresh factual lookup:
Tavily search → official source → Tavily extract

Parallel structured lookup:
AnySearch batch → select important results → inspect original sources

Website investigation:
map → select paths → scrape a few pages → crawl only if necessary

Independent verification:
likely answer → primary source, independent source, limitation, or contradiction
```

A second tool must perform a different job. Do not repeat the same query across providers merely to collect more links.

## Follow a Small Search Loop

1. State the exact information gap.
2. Choose one primary tool.
3. Retrieve a small candidate set, usually three to eight results.
4. Remove duplicates, mirrors, syndicated copies, and low-value summaries.
5. Open the strongest original sources.
6. Add one complementary tool only when:
   - coverage is weak;
   - content cannot be acquired;
   - structured or batch retrieval would reduce work;
   - an important claim needs independent verification.
7. Answer when the evidence is sufficient and expose any remaining uncertainty.

Prefer sources closest to the underlying fact:

1. official documentation, source repositories, standards, datasets, filings, and first-party records;
2. maintainers, authors, researchers, institutions, and direct participants;
3. reputable independent reporting and technical analysis;
4. community discussions and secondary summaries.

Search snippets locate evidence; they are not evidence by themselves.

## Keep the Discipline

- Start with one provider; two are enough for most researched answers.
- Use a third only for consequential disputes or clear coverage gaps.
- Batch independent queries and URLs when supported.
- Do not fetch every result.
- Use native filters before multiplying queries.
- Map before crawling, and bound every crawl by path, depth, and page count.
- Escalate acquisition gradually: ordinary fetch → advanced extraction → Firecrawl → browser interaction.
- Search for limitations or contradictions when a claim is important or surprising.
- Do not retry the same failed strategy indefinitely.
- Stop when further searching is unlikely to change the conclusion.
- Answer the user's question directly; do not narrate routine tool calls.
- Cite sources actually inspected and distinguish sourced facts from inference.

## The Way

```text
Let the question reveal the retrieval shape.
Let one tool handle one stage well.
Combine tools only across distinct stages.
Read the source, not merely the result.
Verify in proportion to consequence.
Stop when more searching no longer changes the answer.
```
