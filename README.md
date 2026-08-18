# Stanford Daily PlasticList EDA

[![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)

Exploratory analysis of [PlasticList](https://www.plasticlist.org/)'s food chemical testing data, done for a data journalism assignment at the Stanford Daily. The dataset covers 618 lab samples across 236 Bay Area food and beverage products tested for phthalates and bisphenols, including a few items collected from Stanford dining halls.

Full writeup: [`analysis.html`](analysis.html) (rendered from [`analysis.qmd`](analysis.qmd))

## Why this exists

PlasticList bought hundreds of products from Bay Area grocery stores, fast food chains, coffee shops, and a few Stanford dining locations, then sent them to a lab to be tested for plastic-associated chemicals. I wanted to work through the resulting dataset myself and see what patterns actually hold up, where the data is too sparse to say much, and how the Stanford dining hall samples compare to everything else that was tested.

PlasticList is upfront that their sample sizes are small and their results shouldn't be read as a verdict on any single product. This analysis tries to hold onto that caution throughout instead of overstating what 1-3 lab samples per product can support.

## The data

The raw dataset is a TSV of 618 samples with columns for the product, where and when it was collected, and measured concentrations (in ng/serving, ng/g, and a few normalized forms) for 18 phthalates and bisphenols. A copy is included at [`data/plastic.tsv`](data/plastic.tsv) so the analysis doesn't depend on an external URL staying available; the original assignment source is `https://jaygupta797.github.io/slides/datasci/plastic.tsv`.

One quirk that shapes a lot of the analysis: concentrations below the lab's limit of quantification are recorded as strings like `"<3550"` rather than left blank. `analysis.qmd` treats that as a real measurement during cleaning, which inflates both detection rates and average concentrations for anything that's mostly non-detects - this is why the writeup spends real time on which chemicals are even worth analyzing individually.

## Key findings

- Of the 18 chemicals tested, only DEHP and DEHT were detected above the lab's limit of quantification in a majority of samples - most of the rest were non-detects 85-100% of the time, which limits how much this dataset can say about them individually.
- Processed and fast foods tended to show higher DEHP levels than less-processed items like produce, meat, and water, consistent with patterns PlasticList reported in their own writeup.
- A Stanford dining hall meal (beans, chicken, rice, and cauliflower from Arrillaga) averaged about 12,000 ng of DEHP per serving across three samples, in the 94th percentile of all current-day products tested here - though its replicate range overlaps with some of the fast-food items it's compared against, so that ranking is closer than a single number suggests.
- Replicate measurements of the same product disagreed by a median of about 13%, and by 40%+ for some products, including the Stanford meal itself. That noise tends to concentrate at low DEHP concentrations rather than high ones, which is a useful sanity check on the top-15 rankings.

See the full writeup for context, caveats, and how each figure was produced.

## Tech stack

- Python (pandas, numpy, matplotlib)
- Quarto for rendering the notebook to HTML
- Jupyter as the execution engine

## Project structure

- `analysis.qmd` - main notebook: data cleaning, EDA, figures, writeup
- `analysis.html` - rendered output
- `data/plastic.tsv` - PlasticList dataset (as provided for the assignment)
- `requirements.txt`

## Limitations

This is a class exploratory-analysis exercise, not a scientific study. Sample sizes are small, non-detect values are approximated rather than treated as unknown, and the data covers a short window in 2024 rather than a trend over time. See the "Limitations" section of the writeup for the full list.

## License

MIT — see [LICENSE](LICENSE). The underlying dataset belongs to
[PlasticList](https://www.plasticlist.org/); see their site for terms of reuse.
