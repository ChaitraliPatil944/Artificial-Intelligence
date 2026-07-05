# Chapter 8 -- Model Evaluation & Optimization

# Lesson 108 -- AUC (Area Under the ROC Curve)

> **AUC (Area Under the ROC Curve) summarizes the entire ROC Curve into
> a single number. It measures how well a classifier separates positive
> and negative classes across all possible decision thresholds. A higher
> AUC indicates a better classifier.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what AUC is.
-   Learn why AUC was introduced.
-   Understand the relationship between ROC and AUC.
-   Interpret AUC scores.
-   Compare AUC with Accuracy and F1-Score.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is AUC?
2.  Why AUC was Introduced
3.  Relationship with ROC
4.  Mathematical Intuition
5.  Interpreting AUC Scores
6.  AUC vs Accuracy
7.  AUC vs F1-Score
8.  Advantages
9.  Limitations
10. Python Implementation
11. Applications
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

------------------------------------------------------------------------

# 1. What is AUC?

AUC stands for **Area Under the ROC Curve**.

Instead of evaluating one threshold, it summarizes performance across
**all thresholds**.

``` text
ROC Curve

TPR ↑
1.0 |       ****
    |     ***
    |   **
    | **
0.0 +----------------→ FPR

Area under curve = AUC
```

------------------------------------------------------------------------

# 2. Why AUC was Introduced

Comparing two ROC curves visually can be difficult.

AUC converts the entire curve into a **single score**, making model
comparison easier.

------------------------------------------------------------------------

# 3. Relationship with ROC

-   ROC is a **curve**.
-   AUC is the **area beneath that curve**.

A better ROC Curve generally results in a higher AUC.

------------------------------------------------------------------------

# 4. Mathematical Intuition

AUC represents the probability that the classifier ranks a randomly
chosen positive sample **higher** than a randomly chosen negative
sample.

Example:

``` text
Positive Score = 0.91
Negative Score = 0.34

Correct ranking ✅
```

The more often this happens, the higher the AUC.

------------------------------------------------------------------------

# 5. Interpreting AUC Scores

  AUC         Interpretation
  ----------- --------------------
  1.0         Perfect classifier
  0.9 - 1.0   Excellent
  0.8 - 0.9   Good
  0.7 - 0.8   Fair
  0.6 - 0.7   Poor
  0.5         Random guessing
  \< 0.5      Worse than random

------------------------------------------------------------------------

# 6. AUC vs Accuracy

  Accuracy                       AUC
  ------------------------------ -----------------
  Single threshold               All thresholds
  Sensitive to class imbalance   More robust
  Overall correctness            Ranking ability

------------------------------------------------------------------------

# 7. AUC vs F1-Score

  AUC                     F1
  ----------------------- ----------------------------------
  Threshold independent   Threshold dependent
  Ranking quality         Balance of Precision & Recall
  Compares classifiers    Evaluates chosen operating point

------------------------------------------------------------------------

# 8. Advantages

-   Threshold independent.
-   Excellent for model comparison.
-   Robust on moderately imbalanced datasets.
-   Widely used in research.

------------------------------------------------------------------------

# 9. Limitations

-   Less informative than Precision-Recall curves for extremely
    imbalanced datasets.
-   Does not indicate the best operating threshold.
-   Can hide practical deployment issues.

------------------------------------------------------------------------

# 10. Python Implementation

``` python
from sklearn.metrics import roc_auc_score

auc = roc_auc_score(y_true, y_scores)

print(auc)
```

Plot ROC with AUC:

``` python
from sklearn.metrics import RocCurveDisplay

RocCurveDisplay.from_predictions(
    y_true,
    y_scores
)
```

------------------------------------------------------------------------

# 11. Applications

-   Medical diagnosis
-   Credit scoring
-   Fraud detection
-   Spam filtering
-   Risk prediction

------------------------------------------------------------------------

# 12. Mini Project

1.  Train two classifiers.
2.  Predict probabilities.
3.  Compute AUC.
4.  Plot ROC curves.
5.  Compare the models using AUC.

------------------------------------------------------------------------

# 13. Interview Questions

### What is AUC?

The area under the ROC Curve.

### What does an AUC of 0.5 mean?

The classifier performs no better than random guessing.

### Why is AUC useful?

It evaluates classifier performance across every threshold.

### Is a higher AUC always better?

Generally yes, but deployment requirements and class imbalance should
also be considered.

------------------------------------------------------------------------

# 14. Summary

You learned:

-   What AUC is.
-   How it relates to ROC.
-   How to interpret AUC values.
-   Comparison with Accuracy and F1.
-   Python implementation.

------------------------------------------------------------------------

# 15. What's Next?

**Lesson 109 -- Regression Metrics**

You'll learn MAE, MSE, RMSE, R² Score, and Adjusted R², understand how
regression models are evaluated, and learn why classification metrics
cannot be used for regression problems.
