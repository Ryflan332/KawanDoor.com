---
description: "Run comprehensive SEO audit and analysis using Claude SEO"
argument-hint: "[audit|page|technical|content|schema|sitemap|geo] [url]"
---

# Claude SEO Workflow

This workflow executes SEO analysis commands for your website.

## Usage

- `/seo audit [url]` - Full website audit with technical, content, schema, sitemap, and performance analysis
- `/seo page [url]` - Deep single-page analysis
- `/seo technical [url]` - Technical SEO audit (crawlability, indexability, security, Core Web Vitals)
- `/seo content [url]` - E-E-A-T and content quality analysis
- `/seo schema [url]` - Schema.org markup validation and generation
- `/seo sitemap [url]` - XML sitemap structure and quality audit
- `/seo geo [url]` - Generative Engine Optimization (AI Overviews, Perplexity, ChatGPT readiness)
- `/seo local [url]` - Local SEO analysis (GBP, NAP consistency, local reviews)

> **Note:** If no URL is provided, default to the current project website: `https://rollingdoorjabodetabek.com/`

## Execution Steps

1. **Parse Arguments**:
   - Determine the requested command (e.g., `audit`, `page`, `technical`, `content`, `schema`, etc.). Default to `audit` if unspecified.
   - Extract the target URL (defaults to `https://rollingdoorjabodetabek.com/` if omitted).

2. **Invoke Appropriate SEO Skill**:
   - For `audit`: Read instructions in `.agent/skills/seo-audit/SKILL.md` and `.agent/skills/seo/SKILL.md`.
   - For `technical`: Read `.agent/skills/seo-technical/SKILL.md`.
   - For `content`: Read `.agent/skills/seo-content/SKILL.md`.
   - For `schema`: Read `.agent/skills/seo-schema/SKILL.md`.
   - For `sitemap`: Read `.agent/skills/seo-sitemap/SKILL.md`.
   - For `geo`: Read `.agent/skills/seo-geo/SKILL.md`.
   - For `local`: Read `.agent/skills/seo-local/SKILL.md`.

3. **Perform Analysis**:
   - Execute the corresponding Python scripts located in `.agent/skills/scripts/` (e.g., `python .agent/skills/scripts/render_page.py <url>`, `extract_metadata.py`, `check_schema.py`, etc.).
   - Follow the directives and evaluation criteria defined in the skill files.

4. **Generate Report**:
   - Summarize findings with an SEO Health Score (0-100).
   - Categorize recommendations by priority: **Critical**, **High**, **Medium**, and **Low**.
   - Output actionable fixes directly to the user.
