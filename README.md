# PlasticList EDA

Exploratory analysis of [PlasticList](https://www.plasticlist.org/)'s food chemical testing
data, done for a data journalism assignment at the Stanford Daily. The dataset covers 618 lab
samples across 236 Bay Area food and beverage products tested for phthalates and bisphenols,
including several items collected from Stanford dining halls.

Full writeup: [`analysis.html`](analysis.html) (rendered from [`analysis.qmd`](analysis.qmd))

## About

PlasticList bought hundreds of products from Bay Area grocery stores, fast food chains, coffee
shops, and a few Stanford dining locations, and sent them to a lab to be tested for plastic-
associated chemicals. This project works through the resulting dataset to see what patterns hold
up, where the data is too sparse to say much, and how a couple of Stanford dining hall samples
compare to everything else that was tested.

The PlasticList team is explicit that their sample sizes are small and their results shouldn't be
read as a verdict on any single product. This analysis tries to hold onto that caution throughout
rather than overstate what 1-3 lab samples per product can support.

## Data

The raw dataset is a TSV of 618 samples with columns for the product, where and when it was
collected, and measured concentrations (in ng/serving, ng/g, and a few normalized forms) for 18
phthalates and bisphenols. A copy is included at [`data/plastic.tsv`](data/plastic.tsv) so the
analysis doesn't depend on an external URL staying available; the original assignment source is:

```
https://jaygupta797.github.io/slides/datasci/plastic.tsv
```

## Setup

```bash
git clone https://github.com/aayanahmed20/plasticlist-eda.git
cd plasticlist-eda
pip install -r requirements.txt
quarto render analysis.qmd
```

This renders `analysis.qmd` to `analysis.html`. [Quarto](https://quarto.org/) needs to be
installed separately (`quarto --version` to check).

## Repository Structure

```
.
├── analysis.qmd        # main notebook: data cleaning, EDA, figures, writeup
├── analysis.html        # rendered output
├── data/
│   └── plastic.tsv      # PlasticList dataset (as provided for the assignment)
├── requirements.txt
└── README.md
```

## Key Findings

- Of the 18 chemicals tested, only DEHP and DEHT were detected above the lab's limit of
  quantification in a majority of samples — most of the rest were non-detects 85-100% of the
  time, which limits how much this dataset can say about them individually.
- Processed and fast foods tended to show higher DEHP levels than less-processed items like
  produce, meat, and water, consistent with patterns PlasticList reported in their own writeup.
- A Stanford dining hall meal (beans, chicken, rice, and cauliflower from Arrillaga) averaged
  about 12,000 ng of DEHP per serving across three samples, in the 94th percentile of all
  current-day products tested here.
- That said, replicate measurements of the same product disagreed by a median of about 13%, and
  by 40%+ for some products, including the Stanford meal itself — a reminder that any single
  ranking in this dataset comes with real measurement noise attached.

See the full writeup for context, caveats, and how each figure was produced.

## Limitations

This is a class exploratory-analysis exercise, not a scientific study. Sample sizes are small,
non-detect values are approximated rather than treated as unknown, and the data covers a short
window in 2024 rather than a trend over time. See the "Limitations" section of the writeup for
the full list.
