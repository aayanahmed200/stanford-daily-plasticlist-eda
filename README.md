# Stanford Daily: PlasticList EDA

[![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/) [![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)

Exploratory analysis of 618 PlasticList lab samples across 236 Bay Area food and beverage products, including samples from Stanford dining locations.

**Full write-up:** [`analysis.html`](analysis.html)

## Overview

The analysis examines measured phthalates and bisphenols, compares product groups, and checks how repeat samples from the same product vary. It follows PlasticList's own caution that small sample counts are not a verdict on an individual product.

## Highlights

- DEHP and DEHT were detected above the lab's quantification limit in a majority of samples; most other measured chemicals were non-detects in 85–100% of samples.
- Processed and fast foods tended to show higher DEHP measurements than less-processed groups in this dataset.
- A Stanford dining-hall meal averaged about 12,000 ng of DEHP per serving across three samples. Its estimated percentile is sensitive to the small replicate count and overlapping ranges.
- Repeat measurements had a median difference of about 13%; some products differed by 40% or more.

## Data and methodology

The included TSV contains 618 samples with product, collection, and concentration fields for 18 chemicals. Values below the lab's quantification limit appear as strings such as `<3550`; the notebook's treatment of these values affects calculated detection rates and averages and should be considered when interpreting results.

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

This is exploratory analysis, not a scientific study. Sample sizes are small, some measurements are near or below quantification limits, and the dataset represents a short collection period rather than a trend over time. Avoid drawing conclusions about any single product from these results.

## License

MIT — see `LICENSE`. The underlying data belongs to [PlasticList](https://www.plasticlist.org/) and is subject to its terms.
