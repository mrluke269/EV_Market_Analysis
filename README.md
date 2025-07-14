# Analyzing Washington State EV Market Size

## Table of Contents

* 1.   [Project Overview](#project-overview)
* 2.   [Business Context](#business-context)
* 3.   [Data Source](#data-source)
* 4.   [Key Analytical Objectives & Findings](#key-analytical-objectives--findings)
* 5.   [Key Deliverables](#key-deliverables)
* 6.   [Project Structure](#project-structure)
* 7.   [Tools & Technologies](#tools--technologies)
* 8.   [Challenges & Key Learnings](#challenges--key-learnings)
* 9.   [Contact](#contact)

## Project Overview

This project provides a comprehensive analysis and forecast of the Electric Vehicle (EV) market in Washington State, leveraging historical registration data. The primary objective was to understand current market penetration, predict future growth, and identify key trends and factors driving market expansion to support strategic decision-making for stakeholders in EV production, infrastructure development, and policy formulation.

**Key Outcome:** The analysis reveals an **accelerating exponential growth** in Washington's EV market, projected to reach over **6 million cumulative vehicles by 2035**, maintaining an estimated Compound Annual Growth Rate (CAGR) of **35.14%**. This growth is heavily driven by Battery Electric Vehicles (BEVs) and concentrated in urban centers.

## Business Context

The rapid global transition to Electric Vehicles necessitates data-driven insights for effective planning. This analysis directly addresses the needs of automotive manufacturers (identifying market leaders and emerging competition), infrastructure providers (pinpointing high-demand areas for charging stations), and policymakers (informing incentive programs and regulatory frameworks). Understanding the dynamics of EV adoption is crucial for a sustainable and efficient energy and transportation future.

## Data Source

The primary dataset used is the "[Electric Vehicle Population Size History By County](https://catalog.data.gov/dataset/electric-vehicle-population-size-history-by-county)" from Data.gov.
* **Note on Scope:** While the raw dataset contained some out-of-state registrations, the analysis was meticulously filtered and focused on Washington State, which comprises the overwhelming majority of the data, aligning with the project's core objective.

## Key Analytical Objectives & Findings

1.  **Assess Historical Growth Trend & Forecast Future Registrations:**
    * **Finding:** WA EV market exhibits strong, accelerating exponential growth, with a pivotal inflection point around 2011 (entry of mass-market EVs). 2023 was a breakout year for new registrations.
    * **Forecast:** Projected to reach **1.35 Million EVs by 2030** and over **6.10 Million EVs by 2035**, with an estimated **35.14% CAGR**.
    * ![Historical Growth Trend & Forecast Future Registrations](https://github.com/mrluke269/EV_Market_Analysis/blob/main/visualizations/2_EV_Adoption_Trends%26Forecast.png)
2.  **Analyze Distribution (Models, Makes, EV Types):**
    * **Finding:** Tesla maintains clear market dominance (~45% share), with Model Y and Model 3 as top sellers. Nissan and Chevrolet hold significant, though smaller, shares.
    * **Finding:** Battery Electric Vehicles (BEVs) overwhelmingly dominate the market (~78.1% share) and continue to increase their lead over Plug-in Hybrid Electric Vehicles (PHEVs).
    * ![](https://github.com/mrluke269/EV_Market_Analysis/blob/main/visualizations/3_Market_Segmentation.png)
    * ![](https://github.com/mrluke269/EV_Market_Analysis/blob/main/visualizations/4_Technology%26Type_Trends.png)
3.  **Analyze Geographical Distribution:**
    * **Finding:** EV adoption is highly concentrated in urban hotbeds: King, Snohomish, and Pierce counties lead in registrations.
    * ![](https://github.com/mrluke269/EV_Market_Analysis/blob/main/visualizations/5_Geographical_Distribution.png)
4.  **Identify Key Trends & Factors:**
    * **Finding:** BEV electric range has generally increased over time (except for a temporary dip around 2011, explained by mass-market entry). PHEV range remains stable.
    * **Finding:** CAFV Eligibility data shows significant "Eligibility unknown" entries for many BEVs, including a large portion of Teslas, highlighting data quality considerations for policy formulation.
    * ![](https://github.com/mrluke269/EV_Market_Analysis/blob/main/visualizations/6_CAFV_Eligibility%26Policy.png)

## Key Deliverables

* **Interactive Market Size Dashboard:** A Power BI dashboard providing dynamic visualizations and key performance indicators of the WA EV market, including historical trends, forecasts, and interactive insights.
    * [EV Market Power BI Dashboard](https://github.com/mrluke269/EV_Market_Analysis/tree/main/reports)

* **Strategic Insights Report:** A comprehensive report (summarized above) detailing findings, methodology, and actionable recommendations for stakeholders.
    * [Strategic Insights Report](https://github.com/mrluke269/EV_Market_Analysis/tree/main/reports)
* **Jupyter Notebooks:** Documenting the end-to-end analytical workflow, from data cleaning to forecasting.
    * [`notebooks/01_explore_clean.ipynb`](notebooks/01_explore_clean.ipynb)
    * [`notebooks/02_eda_feature_engineering.ipynb`](notebooks/02_eda_feature_engineering.ipynb)
    * [`notebooks/03_forecasting.ipynb`](notebooks/03_forecasting.ipynb)
  * **Actionable Recommendations:**:
  * ![](https://github.com/mrluke269/EV_Market_Analysis/blob/main/visualizations/7_Recommendations.png)

## Project Structure

* `data/`: Stores raw dataset (`df_wa.csv`).
* `notebooks/`: Contains Jupyter notebooks detailing the analytical workflow.
* `reports/`: Houses the Strategic Insights Report and the Power BI Desktop file (`.pbix`).
* `visualizations/`: Stores screenshots of dashboard pages and key charts.

## Tools & Technologies

* **Programming Language:** Python
* **Core Libraries:** Pandas (data manipulation), Matplotlib & Seaborn (visualization), SciPy (exponential curve fitting), Scikit-learn (basic regression concepts).
* **Dashboarding:** Power BI Desktop (for interactive dashboard creation).
* **Version Control:** Git & GitHub.
* **Environment:** Google Colab (to overcome local environment challenges).

## Challenges & Key Learnings

This project presented several real-world challenges that provided significant learning opportunities:
* **Data Quality:** Extensive cleaning was required for missing values, inconsistent '0's in `Base MSRP` (leading to its removal) and `Electric Range` (requiring imputation based on `Make` and `Model Year`).
* **Time Series Proxy:** Successfully defining "historical growth trend" using `Model Year` and `DOL Vehicle ID` as a proxy for cumulative active registrations in the absence of explicit registration dates.
* **Forecasting Model Selection:** Adapting the forecasting approach from complex ARIMA (due to environmental constraints) to a robust and intuitive exponential curve fitting (`scipy.optimize.curve_fit`), which proved highly effective for the observed growth pattern.
* **Power BI Data Modeling & DAX:** Overcoming challenges with Power BI's time intelligence functions (e.g., `PREVIOUSYEAR` requiring a continuous `Date Table`) and `Top N` filter limitations, demonstrating resilience in dashboard development.



---
**Contact:** Luke Mai | [[LinkedIn](https://www.linkedin.com/in/lukemai/)] | [luke.trmai@gmail.com]
