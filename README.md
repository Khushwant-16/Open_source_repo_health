# Open-Source Repository Health Predictor 📊

## Overview
Evaluating the long-term viability of open-source software is critical for enterprise adoption. This project utilizes data mining and machine learning to predict whether a GitHub repository is at risk of being abandoned.

Instead of relying solely on basic commit volume, this predictive model engineers advanced structural features—such as developer network density and "Bus Factor" risk—to mathematically quantify the health of a project's collaboration community.

---

## 🏗️ Data Architecture & Pipeline

**Data Extraction (Google BigQuery):** Queried the `githubarchive` dataset to extract over **450,000 raw, human-only interaction logs** (Pushes, Pull Requests, Issues) across **2,000 balanced repositories**.

**Sequential Pattern Mining (PrefixSpan):** Analyzed behavioral timelines to contrast the event sequences of healthy versus dying projects.

**Structural Graph Mining (NetworkX):** Constructed co-working topologies to map the social collaboration network of each repository.

**Predictive Modeling (Scikit-learn):** Trained a **Random Forest Classifier** to forecast abandonment based on the engineered statistical and structural features.

---

## 🧠 Key Engineered Features

**Bus Factor Risk:** A graph-based centrality metric calculating the project's reliance on a single central developer. High risk indicates a single point of failure.

**Network Density:** Measures the interconnectedness of the contributor community. Dense webs indicate redundant, resilient collaboration.

**Issue-to-Push Ratio:** A statistical indicator of maintainer overload, measuring the accumulation of bugs relative to deployed code fixes.

---

## 📈 Results & Business Value

In predictive health systems, **False Negatives** (missing a dying, vulnerable project) are far more dangerous than **False Positives**. The model was aggressively optimized for **Recall**.

**Recall (Risk Detection):** 81% success rate in identifying truly abandoned repositories.

**Overall Accuracy:** 75.6% accuracy on complex, real-world social coding data.

---

## Feature Importance



The model revealed that while sheer push volume is critical, the structural health of the network (**Network Density**) is a top-3 predictor of repository survival.

---

## 🕸️ Community Topologies: Healthy vs. Abandoned

**Left:** A highly dense, resilient developer web (Low Bus Factor Risk).

**Right:** A fragile, hub-and-spoke community overly reliant on a single maintainer (High Bus Factor Risk).

---

## 💻 Tech Stack

**Data Extraction:** Google Cloud BigQuery, SQL

**Data Processing & Engineering:** Pandas, NumPy, PrefixSpan

**Graph Mining & Network Analysis:** NetworkX

**Machine Learning:** Scikit-learn (Random Forest)

**Visualization:** Matplotlib, Seaborn
