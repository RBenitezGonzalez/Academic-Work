# Warehouse Slotting Optimization: A MILP Model and an Iterated Local Search Heuristic

This folder describes a research collaboration on the **Storage Location Assignment Problem** (slotting) that I carried out at the Institute of Mathematics of the University of Seville (IMUS).

* **Author:** Ramiro Benítez González
* **Supervisor:** Alberto Torrejón Valenzuela
* **Institution:** Institute of Mathematics of the University of Seville (IMUS)
* **Date:** June 2026 – September 2026
* **Status:** ✅ Completed

> **Confidentiality note:** the code, data, report and numerical results of this project are confidential and are not included in this repository. This page describes the problem, the methodology and the skills I developed.

---

### The Problem (English Summary)

The system under study is an **automated storage and picking system**: a set of modules made of vertical channels, each holding a single product. Order picking is fully automated, but **replenishment is manual**: operators walk along an aisle, collect stock from replenishment zones placed in front of the modules, and refill the channels. Stock that does not fit in the replenishment zones overflows to an external storage area, which forces extra handling.

The slotting decision is therefore not a classical one-dimensional assignment but a **joint geometric co-location problem**. For every product one must decide, simultaneously:

1. which block of **contiguous channels** it occupies,
2. which **replenishment zone** serves it, and
3. whether it is **excluded** from the automated system when capacity is saturated.

The objective is to minimize the operational effort of replenishment: walking distance weighted by demand, use of external storage, and exclusion of products.

### Methodology

**1. Exact model (MILP).** A mixed-integer linear programming formulation with binary assignment variables for channels, zones and inclusion; **contiguity constraints** based on rising-edge detection of each product's block; **McCormick linearisation** of the products of binary variables; a **three-level inventory cascade** (channel, replenishment zone, external storage); and a normalized multi-objective function. It was implemented and solved with Gurobi.

**2. Three-phase heuristic.** Because the exact model becomes intractable as the number of products grows, I designed and implemented in Python a heuristic that reproduces the same objective:

* **Phase I, preprocessing:** cleaning of the physical layout, computation of the number of channels each product needs, and pre-computation of cost matrices so that each move can be evaluated in $O(1)$.
* **Phase II, greedy construction:** an initial feasible solution built with a sliding window over the channels, prioritizing products by the **Cube-per-Order Index** (COI).
* **Phase III, Iterated Local Search (ILS):** four neighbourhood structures (symmetric and asymmetric swaps with cascading shifts, in-out exchanges and volumetric elasticity), **incremental evaluation** of the objective ($\Delta Z$) instead of global recomputation, and a **ruin-and-recreate** perturbation with adaptive intensity.

**3. Validation.** An experimental pipeline compared the heuristic with the exact solver on synthetic instances of increasing size, evaluating both solutions on the same objective function.

### Skills Developed

* **Mathematical modelling:** translating a real operational process into a MILP, including linearisation techniques and the normalization of competing objectives.
* **Algorithm design:** constructive heuristics and metaheuristics (ILS, ruin-and-recreate), neighbourhood design and efficient incremental evaluation.
* **Scientific programming:** Python (`pandas`, `NumPy`, `Matplotlib`) and Gurobi (`gurobipy`).
* **Experimental methodology:** reproducible benchmarking of an exact method against a heuristic.
* **Research practice:** literature review on slotting, technical writing in LaTeX and presentation of results to the supervisor.

### Background References

* Kallina, C. and Lynn, J. (1976). Application of the cube-per-order index rule for stock location in a distribution warehouse. *Interfaces*, 7(1), 37–46.
* Lourenço, H. R., Martin, O. C. and Stützle, T. (2003). Iterated local search. In *Handbook of Metaheuristics*, 320–353. Springer.
* McCormick, G. P. (1976). Computability of global solutions to factorable nonconvex programs: Part I — Convex underestimating problems. *Mathematical Programming*, 10, 147–175.
* Schrimpf, G., Schneider, J., Stamm-Wilbrandt, H. and Dueck, G. (2000). Record breaking optimization results using the ruin and recreate principle. *Journal of Computational Physics*, 159(2), 139–171.

---

### ⬅️ Navigation
[**Return to Projects**](../README.md) · [**Return to Main Portfolio**](../../README.md)
