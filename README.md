# Analyzing Washington State EV Market Size

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
2.  **Analyze Distribution (Models, Makes, EV Types):**
    * **Finding:** Tesla maintains clear market dominance (~45% share), with Model Y and Model 3 as top sellers. Nissan and Chevrolet hold significant, though smaller, shares.
    * **Finding:** Battery Electric Vehicles (BEVs) overwhelmingly dominate the market (~78.1% share) and continue to increase their lead over Plug-in Hybrid Electric Vehicles (PHEVs).
3.  **Analyze Geographical Distribution:**
    * **Finding:** EV adoption is highly concentrated in urban hotbeds: King, Snohomish, and Pierce counties lead in registrations.
4.  **Identify Key Trends & Factors:**
    * **Finding:** BEV electric range has generally increased over time (except for a temporary dip around 2011, explained by mass-market entry). PHEV range remains stable.
    * **Finding:** CAFV Eligibility data shows significant "Eligibility unknown" entries for many BEVs, including a large portion of Teslas, highlighting data quality considerations for policy formulation.

## Key Deliverables

* **Interactive Market Size Dashboard:** A Power BI dashboard providing dynamic visualizations and key performance indicators of the WA EV market, including historical trends, forecasts, and interactive insights.
    * [Link to Power BI Published Report (if you publish it online - e.g., Power BI Service)]
    * (Alternatively: "Power BI Desktop file (.pbix) available upon request or in the `reports/` folder.")
* **Strategic Insights Report:** A comprehensive report (summarized above) detailing findings, methodology, and actionable recommendations for stakeholders.
    * [Link to Report PDF/Markdown file in `reports/` folder]
* **Jupyter Notebooks:** Documenting the end-to-end analytical workflow, from data cleaning to forecasting.
    * [`notebooks/01_explore_clean.ipynb`](notebooks/01_explore_clean.ipynb)
    * [`notebooks/02_eda_feature_engineering.ipynb`](notebooks/02_eda_feature_engineering.ipynb)
    * [`notebooks/03_forecasting.ipynb`](notebooks/03_forecasting.ipynb)

## Project Structure

* `data/`: Stores raw and processed datasets (`df_wa.csv`, `combined_ev_forecast_with_type.csv`).
* `notebooks/`: Contains Jupyter notebooks detailing the analytical workflow.
* `reports/`: Houses the Strategic Insights Report (e.g., PDF) and potentially the Power BI Desktop file (`.pbix`).
* `visualizations/`: Stores screenshots of dashboard pages and key charts.

## Tools & Technologies

* **Programming Language:** Python
* **Core Libraries:** Pandas (data manipulation), Matplotlib & Seaborn (visualization), SciPy (exponential curve fitting), Scikit-learn (basic regression concepts).
* **Dashboarding:** Power BI Desktop (for interactive dashboard creation).
* **Version Control:** Git & GitHub.
* **Environment:** Google Colab (to overcome local environment challenges).

## How to View This Project

1.  **Dashboard:** Access the interactive Power BI dashboard via the [link provided above](#key-deliverables) (if published online). Otherwise, download the Power BI Desktop file from the `reports/` folder and open it with Power BI Desktop.
2.  **Report:** View the full Strategic Insights Report [here](#key-deliverables).
3.  **Code:** Explore the detailed analytical steps by opening the Jupyter Notebooks in the `notebooks/` directory. These can be viewed directly on GitHub or opened in Jupyter/Google Colab.

## Challenges & Key Learnings

This project presented several real-world challenges that provided significant learning opportunities:
* **Data Quality:** Extensive cleaning was required for missing values, inconsistent '0's in `Base MSRP` (leading to its removal) and `Electric Range` (requiring imputation based on `Make` and `Model Year`).
* **Time Series Proxy:** Successfully defining "historical growth trend" using `Model Year` and `DOL Vehicle ID` as a proxy for cumulative active registrations in the absence of explicit registration dates.
* **Forecasting Model Selection:** Adapting the forecasting approach from complex ARIMA (due to environmental constraints) to a robust and intuitive exponential curve fitting (`scipy.optimize.curve_fit`), which proved highly effective for the observed growth pattern.
* **Power BI Data Modeling & DAX:** Overcoming challenges with Power BI's time intelligence functions (e.g., `PREVIOUSYEAR` requiring a continuous `Date Table`) and `Top N` filter limitations, demonstrating resilience in dashboard development.
* **Environment Management (Windows ARM):** Navigating persistent `numpy`/`pandas` installation issues on a Windows ARM architecture by strategically leveraging Google Colab, highlighting the importance of adaptable tool utilization.

## Future Work

* Integrate additional data sources such as charging infrastructure availability, local demographic data, and economic indicators for more granular insights and refined forecasts.
* Explore more advanced time series models (e.g., Prophet, SARIMAX) if future data patterns become more complex or seasonality emerges.
* Conduct a deeper analysis of EV adoption by vehicle segment (e.g., sedans vs. SUVs vs. trucks) as more models become available.
* Investigate the impact of specific policy changes or incentives on adoption rates.

---
**Contact:** [Your Name] | [Your LinkedIn Profile Link (Recommended)] | [Your Email Address (Optional)]
