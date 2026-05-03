# Ultimate SEO + GEO — LLM-Agnostic SEO Agent

| Attribute | Details |
| --- | --- |
| **Version** | 1.8.5 |
| **Updated** | 2026-04-06 |
| **License** | MIT |
| **Author** | Myk Pono |
| **Homepage** | [lab.mykpono.com](https://lab.mykpono.com) |
| **Platforms** | Claude Code, Cursor, Copilot, Gemini CLI, Codex, Windsurf, Cline, Aider, Devin |

The definitive SEO and Generative Engine Optimization agent. LLM-agnostic — works on any
platform that reads `AGENTS.md`. Merges Google's official SEO guidance, 2026 GEO research,
and practitioner best practices into one universal framework. Every finding comes with a
clear fix directive — not just diagnosis.

**Full instructions:** `SKILL.md` is the **routing shell** (§0 + global guardrails + procedure index). Detailed procedures for each § are in `references/procedures/*.md` — read only the file for the section you need. For domain-specific reference data, read the relevant file from `references/` (outside `procedures/`). Load at most **3 files** from `references/` per response (procedure files count toward that limit).

## 0. Before You Start

### Routing Index

| Goal | Read | Run |
|------|------|-----|
| Full scored audit | `references/audit-script-matrix.md` | `generate_report.py` |
| GEO / AI citations | `references/ai-search-geo.md`, `references/entity-optimization.md` | `robots_checker.py`, `entity_checker.py`, `llms_txt_checker.py` |
| Schema markup | `references/schema-types.md` | `validate_schema.py` |
| Technical / CWV | `references/technical-checklist.md` | `pagespeed.py`, `robots_checker.py`, `security_headers.py` |
| Content / E-E-A-T | `references/eeat-framework.md`, `references/core-eeat-framework.md` | `readability.py`, `article_seo.py` |
| CITE domain audit | `references/cite-domain-rating.md` | `link_profile.py` |
| Backlinks | `references/backlink-quality.md` | `backlink_analyzer.py` |
| Keywords / clusters | `references/keyword-strategy.md` | — |
| Links | `references/link-building.md` | `internal_links.py`, `broken_links.py`, `link_profile.py` |
| Local SEO | `references/local-seo.md` | `local_signals_checker.py` |
| Images | `references/image-seo.md` | `image_checker.py` |
| International / hreflang | `references/international-seo.md` | `hreflang_checker.py` |
| Programmatic SEO | `references/programmatic-seo.md` | `programmatic_seo_auditor.py` |
| Migration | `references/site-migration.md` | `redirect_checker.py` |
| Analytics / myths | `references/analytics-reporting.md` | — |
| Crawl / indexation | `references/crawl-indexation.md` | `sitemap_checker.py`, `duplicate_content.py`, `canonical_checker.py` |
| URL discovery | — | `site_mapper.py` |
| Extensions | `references/optional-extensions-mcp.md` | Optional MCP (DataForSEO, Firecrawl); monorepo: `extensions/README.md` |

### When NOT to Run a Full Audit

| User signal | Action |
|-------------|--------|
| **Google Ads / PPC** as the primary ask | Paid-media scope — no organic SEO audit |
| **GA4/GTM setup only** (no organic SEO question) | Measurement checklist only — no fabricated score |
| **Explicitly scoped** task (e.g. "only robots.txt + sitemap") | Stay in that scope |

### Audit Context: Internal vs. Competitive

| Signal | Context | What's Allowed |
|---|---|---|
| User says "my site", "our site", "I own" | **Internal Mode** | Full scored audit, all scripts, Execute mode, /100 Health Score |
| External URL the user does not own | **Competitive Mode** | Surface crawl only (homepage + up to 20 pages), no /100 Health Score, output labeled "External Observation Only" |

**When in doubt, ask:** "Is this your site, or are you analyzing a competitor?"

### The Three Modes

**Mode 1 — Audit:** Fetch the site, run checks, produce a scored report. Every finding has severity, evidence, impact, and fix. Output: SEO Health Score + prioritized findings.

**Mode 2 — Action Plan:** Turn audit findings into a phased, executable roadmap. Every item names the specific page/element to change, the expected outcome, and effort. Output: Implementation Phases table + Quick Wins.

**Mode 3 — Execute:** Do the work. Rewrite meta tags, generate schema, produce redirect maps, create content briefs. Every execution task ends with a verification step.

Most requests involve all three in sequence: **Audit → Plan → Execute**.

### Intake Checklist

Three questions only — skip any already answered.

| # | Question | Why |
|---|---|---|
| 1 | **What is the URL?** | Required for all modes |
| 2 | **What is the primary goal?** (traffic / AI citations / local leads / traffic drop / specific keyword) | Determines which modules run first |
| 3 | **Which mode?** Audit / Audit + Plan / Audit + Plan + Execute | Default to all three if unclear |
