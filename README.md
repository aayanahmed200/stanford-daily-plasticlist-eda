# PlasticList Data Analysis

An exploratory analysis of PlasticList's laboratory measurements for chemicals in food and drink products, including samples collected at Stanford dining locations.

**[Read the rendered analysis](analysis.html)**

## Overview

The Quarto report examines 618 samples covering 236 food and beverage products. It looks at measured phthalates and bisphenols, compares product groups, and checks how repeat samples of the same product vary. The analysis uses the absolute nanograms-per-serving columns in the supplied dataset.

## Repository contents

- `analysis.qmd` — source document, code and narrative.
- `analysis.html` — rendered report.
- `data/plastic.tsv` — the dataset used by the analysis.
- `requirements.txt` — Python dependencies.

## Technology

Python, pandas, NumPy, matplotlib, Jupyter and Quarto. Install the packages from `requirements.txt`; install [Quarto](https://quarto.org/) separately to render the report.

## Run locally

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
quarto render analysis.qmd
```

The source data is included in `data/plastic.tsv`, so the analysis does not need to download it again. Open `analysis.html` to read the checked-in report without rendering it.

## Scope and limitations

This is an exploratory analysis of the samples in the supplied dataset, not a representative survey of all products or servings. The notebook notes that values reported below the laboratory's limit of quantification are converted to the stated threshold for parts of the analysis; this simplification can overstate apparent detections and measured amounts for non-detects. The results do not establish personal exposure or the health risk of any product.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for the full text.
