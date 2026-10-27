# Ramiro Benítez González - Academic Portfolio

Welcome to my academic portfolio. I am a 3rd-year Mathematics undergraduate at the University of Seville (US), focused on **Operations Research, Mathematical Optimization and Quantitative Finance**, with a strong interest in Probability Theory and Stochastic Processes.

Since **October 2026** I am a **Research Assistant at the Department of Statistics and Operations Research** of the University of Seville, working on portfolio optimization for the 2026-27 academic year. During the summer of 2026 I collaborated with the Institute of Mathematics of the University of Seville (IMUS) on a warehouse slotting problem. Both projects follow the same line of work: write an operational or financial decision as a mixed-integer linear program, and then make that program solvable at a realistic size.

This repository contains my research projects, CV source code, and independent study explorations.

---

## 1. Research Projects

This section contains my formal research and departmental collaborations. You can browse the full directory of projects here: [📂 View All Projects](Projects/).

### ➡️ [Current] [Portfolio Optimization](Projects/Portfolio-Optimization/)
* **Description:** Portfolio selection beyond the mean-variance model: LP-computable risk measures (mean absolute deviation, semideviation, minimax, Gini's mean difference, CVaR) and the mixed-integer formulations that appear once real market constraints — cardinality, minimum buy-in, minimum lots, transaction costs — are imposed.
* **Role:** Research Assistant, Department of Statistics and Operations Research, University of Seville.
* **Tutor:** Justo Puerto Albandoz, Head of the Department. **Supervision:** Alberto Torrejón Valenzuela.
* **Dates:** October 2026 – present (2026-27 academic year).
* *(Work in progress. The folder documents the work plan, the formulations and the progress so far.)*

### ➡️ [Warehouse Slotting Optimization](Projects/Warehouse-Slotting-Optimization/)
* **Description:** A Storage Location Assignment Problem (slotting) for an automated storage and picking system, modelled as a mixed-integer linear program and solved at scale with a three-phase heuristic based on Iterated Local Search.
* **Role:** Research Collaborator, Institute of Mathematics of the University of Seville (IMUS).
* **Supervisor:** Alberto Torrejón Valenzuela.
* **Dates:** July – September 2026. ✅ Completed.
* *(Code and data are confidential. The folder describes the problem, the methodology and the skills developed.)*

---

## 2. CV Template (LaTeX)

This section contains the source code of my Academic CV.

### ➡️ [CV Source Code](CV/)
* **Description:** A one-page LaTeX academic CV using the Palatino font, designed as a reusable template.
* **Key Feature:** A **boolean switch** (`\setbool{showphoto}{...}`) toggles between a European layout (with photo) and an International layout (text-only). All personal data live in a single block of macros at the top of the file.
* **Format:** `.tex` source code and the generated `.pdf`.

---

## 3. Independent Study & Code Explorations

This section contains code related to my self-study interests.

### ➡️ [Python](Python_Tests/)
* **Description:** Computational experiments that complement my research, built with `NumPy`, `pandas`, `SciPy`, `Matplotlib` and the Gurobi optimizer (`gurobipy`).
* **Notebook:** [`Portfolio_Data_Reconstruction.ipynb`](Python_Tests/Portfolio_Data_Reconstruction.ipynb)
* **Content:** This notebook **reverse-engineers the dataset used by Gurobi Finance** (462 S&P 500 stocks, weekly prices 2013–2023): it reproduces its covariance matrix exactly and its expected returns through **Jorion's Bayes–Stein shrinkage**, identifies the data provider and its **survivorship bias**, and traces the **efficient frontier** in closed form and under a long-only constraint.

---

📫 **Contact:** [ramirobg04@gmail.com](mailto:ramirobg04@gmail.com) · [LinkedIn](https://www.linkedin.com/in/ramiro-benitez-gonzalez)
