---
title: "Financial Agent Hub"
source: "https://replit.com/@cykchrischan/Financial-Agent-Hub"
author:
  - "[[replit]]"
published:
created: 2026-05-03
description: "Build and deploy software collaboratively with the power of AI without spending a second on setup."
tags:
  - "clippings"
---
In summary, the most interesting aspect is the comprehensive AI-powered financial analysis platform that parses Obsidian markdown files from a GitHub repo into semantic-searchable JSON, integrates Perplexity AI across five workflows (A-E), automates GitHub PRs with review comments, and delivers a mobile PWA dashboard for stock valuation, fundamentals, overviews, cost-return segments, and HK-IPO tracking.

## Headlines

- **Backend foundation completes with 77 parsed finance records loaded into memory, semantic search via Perplexity embeddings, and full API endpoints for memory management and agent execution.** All endpoints validated with typechecks passing and server running cleanly on port 8080.
- **Five workflows (A-E) wired to Perplexity AI agent with GitHub write-back automation**, creating branches, commits, PRs, and review comments; Workflow E handles segment splitting with existence checks and renames.
- **Mobile-first PWA dashboard planned with React+Vite, featuring moat-cycle scatter plots, valuation comparisons, ticker drill-downs, HK-IPO scoring radars, and AI trigger buttons** that notify via PR links and summaries.
- **OpenAPI spec drives codegen for type-safe React Query hooks**, enabling live GitHub data reads/writes without auth in browser; global semantic search overlays results by type.

## Things

- **People**: yk-chris (GitHub username), Xuan Liu (unrelated WRDS doc), Craig Kielburger (WE Charity founder).
- **Places**: yk-chris/Obsidian_2nd_brain (GitHub repo), 03-(FINANCE) 財務筆記/ (folder), Replit (platform).
- **Numbers**: 77 records, 5 workflows (A-E), port 8080, 41 seconds (work time), 13 minutes (checkpoint).
- **Things & Concepts**: GITHUB_TOKEN, PERPLEXITY_API_KEY (secrets), semantic search (cosine similarity), moat-cycle scatter plot, PWA (manifest/service worker), OpenAPI spec (openapi.yaml), FinanceRecord (JSON schema).

---

## #1 - Finance Memory Layer & AI Agent Backend

## What & Why

Build the backend foundation: parse all existing Obsidian markdown files from the GitHub repo into structured JSON records, implement `load_memory()` and `search_memory(query)` with semantic search, add GitHub write-back (branch → commit → PR → review comment), and wire up Perplexity API as the AI agent for generating analysis content across all five workflows (A–E from schema\_finance.md).

The GitHub repo is `yk-chris/Obsidian_2nd_brain` (public read, authenticated write). Token stored as env secret `GITHUB_TOKEN`. Perplexity key stored as `PERPLEXITY_API_KEY`.

## Done looks like

- GET `/api/memory/load` returns the full in-memory JSON store of all parsed finance records (TA, fundamental, overview, industry, IPO)
- GET `/api/memory/search?q=...` returns semantically ranked results using cosine similarity on embeddings (use OpenAI-compatible Perplexity embeddings or a lightweight local model like `@xenova/transformers` all-MiniLM)
- POST `/api/agent/run` accepts `{ workflow: "A"|"B"|"C"|"D"|"E", ticker?, date? }`, calls Perplexity to generate content, writes back to GitHub, creates a PR, and posts a review comment on the PR with a summary notification
- All existing markdown files are parsed into typed JSON records matching each workflow's schema (see schema\_finance.md)
- The OpenAPI spec (`lib/api-spec/openapi.yaml`) defines all endpoints so the frontend can use generated hooks

## Out of scope

- Authentication / user accounts
- Historical embedding index persistence (in-memory is fine for first build)
- Real-time GitHub webhook listening

## Steps

1. **Add secrets** — Register `GITHUB_TOKEN` and `PERPLEXITY_API_KEY` as environment secrets. Read the `environment-secrets` skill before this step.
2. **OpenAPI spec** — Define all endpoints in `lib/api-spec/openapi.yaml`:
	- `GET /memory/load` → returns `MemoryStore` (array of `FinanceRecord`)
		- `GET /memory/search` with `q` query param → returns ranked `FinanceRecord[]`
		- `POST /agent/run` → accepts `AgentRunRequest`, returns `AgentRunResult` with PR URL and summary
		- `GET /tickers` → lists all known tickers with their available workflows
3. **Run codegen** — `pnpm --filter @workspace/api-spec run codegen` after writing the spec.
4. **Markdown parser** — Write a GitHub fetcher + markdown parser service in `artifacts/api-server/src/lib/github.ts` that:
	- Fetches directory listings for all 5 folders via GitHub REST API
		- Parses frontmatter + body of each markdown file into typed `FinanceRecord` objects
		- Extracts key fields: ticker, 綜合公允價值, 護城河強度, 週期暴露度, scores, segments, IPO scoring table rows
		- Stores in an in-memory `Map<string, FinanceRecord>` keyed by `{workflow}:{ticker}`
5. **Semantic search** — Write `artifacts/api-server/src/lib/search.ts`:
	- On startup, embed all record summaries using `GET https://api.perplexity.ai/embeddings` (or a lightweight local model)
		- `search_memory(query)`: embed the query, compute cosine similarity against all stored embeddings, return top-k ranked records
6. **Perplexity AI agent** — Write `artifacts/api-server/src/lib/agent.ts`:
	- For all five workflows (A, B, C, D, E), build an appropriate system prompt referencing the relevant skill description from schema\_finance.md
		- Workflow E logic: after generating cost-return analysis, split output into one record per business segment (`{ticker}_{貢獻佔比}_{業務部門}.md`), applying the existence check rule (match by ticker + 業務部門, rename if 貢獻佔比 changed)
		- Call Perplexity `sonar-pro` or `sonar` model with the prompt
		- Parse the response into the workflow's output format
7. **GitHub write-back** — Write `artifacts/api-server/src/lib/githubWrite.ts`:
	- Create a new branch `agent/{workflow}/{ticker}-{date}`
		- Commit the generated markdown to the correct folder using GitHub Contents API
		- Open a PR against `main` with a structured description
		- Post a review comment on the PR with a formatted notification summary (ticker, workflow, key metrics extracted)
8. **Route handlers** — Wire everything up in `artifacts/api-server/src/routes/`:
	- `GET /memory/load` → calls parser, returns JSON
		- `GET /memory/search` → calls semantic search
		- `POST /agent/run` → calls agent + write-back
		- `GET /tickers` → returns ticker list with workflow availability map

## Relevant files

- `artifacts/api-server/src/app.ts`
- `artifacts/api-server/src/routes/index.ts`
- `artifacts/api-server/src/routes/health.ts`
- `lib/api-spec/openapi.yaml`
- `lib/api-client-react/src/generated/api.ts`

## #2 - Finance PWA Dashboard — Mobile Web App

## What & Why

Build a mobile-first PWA (React + Vite) that reads from and writes to the GitHub Obsidian finance repo via the backend API. The app has two main sections:

**Section One — Stock Analysis Dashboard**: Compare a list of tickers across valuation (Workflow A), fundamental/moat/cycle (Workflow B), overviews (Workflow C), and cost-return by segment (Workflow E). The experience starts with a high-level multi-ticker comparison dashboard, then drills down into per-ticker detail pages.

**Section Two — HK-IPO Tracker**: Browse daily IPO notes with scoring tables, candidate watchlists, and recommendation levels. Filter by date, score, or sector.

AI agent trigger buttons call `POST /api/agent/run` to invoke the Perplexity-powered analysis, then notify the user that a PR has been created in GitHub with the new content.

## Done looks like

- Installable as a PWA on iOS/Android (manifest + service worker)
- Section One: Multi-ticker comparison table/chart showing 綜合公允價值, 護城河強度 (Y-axis), 週期暴露度 (X-axis), moat-cycle scatter plot, valuation gap vs current price
- Section One: Per-ticker drill-down page showing valuation detail, fundamental scores, company overview summary, and segment cost-return breakdown (産業)
- Section Two: Daily IPO list with scoring cards (market heat, business quality, sponsor quality, valuation reasonableness, float risk), total score badge, recommendation level badge
- Each section has AI agent buttons (e.g. "Run TA Analysis", "Run Fundamental", "Run HK-IPO") that call the backend and show a success toast with the PR link
- Global search bar calls `/api/memory/search` for semantic ticker/concept search
- GitHub-connected: reads live data from the backend which fetches from GitHub on demand

## Out of scope

- Offline mode / full PWA cache of all GitHub data
- Authentication / login
- Direct GitHub OAuth in the browser (all writes go through backend)
- Portfolio tracking / transaction recording

## Steps

1. **Create artifact** — Create a new `react-vite` artifact at slug `finance-dashboard` with `previewPath: "/"`. This replaces the root path with the PWA.
2. **PWA setup** — Add `vite-plugin-pwa` with a web app manifest (name, icons, theme color, display: standalone). Configure service worker for basic shell caching.
3. **OpenAPI codegen** — After the backend task's spec is finalized, run `pnpm --filter @workspace/api-spec run codegen` and use the generated React Query hooks throughout the app.
4. **App shell & navigation** — Bottom tab bar with two tabs: "分析" (Section One) and "HK-IPO" (Section Two). Add a global search overlay triggered by a top search icon.
5. **Section One — Ticker List & Comparison Dashboard**:
	- Top-level view: cards per ticker showing 綜合公允價值, 護城河強度, 週期暴露度, upside %, workflow badges (A/B/C/E available)
		- Moat-Cycle scatter chart: X = 週期暴露度, Y = 護城河強度, bubbles sized by market cap or upside
		- Valuation comparison bar chart: fair value vs (implied) current price gap across all tickers
		- "Run AI Analysis" floating action buttons per ticker (dropdown: A, B, C, D, E workflows)
6. **Section One — Ticker Detail Page**:
	- Valuation tab: fair value breakdown, TA analysis summary, target price range
		- Fundamental tab: moat type, moat score bar, cycle exposure score, business model summary
		- Overview tab: Part A (moat & margin), Part B (bottleneck deep-dive) rendered as formatted sections
		- Cost-Return tab: stacked bar chart of business segments by contribution %, per-segment detail cards
7. **Section Two — HK-IPO Section**:
	- Date picker / list of available IPO daily files
		- Per-day view: IPO cards with 5-dimension radar/bar chart (市場熱度, 業務質素, 保薦人及基石, 估值合理性, 流通風險), total score badge, recommendation badge (積極認購 / 審慎認購 / 不建議), first-day premium field
		- Candidate watchlist table at bottom
		- "Run HK-IPO Analysis" button → calls Workflow D → shows PR link toast
		- Score summary table comparing all IPOs in the selected date
8. **Search overlay** — Full-screen search modal calling `/api/memory/search`, showing result cards grouped by type (Valuation / Fundamental / IPO).
9. **Agent result notifications** — After `POST /agent/run`, show a bottom sheet with: "PR created", clickable GitHub PR link, and a short summary of key metrics extracted (e.g. 綜合公允價值 = $X, 護城河強度 = Y).
10. **PWA manifest & icons** — Generate app icon (finance/chart theme), configure manifest.json with correct start\_url and scope relative to previewPath.

## Relevant files

- `lib/api-client-react/src/generated/api.ts`
- `lib/api-client-react/src/generated/api.schemas.ts`
- `lib/api-spec/openapi.yaml`
- `artifacts/api-server/src/routes/index.ts`

Dependencies