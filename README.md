# Research Impact Explorer

Research Impact Explorer is an **exploratory** Python project that helps you **understand and communicate the research impact** of an individual researcher (or a small set of researchers) using publicly available scholarly metadata.

It is built for people who need a **quick, repeatable, and shareable impact snapshot**—with structured data exports and simple visuals—without spending hours manually compiling citation and publication details.

---

## Why this project exists

Researchers and teams often need to answer questions like:

- What are the most influential papers in a researcher’s portfolio?
- How does their output and citation footprint change over time?
- Which venues (journals/conferences) contribute most to their impact?
- What are the most common topics and collaboration patterns?
- How can we create a consistent “impact pack” for reporting, evaluation, or communication?

This project focuses on **exploration and storytelling** using data:
- Collect publications + citations
- Clean and structure them into usable datasets
- Generate summaries and charts to support narrative impact reporting

---

## Global usefulness: showcasing research reach and influence

Research impact is often global—papers influence **international labs, institutions, and communities**. This project is useful for:

- Building a **global impact narrative** for a researcher or lab
- Supporting **funding proposals** and **annual reports**
- Producing shareable artifacts (CSV + charts) to communicate influence to:
  - collaborators
  - research offices
  - hiring committees
  - conference organizers
  - public-facing research pages

> Note: The “global impact” signal is strengthened when enrichment sources provide affiliation / institution / location metadata. Depending on your configuration and data sources, you may be able to explore impact beyond citations—e.g., where citing authors are located, institutional reach, and topic diffusion.

---

## What you get (typical outputs)

Depending on the available metadata and the configuration you use, a run can generate:

- `publications.csv` — cleaned publication list (title, year, venue, citations, links, etc.)
- `citations.csv` — citation signals and derived metrics (if available)
- `summary.json` — computed summaries (top papers, top venues, yearly trends)
- `charts/` — simple visuals (top papers, venues, timeline trends)
- `exports/*.zip` — packaged bundle to share with others

Example output layout:

```text
outputs/
  publications.csv
  citations.csv
  summary.json
  charts/
    top_papers.png
    top_venues.png
    citations_over_time.png
  exports/
    impact_export.zip
```

## When to use it

### Best fit
- **Individual researchers** building an impact snapshot
- **Labs and small teams** generating consistent reporting
- **Research offices** doing lightweight exploratory analysis
- **Students** learning scholarly data exploration and impact metrics

### Not the best fit
- **Large-scale bibliometrics** across thousands of authors (you’ll need a dedicated pipeline)
- **High-stakes evaluation** where methodological rigor and field-normalization are required  
  - *(This project is exploratory; you can extend it, but treat it as a starting point.)*

---

## Data sources and configuration (important)

This project can use multiple sources depending on how the code is configured. Commonly used identifiers/keys include:

### ✅ Common values you may need to add

| Config name | What it is | Example |
|------------|------------|---------|
| `SCHOLAR_AUTHOR_ID` | Google Scholar Author ID | `aBcDeFgHiJkL` |
| `SERPAPI_KEY` | SerpAPI key for stable Scholar collection | `xxxxxxxxxxxxxxxxxxxx` |
| `MAILTO_EMAIL` | Contact email for polite API usage (e.g., OpenAlex) | `you@domain.com` |

> **Note:** Your code may not require all of these. They exist so users can **fill the missing keys** cleanly and safely.

## How to find your Google Scholar Author ID

1. Open your **Google Scholar profile**.
2. The URL will look like:

```text
https://scholar.google.com/citations?user=YOUR_AUTHOR_ID&hl=en
```

### Scholar
SCHOLAR_AUTHOR_ID=YOUR_SCHOLAR_ID_HERE

### SerpAPI (recommended for stable collection - some chart might not work without this)
SERPAPI_KEY=YOUR_SERPAPI_KEY_HERE

### Optional / enrichment etiquette
MAILTO_EMAIL=you@domain.com


