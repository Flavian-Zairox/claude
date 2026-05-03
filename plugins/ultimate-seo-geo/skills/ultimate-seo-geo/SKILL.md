---
name: ultimate-seo-geo
description: Audits and optimizes websites for search engine visibility (SEO) and AI search citation (GEO), covering technical health, E-E-A-T content scoring, domain authority, structured data, rich results, and entity signals. Use when running SEO audits, diagnosing traffic drops or ranking losses, generating Schema.org JSON-LD, checking Core Web Vitals, crawlability, robots.txt, sitemaps, hreflang, backlinks, planning content strategy or site migrations, fixing indexing issues, or optimizing for AI Overviews, ChatGPT, and Perplexity. NOT for paid ads (PPC/SEM), social media strategy, email marketing, or general web development unrelated to search.
version: 1.8.5
---

# Ultimate SEO + GEO — LLM-Agnostic SEO Agent

| Attribute | Details |
| --- | --- |
| **Version** | 1.8.5 |
| **Updated** | 2026-04-11 |
| **License** | MIT |
| **Author** | Myk Pono |
| **Lab** | [lab.mykpono.com](https://lab.mykpono.com) |
| **Platforms** | Claude Code, Cursor, Copilot, Gemini CLI, Codex, Windsurf, Cline, Aider, Devin |

The definitive SEO and Generative Engine Optimization agent. LLM-agnostic — works on any platform that reads `AGENTS.md`.

**This file is the routing shell.** Detailed procedures for §1–§21 live under `references/procedures/`.

## 0. Before You Start

| Goal | Procedure file(s) | Also read / run |
|------|-------------------|-----------------|
| Full scored audit | `references/procedures/02-full-site-audit.md` | `references/audit-script-matrix.md`, `generate_report.py` |
| AI citations / GEO | `references/procedures/03-geo-ai-search.md` | `references/ai-search-geo.md` |
| Schema only | `references/procedures/05-schema-structured-data.md` | `references/schema-types.md` |
| Local | `references/procedures/12-local-seo.md` | `references/local-seo.md` |
| Migration | `references/procedures/20-site-migration.md` | `references/site-migration.md` |

## Global guardrails

- Never fabricate metrics without script data
- Every finding: Finding / Evidence / Impact / Fix / Confidence
- High-Risk changes (robots.txt, canonicals, redirects): describe + confirm before outputting
- Internal Mode (/100 score valid) vs Competitive Mode (External Observation Only)

## Procedure index

| § | File |
|---|------|
| 1–21 | `references/procedures/0{1..9}-*.md` and `references/procedures/{10..21}-*.md` |
