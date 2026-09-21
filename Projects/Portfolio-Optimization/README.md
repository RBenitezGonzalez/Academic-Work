# Portfolio Optimization: Mean-Risk Models and Mixed-Integer Formulations

This folder documents my ongoing research project on portfolio optimization, carried out as an "Alumno Interno" (Undergraduate Researcher) at the University of Seville.

* **Author:** Ramiro Benítez González
* **Supervisors:** Justo Puerto Albandoz (Head of Department) and Alberto Torrejón Valenzuela
* **Institution:** University of Seville, Department of Statistics and Operations Research
* **Date:** September 2026 – Present
* **Status:** 🚧 Phase 1 of 3 (foundations)

---

### Project Overview (English Summary)

The **portfolio selection problem** asks how to split a budget among $n$ risky assets. Each asset $i$ has an uncertain rate of return $R_i$; a portfolio $x \in \mathbb{R}^n$ with $\sum_i x_i = 1$ then has return $R_x = \sum_i R_i x_i$, with expected return $\mu^\top x$. Since no portfolio maximizes return and minimizes risk simultaneously, the problem is **bicriteria**: the goal is to compute the set of *efficient* portfolios, those that cannot improve one criterion without worsening the other.

Markowitz (1952) measured risk with the variance $x^\top \Sigma x$, which yields a quadratic program. The project studies this model and the alternatives that keep the problem **linear**: risk measures such as the Conditional Value-at-Risk (CVaR) or the Mean Absolute Deviation (MAD) can be written as linear programs over return scenarios, so realistic constraints requiring binary variables remain within **mixed-integer linear programming (MILP)**. The choice of risk measure and constraints determines the mathematical nature of the problem:

| Risk measure | Constraints | Problem class |
| :--- | :--- | :--- |
| Variance | Budget and no short-selling only | Convex QP |
| Variance | + cardinality or minimum lots | MIQP (NP-hard) |
| CVaR / MAD | Budget only | LP |
| CVaR / MAD | + cardinality or minimum lots | MILP |

### Roadmap

| Phase | Content | Status |
| :--- | :--- | :--- |
| **1 · Foundations** | Rates of return, estimation of $\mu$ and $\Sigma$, mean-risk analysis, and the catalogue of mean-variance models with their implementation in Gurobi | 🚧 In progress |
| **2 · Risk measurement** | Research literature on risk measures for portfolio optimization | 🔜 Planned |
| **3 · Research project** | To be defined with the supervisors | 🔜 Planned |

### Work So Far

1. **Theoretical foundations.** Study of Mansini, Ogryczak & Speranza (2015), *Linear and Mixed Integer Programming for Portfolio Optimization*: rates of return and their estimation from prices, the mean-risk framework, efficiency and safety measures.
2. **Mean-variance model catalogue.** Analysis of the models in [Gurobi Finance](https://gurobi-finance.readthedocs.io/), identifying the problem class of each (QP, MIQP, SOCP): return maximization, variance minimization and utility maximization; factor models; minimum buy-in, cardinality, diversification, round lots and sector allocation; leverage by short-selling or borrowing; turnover limits, transaction costs, rebalancing and market impact.
3. **Data reconstruction.** Reverse-engineering of the dataset used by Gurobi Finance, which does not document its origin: exact reproduction of $\Sigma$, reproduction of $\mu$ through Jorion's Bayes–Stein shrinkage, identification of the data provider, and analysis of its survivorship and look-ahead biases. This is the starting point for building the project's own dataset. **Code:** [`Portfolio_Data_Reconstruction.ipynb`](../../Python_Tests/Portfolio_Data_Reconstruction.ipynb).

### Skills Being Developed

* Mean-risk modelling and its LP, QP and MILP formulations.
* Statistical estimation of model inputs (shrinkage estimators, factor models) and awareness of data biases.
* Modelling and solving with Gurobi (`gurobipy`) in Python.
* Reading research literature in quantitative finance and operations research.

### Key References

* Markowitz, H. (1952). Portfolio selection. *The Journal of Finance*, 7(1), 77–91.
* Rockafellar, R. T. and Uryasev, S. (2000). Optimization of conditional value-at-risk. *Journal of Risk*, 2(3), 21–41.
* Mansini, R., Ogryczak, W. and Speranza, M. G. (2015). *Linear and Mixed Integer Programming for Portfolio Optimization*. EURO Advanced Tutorials on Operational Research. Springer.
* Gurobi Optimization. *Gurobi Finance*. <https://gurobi-finance.readthedocs.io>

---

### ⬅️ Navigation
[**Return to Projects**](../README.md) · [**Return to Main Portfolio**](../../README.md)
