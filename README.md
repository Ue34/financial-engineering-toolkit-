# Quantitative Risk & Financial Engineering Toolkit

This repository contains a production-ready framework for banking Asset-Liability Management (ALM) analytics, statistical risk modeling, and business intelligence pipelines. It bridges quantitative financial engineering with enterprise-grade data automation.

## Core Features

- **ALM Liquidity Stress Testing:** A dynamic simulation engine modeling maturity gap distributions (`O/N` to `5Y+`) and deposit run-off shocks (e.g., 15% overnight withdrawal).
- **Advanced Quantitative Risk:** Analytic computation of option Greeks (Delta, Gamma, Vega) and Historical Value-at-Risk (VaR) estimation with robust error logging.
- **Production-Grade Analytics:** Refactored financial operations utilizing industry-standard libraries (`SciPy`, `Statsmodels` for ADF stationarity, and `PyPortfolioOpt` for Markowitz optimization).
- **Power BI ETL Pipeline:** A script designed for direct embedding into Power BI Desktop to handle automated balance sheet data cleaning and Z-score outlier isolation.

## Technical Architecture & Best Practices

- **Security Isolation:** Fully decoupled environment using `python-dotenv` for database access and secure vault variables.
- **Clean Code & DevOps:** Implements PEP 8 standards, modular object-oriented structures, structured business logging, and strict Git version filtering via explicit `.gitignore` matrices.
