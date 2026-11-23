# Stanford Daily: PlasticList EDA

**Live:** [aayanahmed200.github.io/stanford-daily-plasticlist-eda](https://aayanahmed200.github.io/stanford-daily-plasticlist-eda/)

**Series:** [The Price of Prestige](https://aayanahmed200.github.io/stanford-daily-price-of-prestige/) · [Blotter fiction](https://aayanahmed200.github.io/stanford-daily-blotter-fiction/) · [ICE pipeline](https://aayanahmed200.github.io/stanford-daily-biglocal-ice-pipeline/)

[![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/) [![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/) [![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

Exploratory analysis of 618 PlasticList lab samples across 236 Bay Area food and beverage products, including samples from Stanford dining locations.

## Overview

The analysis examines measured phthalates and bisphenols, compares product groups, and checks how repeat samples from the same product vary. It is written as a single rendered notebook, so every figure can be traced back to the code that produced it.

## Highlights

- DEHP and DEHT were detected above the lab's quantification limit in a majority of samples.
- Most other measured chemicals were non-detects in 85-100% of samples.
- Processed and fast foods tended to show higher DEHP measurements than less-processed groups in this dataset.
- A Stanford dining-hall meal averaged about 12,000 ng of DEHP per serving across three samples.
- Repeat measurements had a median difference of about 13%; some products differed by 40% or more.

## Repository contents

- `analysis.qmd` - the source notebook: code, figures and prose.
- `analysis.html` - the rendered, self-contained report.
- `site/` - the published page: a landing summary, the full report, and the shared stylesheet.
- `data/plastic.tsv` - the dataset the analysis reads.

## Run locally

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
quarto render analysis.qmd
```

Quarto must be installed separately to render the source notebook to HTML. The published site reads `site/index.html`, `site/analysis.html` and `site/series.css` directly; after re-rendering, copy `analysis.html` into `site/`.

## Notes and limitations

The findings describe the 618 samples in this dataset, not every product or serving. The analysis is observational and should not be treated as a direct measure of an individual's exposure or health risk.

## License

MIT - see `LICENSE`.
