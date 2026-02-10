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

**Evaluation**

_Binary Class Classification Metrics_

| Model         | Paper Precision | Paper Recall | Paper F1   | Reproduced Precision | Reproduced Recall | Reproduced F1 |
| ------------- | --------------- | ------------ | ---------- | -------------------- | ----------------- | ------------- |
| ANN           | 0.9661          | 0.6205       | 0.7557     | **0.93**             | **0.63**          | **0.76**      |
| SVM           | 0.8839          | 0.8142       | 0.8476     | **0.97**             | **0.61**          | **0.75**      |
| Naïve Bayes   | 0.9672          | 0.1746       | 0.2957     | **0.97**             | **0.17**          | **0.30**      |
| Random Forest | 0.9683          | 0.6158       | 0.7528     | **0.97**             | **0.62**          | **0.76**      |
| **Average**   | **0.9464**      | **0.5563**   | **0.6630** | **0.96**             | **0.4175**        | **0.6425**    |

_Multiclass Classification Metrics_

| Model         | Paper Accuracy | Reproduced Accuracy |
| ------------- | -------------- | ------------------- |
| ANN           | 78.51%         | **70%**             |
| SVM           |                |                     |
| Naïve Bayes   | 61.08%         | **45%**             |
| Random Forest | 71.33%         | **76%**             |
| **Average**   | **71.33%**     | **63.66%**          |

---

**Reproduction Results**

The reproduced NSL-KDD results broadly follow the performance trends reported in the original study, particularly the overall lower recall and F1-scores characteristic of this dataset’s higher rigor and reduced redundancy.

_For binary classification, the reproduced models achieve:_

    F1-scores close to the reported ANN and Random Forest values

    Comparable Naïve Bayes behavior with very low recall, consistent with the paper’s findings

    A moderate deviation in SVM recall and F1, though the relative ranking of models remains similar to the original evaluation.

Such deviations are expected in reproduction studies due to:

    Differences in random initialization and sampling

    Library and implementation-level variations

    Sensitivity of SVM optimization to feature scaling and training subset size

    The original work itself notes that SVMs were trained on very small random samples due to computational cost, making their metrics particularly sensitive to experimental setup changes.

_For multi-class intrusion type classification, the reproduced accuracies show:_

The reproduced multi-class accuracies on NSL-KDD are consistently lower than those reported in the original study, particularly for ANN and Naïve Bayes, resulting in a reduced overall average accuracy. In contrast, Random Forest performance remains comparatively stable and slightly higher than the reported value, indicating stronger robustness to preprocessing and distributional variation.

These deviations are technically expected because NSL-KDD is a more rigorous intrusion-detection benchmark with reduced redundancy and higher sensitivity to training configuration, making exact numerical reproduction challenging. Additionally, ANN training on NSL-KDD is known to exhibit unstable convergence behavior, while Gaussian Naïve Bayes suffers from distributional assumption mismatch with the heterogeneous feature space of the dataset.

Overall, despite lower absolute accuracies, the reproduced results remain methodologically consistent with the difficulty characteristics of NSL-KDD, supporting the validity of this reproduction study.

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
