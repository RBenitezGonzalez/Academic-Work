# Portfolio Optimization: Linear and Mixed-Integer Formulations and Computational Implementation

Research project on portfolio selection carried out at the **Department of Statistics and Operations Research** of the University of Seville, as a research assistant for the 2026-27 academic year.

* **Author:** Ramiro Benítez González
* **Tutor:** Justo Puerto Albandoz, Head of the Department
* **Supervision:** Alberto Torrejón Valenzuela
* **Institution:** University of Seville, Department of Statistics and Operations Research
* **Date:** October 2026 – Present
* **Status:** 🚧 Stage 1 of 4 (theoretical framework)

---

### The Problem

The **portfolio selection problem** asks how to split a budget among $n$ risky assets. Each asset $i$ has an uncertain rate of return $R_i$; a portfolio $x \in \mathbb{R}^n$ with $\sum_i x_i = 1$ then has return $R_x = \sum_i R_i x_i$, with expected return $\mu^\top x$. Since no portfolio maximizes return and minimizes risk simultaneously, the problem is **bicriteria**: the goal is to compute the set of *efficient* portfolios, those that cannot improve one criterion without worsening the other.

### Why Not Just Variance

Markowitz (1952) measured risk with the variance $x^\top \Sigma x$, and that model is still the reference point. It has, however, two kinds of limitation. **Conceptually**, variance is symmetric: it penalizes returns above the mean exactly as much as returns below it, and it says nothing about the size of the losses in the tail. **Computationally**, it turns the problem into a quadratic program, and into a mixed-integer quadratic one — considerably more expensive — as soon as realistic constraints are added.

When the returns of the assets are represented by a **finite set of historical scenarios**, a different family of risk measures becomes available: measures that can be computed by **linear programming**. Among them are the mean absolute deviation, the semideviation, the minimax rule, Gini's mean difference, and both the Value-at-Risk and the Conditional Value-at-Risk. Each measure gives rise to a different optimization model, with its own theoretical properties and its own computational behaviour, and the choice between them is the subject of this project.

| Risk measure | Constraints | Problem class |
| :--- | :--- | :--- |
| Variance | Budget and no short-selling only | Convex QP |
| Variance | + cardinality or minimum lots | MIQP (NP-hard) |
| MAD · semideviation · minimax · Gini's mean difference · CVaR | Budget only | LP |
| MAD · semideviation · minimax · Gini's mean difference · CVaR | + cardinality, minimum lots, transaction costs | MILP |

### Work Plan

The project is organized as a sequence of stages, developed progressively over the academic year with periodic meetings with the tutor.

**1 · Theoretical framework.** The representation of returns by scenarios and the fundamentals of portfolio optimization: the decision vector, the budget constraint and the distinction between measures of return and measures of risk. Study of the properties that characterize **coherent risk measures** and of their role in portfolio selection.

**2 · Explicit formulations.** Derivation of the mixed-integer mathematical programming formulations of each of the measures considered: how to compute the **mean absolute deviation**, the **semideviation**, the **minimax rule**, **Gini's mean difference**, the **CVaR in the Rockafellar–Uryasev formulation**, and weighted combinations of CVaR. Should the project advance well, **bilevel** and **ordered** formulations will be studied as well.

**3 · Implementation.** A unified code environment in **Python with Gurobi**, in which every model is solved from the same data and through the same structure, which is what makes them comparable. Each implementation is validated on small instances with a verifiable solution. Realistic constraints are then incorporated — **cardinality**, **minimum investment thresholds**, **minimum transaction lots**, and **fixed or piecewise-linear transaction costs** — discussing the modelling alternatives for each and their effect on solution time.

**4 · Computational study.** The whole set of models is solved on **public market data**, over instances of increasing size, varying the number of assets and the length of the historical window. Solution times, formulation sizes and relaxation gaps are recorded and presented in tables and figures. The optimal portfolios obtained under each measure are then compared in terms of **overlap, concentration and diversification**, and their **in-sample and out-of-sample** behaviour is evaluated on rolling windows.

### Deliverables

* The final report on the activity required by the research assistant programme.
* A **technical report in LaTeX** documenting the theoretical framework, the formulations, the computational study and the conclusions.
* A **reproducible code repository** with the implementation of the models.

### Where the Project Stands

1. **Theoretical foundations.** Study of Mansini, Ogryczak & Speranza (2015), *Linear and Mixed Integer Programming for Portfolio Optimization*: rates of return and their estimation from prices, the mean-risk framework, efficiency and safety measures.
2. **Mean-variance model catalogue.** Analysis of the models in [Gurobi Finance](https://gurobi-finance.readthedocs.io/), identifying the problem class of each (QP, MIQP, SOCP): return maximization, variance minimization and utility maximization; factor models; minimum buy-in, cardinality, diversification, round lots and sector allocation; leverage by short-selling or borrowing; turnover limits, transaction costs, rebalancing and market impact.
3. **Data reconstruction.** Reverse-engineering of the dataset used by Gurobi Finance, which does not document its origin: exact reproduction of $\Sigma$, reproduction of $\mu$ through Jorion's Bayes–Stein shrinkage, identification of the data provider, and analysis of its survivorship and look-ahead biases. This is the starting point for building the project's own dataset. **Code:** [`Portfolio_Data_Reconstruction.ipynb`](../../Python_Tests/Portfolio_Data_Reconstruction.ipynb).

### Skills Being Developed

* Mean-risk modelling and its LP, QP and MILP formulations.
* Statistical estimation of model inputs (shrinkage estimators, factor models) and awareness of data biases.
* Modelling and solving with Gurobi (`gurobipy`) in Python, with an emphasis on comparable implementations.
* Experimental methodology: benchmarking formulations by solution time, size and relaxation gap.
* Reading research literature in quantitative finance and operations research, and technical writing in LaTeX.

### Key References

* Markowitz, H. (1952). Portfolio selection. *The Journal of Finance*, 7(1), 77–91.
* Rockafellar, R. T. and Uryasev, S. (2000). Optimization of conditional value-at-risk. *Journal of Risk*, 2(3), 21–41.
* Mansini, R., Ogryczak, W. and Speranza, M. G. (2015). *Linear and Mixed Integer Programming for Portfolio Optimization*. EURO Advanced Tutorials on Operational Research. Springer.
* Gurobi Optimization. *Optimization models for finance*. <https://gurobi-finance.readthedocs.io>

---

### ⬅️ Navigation
[**Return to Projects**](../README.md) · [**Return to Main Portfolio**](../../README.md)
