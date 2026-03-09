# LitSearch — Literature Discovery Tool

> Search 5 academic APIs simultaneously, auto-deduplicate, get free PDF links via Unpaywall, and generate Vancouver citations. No server, no API keys, runs entirely in the browser.

**[🔍 Live Demo →](https://mojo8787.github.io/litsearch)**

---

## Features

- **5 APIs in parallel** — Semantic Scholar, PubMed E-utilities, OpenAlex, CrossRef, Europe PMC
- **Free PDF links** — Unpaywall enriches results with legal open-access PDF links when available
- **3 search modes** — Keyword search, DOI lookup, PMID lookup
- **Smart deduplication** — same paper from multiple APIs is merged into one enriched record
- **Quality filtering** — removes journal covers, retractions, acknowledgement pages, and other CrossRef noise
- **Relevance sorting** — multi-source matches float to top; scored by title match, recency, completeness
- **Vancouver citations** — auto-formatted, copy per-card or copy entire reference list
- **Export** — RIS (→ Zotero / Mendeley) and BibTeX (→ LaTeX)
- **Zero dependencies** — single HTML file, no build step, no API keys required

## Usage

Open `index.html` in any modern browser — or visit the live site above.

### Keyword Search
Type your query and hit Search. All checked APIs are queried in parallel. Results appear ranked by relevance.

### DOI Lookup
Switch to the **DOI Lookup** tab and paste a DOI (e.g. `10.1016/j.watres.2023.120123`). Queries Semantic Scholar, OpenAlex, CrossRef, and Europe PMC to build the richest possible record. Unpaywall adds a free PDF link when available.

### PMID Lookup
Switch to the **PMID Lookup** tab and enter a PubMed ID. Fetches from PubMed then enriches via DOI lookup.

### Vancouver Citations
- Each result card shows its formatted Vancouver citation inline
- Click **⎘** on any card to copy that citation
- Switch to **¶ Vancouver** view for the full numbered reference list
- Click **⎘ Copy All** to copy the entire list to clipboard

### Export
- **↓ RIS** — imports into Zotero, Mendeley, EndNote
- **↓ BibTeX** — for LaTeX or any compatible reference manager

## APIs Used

| API | Base URL | Auth |
|-----|----------|------|
| Semantic Scholar | `api.semanticscholar.org` | None |
| PubMed E-utilities | `eutils.ncbi.nlm.nih.gov` | None |
| OpenAlex | `api.openalex.org` | None (polite pool) |
| CrossRef | `api.crossref.org` | None (polite pool) |
| Europe PMC | `www.ebi.ac.uk/europepmc/webservices/rest` | None |
| Unpaywall | `api.unpaywall.org` | Email param (enrichment only: free PDF links by DOI) |

All requests are made client-side directly from the browser. No data is sent to any backend.

## Deployment

This is a single static HTML file. To deploy:

1. Fork or clone this repo
2. Rename `lit_search_ui.html` → `index.html` (already done)
3. Enable GitHub Pages: **Settings → Pages → Source: main branch / root**
4. Your site will be live at `https://mojo8787.github.io/litsearch`

## License

MIT — free to use, modify, and distribute.
