# Parallel audit workers (subagent scopes)

Platform-neutral definitions for delegating independent audit slices. Same routing and scripts as `references/procedures/` and `AGENTS.md` — this file only names **who runs what** when using a Task/subagent tool.

Orchestration: run `site_mapper.py` if needed → spawn workers in parallel → merge JSON → `finding_verifier.py` → Health Score. Do **not** run `generate_report.py` and the same per-script workers on the same URL simultaneously.

---

## seo-technical

Analyzes crawlability, indexability, security, redirects, and Core Web Vitals.

**Scope:** robots.txt + AI crawlers, security headers, CWV via PSI, redirects, canonicals, IndexNow, sitemaps, mobile readiness.

| Script | Purpose |
|--------|----------|
| `robots_checker.py` | robots.txt + AI crawler status |
| `security_headers.py` | Response headers |
| `pagespeed.py` | PageSpeed Insights (CWV) |
| `redirect_checker.py` | Redirect chains |
| `canonical_checker.py` | Canonical validation |
| `indexnow_checker.py` | IndexNow key |
| `sitemap_checker.py` | Sitemap health |

**References:** `references/technical-checklist.md`, `references/crawl-indexation.md`
