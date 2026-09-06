# Solutions to Problem Set

> **Course:** M.Sc. Economics — Probability, Statistics & Machine Learning  
> **Institute:** IIT Kanpur

A complete, well-organised collection of Python notebook solutions for all six
coding exercises. Every notebook is self-contained, generic (parameters are
clearly labelled so small changes to any question require editing only one
block), and fully verified to run end-to-end.

---

## Repository Structure

```
.
├── README.md
├── questions/          # Original problem-set PDFs
│   ├── Exercise_1.pdf
│   ├── Exercise_2.pdf
│   ├── Exercise_3.pdf
│   ├── Exercise_4.pdf
│   └── Exercise_5.pdf   ← Q5 & Q6 notebooks come from this PDF
│
├── solutions/          # Jupyter notebooks — one per exercise
│   ├── Exercise_1_and_2.ipynb
│   ├── Exercise_3_TimeSeries.ipynb
│   ├── Exercise_4_Classification.ipynb
│   ├── Exercise_5_ML.ipynb
│   └── Exercise_6_Advanced.ipynb
│
└── data/               # CSV datasets used in the notebooks
    ├── bjm.csv          ← Exercise 3 (AR/ARMA identification)
    ├── Carseats.csv     ← Exercise 5 Q3 (regression tree / random forest)
    └── spambase.csv     ← Exercise 5 Q5 (spam email classification)
```

---

## Exercise Summary

### Exercise 1 & 2 — `Exercise_1_and_2.ipynb`
| Q | Topic | Key detail |
|---|-------|-----------|
| 1 | Generate Binomial / Geometric / NegBin | `rand` only |
| 2 | Generate Poisson(λ) | `exponential` only |
| 3 | Chi-squared GOF test | No `scipy.stats.chisquare`; low-E bin removal |
| 4 | Gamma(3,β) + KS test | No `ks_1samp`; Kolmogorov series |
| 5 | EM — Gaussian mixture (K=2 and K=3) | Generic K |
| 6 | EM — Binomial mixture | M-step as given |
| Ex2-1 | Binomial exact test | No `scipy.stats.binom` |
| Ex2-2 | Fisher's exact test | No built-ins |
| Ex2-3 | Bootstrap kurtosis CI | Percentile method |
| Ex2-4 | Monte Carlo kurtosis test (a/b/c) | Symmetry discussion |

### Exercise 3 — `Exercise_3_TimeSeries.ipynb`
| Q | Topic | Key detail |
|---|-------|-----------|
| 1 | MA(q) generation & verification | Theoretical moments formula |
| 2 | AR(3) + Yule-Walker equations | (p+1)×(p+1) linear system |
| 3 | Identify AR(p) from bjm.csv col 1 | PACF cutoff → YW estimation |
| 4 | ARMA Box-Jenkins (bjm.csv cols 2 & 3) | AIC grid → MLE → Ljung-Box |
| 5 | VAR(p) generation & identification | OLS + AIC/BIC order selection |

### Exercise 4 — `Exercise_4_Classification.ipynb`
| Q | Topic | Key detail |
|---|-------|-----------|
| 1 | Dataset construction (200 pts, 2 classes) | Gaussian mixture clusters |
| 2 | Linear classifier | Least-squares normal equations |
| 3 | 15-NN classifier | Decision regions plotted |
| 4 | 1-NN classifier | Overfitting visualised |
| 5 | Train vs test error comparison | All 3 classifiers; bar chart |

### Exercise 5 — `Exercise_5_ML.ipynb`
| Q | Topic | Key detail |
|---|-------|-----------|
| 1 | OLS / Ridge / Lasso + 5-fold CV | Closed form + sklearn verify |
| 2 | Decision tree from scratch (Gini) | Max depth 3, ≤10 pts |
| 3 | Carseats: DT Regressor + Random Forest | B=100, 4 features |
| 4 | MLP for y=‖x‖² | 5-fold CV, 3D surface plot |
| 5 | Spam email MLP (sklearn) | 75/25 split, confusion matrix |

### Exercise 6 — `Exercise_6_Advanced.ipynb`
| Q | Topic | Key detail |
|---|-------|-----------|
| 1 | Poisson(1.72) via `exponential` | Manual χ² test, bin removal |
| 2 | MA(5) with Uniform noise | numpy only; γ(s) verified |
| 3 | VAR(3): generate, stationarity, estimate | numpy only; Cholesky + OLS |
| 4 | Ridge regression (sparse) | Closed form; top-5 features |
| 5 | Regression tree from scratch (SSE) | Depth 2; sklearn verify |
| 6 | 2-hidden-layer MLP, 27 configs | 5-fold CV from scratch |

---

## Setup

```bash
pip install numpy scipy matplotlib pandas statsmodels scikit-learn nbformat
```

Open any notebook in Jupyter:

```bash
jupyter notebook solutions/Exercise_1_and_2.ipynb
```

> **Changing parameters:** every notebook has a clearly labelled
> `# PARAMETERS (change freely)` block at the top of each question.
> Edit only that block — all functions adapt automatically.

---

## Notes on Data Files

| File | Source |
|------|--------|
| `bjm.csv` | Provided with Exercise 3 |
| `Carseats.csv` | ISLR-schema synthetic dataset (matches original structure) |
| `spambase.csv` | [UCI Spambase](https://archive.ics.uci.edu/dataset/94/spambase) — replace with the real download for Exercise 5 Q5 |
