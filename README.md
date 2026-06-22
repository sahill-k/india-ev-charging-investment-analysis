# India EV Charging Investment Opportunity Analysis

## Project Overview

This project identifies high-potential Indian states/UTs for EV charging infrastructure expansion using EV adoption, public charging infrastructure, economic indicators, and investment opportunity scoring.

The analysis focuses on 14 major EV-relevant Indian states/UTs selected for a focused Version 1 study. The objective is not to create a complete national ranking, but to build a clean and explainable data-driven framework for identifying where EV charging infrastructure expansion may be most attractive.

## Business Problem

India's EV adoption is growing quickly, but charging infrastructure is not expanding evenly across regions. A state with high EV registrations may not always be the strongest investment opportunity if charging infrastructure is already well developed. Similarly, a state with fewer chargers may not be attractive unless EV demand and market size are also meaningful.

This project answers the question:

> Which selected Indian states/UTs show the strongest opportunity for EV charging infrastructure expansion based on EV demand, charging gaps, economic strength, and growth momentum?

## Data Sources

| Dataset | Source | Purpose |
|---|---|---|
| EV Public Charging Stations | [Bureau of Energy Efficiency - E Mobility](https://beeindia.gov.in/WriteReadData/RTF1984/EV_PCS_Data_29277.pdf) | Charging station count, connector availability, charger type, and fast charger share |
| EV Registration Data | [India Climate and Energy Dashboard](https://iced.niti.gov.in/analytics/ice-and-ev-vehicle-registered/) | Annual EV registrations, cumulative EV registrations, EV share, and EV growth |
| State-wise GSDP and Per-Capita NSDP | [MoSPI State-wise SDP](https://www.mospi.gov.in/sites/default/files/press_releases_statements/Statewise_SDP.xls) | Economic strength indicators |
| Power Supply Position | [Central Electricity Authority - Power Supply](https://cea.nic.in/dashboard/?lang=en) | Explored as a power readiness indicator |

All datasets were cleaned, standardized at the state/UT level, and merged into a final master dataset for EDA, scoring, PCA, and exploratory regression.

## Selected Regions

This Version 1 analysis focuses on the following 14 major EV-relevant states/UTs:

- Maharashtra
- Karnataka
- Uttar Pradesh
- Delhi
- Tamil Nadu
- Gujarat
- Rajasthan
- Kerala
- Telangana
- Madhya Pradesh
- Haryana
- West Bengal
- Andhra Pradesh
- Punjab

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Scikit-learn
- Statsmodels
- Jupyter Notebook

## Methodology

The project follows a complete data analysis workflow:

1. Loaded and cleaned EV registration, charging station, economy, and power readiness datasets.
2. Standardized state/UT names across all datasets.
3. Aggregated public charging infrastructure at the state/UT level.
4. Created EV demand and growth metrics using annual and cumulative EV registrations.
5. Built charging pressure indicators such as EVs per connector and EVs per charging station.
6. Added economic indicators such as GSDP and per-capita NSDP.
7. Performed exploratory data analysis to compare EV demand, charging supply, and infrastructure gaps.
8. Created an investment opportunity score using weighted demand, growth, infrastructure gap, charger quality, and economic indicators.
9. Used PCA to understand state-level investment profiles.
10. Used exploratory regression to study directional relationships between EV registrations and selected explanatory variables.

## Key Metrics Created

| Metric | Purpose |
|---|---|
| Annual EV Registrations | Measures latest EV demand momentum |
| Cumulative EV Registrations | Measures existing EV market size |
| EV CAGR | Measures long-term EV growth momentum |
| EV Share | Measures EV adoption intensity |
| Charging Station Count | Measures public charging supply |
| Total Connectors | Measures charging connector availability |
| Fast Charger Share | Measures charging infrastructure quality |
| EVs per Connector | Measures charging pressure |
| EVs per Charging Station | Measures infrastructure gap |
| GSDP | Measures economic scale |
| Per-Capita NSDP | Measures income and market strength |

## Exploratory Data Analysis

The EDA compares EV adoption and charging infrastructure availability across selected states/UTs.

Key questions explored:

- Which regions have the largest annual EV registrations?
- Which regions have the largest cumulative EV base?
- Which regions have stronger public charging infrastructure?
- Where is charging infrastructure relatively under-supplied?
- How does economic strength relate to EV market size?
- Which states show stronger charging pressure based on EVs per connector and EVs per station?

## Investment Opportunity Scoring

A composite investment opportunity score was created to rank states/UTs using multiple indicators instead of relying on a single metric.

The score considers:

- EV demand
- Cumulative EV market size
- EV growth momentum
- EV adoption intensity
- Charging infrastructure gap
- Charging station availability
- Fast charger quality
- Economic strength

This helps identify regions where EV adoption is strong but public charging infrastructure may still be underdeveloped.

## PCA and Regression

PCA was used to understand whether states/UTs form different investment profiles based on demand, infrastructure, growth, and economy-related variables.

Exploratory regression was used to study directional relationships between EV registrations and selected indicators. The regression results are treated as exploratory because the analysis uses a small state-level sample.

## Key Findings

- Uttar Pradesh emerged as one of the strongest EV charging expansion opportunities due to its large EV market and high charging pressure.
- Maharashtra showed strong investment potential due to its large EV market, high annual EV demand, and strong economic base.
- Madhya Pradesh and Gujarat appeared as attractive expansion opportunities due to a combination of growth momentum, economic relevance, and charging gap indicators.
- Karnataka and Delhi are important EV markets, but they ranked lower in the opportunity score because the scoring model prioritizes underserved charging gaps rather than market size alone.
- Charging opportunity is not determined only by the number of EVs. A stronger opportunity appears when EV demand, charging gap, growth, and economic strength are considered together.

## Final Conclusion

The analysis found that Uttar Pradesh is the strongest EV charging infrastructure expansion opportunity among the selected states/UTs because it combines a large EV market with high charging pressure. Maharashtra, Madhya Pradesh, and Gujarat also show strong investment potential.

The project shows that mature EV markets are not always the highest expansion opportunities. States with high EV adoption but limited public charging supply may offer stronger infrastructure investment potential than states that are already better supplied.

## Limitations

- This version focuses on 14 selected major EV-relevant states/UTs and is not intended to represent a complete national ranking.
- The charging station dataset is a current infrastructure snapshot and does not provide historical charging station growth.
- Cumulative EV registrations were created using available year-wise EV registration data and may not perfectly represent the exact active EV stock on road.
- The scoring model uses manually assigned weights. Different weighting choices may produce different rankings.
- Regression analysis is exploratory because the dataset contains a small number of state-level observations.
- Some useful factors such as land cost, city-level EV demand, charger utilization, electricity tariffs, road density, highway traffic, and policy incentives were not included in this version.

## Future Scope

- Expand the analysis to all Indian states and Union Territories.
- Add city-level EV registration and charging station data.
- Include charger utilization, electricity tariffs, land cost, and state EV policy incentives.
- Test multiple scoring weight scenarios.
- Build an interactive Streamlit or Power BI dashboard.
- Add an India map visualization for state-level opportunity categories.

## Repository Structure

```text
notebooks/
  01_data_loading_and_cleaning.ipynb
  02_eda_scoring_pca_regression.ipynb

data/
  cleaned/
    master_ev_investment_dataset_updated.csv

reports/
  charts/

README.md
requirements.txt
```

## Author

Sahil Kochhar
