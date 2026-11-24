# Stanford Daily: PlasticList EDA

**Live:** [aayanahmed200.github.io/stanford-daily-plasticlist-eda](https://aayanahmed200.github.io/stanford-daily-plasticlist-eda/)

**Series:** [The Price of Prestige](https://aayanahmed200.github.io/stanford-daily-price-of-prestige/) · [Blotter fiction](https://aayanahmed200.github.io/stanford-daily-blotter-fiction/) · [ICE pipeline](https://aayanahmed200.github.io/stanford-daily-biglocal-ice-pipeline/)

[![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/) [![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/) [![Quarto](https://img.shields.io/badge/quarto-75AADB?style=for-the-badge&logo=quarto&logoColor=white)](https://quarto.org/) [![GitHub Actions](https://img.shields.io/badge/github%20actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/features/actions)

Exploratory analysis of 618 PlasticList lab samples across 236 Bay Area food and beverage products, including samples from Stanford dining locations.

## Overview

The analysis examines measured phthalates and bisphenols, compares product groups, and checks how repeat samples from the same product vary. It is written as a single rendered notebook, so every figure can be traced back to the code that produced it.

## How it was made

The samples come from the PlasticList dataset, committed as `data/plastic.tsv`. The analysis is one Quarto notebook, `analysis.qmd`, written in Python with pandas: it groups the measured chemicals by product category, compares detections against the lab's quantification limit, and checks repeat samples from the same product for spread. Rendering it produces a single self-contained HTML file, so the charts travel with the code that made them.

The published page wraps the full report in a short landing summary and uses the same stylesheet as the other three pages in the series. A GitHub Actions workflow builds `site/` and deploys it to GitHub Pages on every push to `main`.

## Highlights

- DEHP and DEHT were detected above the lab's quantification limit in a majority of samples.
- Most other measured chemicals were non-detects in 85-100% of samples.
- Processed and fast foods tended to show higher DEHP measurements than less-processed groups in this dataset.
- A Stanford dining-hall meal averaged about 12,000 ng of DEHP per serving across three samples.
- Repeat measurements had a median difference of about 13%; some products differed by 40% or more.

## Repository contents

- `analysis.qmd` — the source notebook: code, figures and prose.
- `analysis.html` — the rendered, self-contained report.
- `site/` — the published page: a landing summary, the full report, and the shared stylesheet.
- `data/plastic.tsv` — the dataset the analysis reads.

## Notes and limitations

The findings describe the 618 samples in this dataset, not every product or serving. The analysis is observational and should not be treated as a direct measure of an individual's exposure or health risk. The published site reads `site/index.html`, `site/analysis.html` and `site/series.css` directly, so a re-render has to be copied into `site/` before it goes live.

## License

MIT — see `LICENSE`.
