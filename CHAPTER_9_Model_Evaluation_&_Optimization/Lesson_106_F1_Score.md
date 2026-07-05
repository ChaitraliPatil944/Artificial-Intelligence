# Chapter 8 -- Model Evaluation & Optimization

# Lesson 106 -- F1-Score

> **F1-Score combines Precision and Recall into a single metric using
> the Harmonic Mean. It is widely used when datasets are imbalanced and
> both False Positives and False Negatives are important.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what F1-Score is.
-   Learn why it was introduced.
-   Understand the Harmonic Mean.
-   Calculate F1-Score.
-   Compare F1 with Accuracy, Precision, and Recall.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is F1-Score?
2.  Why F1-Score was Introduced
3.  Harmonic Mean
4.  Formula
5.  Intuition
6.  Example
7.  F1 vs Accuracy
8.  F1 vs Precision vs Recall
9.  Macro, Micro & Weighted F1
10. Advantages
11. Limitations
12. Python Implementation
13. Applications
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

------------------------------------------------------------------------

# 1. What is F1-Score?

F1-Score measures the balance between **Precision** and **Recall**.

``` text
Precision
     \\
      \\
      F1
      //
Recall
```

A model must perform well on **both** metrics to achieve a high
F1-Score.

------------------------------------------------------------------------

# 2. Why F1-Score was Introduced

Sometimes a model has:

-   High Precision but Low Recall
-   High Recall but Low Precision

Neither tells the complete story.

F1 summarizes both into one value.

------------------------------------------------------------------------

# 3. Harmonic Mean

Unlike the arithmetic mean, the harmonic mean heavily penalizes low
values.

Example:

``` text
Precision = 1.0
Recall    = 0.2

Average = 0.6

F1 ≈ 0.33
```

A weak Precision or Recall significantly lowers the F1-Score.

------------------------------------------------------------------------

# 4. Formula

``` text
          2 × Precision × Recall
F1 = --------------------------------
      Precision + Recall
```

Equivalent form:

``` text
        2TP
------------------
2TP + FP + FN
```

------------------------------------------------------------------------

# 5. Intuition

Imagine a football striker.

-   Precision = Shots that become goals.
-   Recall = Number of scoring opportunities converted.

F1 rewards players who are both accurate and productive.

------------------------------------------------------------------------

# 6. Example

Suppose:

``` text
Precision = 0.80
Recall    = 0.60
```

Then:

``` text
F1

= 2 × 0.8 × 0.6
  -------------
   0.8 + 0.6

≈ 0.686
```

------------------------------------------------------------------------

# 7. F1 vs Accuracy

  Accuracy                 F1-Score
  ------------------------ -------------------------------
  Overall correctness      Balance of Precision & Recall
  Good for balanced data   Good for imbalanced data
  Can be misleading        More informative

------------------------------------------------------------------------

# 8. F1 vs Precision vs Recall

  Metric      Focus
  ----------- -----------------
  Precision   False Positives
  Recall      False Negatives
  F1          Balance of both

------------------------------------------------------------------------

# 9. Macro, Micro & Weighted F1

### Macro F1

Treats every class equally.

### Micro F1

Aggregates all predictions before computing F1.

### Weighted F1

Weights classes according to their frequency.

------------------------------------------------------------------------

# 10. Advantages

-   Excellent for imbalanced datasets.
-   Balances Precision and Recall.
-   Widely used in ML competitions and research.

------------------------------------------------------------------------

# 11. Limitations

-   Ignores True Negatives.
-   Less intuitive than Accuracy.
-   Doesn't distinguish whether Precision or Recall is causing poor
    performance.

------------------------------------------------------------------------

# 12. Python Implementation

``` python
from sklearn.metrics import f1_score

score = f1_score(y_true, y_pred)

print(score)
```

For multiclass:

``` python
f1_score(y_true, y_pred, average="weighted")
```

------------------------------------------------------------------------

# 13. Applications

-   Medical diagnosis
-   Fraud detection
-   Spam filtering
-   Intrusion detection
-   Information retrieval

------------------------------------------------------------------------

# 14. Mini Project

1.  Train a classifier.
2.  Compute Accuracy, Precision, Recall, and F1.
3.  Compare all metrics.
4.  Explain why F1 is useful on imbalanced data.

------------------------------------------------------------------------

# 15. Interview Questions

### What is F1-Score?

The harmonic mean of Precision and Recall.

### Why harmonic mean?

Because it penalizes low values more strongly than the arithmetic mean.

### When is F1 preferred?

When both False Positives and False Negatives matter, especially on
imbalanced datasets.

### Can F1 be high if Recall is very low?

No. The harmonic mean drops sharply if either Precision or Recall is
poor.

------------------------------------------------------------------------

# 16. Summary

You learned:

-   What F1-Score is.
-   Harmonic Mean intuition.
-   Formula.
-   Comparison with other metrics.
-   Macro, Micro, and Weighted F1.
-   Python implementation.

------------------------------------------------------------------------

# 17. What's Next?

**Lesson 107 -- ROC Curve**

You'll learn how ROC Curves evaluate classifiers across different
thresholds, understand True Positive Rate and False Positive Rate, and
visualize the trade-off between sensitivity and specificity.
