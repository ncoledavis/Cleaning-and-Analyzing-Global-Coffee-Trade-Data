# Cleaning and Analyzing Global Coffee Trade Data

AD450 Data Science Development — a `uv`-managed project that cleans and analyzes
three global coffee datasets (exports, imports, production).

## Setup

Dependencies are declared in `pyproject.toml` and locked in `uv.lock`.

```bash
uv sync          # create the environment and install pandas, matplotlib, notebook
```

In VS Code, open `coffee_cleaning_analysis.ipynb`, click **Select Kernel →
Python Environments…**, and choose the `.venv` environment created by uv.

## Contents

- `coffee_cleaning_analysis.ipynb` — the full analysis notebook (Parts 1–5).
- `Coffee_export.csv`, `Coffee_import.csv`, `Coffee_production.csv` — source data.

## Notebook outline

1. **Load & inspect** — shapes, dtypes, and country lists.
2. **Assess data quality** — nulls, mis-typed numerics, the `-2147483648`
   integer-overflow sentinel in Brazil's exports, and country-name issues
   (leading whitespace in the import file).
3. **Clean** — strip/standardize country names, coerce numerics, replace the
   overflow sentinel with `NaN`, fill gaps with each country's median year
   value, and recompute the `Total_*` columns.
4. **Trade questions** — largest production change, net trade balance
   (top exporters vs. importers), production ratio by coffee type, and the
   export-without-production anomaly.
5. **Visualizations** — stacked bar (exporters vs. importers), line chart
   (global exports over time), and a donut chart (production share by type).
