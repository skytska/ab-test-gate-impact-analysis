# `A/B Test Analysis`: Impact of Game Progression Gate on User Retention

## I. Project Background

This project presents an analysis of an **A/B test** conducted in the mobile game *Cookie Cats*.

The objective is to evaluate the impact of changing the **first game progression gate from level 30 to level 40** on:

* **User retention**
* **User engagement**

---

### Business Problem & Hypothesis

**Business question:**

Does moving the first game gate from **level 30 to level 40** affect **user retention and engagement**?

---

**Hypotheses:**

**Retention (core KPI)**

* H0: retention_1 and retention_7 are equal between groups
* H1: there is a **statistically significant difference**

**Engagement (secondary KPI)**

* H0: sum_gamerounds is equal between groups
* H1: there is a difference

---

**Business intuition:**

A later gate may increase **short-term engagement** by allowing uninterrupted gameplay, but it could negatively impact **retention** if players lose motivation or face delayed progression friction.

---

### Scope of Analysis

* Compare **control (gate_30)** and **test (gate_40)** groups
* Evaluate **retention (Day 1 and Day 7)** and **engagement (gamerounds)**
* Apply **statistical testing** to validate observed differences
* Quantify **effect size and business impact**
* Build a **Tableau dashboard** for result communication

---

## II. Data Structure & Data Model

The dataset includes **90,000+ records** and is structured at a **user level**.
This dataset is taken from [Kaggle](https://www.kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats).

The project follows a **layered data approach**:

* Raw data (user-level dataset)
* Aggregated metrics and statistical analysis in Python
* Visualization-ready datasets for Tableau
* Final dashboard for business insights

![Data Model](output/Data_Structure.png)

---

### Data Preparation Workflow

**Python (Pandas)**

* Data cleaning and validation
* Metric calculation (**retention rates, average gamerounds**)
* Aggregation by experiment group
* Statistical testing:

  * Z-test (proportions)
  * T-test (means)
  * Mann–Whitney U test (distribution comparison)
  * Bootstrapping (confidence intervals)
* Creation of **summary and visualization datasets**

---

**Tableau**

* KPI visualization (**retention and engagement**)
* Group comparison charts
* Effect size (**delta**) visualization
* Statistical significance table
* Bootstrap distribution visualization

---

## III. Executive Summary

### Tableau Dashboard

![Dashboard](output/Dashboard.png)

Click the [Tableau Public dashboard](https://surl.lu/qicavv) to explore **interactive filters and drill-downs**.

---

### Business Impact

> The analysis reveals a **negative impact of moving the gate to level 40 on user retention**, with **no improvement in engagement**.

---

### Key Findings

* **Retention Day 1:** No statistically significant difference
* **Retention Day 7:** **Statistically significant decrease** in the test group
* **Engagement (gamerounds):** No significant difference between groups
* All observed changes are negative, but only **long-term retention** shows statistical significance

---

### Strategic Interpretation

Delaying the first progression barrier reduces **long-term retention** without generating additional engagement. This suggests that **early progression structure** plays a critical role in maintaining player motivation and return behavior.

---

### Strategic Insights

* **Early friction (gate at level 30)** may support stronger habit formation
* Removing or delaying progression constraints does not necessarily improve engagement
* **Long-term retention** is more sensitive to game design changes than short-term behavior

---

## IV. Strategic Recommendations

* **Maintain the gate at level 30**
* Avoid delaying early progression barriers without clear engagement benefits
* Prioritize experiments that improve **long-term retention**
* Complement A/B testing with **qualitative insights** (player behavior, UX feedback)

---

<br>

*Technical summary of tools and analytical methods used in this project*:

* Tools: Python (Pandas), Jupyter Notebook, Tableau
* Analytical Techniques: Descriptive analysis, Z-test for proportions, T-test (Welch), Mann–Whitney U test, Bootstrapping (confidence intervals)
* Key Metrics: Retention Day 1 (retention_1), Retention Day 7 (retention_7), Average gamerounds (engagement)
