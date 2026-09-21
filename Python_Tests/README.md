# Computational Mathematics & Python

This directory serves as a computational laboratory for my independent study. The goal is to bridge the gap between mathematical models and real data, implementing the estimation and optimization techniques behind my research in portfolio optimization.

---

## 1. Current Explorations

### ➡️ [Notebook: Portfolio Data Reconstruction](Portfolio_Data_Reconstruction.ipynb)
* **Focus:** Estimation of portfolio inputs and mean-variance optimization with **pandas**, **SciPy** and **Gurobi**.
* **Objective:** To reconstruct how the undocumented dataset used by [Gurobi Finance](https://gurobi-finance.readthedocs.io/) was built, and to understand what its estimated inputs imply for portfolio optimization.
* **Methodology:**
    1.  Computation of weekly **rates of return** for 462 S&P 500 stocks (2013–2023) and exact reproduction of the **sample covariance matrix** $\hat\Sigma$.
    2.  Reproduction of the **expected returns** through **Jorion's Bayes–Stein shrinkage** towards the Global Minimum Variance portfolio (intensity $w \approx 0.57$).
    3.  Forensic analysis of the data: split-adjusted prices, dating of the constituent list, identification of the provider and its **survivorship bias**.
    4.  X-ray of the data: volatilities, correlations and the **spectrum of $\hat\Sigma$** (a market factor explaining 36% of the variance; condition number $\approx 3.5\cdot10^5$).
    5.  **Efficient frontier** in closed form (short-selling allowed) and as a long-only **quadratic program** solved with Gurobi, showing how estimation error drives the unconstrained solution to extreme leverage.

The data are downloaded automatically from the Gurobi Finance documentation the first time the notebook runs; they are not redistributed in this repository.

---

## 2. Technical Stack

The following tools are currently being used to support mathematical experimentation:

| Library | Mathematical Application | Utility |
| :--- | :--- | :--- |
| **[Gurobi](https://www.gurobi.com/)** (`gurobipy`) | **Mathematical Optimization** | LP, MILP and QP modelling and solving |
| **NumPy** / **SciPy** | **Linear Algebra** | Matrix operations, linear systems, eigenvalues |
| **pandas** | **Statistics** | Time series of prices and returns, sample estimators |
| **Matplotlib** | **Visualization** | Histograms, spectra and efficient frontiers |

---

### ⬅️ [Return to Main Portfolio](../README.md)
