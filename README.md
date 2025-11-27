
<p align="center">
  <img src="image.png" alt="Startup Success Prediction Project Cover Image" width="800">
</p>
<br>

# Startup Success Prediction Project

This project is for the DSA210 course. The goal is to study which **early observable features** of startups are associated with **eventual success or failure**, using a combination of:

- A **startup outcome dataset** (`startup_success.csv`)
- A **funding composition dataset** (`investments_VC.csv`)

Success is defined as the startup being *operating / acquired / IPO*, while failure is defined as *closed*.

---

## 1. Datasets

All raw data are under the `data/` folder:

- `startup_success.csv` – startup outcomes, locations, basic funding info and relationships.
- `investments_VC.csv` – detailed funding amounts per round type (seed, A, B, …).

The project **enriches** the main outcome dataset (`startup_success.csv`) with round-level funding information from `investments_VC.csv`.

---

## 2. Project Steps

The project is organized into several steps that roughly follow the course structure:

1. **Step 0 – Data Understanding (conceptual)**
   - Read the dataset descriptions and course notes.
   - Decide what “success” means and which variables might be useful (e.g., number of rounds, relationships, early funding, timing of first funding).

2. **Step 1 – Data Cleaning & Enrichment**
   - Load both CSV files, handle encoding issues.
   - Create a common startup identifier (normalized company name) to **merge** the two datasets.
   - Parse date and funding columns into usable numeric and datetime formats.
   - Construct a *clean, merged table* (`data`) that will be used in later steps.

3. **Step 2 – Exploratory Data Analysis (EDA) & Hypothesis Testing**
   - Check class balance of the success label.
   - Summarize key variables (funding amounts, number of rounds, relationships, average participants, timing of first funding).
   - Define simple **derived features** (for example):
     - relationships per round,
     - early total funding,
     - age at first funding,
     - outcome-based age (from founding to closed/acquired/snapshot date),
     - simple seed ratios.
   - Formulate and test a small set of hypotheses (H1–H6) with two-sample t-tests, focusing on:
     - whether **network intensity** (e.g., relationships per round, investors per round),
     - **timing of first funding**, and
     - **early funding size / seed proportions**
     are statistically different between successful and failed startups.

4. **Step 3 – Modeling (planned)**
   - Use the cleaned and enriched features to build a simple predictive model (e.g. logistic regression / tree-based model).
   - Evaluate performance with appropriate metrics (e.g. accuracy, precision/recall, ROC-AUC).

5. **Step 4 – Interpretation & Reporting (planned)**
   - Summarize which early features are most informative in the model.
   - Compare modeling results with the earlier hypothesis tests.
   - Discuss limitations (data collection bias, survivorship bias, timing effects) and possible future improvements.

---

## 3. Repository Structure

```text
data/
    startup_success.csv
    investments_VC.csv

EDA.ipynb     # Main notebook: Step 1 (cleaning/merging) + Step 2 (EDA & H1–H6 tests)
README.md     # This file
