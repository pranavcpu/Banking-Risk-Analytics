Banking Risk & Export Financing Analytics

Analysis and interactive Power BI dashboard exploring U.S. export financing/authorization data (2007–2017) — covering total financing volumes, country and industry exposure, small-business/woman-owned/minority-owned participation, and portfolio risk indicators

Overview

This project analyzes trade-finance authorization records to answer questions relevant to bank/export-credit risk teams:

How much financing has been authorized globally, and how has it trended over time?
Which countries and industries carry the largest share of financing and exposure?
What is the Exposure Ratio (Outstanding Exposure ÷ Approved Amount) per deal, and which authorizations carry the highest risk?
How much of total financing supports small businesses, woman-owned businesses, and minority-owned businesses?
How is financing distributed across program/policy types (e.g. Guarantee, MTS, MSM, MTR, GCE, ESS)?

Headline numbers from the dataset (2007–2017):

Metric	Value
Total Authorized Financing	$160.88bn
Countries Covered	142
Total Deals	~13,000
Small Business Share	14.9%
Woman Owned Share	10.3%
Minority Owned Share	1.6%
Avg. Exposure Ratio	28


Project Structure
banking-risk-analytics/
├── README.md                          # this file
├── requirements.txt                   # Python dependencies
├── .gitignore
├── LICENSE
│
├── data/
│   ├── README.md                      # data source & schema notes
│   ├── raw/                            # original authorizations CSV (not committed)
│   └── processed/                      # cleaned_bank_data.csv output
│
├── notebooks/
│   └── Banking_Risk_Analytics_Project.py   # original exploratory Colab script
│
│
├── dashboard/
│   ├── pbix/                          # Power BI (.pbix) source file
│   └── screenshots/
│       └── executive_overview.png     # dashboard preview image
│
└── docs/                              # additional documentation / write-ups
Tech Stack
Python — pandas, NumPy, Matplotlib, Seaborn, Plotly (data cleaning, EDA, static visualizations)
Power BI — interactive dashboard (Executive Overview, Country Detail, Program Tooltip pages)
Jupyter / Google Colab — original exploratory analysis
Data Pipeline
Load raw authorization records (data/raw/authorizations.csv)
Clean
Strip currency symbols/commas and cast Approved/Declined Amount to numeric
Parse Decision Date and derive Year
Drop duplicate records
Engineer features
Exposure Ratio = Outstanding Exposure Amount / Approved/Declined Amount
Aggregate & analyze
Total financing, top 10 countries, top 10 industries (NAICS/SIC)
Small business / woman-owned / minority-owned financing breakdowns
Correlation heatmap across numeric fields
Export cleaned dataset to data/processed/cleaned_bank_data.csv for use in Power BI
Dashboard

The Power BI dashboard (dashboard/pbix/) has three pages:

Executive Overview — KPI cards (financing share by ownership type, total deals, exposure ratio), financing trend over time, authorization vs. exposure risk scatter, minority-owned share by policy type, top financing countries, geo map, and policy-type distribution
Country Detail — drill-down view by country
Program Tooltip — drill-down view by financing program/policy type

Filters available: Fiscal Year, Country, Program.

Getting Started
Prerequisites
Python 3.9+
Power BI Desktop (to open/edit dashboard/pbix/*.pbix)
Setup
bash
git clone https://github.com/<your-username>/banking-risk-analytics.git
cd banking-risk-analytics
pip install -r requirements.txt
Run the analysis
bash
python src/data_processing.py \
    --input data/raw/authorizations.csv \
    --output data/processed/cleaned_bank_data.csv

This will print summary statistics to the console and save chart images to outputs/figures/.

View the dashboard

Open dashboard/pbix/Banking_Risk_Analytics.pbix in Power BI Desktop, or view the static preview in dashboard/screenshots/.

Key Insights
Financing volume peaked around 2011 (~$31bn) before declining sharply through 2015–2017.
The United States, Mexico, India, China, Turkey, and Brazil are the top financing destinations by authorized amount.
Minority-owned business participation (1.6%) lags significantly behind small-business (14.9%) and woman-owned (10.3%) shares, highlighting a potential focus area for inclusive lending initiatives.
Exposure Ratio varies widely across deals, useful for flagging higher-risk authorizations relative to approved amount.
License

This project is licensed under the MIT License — see LICENSE for details.

Acknowledgments

Original exploratory analysis developed in Google Colab; refactored and documented for public portfolio use.
