# fintech-wiki

We are building an LLM-powered wiki covering **fintech** (payments, neobanks, wealthtech) and **digital infrastructure** (blockchain and tokenization).

## Use case

Provide a reference website for students in a fintech course with information about fintech subsectors ("verticals") and individual companies,
based on public company reports, open thematic reports and opinions expressed in media.  

The learner user browses a Fintech LLM Wiki and, using the wiki, can express informed opinion about business models and product propositions
in different subsectors, individual company valuation drivers, decisions made by the investors and regulators, and consumer satisfaction
in financial services.

A lecturer user may assign parts of the fintech wiki as a reading to the students, as summaries or original text. Quality of topic coverage
may be discussed in class.

A subject matter expert may place their own commentary in the wiki with reference to the original source.  

## Structure 

The wiki should have:

- introduction (project goals and suggested uses)
- subsector breakdown ("verticals") - description of what we consider a specific vertical in fintech
- topic section (e.g. stablecoins, tokenization, expected IPOs) - opened by relevance, "hot" topics only
- companies - links to annual reports
- investors (to be added)
- regulation (to be added)
- news sources (to be added)
- glossary ("glossary.md")

As a start, let us make the list with links to the company reports.

## Wiki LLM concept 

The [Karpathy Wiki LLM concept](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f):

- LLM-generated markdown from raw text sources 
- it's a document store, not a RAG
- ingest/lint and query commands
- index.md and log.md
- static site generator

Please refine this summary if we missed something. The original concept is "intentionally abstract",
many implementations are possible.

## Tooling

Specific stack is yet to be defined. We need some agent to process raw data and create the markdown files and some static site generator to publish the files.  

Wiki management (raw docs to markdown):
- `AGENTS.md` — a file at the repo root that provides instructions for AI agents.
  GitHub Copilot [now supports `AGENTS.md`](https://github.blog/changelog/2026-06-18-copilot-code-review-agents-md-support-and-ui-improvements/)
  and will apply its contents when running tasks in this repository.
  To use it: open GitHub Copilot in agent mode and invoke any task — Copilot will
  automatically pick up the instructions in `AGENTS.md`.
  Are there any existing implementations like [llm-wiki-agent](https://github.com/SamurAIGPT/llm-wiki-agent)?
- [llm_wiki](https://github.com/nashsu/llm_wiki) - uses Obsidian and has a desktop application

Publishing:
- [Quartz](https://quartz.jzhao.xyz/) — publish the wiki as a static site to GitHub Pages.

## Source Documents

The first three documents to be ingested into the wiki:

1. **Coinbase 10-K** — [SEC filing](https://investor.coinbase.com/financials/sec-filings/sec-filings-details/default.aspx?FilingId=19142207)
2. **Circle 10-K** — [SEC filing](https://investor.circle.com/financials/sec-filings/sec-filings-details/default.aspx?FilingId=19230318)
3. **Strategy 10-K** — [PDF](https://assets.contentstack.io/v3/assets/bltf8d808d9b8cebd37/bltb2a1a99f8fe760de/69978d8ecf7e250008e6854b/form-10-k_02-19-2026.pdf) (may change link to HTML)

## Next steps 

Publish `index.md` and `log.md` in this repo.

`index.md` should have a short intro ("We started publishing summaries of fintech company reports on this page")
followed by summary of "Business description" from the annual reports.

Upon completion we will need to solve:

- [ ] which LLM or endpoint do we use
- [ ] where the `ingest` command is stored, how it is invoked and what works when it is called 
- [ ] which paths the raw and markdown files are at in this repo
- [ ] other considerations 

No rendering of markdown to HTML is needed at this point.

This section may be an Issue.



 
 
