# Chapter 8 -- Model Evaluation & Optimization

# Lesson 107 -- ROC Curve (Receiver Operating Characteristic)

> **The ROC Curve evaluates a binary classifier across every possible
> decision threshold by plotting the True Positive Rate (Recall) against
> the False Positive Rate. It helps compare classifiers without
> committing to a single threshold.**

------------------------------------------------------------------------

## Learning Objectives

-   Understand ROC Curves.
-   Learn TPR and FPR.
-   Understand thresholds.
-   Interpret ROC plots.
-   Prepare for interviews.

------------------------------------------------------------------------

## What is the ROC Curve?

    TPR ↑
    1.0 |        *
        |      *
        |    *
        |  *
    0.0 +-----------------> FPR
        0                1

The closer the curve is to the **top-left corner**, the better the
classifier.

------------------------------------------------------------------------

## Why was it introduced?

Many models predict probabilities instead of labels. Changing the
classification threshold changes Precision and Recall. The ROC Curve
evaluates performance for **all thresholds**.

------------------------------------------------------------------------

## Key Metrics

### True Positive Rate (Recall)

    TP / (TP + FN)

### False Positive Rate

    FP / (FP + TN)

------------------------------------------------------------------------

## Decision Threshold

    Probability >= 0.5

    Positive

Increasing the threshold reduces positive predictions. Lowering it
increases positive predictions.

------------------------------------------------------------------------

## Random vs Ideal Classifier

Random:

    \\
     \\
      \\

Ideal:

    |
    |
    |_______

------------------------------------------------------------------------

## ROC vs Precision-Recall

  ROC                       PR Curve
  ------------------------- ----------------------------------
  Uses TPR & FPR            Uses Precision & Recall
  Better on balanced data   Better on highly imbalanced data

------------------------------------------------------------------------

## Python

``` python
from sklearn.metrics import RocCurveDisplay

RocCurveDisplay.from_predictions(y_true, y_scores)
```

------------------------------------------------------------------------

## Applications

-   Medical diagnosis
-   Fraud detection
-   Spam filtering
-   Credit scoring

------------------------------------------------------------------------

## Interview Questions

-   What does ROC stand for?
-   What are TPR and FPR?
-   What does the diagonal line represent?
-   Why evaluate multiple thresholds?

------------------------------------------------------------------------

## Summary

-   ROC evaluates classifiers across thresholds.
-   Uses TPR and FPR.
-   Better curves stay near the top-left.

------------------------------------------------------------------------

## What's Next?

**Lesson 108 -- AUC (Area Under the ROC Curve)**
