# PlasticList Exploratory Data Analysis

> An exploratory analysis of 618 PlasticList lab samples across 236 Bay Area food and beverage products, including samples collected at Stanford dining locations.

**Live report:** [aayanahmed200.github.io/stanford-daily-plasticlist-eda](https://aayanahmed200.github.io/stanford-daily-plasticlist-eda/)

**Stanford Daily series:** [The Price of Prestige](https://aayanahmed200.github.io/stanford-daily-price-of-prestige/) · [Blotter Fiction](https://aayanahmed200.github.io/stanford-daily-blotter-fiction/) · [ICE Extraction Pipeline](https://aayanahmed200.github.io/stanford-daily-biglocal-ice-pipeline/)

[![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/) [![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/) [![Matplotlib](https://img.shields.io/badge/matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)](https://matplotlib.org/) [![Quarto](https://img.shields.io/badge/quarto-75AADB?style=for-the-badge&logo=quarto&logoColor=white)](https://quarto.org/) [![GitHub Actions](https://img.shields.io/badge/github%20actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/features/actions)

## Overview

This report explores PlasticList's measurements of phthalates and bisphenols in food and beverage products. It compares chemical measurements across product groups, looks at samples collected at Stanford dining locations, and examines how repeated samples of the same product vary.

The analysis is descriptive. Its purpose is to explore the dataset and its measurement patterns, not to rank products as safe or unsafe or estimate an individual's health exposure.

## Highlights

- 618 samples covering 236 unique products and 18 measured chemicals.
- DEHP and DEHT were detected above the lab's limit of quantification in a majority of samples.
- Detection rates and measured concentrations vary substantially by chemical and product group.
- Repeated samples of the same product can differ, which is important when interpreting individual measurements.
- Stanford dining samples are included as a small subset of the larger dataset.

## Implementation

The source notebook is `analysis.qmd`, written in Python with pandas and Matplotlib. The source data is bundled in `data/plastic.tsv` so the report does not depend on an external download URL at render time. Quarto renders the notebook into a self-contained HTML report; the published series page provides a landing summary and links to the full analysis.

The notebook flags an important data-cleaning caveat: values reported below the limit of quantification are strings such as `<3550`. The current digit-extraction step converts those strings to the numeric threshold, which treats non-detects as threshold-level values and can overstate detection rates and apparent concentrations.

## Repository structure

- `analysis.qmd` — source notebook containing the analysis, code, figures, and narrative.
- `analysis.html` — rendered, self-contained report.
- `data/plastic.tsv` — source dataset used by the notebook.
- `site/` — published landing page, full report copy, and shared Stanford Daily series stylesheet.
- `requirements.txt` — Python dependencies for the analysis.

## Status and limitations

The findings describe the samples in this dataset, not all products or servings. The source is a volunteer-run testing project with a limited sample and no peer review. Below-LOQ values are currently represented by their numeric thresholds for parts of the analysis, which affects detection and concentration summaries. These results should not be interpreted as direct exposure estimates or health conclusions. The published site carries its own copy of the report at `site/analysis.html`, separate from the rendered `analysis.html` at the repository root, so a re-render only reaches the site once that copy is updated.

## License

MIT. See [LICENSE](LICENSE).
