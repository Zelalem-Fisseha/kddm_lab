# kddm_lab: SWEN466 Knowledge Discovery and Data Mining

## Assignment 1: Data Quality Analysis and ERD Design

| Deliverable | File |
|---|---|
| Notebook with the SQL checks (Exercises 1–5 + key/cardinality checks) | [notebooks/01_explore_source_data.ipynb](notebooks/01_explore_source_data.ipynb) |
| ERD (crow's foot) | [docs/erd.png](docs/erd.png), [docs/erd.pdf](docs/erd.pdf) (source: [docs/erd.mmd](docs/erd.mmd)) |
| Short note | [docs/note.md](docs/note.md) |

### How to run

1. Put the five Olist CSV files in `data/raw/` (they are not committed; see `.gitignore`).
2. Install the libraries and open the notebook:

```bash
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/jupyter lab notebooks/01_explore_source_data.ipynb
```

The notebook creates `data/warehouse/ecommerce.duckdb` and loads the CSVs into the `raw` schema.
