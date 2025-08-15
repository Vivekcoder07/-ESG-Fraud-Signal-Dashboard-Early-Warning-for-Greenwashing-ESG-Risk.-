
# ESG Fraud Signal — End-to-End Pipeline

This project demonstrates a full workflow for detecting potential ESG (Environmental, Social, Governance) fraud signals using synthetic data, NLP, graph analytics, anomaly detection, and supervised machine learning. The final outputs are ready for analysis in Power BI or similar BI tools.

## Why This Pipeline?
ESG fraud is a complex, multi-faceted problem. This pipeline simulates a real-world workflow:
- **Synthetic data** lets you experiment and prototype without sensitive data.
- **Text cleaning and NLP** extract risk signals from unstructured filings/news.
- **Graph features** capture relationships between companies (e.g., board interlocks, supply chains).
- **Anomaly detection** highlights unusual patterns that may indicate fraud.
- **Supervised learning** combines all features to score companies/months for fraud risk.
- **Power BI export** enables easy dashboarding and further business analysis.

## Folder Structure
- `data/raw/` — Raw synthetic data (CSV)
- `data/interim/` — Cleaned and processed data (Parquet)
- `data/processed/` — Final features and model outputs (CSV/Parquet)
- `scripts/` — All processing/modeling scripts (run in order)
- `models/` — Saved ML models and scalers
- `outputs/` — (Optional) Plots, reports, or exports

## Quickstart: How to Run Everything
1. **Set up your environment**
   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   pip install -r requirements.txt
   ```
2. **Run each script in order:**
   ```powershell
   python scripts/01_generate_synthetic_data.py
   python scripts/02_clean_and_aggregate.py
   python scripts/03_nlp_train_and_score.py
   python scripts/04_graph_features.py
   python scripts/05_anomalies_and_model.py
   python scripts/06_export_for_powerbi.py
   ```
3. **Open `data/processed/pb_company_monthly.csv` and `pb_company_latest.csv` in Power BI or Excel.**

## Step-by-Step Pipeline Overview

### 1. Generate Synthetic Data (`01_generate_synthetic_data.py`)
Creates realistic fake data for companies, ESG ratings, filings, news, and inter-company relationships. This allows you to test the pipeline end-to-end without real data.

### 2. Clean & Aggregate (`02_clean_and_aggregate.py`)
Cleans text, standardizes dates, and saves efficient Parquet files. This step ensures all downstream analysis is fast and reliable.

### 3. NLP Risk Scoring (`03_nlp_train_and_score.py`)
Extracts risk signals from text using:
- Keyword-based scoring (e.g., "whistleblower", "falsify")
- Trains a TF-IDF + Logistic Regression model to predict risk from text
- Aggregates scores to the company-month level for both news and filings

### 4. Graph Features (`04_graph_features.py`)
Builds a company relationship graph (e.g., board interlocks, supply chain links). Computes centrality and neighbor risk features, which help spot companies at the center of risky networks.

### 5. Anomaly Detection & Supervised Model (`05_anomalies_and_model.py`)
Detects outliers using Isolation Forest and Local Outlier Factor. Then, creates a synthetic "fraud-like" label and trains a LightGBM model to score all company-months for fraud risk. Outputs a normalized `fraud_risk_score` (0-100).

### 6. Export for Power BI (`06_export_for_powerbi.py`)
Prepares two files for BI tools:
- `pb_company_monthly.csv`: All company-months with features and risk scores
- `pb_company_latest.csv`: Only the latest month per company
These are ready for dashboarding, filtering, and further analysis in Power BI.

## Why Each Step Matters
- **Synthetic data**: Safe, reproducible, and lets you test the full stack.
- **Cleaning**: Ensures data quality and performance.
- **NLP**: Finds hidden risk in unstructured text.
- **Graph**: Captures network effects and indirect risk.
- **Anomaly/model**: Flags both rare events and systematic risk.
- **Export**: Makes results accessible for business users.

---
This pipeline is modular—adapt any step for your own ESG, fraud, or risk analytics projects!
