# ECB-Monetary-Policy-Transmission-Analysis


## Quantifying Policy Rate Pass-Through to Euro Money Markets (2019-2025)

This project analyzes the transmission mechanism of European Central Bank (ECB) monetary policy by examining how changes in policy rates (particularly the Deposit Facility rate) pass through to the Euro Short-Term Rate (€STR), the benchmark overnight lending rate for the eurozone.

## 📊 Project Overview

The analysis reveals a **near-perfect transmission** with a beta coefficient of **0.996**, demonstrating that ECB policy rate changes are almost fully reflected in overnight market rates. This validates the effectiveness of the ECB's interest rate corridor system in controlling short-term money market rates.

## 📁 Repository Contents

- **`ECB_DF_vs_€STR_(2019–2025).ipynb`** - Complete Jupyter notebook with data pipeline, analysis, and visualizations
- **`ECB_DF_vs_€STR_(2019–2025).pdf`** - PDF export of analysis results and findings

## 🔧 Technical Implementation

### Data Pipeline
- Automated ingestion of ECB statistical data warehouse exports
- Robust data cleaning handling multiple date formats and column naming conventions
- Time series alignment using `pandas.merge_asof` for business-day frequency data
- Forward-fill methodology for policy rate series (capturing "date of changes" format)

### Feature Engineering
- **Transmission Spread**: €STR minus Deposit Facility rate
- **Daily Changes**: First differences for all rate series
- **Event Windows**: ±5 business days around policy announcements

### Analytical Methods
1. **Time Series Visualization**: Multi-rate comparison of ECB policy corridor and €STR
2. **Event Study Analysis**: Average market response to policy rate changes
3. **Regression Analysis**: OLS estimation of pass-through coefficient
4. **Correlation Analysis**: Statistical relationship between policy and market rates

## 📈 Key Findings

- **Pass-Through Coefficient**: 0.996 (Δ€STR on ΔDeposit Facility)
- **Correlation**: 0.996 between policy rate changes and €STR changes
- **Interpretation**: Nearly 1:1 transmission indicates effective monetary policy implementation
- **Spread Dynamics**: €STR typically trades slightly below the Deposit Facility rate

## 🛠️ Technologies Used

**Core Libraries:**
- `pandas` - Time series data manipulation and alignment
- `numpy` - Numerical computations
- `matplotlib` - Publication-quality visualizations

**Statistical Techniques:**
- Event study methodology
- Ordinary Least Squares (OLS) regression
- Time series interpolation and forward-filling
- Business-day frequency alignment

## 📊 Data Sources

The analysis uses official ECB statistical data:
- ECB Policy Rates (Deposit Facility, MRO, Marginal Lending Facility)
- €STR (Euro Short-Term Rate) - Volume-weighted trimmed mean rate
- Optional: €STR liquidity metrics

**Data Period**: October 2019 - October 2025

## 🚀 Running the Analysis

### Requirements
```bash
pip install pandas numpy matplotlib
```

### Execution
1. Open `ECB_DF_vs_€STR_(2019–2025).ipynb` in Jupyter Notebook or Google Colab
2. Upload required CSV files:
   - `ecb_policy_rates.csv`
   - `estr.csv`
   - `estr_liquidity.csv` (optional)
3. Run all cells to generate analysis and visualizations

### Output
The notebook generates:
- **Charts**: Policy vs €STR comparison, transmission spread, daily changes, event study
- **Statistics**: Regression coefficients, correlations
- **Data**: Merged dataset with engineered features

## 💡 Skills Demonstrated

- **Quantitative Finance**: Central bank policy transmission, money market dynamics
- **Econometric Analysis**: Event studies, regression analysis, time series methods
- **Data Engineering**: ETL pipeline, data cleaning, temporal alignment
- **Python Programming**: Pandas proficiency, modular code design, automation
- **Financial Domain Knowledge**: ECB operational framework, interest rate corridor systems

## 📚 Context & Interpretation

The Deposit Facility rate serves as the **floor** of the ECB's interest rate corridor. Banks can deposit excess reserves overnight at this rate, making it the minimum rate at which they're willing to lend to other banks. The €STR, as the benchmark overnight rate, should track closely with this floor—and our analysis confirms this relationship holds strongly across various monetary policy regimes (including the transition from negative to positive rates during 2022-2023).

For detailed interpretation of results and policy implications, refer to the accompanying presentation.

## 📝 Use Cases

This analysis is relevant for:
- **Central Banking**: Assessing policy implementation effectiveness
- **Financial Markets**: Understanding money market dynamics
- **Economic Research**: Studying monetary transmission mechanisms
- **Risk Management**: Modeling overnight rate behavior

## 👤 Author

Ayush Singh

## 📄 License

This project is available for educational and research purposes.

---

*Last Updated: November 2025*
