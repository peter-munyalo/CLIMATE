# The Environmental and Health Impacts of Agriculture Expansion in Kenya

This repository contains a complete time‑series analysis of how agricultural expansion in Kenya has affected forest cover, freshwater withdrawals, child mortality, and malnutrition over the period 1960–2023. The project combines two World Bank datasets and applies rigorous econometric methods to uncover both short‑term and lagged relationships.

## 📌 Overview

Agriculture is the backbone of Kenya’s economy, but its expansion often comes at a cost to the environment and may influence population health. This study investigates:

- **Environmental impacts**: Does agricultural land expansion reduce forest cover and increase freshwater withdrawals?
- **Health impacts**: Is agricultural expansion associated with changes in under‑5 mortality and child malnutrition?
- **Dynamic effects**: Do changes in agricultural land have immediate or delayed effects?

The analysis uses time‑series regression, Granger causality tests, and extensive robustness checks to provide credible evidence for policymakers and researchers.

## 📊 Data Sources

Two datasets from the World Bank (downloaded as CSV files) are used:

- `climate-change_ken.csv` – Contains climate‑related and agricultural indicators (e.g., agricultural land, forest area, cereal yield, freshwater withdrawals, electricity access).
- `qc_climate-change_ken.csv` – Contains socio‑economic indicators (under‑5 mortality, poverty headcount, population growth).

Both datasets cover Kenya for 1960–2024 (with varying completeness). After cleaning and merging, a final analysis file `kenya_analysis_ready.csv` is created.

## 🔬 Methodology

The project follows a structured workflow:

1. **Data cleaning & merging** – Handling metadata rows, standardising column names, merging on year, and reshaping to wide format.
2. **Exploratory data analysis** – Time‑series plots, correlation matrices, and stationarity tests (Augmented Dickey‑Fuller).
3. **Statistical modelling**  
   - **Environmental models**: OLS with Newey‑West standard errors on differenced variables to assess impacts on forest cover and water withdrawals.  
   - **Health models**: Similar approach for child mortality, plus descriptive analysis of sparse malnutrition data.
4. **Robustness checks** – Using absolute agricultural land, including lagged variables, subsample analysis (pre‑/post‑1990), and variance inflation factor (VIF) tests.
5. **Granger causality** – Testing whether agricultural land Granger‑causes environmental/health outcomes.

All analyses are implemented in a Jupyter Notebook with detailed comments and markdown explanations.

## 📈 Key Findings

- **Agricultural expansion drives deforestation, but with a lag** – A 1‑percentage‑point increase in agricultural land reduces forest cover by about **0.033 percentage points over two years** (significant in the lagged model).
- **No significant short‑term link to freshwater withdrawals** – Possibly because irrigation is not yet the dominant water use, or due to data limitations.
- **Child mortality is strongly linked to urbanisation and population growth**, not directly to agricultural land. However, malnutrition shows a strong negative correlation with agricultural land (Pearson r = –0.90, based on sparse data), suggesting potential food security benefits.
- **Urbanisation emerges as the most consistent predictor** of both environmental degradation and health improvement, highlighting the need for integrated urban‑environmental planning.
- **Granger causality tests are non‑significant**, indicating that the observed relationships are contemporaneous rather than predictive.

## 📁 Repository Structure
