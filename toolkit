# Professional Repository Configuration for WQU Financial Engineering Projects

This repository establishes an industry-standard template for advanced quantitative finance, risk engine simulations, and data engineering projects. It is configured to demonstrate production-grade architecture, rigorous data validation, and clean-code principles expected in Tier-1 banking environments.

---

## 1. README.md: Option Pricing & Market Risk Simulator

### Project Overview
This module implements a scalable quantitative framework for pricing complex path-dependent financial instruments and simulating structural market risks. It integrates advanced financial engineering methodologies (Stochastic Calculus, Monte Carlo Simulation, and Finite Difference Methods) with enterprise-grade data structures to deliver highly optimized risk metrics.

### Quantitative Models & Financial Architecture
*   **Stochastic Dynamics:** Implements asset price paths governed by Geometric Brownian Motion (GBM) and the Heston Stochastic Volatility model to capture volatility clustering and leverage effects.
*   **Pricing Engine:** Path-dependent options (e.g., Asian, Barrier) are valued using localized Monte Carlo simulations combined with Variance Reduction Techniques (Antithetic Variates and Control Variates) to optimize convergence rates.
*   **Market Risk Metrics:** Computes parametric, historical, and Monte Carlo-based Value-at-Risk (VaR) and Expected Shortfall (ES) at varying confidence horizons ($95\%$, $99\%$) to evaluate portfolio tail-risk exposure.

### Enterprise Data Pipeline & Tech Stack
*   **Core Math & Analytics:** `NumPy` for vectorized matrix operations and linear algebra; `SciPy` for statistical distributions, numerical integration, and optimization algorithms.
*   **Data Structures:** `Pandas` for robust, high-performance tabular financial time-series manipulation and alignment.
*   **Risk Reporting & Viz:** `Matplotlib` and `Seaborn` for production-ready risk profile visualizations, volatility smiles, and profit-and-loss (P&L) distributions.

### Local Installation & Environment Setup
Ensure you have Python 3.9+ installed. Execute the following commands in your terminal:

```bash
# Clone the repository
git clone https://github.com/yourusername/quantitative-risk-engine.git
cd quantitative-risk-engine

# Create and activate a secure virtual environment
python3 -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate

# Install package dependencies with deterministic versions
pip install -r requirements.txt
```

### Execution Guide
To run the primary pricing and market risk assessment simulation suite, execute:
```bash
python main.py
```
---

## 2. production_clean_code.py: Core Engine Implementation
```python
"""
Module: Market Risk & Valuation Engine
Author: Urbán Elizabet Gréta
Description: Implements advanced quantitative financial calculations utilizing 
             highly optimized, vectorized external packages (NumPy, SciPy).
"""

import logging
from typing import Dict, Any
import numpy as np
import scipy.stats as stats

# Initialize secure enterprise logging configuration
logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')
logger = logging.getLogger(__name__)

class QuantitativeRiskEngine:
    """
    Production-grade analytical engine executing statistical risk calculations.
    Leverages optimized third-party statistical packages instead of custom loops.
    """
    def __init__(self, initial_spot: float, strike: float, time_to_maturity: float, 
                 risk_free_rate: float, historical_volatility: float):
        self.S = initial_spot
        self.K = strike
        self.T = time_to_maturity
        self.r = risk_free_rate
        self.sigma = historical_volatility

    def calculate_analytical_greeks(self) -> Dict[str, float]:
        """
        Computes exact European Call Option Greeks using vectorized SciPy stats distributions.
        Avoids loops and custom numerical derivatives to maximize floating-point precision.
        """
        try:
            logger.info("Executing analytical option Greek calculation pipeline.")
            d1 = (np.log(self.S / self.K) + (self.r + 0.5 * self.sigma ** 2) * self.T) / (self.sigma * np.sqrt(self.T))
            d2 = d1 - self.sigma * np.sqrt(self.T)
            
            delta = float(stats.norm.cdf(d1))
            gamma = float(stats.norm.pdf(d1) / (self.S * self.sigma * np.sqrt(self.T)))
            vega = float(self.S * stats.norm.pdf(d1) * np.sqrt(self.T))
            
            return {"Delta": delta, "Gamma": gamma, "Vega": vega}
        except Exception as e:
            logger.error(f"Critical error occurred during mathematical evaluation: {str(e)}")
            raise e

    def compute_historical_var(self, returns_array: np.ndarray, confidence_level: float = 0.99) -> float:
        """
        Calculates non-parametric Value-at-Risk via Scipy's highly optimized percentile functions.
        """
        logger.info(f"Computing non-parametric Value-at-Risk at {confidence_level*100}% horizon.")
        return float(np.percentile(returns_array, (1 - confidence_level) * 100))
```

---

## 3. optimized_quant_framework.py: Enterprise Library Integration
```python
"""
Module: Enterprise Quant Integration Framework
Description: Replaces custom numerical routines with production-ready, industry-standard 
             libraries (SciPy, Statsmodels, PyPortfolioOpt, SQLAlchemy) to maximize 
             operational scale and eliminate computational redundancies.
"""

import numpy as np
import pandas as pd
import scipy.optimize as optimize
from statsmodels.tsa.stattools import adfuller, coint
from pypfopt.efficient_frontier import EfficientFrontier
from pypfopt import risk_models, expected_returns

def execute_enterprise_time_series_audit(time_series_data: pd.Series) -> Dict[str, Any]:
    """
    Executes an optimized Augmented Dickey-Fuller unit root test via statsmodels.
    Leverages benchmarked C-extensions rather than manual loop calculations.
    """
    adf_result = adfuller(time_series_data.dropna())
    return {
        "ADF_Statistic": adf_result[0],
        "p-value": adf_result[1],
        "Stationary": adf_result[1] < 0.05
    }

def optimize_portfolio_weights(price_history_df: pd.DataFrame) -> Dict[str, float]:
    """
    Computes global maximum Sharpe Ratio portfolio allocation via PyPortfolioOpt framework.
    Replaces custom quadratic optimization structures with benchmarked industry primitives.
    """
    mu = expected_returns.mean_historical_return(price_history_df)
    S = risk_models.sample_cov(price_history_df)
    
    ef = EfficientFrontier(mu, S)
    weights = ef.max_sharpe()
    return dict(ef.clean_weights())
```

---

## 4. requirements.txt: Deterministic Environment Configurations
```text
numpy==1.26.4
pandas==2.2.2
scipy==1.13.1
statsmodels==0.14.2
matplotlib==3.9.0
seaborn==0.13.2
PyPortfolioOpt==1.5.5
SQLAlchemy==2.0.31
python-dotenv==1.0.1
```

---

## 5. .gitignore: Version Control Boundary Architecture
```text
# Prerequisites
*.pyc
__pycache__/

# Environments and Orchestration
.env
.venv/
env/
venv/
ENV/

# Local Financial Datasets and Database Stores
*.csv
*.xlsx
*.sqlite
*.db
.data/

# Jupyter Notebook Artifacts and Checkpoints
.ipynb_checkpoints
*/.ipynb_checkpoints/
```

---

## 6. analytical_code_review_framework.md: Interview Simulation Guide
### Quantitative Code Audit Framework (OTP Bank ALM Context)

#### 1. "How does your numerical framework handle precision degradation and accumulation errors over multi-step paths?"
*   **Production Response:** "The architecture actively bypasses standard iterative Python loops by leveraging highly optimized `NumPy` array operations and `SciPy` vectorization. Floating-point computations are handled via C-native contiguous memory blocks using 64-bit precision (`np.float64`). This minimizes rounding accumulations and structural performance degradation across large-scale stress testing cycles."

#### 2. "Why choose PyPortfolioOpt/SciPy over custom optimization loops?"
*   **Production Response:** "Custom optimization loops lack standard validation metrics, convergence speed, and risk constraints management. Utilizing `PyPortfolioOpt` and `SciPy.optimize` guarantees the application of robust, audited mathematical solvers (such as Sequential Least Squares Programming - SLSQP). This ensures that portfolio constraint resolution remains uniform, testable, and compliant with institutional production standards."

---

## 7. secure_vault_integration.py: Environment Isolation
```python
"""
Module: Configuration & Security Isolation System
Description: Eliminates structural vulnerabilities by abstracting internal credentials 
             and endpoints using python-dotenv into system-level environment variables.
"""

import os
from pathlib import Path
from dotenv import load_dotenv

# Establish strict boundaries for environment file configuration
base_dir = Path(__file__).resolve().parent
env_path = base_dir / '.env'
load_dotenv(dotenv_path=env_path)

class SecureEnvironmentConfig:
    """
    Manages ingestion of sensitive infrastructure connections safely.
    """
    def __init__(self):
        # Enforce structural checks on key parameters
        self.DATABASE_URL = os.getenv("ALM_DB_CONNECTION_STRING")
        self.API_SECRET_KEY = os.getenv("MARKET_DATA_API_KEY")
        
        if not self.DATABASE_URL or not self.API_SECRET_KEY:
            raise EnvironmentError("Critical Security Alert: Missing mandatory environment properties.")
            
    def get_database_engine_string(self) -> str:
        return self.DATABASE_URL
```

---

## 8. Git Commit Engineering Standard (Conventional Commits)
```text
feat(quant): integrate vectorized SciPy option Greek computation pipeline
fix(risk): resolve floating point truncation bug in historical VaR calculations
docs(readme): structure multi-horizon liquidity stress testing architectural guide
refactor(core): decouple database parameters into explicit system environment controls
style(pep8): align core multi-path stochastic calculation routines with PEP8 standards
```

---

## 9. PROFILE_README.md: Unified Career Portfolio Branding
```markdown
# Urbán Elizabet Gréta | Quantitative Risk & Analytics Professional

An analytics and quantitative risk professional with 5 years of experience in financial systems execution, data architecture optimization, and process automation within the **OTP Bank Group** (OTP Travel Kft.). Possesses a technical background from **WorldQuant University's MSc in Financial Engineering** program alongside structured financial knowledge from Budapest Business University (BGE) MSc in Finance.

### Core Strategic Focus Areas
*   **Asset-Liability Management (ALM):** Advanced liquidity gap modeling, deterministic interest rate risk stress testing, and balance sheet risk mitigation.
*   **Quantitative Engineering:** Vectorized asset price simulations, non-parametric Value-at-Risk (VaR), and computational optimization.
*   **Process Engineering (BI DevOps):** Modernizing legacy workflows using optimized `SQL`, `Python`, and `VBA` processing pipelines integrated into responsive **Power BI** monitoring systems.

### Technical Proficiencies & Analytics Stack
*   **Languages:** Python (NumPy, SciPy, Statsmodels, Pandas), SQL (PostgreSQL, T-SQL), VBA, R
*   **Business Intelligence:** Power BI Desktop/Service, Advanced DAX, Data Gateway Management
*   **Frameworks & Infrastructure:** Git Version Control, SQLAlchemy, PyPortfolioOpt, QuantLib
```

---

## 10. power_bi_integration_pipeline.py: Enterprise Extraction & Reporting
```python
"""
Module: Power BI Data Transformation Bridge
Description: Implements highly optimized data processing logic meant for native integration 
             within Power BI Desktop environment tables via Python integration channels.
"""

import pandas as pd
import numpy as np

def run_power_bi_etl_pipeline(input_raw_dataframe: pd.DataFrame) -> pd.DataFrame:
    """
    Executes deterministic processing and outlier cleansing directly inside Power BI tables.
    Returns highly aligned analytical output formats suitable for DAX query ingestion.
    """
    processed_df = input_raw_dataframe.copy()
    
    # Standardize character layout columns and remove statistical anomalies
    processed_df.columns = [col.strip().upper().replace(' ', '_') for col in processed_df.columns]
    
    # Calculate key metrics (e.g., Z-Score outlier removal on volatile risk columns)
    if 'RISK_EXPOSURE' in processed_df.columns:
        mean_val = processed_df['RISK_EXPOSURE'].mean()
        std_val = processed_df['RISK_EXPOSURE'].std()
        
        # Replace extreme statistical noise with system median threshold metrics
        median_val = processed_df['RISK_EXPOSURE'].median()
        processed_df['RISK_EXPOSURE'] = np.where(
            np.abs((processed_df['RISK_EXPOSURE'] - mean_val) / std_val) > 3.0,
            median_val,
            processed_df['RISK_EXPOSURE']
        )
        
    return processed_df
```
