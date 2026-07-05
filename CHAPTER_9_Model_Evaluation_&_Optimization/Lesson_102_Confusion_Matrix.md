# Chapter 8 -- Model Evaluation & Optimization

# Lesson 102 -- Confusion Matrix

> **A Confusion Matrix is the foundation of classification model
> evaluation. It tells us not only how many predictions were correct,
> but also *what kinds of mistakes* the model made. Almost every
> classification metric, including Accuracy, Precision, Recall, and
> F1-Score, is derived from the Confusion Matrix.**

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will:

-   Understand what a Confusion Matrix is.
-   Learn why it was invented.
-   Understand True Positives, False Positives, False Negatives, and
    True Negatives.
-   Interpret model performance using a Confusion Matrix.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Confusion Matrix?
2.  Why was it Invented?
3.  History
4.  The Four Outcomes
5.  Building a Confusion Matrix
6.  Example Walkthrough
7.  Why Accuracy Alone Fails
8.  Common Mistakes
9.  Python Implementation
10. Real-World Applications
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is a Confusion Matrix?

A Confusion Matrix is a table that compares **actual labels** with
**predicted labels**.

``` text
                    Actual
               Positive   Negative

Pred Positive      TP         FP

Pred Negative      FN         TN
```

Every prediction falls into exactly one of these four cells.

------------------------------------------------------------------------

# 2. Why was it Invented?

A single number like **Accuracy** cannot explain *how* a model fails.

Imagine a disease detection model:

-   990 healthy patients
-   10 sick patients

If the model predicts **everyone as healthy**, it still gets:

``` text
Accuracy = 990 / 1000 = 99%
```

Yet it misses every sick patient.

The Confusion Matrix exposes this problem immediately.

------------------------------------------------------------------------

# 3. History

The idea comes from statistics and diagnostic testing.

``` text
Statistics
     │
Medical Diagnosis
     │
Confusion Matrix
     │
Machine Learning
```

Today, it is the standard evaluation tool for classification models.

------------------------------------------------------------------------

# 4. The Four Outcomes

## True Positive (TP)

The model predicts **Positive**, and the actual label is **Positive**.

``` text
Spam Email

Predicted: Spam ✅
Actual: Spam ✅
```

------------------------------------------------------------------------

## False Positive (FP)

The model predicts **Positive**, but the actual label is **Negative**.

``` text
Normal Email

Predicted: Spam ❌
Actual: Normal
```

Also called a **Type I Error**.

------------------------------------------------------------------------

## False Negative (FN)

The model predicts **Negative**, but the actual label is **Positive**.

``` text
Cancer Patient

Predicted: Healthy ❌
Actual: Cancer
```

Also called a **Type II Error**.

------------------------------------------------------------------------

## True Negative (TN)

The model predicts **Negative**, and the actual label is **Negative**.

``` text
Healthy Patient

Predicted: Healthy ✅
Actual: Healthy ✅
```

------------------------------------------------------------------------

# 5. Building a Confusion Matrix

Example:

``` text
                    Actual
               Yes        No

Pred Yes        40         8

Pred No          5        47
```

Interpretation:

-   TP = 40
-   FP = 8
-   FN = 5
-   TN = 47

------------------------------------------------------------------------

# 6. Example Walkthrough

Suppose 100 emails are classified.

``` text
TP = 30
FP = 10
FN = 5
TN = 55
```

This immediately tells us:

-   30 spam emails correctly detected.
-   10 normal emails incorrectly marked as spam.
-   5 spam emails missed.
-   55 normal emails correctly identified.

------------------------------------------------------------------------

# 7. Why Accuracy Alone Fails

``` text
10,000 Transactions

9,900 Normal
100 Fraud
```

Predict everything as **Normal**:

``` text
Accuracy = 99%
Frauds Found = 0
```

Looks impressive.

Actually useless.

This is why Precision, Recall, and F1-score are derived from the
Confusion Matrix.

------------------------------------------------------------------------

# 8. Common Mistakes

-   Looking only at accuracy.
-   Ignoring false negatives in healthcare.
-   Ignoring false positives in spam filtering.
-   Comparing models without inspecting the confusion matrix.

------------------------------------------------------------------------

# 9. Python Implementation

``` python
from sklearn.metrics import confusion_matrix

cm = confusion_matrix(y_true, y_pred)

print(cm)
```

Visualize:

``` python
from sklearn.metrics import ConfusionMatrixDisplay

ConfusionMatrixDisplay.from_predictions(
    y_true,
    y_pred
)
```

------------------------------------------------------------------------

# 10. Real-World Applications

-   Medical diagnosis
-   Fraud detection
-   Spam filtering
-   Credit approval
-   Face recognition
-   Intrusion detection

------------------------------------------------------------------------

# 11. Mini Project

1.  Train a Logistic Regression classifier.
2.  Predict the test data.
3.  Compute the confusion matrix.
4.  Interpret TP, FP, FN, and TN.
5.  Explain which errors matter most for your application.

------------------------------------------------------------------------

# 12. Interview Questions

### What is a Confusion Matrix?

A table comparing predicted labels with actual labels.

### What are TP, FP, FN, and TN?

-   TP: Correct positive prediction
-   FP: Incorrect positive prediction
-   FN: Incorrect negative prediction
-   TN: Correct negative prediction

### Why is it important?

Because it reveals the kinds of mistakes a model makes.

### Which metrics come from the Confusion Matrix?

-   Accuracy
-   Precision
-   Recall
-   F1-Score
-   Specificity

------------------------------------------------------------------------

# 13. Summary

You learned:

-   What a Confusion Matrix is.
-   The meaning of TP, FP, FN, and TN.
-   Why accuracy can be misleading.
-   How to build and interpret a confusion matrix.
-   Python implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 103 -- Accuracy**

You'll learn how Accuracy is calculated, when it works well, when it
completely fails, its mathematical formulation, advantages, limitations,
and its relationship with class imbalance.
