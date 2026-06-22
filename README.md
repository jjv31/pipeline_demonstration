# Coding Strategy Demonstration

A minimal, runnable demonstration of the **seven-step, leakage-resistant machine-learning
pipeline** described in Chapter 2 (Figure 2-1) and implemented in Chapter 3 (§3.3–§3.8).

The task is **violent-recidivism forecasting**: for each convicted offender, at the time of their
disposition, predict whether they commit a violent offence within the next three years. Each
section of the notebook implements one step of the pipeline with the bare minimum of code needed
to show it clearly.

| Figure 2-1 step | Section | Leakage addressed |
|---|---|---|
| 1. Dataset download | 1 | — |
| 2. Stateless preprocessing | 2 | Temporal, Target |
| 3–4. Cross-validation prep & assignment | 3 | **Group** |
| 5. State-dependent preprocessing | 4 | Preprocessing |
| 6. Model building / hyperparameter tuning | 5 | Hyperparameter |
| 7. Evaluation on the held-out test set | 6 | — |

## Running it

The notebook is **self-contained** — it generates its own synthetic, PNC-like dataset (the real
data is confidential), so it runs top to bottom with no external data files.

```bash
pip install numpy pandas matplotlib scikit-learn
jupyter lab "Coding Strategy Demonstration.ipynb"
```

Then run all cells. The synthetic dataset (`res/pnc_demo_raw.csv`) and the cross-validation fold
CSVs (`res/dataset_folds/`) are created automatically at run time and are intentionally **not**
tracked in this repository.

## Note on the results

The reported metrics come from a randomly generated synthetic dataset, not the real PNC data. They
exist only to show that the pipeline runs end to end and produces sensible output; they will not
match the figures in the paper and may shift between runs.
