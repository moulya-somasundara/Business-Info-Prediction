```markdown
# Yelp Restaurant Business Info Prediction  
**A lightweight pipeline for scraping, cleaning, and modelling Yelp restaurant data**

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## ✨  Why this project?

Restaurant discovery platforms such as **Yelp** are gold-mines of operational and customer sentiment data.  
This repository shows—end to end—how to

1. **Collect** basic business details (name, slug, URL, etc.) for any cuisine / location on Yelp  
2. **Clean & normalise** that raw HTML into a tidy dataset  
3. **Prototype prediction models** that relate those attributes to downstream outcomes (e.g. engagement, ratings, revenue proxies)

Use it as boiler-plate for research projects, data-science portfolio pieces, or internal competitive-intelligence dashboards.

---

## 📂  Repository layout

```

yelp-business-info-prediction/
├── src/
│   ├── scrape.py           ← Module 1:   HTML collection helpers
│   ├── clean.py            ← Module 2:   Data-cleaning / preprocessing
│   └── model.py            ← Module 3:   Quick-start ML workflows
├── notebooks/
│   └── exploratory.ipynb   ← Scratch pad & visualisations
├── data/
│   ├── raw/                ← ↳  \*.txt files straight from the scraper
│   └── processed/          ← ↳  Parquet / CSV after cleaning
├── requirements.txt
├── README.md
└── LICENSE

````

---

## 🚀  Quick start

> **Prerequisites:** Python ≥ 3.9

```bash
# 1. Clone & install dependencies
git clone https://github.com/<your-username>/yelp-business-info-prediction.git
cd yelp-business-info-prediction
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
````

```bash
# 2. Scrape 10 Korean restaurants in Manhattan
python -m src.scrape \
        --count 10 \
        --cuisine "Food+-+Korean" \
        --location "Manhattan%2C+NY"
# ↳ outputs data/raw/restaurantsList.txt
```

```bash
# 3. Clean the raw file
python -m src.clean data/raw/restaurantsList.txt
# ↳ outputs data/processed/restaurants.parquet
```

```bash
# 4. Train a baseline model
python -m src.model data/processed/restaurants.parquet --target engagement
```

Check `notebooks/exploratory.ipynb` for an interactive walk-through.

---

## 🧩  Module overview

| Module        | Purpose                                                                                             | Key functions / classes                                          |
| ------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **scrape.py** | Fetch restaurant “cards” from Yelp search results and write them to a plain-text file.              | `is_ad`, `get_name`, `get_href`, `get_username`, `scrape_list()` |
| **clean.py**  | Deduplicate, handle nulls, standardise names & URLs, and output a columnar dataset (CSV / Parquet). | `drop_dupes`, `normalise_strings`, `CleanPipeline`               |
| **model.py**  | Simple scikit-learn / XGBoost wrappers for regression & classification tasks.                       | `train_test_split_plus`, `BaselineRegressor`, `FeatureSelector`  |

Feel free to swap in Selenium, Playwright, or an async stack for heavier scraping workloads.

---

## 🛠️  Configuration

`scrape_list()` accepts the following arguments:

| Argument      | Example                        | Description                                                    |
| ------------- | ------------------------------ | -------------------------------------------------------------- |
| `count`       | `10`                           | Approximate number of restaurants to fetch                     |
| `cuisine`     | `"Food+-+Korean"`              | Any Yelp search facet (see the URL after filtering by cuisine) |
| `location`    | `"Manhattan%2C+NY"`            | URL-encoded location string                                    |
| `output_path` | `data/raw/restaurantsList.txt` | Where to save results                                          |

---

## 📈  Roadmap / future work

* [ ] Enrich with Yelp API data (ratings, review counts, price range)
* [ ] Geocode addresses for spatial analysis
* [ ] Deploy a **Streamlit** dashboard for live inference
* [ ] Containerise with **Docker** & add CI tests via **GitHub Actions**

Contributions are welcome—see below!

---

## ⚖️  Legal & ethical note

Web scraping may violate website **Terms of Service**.
**You are responsible** for ensuring that your usage complies with Yelp’s robots.txt, rate-limits, and local data-privacy laws.

---

## 🤝  Contributing

1. Fork the repo & create your feature branch (`git checkout -b feature/foo`)
2. Commit your changes (`git commit -m 'Add foo'`)
3. Push to the branch (`git push origin feature/foo`)
4. Open a Pull Request

All PRs must pass `ruff` (style) and `pytest` (unit tests).

---

## 📝  License

This project is distributed under the **MIT License**—see [`LICENSE`](LICENSE) for details.

```
```
