# 🛡 ESG Fraud Signal — End-to-End Analytics & ML Pipeline

## 📌 Project Overview
**ESG Fraud Signal** is a **full-stack data analytics & machine learning pipeline** designed to detect potential Environmental, Social, and Governance (ESG) fraud signals.  
It uses **synthetic data**, **NLP**, **graph analytics**, **anomaly detection**, and **supervised ML models** to simulate real-world fraud risk detection workflows.  
The project concludes with an **interactive dashboard in Power BI** for actionable business insights.

![Dashboard Preview](https://github.com/Vivekcoder07/-ESG-Fraud-Signal-Dashboard-Early-Warning-for-Greenwashing-ESG-Risk.-/blob/main/ESG%20Fraud%20Signal%20Dashboard%20%E2%80%94%20Early%20Warning%20for%20Greenwashing%20%26%20ESG%20Risk..png)

---

## 🎯 Business Problem
ESG fraud — such as falsified sustainability reports, concealed supply chain violations, or unethical governance practices — is **difficult to detect** due to its multi-layered and hidden nature.  
Regulatory bodies, investors, and compliance teams need **early warning systems** to identify companies showing **red flags** in reports, news, or business networks.

This pipeline simulates a **risk scoring system** to:
- Extract **risk signals** from text data
- Detect **network-related risks** using graph analysis
- Flag **anomalous company behavior**
- Provide **decision-ready insights** via Power BI

---

## 🌍 Industry Relevance
- **Finance & ESG Investing** – Identify greenwashing and fraud risks in ESG portfolios.
- **Regulatory Compliance** – Support audits and monitoring for governance breaches.
- **Corporate Risk Management** – Strengthen ESG due diligence in mergers and acquisitions.

---

## 🛠 Technologies & Tools
- **Programming Language:** Python 3.10+
- **Libraries:** `pandas`, `numpy`, `scikit-learn`, `lightgbm`, `networkx`, `nltk`
- **BI Tool:** Power BI
- **ML Models:** Logistic Regression, LightGBM, Isolation Forest, Local Outlier Factor
- **Data Format:** CSV, Parquet (synthetic datasets)
- **Environment:** VS Code / Jupyter Notebook

---

## 📂 Dataset Details
- **Source:** Generated synthetic dataset for safe, reproducible experimentation.
- **Files Produced:**
  - `pb_company_monthly.csv` – All company-month records with features & scores.
  - `pb_company_latest.csv` – Latest month snapshot for dashboarding.

> ⚠️ Data is synthetic — no sensitive information is used.

---

## 🔄 Project Workflow

### 1️⃣ Generate Synthetic Data  
`01_generate_synthetic_data.py`  
- Creates realistic fake company data: ESG scores, news, filings, board links.

### 2️⃣ Data Cleaning & Aggregation  
`02_clean_and_aggregate.py`  
- Cleans text, normalizes dates, stores in Parquet for efficiency.

### 3️⃣ NLP Risk Scoring  
`03_nlp_train_and_score.py`  
- Keyword scoring + TF-IDF Logistic Regression to detect risk in text.

### 4️⃣ Graph Feature Engineering  
`04_graph_features.py`  
- Creates network graph & calculates centrality + neighbor risk.

### 5️⃣ Anomaly Detection & ML Model  
`05_anomalies_and_model.py`  
- Isolation Forest + LOF + LightGBM for fraud_risk_score (0–100).

### 6️⃣ Export for Power BI  
`06_export_for_powerbi.py`  
- Generates CSV files ready for dashboard import.

---

## 📊 Dashboard Overview (Power BI)
- **Fraud Risk Heatmap** – High-risk companies per month.
- **ESG Component Breakdown** – Environmental, Social, Governance scores.
- **Network Risk Map** – Visualizes inter-company connections.
- **Top Risk Alerts** – List of companies with sudden score spikes.

---

## 🚀 Installation & Setup

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/esg-fraud-signal.git
cd esg-fraud-signal

# 2. Create virtual environment
python -m venv .venv
# Activate
# Windows:
.\.venv\Scripts\activate
# Mac/Linux:
source .venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt
▶ How to Run
bash
Copy code
# Run all steps sequentially
python scripts/01_generate_synthetic_data.py
python scripts/02_clean_and_aggregate.py
python scripts/03_nlp_train_and_score.py
python scripts/04_graph_features.py
python scripts/05_anomalies_and_model.py
python scripts/06_export_for_powerbi.py
Open pb_company_latest.csv in Power BI to load visuals.

Connect visuals to company-month dataset for trend analysis.

📈 Results & Insights
Detected high-risk companies based on anomalies + NLP risk scores.

Identified network clusters where fraud likelihood is higher.

Enabled interactive filtering for month, sector, and ESG dimension.

💡 Why This Project is Valuable
ESG: Detect greenwashing early.

Fintech: Integrate fraud scoring into investment analytics.

Regulatory Compliance: Strengthen audit readiness.

🔮 Future Improvements
Integrate real ESG datasets (e.g., Refinitiv, Sustainalytics).

Deploy as an API for real-time scoring.

Add sentiment analysis from social media feeds.

📁 Repository Structure
graphql
Copy code
esg-fraud-signal/
│
├── data/
│   ├── raw/          # Initial synthetic CSV files
│   ├── interim/      # Cleaned & aggregated Parquet
│   └── processed/    # Final outputs for BI tools
│
├── scripts/          # Python scripts (01 to 06)
├── models/           # Saved ML models
├── outputs/          # Optional reports, plots
├── images/           # Dashboard screenshots
├── requirements.txt
└── README.md
🤝 Contributing
Contributions are welcome!
Please fork the repo and submit a pull request.

📜 License
This project is licensed under the MIT License – see the LICENSE file for details.

🔖 Keywords
#ESG Fraud Detection #Power BI #Machine Learning #NLP #Graph Analytics #Risk Scoring #LightGBM #Anomaly Detection #Synthetic Data

Contact me
💼 www.linkedin.com/in/vivekpatel07
📧 Vivekpatel07904@gmail.com
ESG Fraud Detection Power BI Machine Learning NLP Graph Analytics Risk Scoring LightGBM Anomaly Detection Synthetic Data

📬 Connect with Me
