**NSL-KDD Classical IDS Reproduction & Preprocessing Analysis**

This repository presents a reproducibility and experimental study of classical machine-learning-based Intrusion Detection Systems (IDS) using the NSL-KDD benchmark dataset.

The work has two primary goals:

Faithfully reproduce the classical IDS pipeline described in prior research.

Experimentally analyze preprocessing strategies to understand their effect on IDS performance.

Unlike comparative studies that evaluate multiple datasets, this project focuses exclusively on NSL-KDD, a refined intrusion-detection benchmark created by removing redundant and biased records from earlier datasets, thereby producing a more rigorous and realistic IDS evaluation setting.

---

**Core Research Idea**

Classical IDS performance is highly sensitive to preprocessing.

This repository studies that sensitivity through two conceptual pipelines implemented across multiple structured notebooks:

1. Paper-Faithful Reproduction

   One-hot encoding of categorical features

   L2 normalization of feature vectors

   Classical ML training and evaluation

This mirrors the preprocessing methodology described in the referenced study.

2. Author’s Experimental Extension

   Identical dataset, models, and evaluation

   Replaces L2 normalization with statistical standardization (z-score scaling)

Purpose:

Determine whether standardization improves classical IDS learning behavior on a rigorous dataset.

This transforms the project from pure reproduction into a methodological research exploration.

---

**Implemented Machine Learning Models**

The study evaluates widely used classical IDS classifiers:

Naïve Bayes — probabilistic baseline

Support Vector Machine — linear margin classifier

Random Forest — ensemble decision-tree method

Artificial Neural Network — multilayer nonlinear classifier

These models form the traditional benchmarking foundation for intrusion detection research.

---

**Evaluation Strategy**

Two IDS problem settings are reproduced:

1.  Binary Intrusion Detection

    Metrics:

        Precision

        Recall

        F1-score

Defined using TP/FP/TN/FN relationships standard in IDS evaluation.

2.  Multi-Class Intrusion Type Classification

    Metric:

        Overall testing accuracy across:

            Normal

            DoS

            Probe

            R2L

            U2R

These intrusion categories are defined within the NSL-KDD dataset design.

---

**Notebook-Based Experimental Structure**

Instead of a single monolithic pipeline, the repository contains multiple clearly named notebooks, each representing:

    A specific preprocessing configuration

    A particular model experiment

    Or a dedicated evaluation/analysis step

This modular notebook structure enables:

    Transparent experimentation

    Easier reproducibility

    Incremental research extension

---

**Key Contributions**

1. Faithful Reproduction on NSL-KDD

   Recreates the classical ML IDS evaluation pipeline

   Provides a clean baseline for future research

2. Preprocessing Sensitivity Study (Original Work)

   Direct comparison between:

   L2 normalization

   Standardization

   Highlights how data scaling alone can influence IDS metrics.

---

**Reproducibility**

```bash
git clone https://github.com/SantanuOjha/nsl-kdd-classical-ids-reproduction.git
cd nsl-kdd-classical-ids-reproduction
pip install -r requirements.txt
jupyter notebook
```

Run notebooks in logical order:

    Reproduction notebooks (L2 normalization baseline)

    Standardization notebooks (experimental extension)

    Evaluation notebooks

---

**Future Research Directions**

This foundation enables progression toward:

    Feature-selection-enhanced IDS

    Ensemble or stacked classical models

    Modern intrusion datasets (CICIDS2017, UNSW-NB15)

    Explainable AI for IDS interpretability

Such directions follow the broader evolution of IDS research beyond classical baselines.

---

**Author**

_Santanu Ojha_
_B.Tech – Internet of Things_
_University School of Automation and Robotics_
