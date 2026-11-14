# Stanford Daily: PlasticList EDA

[![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/) [![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)

Exploratory analysis of 618 PlasticList lab samples across 236 Bay Area food and beverage products, including samples from Stanford dining locations.

**Full write-up:** [`analysis.html`](analysis.html)

## Overview

The analysis examines measured phthalates and bisphenols, compares product groups, and checks how repeat samples from the same product vary.

## Highlights

- DEHP and DEHT were detected above the lab's quantification limit in a majority of samples; most other measured chemicals were non-detects in 85–100% of samples.
- Processed and fast foods tended to show higher DEHP measurements than less-processed groups in this dataset.
- A Stanford dining-hall meal averaged about 12,000 ng of DEHP per serving across three samples.
- Repeat measurements had a median difference of about 13%; some products differed by 40% or more.

## Technology

Python, pandas, NumPy, matplotlib, Quarto, and Jupyter.

## Run locally

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
quarto render analysis.qmd
```

Quarto must be installed separately to render the source notebook to HTML.

## Notes and limitations

This is exploratory analysis, not a scientific study. The included TSV contains 618 samples and concentration fields for 18 chemicals. Values below the lab's quantification limit affect detection rates and averages. Sample sizes are small, and repeat counts can change percentile estimates. The results should not be used as a verdict on an individual product. The underlying data belongs to [PlasticList](https://www.plasticlist.org/) and is subject to its terms.

## License

MIT — see `LICENSE`.
