# Banking Risk Analytics — U.S. Export Financing (2007–2017)

A data analytics project examining U.S. export financing authorizations to identify portfolio risk, exposure concentration, and inclusion trends (small business, woman-owned, and minority-owned participation) across 142 countries and $160.88bn in authorized financing.



## 📊 Project Overview

This project analyzes historical U.S. export financing authorization data (2007–2017) to answer key risk and portfolio management questions:

- Which countries and industries carry the largest financing exposure?
- What is the relationship between authorized amounts and outstanding exposure risk?
- How has financing volume trended over the decade?
- What share of financing supports small business, woman-owned, and minority-owned enterprises?

The workflow combines **Python-based data cleaning and exploratory analysis** with an **interactive BI dashboard** (Power BI) for executive-level reporting.

## 🗂️ Repository Structure

   Banking-Risk-Analytics/
   │
   ├── README.md                          # Project documentation
   ├── Banking_Risk_Analytics_Project.ipynb   # Data cleaning & analysis notebook
   ├── banking dashboard.pbix             # Power BI dashboard file
   └── Screenshot 2026-07-21 204724.png   # Dashboard preview image

## 🔑 Key Metrics (from Dashboard)

| Metric | Value |
|---|---|
| Total Authorized Financing | $160.88bn |
| Countries Covered | 142 |
| Total Deals | 13,000 |
| Small Business Share | 14.9% |
| Woman-Owned Share | 10.3% |
| Minority-Owned Share | 1.6% |
| Average Exposure Ratio | 28 |

## 🛠️ Tech Stack

- **Python**: pandas, numpy, matplotlib, seaborn, plotly
- **Environment**: Google Colab / Jupyter
- **Visualization / Dashboard**: Power BI
- **Version Control**: Git & GitHub

## 📈 Analysis Highlights

1. **Data Cleaning** — Removed duplicate records, converted currency-formatted strings to numeric types, and parsed decision dates.
2. **Exposure Risk** — Calculated an `Exposure Ratio` (Outstanding Exposure ÷ Approved/Declined Amount) to flag deals with disproportionate risk relative to authorized size.
3. **Geographic Concentration** — Identified the top 10 countries and industries (by NAICS/SIC code) by total financing.
4. **Inclusion Metrics** — Aggregated financing by small business, woman-owned, and minority-owned authorization status.
5. **Correlation Analysis** — Built a correlation heatmap across numeric fields to explore relationships between exposure, deal size, and other variables.
6. **Executive Dashboard** — Built a multi-page Power BI dashboard (Executive Overview, Country Detail, Program Tooltip) with filters for fiscal year, country, and program type.

## 🚀 Getting Started

### Prerequisites
```bash
pip install -r requirements.txt
```

### Run the Analysis
```bash
python src/risk_analysis.py --input data/Authorizations_From_new.csv --output outputs/cleaned_bank_data.csv
```

This will:
- Clean and process the raw authorization data
- Print summary statistics (total financing, top countries, top industries)
- Save chart images to `outputs/figures/`
- Save the cleaned dataset to `outputs/cleaned_bank_data.csv`

### Explore in Notebook Form
The original exploratory version of this analysis is available in `notebooks/banking_risk_analytics_project.py` (exported from Google Colab).

## 📌 Data Source

The dataset used is U.S. export financing authorization data (not included in this repo due to size/licensing — see `data/README.md` for details on sourcing it, e.g. from EXIM Bank public disclosure data).

## 📄 License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

## 🙋 Author

Feel free to reach out or open an issue if you have questions or suggestions for improving this analysis.
