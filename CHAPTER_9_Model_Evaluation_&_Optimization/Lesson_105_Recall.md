# Chapter 8 -- Model Evaluation & Optimization

# Lesson 105 -- Recall

> **Recall measures how many of the actual positive cases a model
> successfully identifies. It answers the question: *Of all the real
> positive cases, how many did the model find?* Recall is crucial when
> missing a positive case has serious consequences.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Recall is.
-   Learn why Recall is important.
-   Calculate Recall using the Confusion Matrix.
-   Compare Recall with Precision and Accuracy.
-   Learn real-world applications.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Recall?
2.  Why Recall was Introduced
3.  Recall Formula
4.  Recall from the Confusion Matrix
5.  Intuition
6.  When Recall Matters
7.  Recall vs Precision
8.  Recall vs Accuracy
9.  Advantages
10. Limitations
11. Python Implementation
12. Real-World Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. What is Recall?

Recall measures how many **actual positive** samples were correctly
identified.

``` text
Actual Positives
        │
How many were found?
```

------------------------------------------------------------------------

# 2. Why Recall was Introduced

Some problems are far more sensitive to **False Negatives** than False
Positives.

Example:

``` text
Cancer Patient

↓

Predicted Healthy ❌

↓

Treatment Delayed
```

In such situations, missing a positive case can be extremely costly.

------------------------------------------------------------------------

# 3. Recall Formula

``` text
        TP
Recall = ------
       TP + FN
```

Where:

-   TP = True Positives
-   FN = False Negatives

------------------------------------------------------------------------

# 4. Recall from the Confusion Matrix

``` text
                    Actual
               Positive   Negative

Pred Positive      45         5
Pred Negative      15        35
```

``` text
Recall

= 45 / (45 + 15)

= 75%
```

The model successfully found 75% of all actual positive cases.

------------------------------------------------------------------------

# 5. Intuition

Imagine airport security.

``` text
Dangerous Items
        │
How many were detected?
```

Recall measures how effective the screening process is at finding every
real threat.

High Recall:

-   Few missed positives.

Low Recall:

-   Many missed positives.

------------------------------------------------------------------------

# 6. When Recall Matters

Prioritize Recall when **False Negatives are expensive**.

Examples:

-   Cancer detection
-   Fraud detection
-   Credit card fraud
-   Network intrusion detection
-   Disease screening

------------------------------------------------------------------------

# 7. Recall vs Precision

  Recall                   Precision
  ------------------------ ----------------------------
  Finds actual positives   Trusts predicted positives
  Focuses on FN            Focuses on FP

Increasing Recall often decreases Precision, and vice versa.

------------------------------------------------------------------------

# 8. Recall vs Accuracy

Accuracy counts all correct predictions.

Recall looks only at the ability to identify positive cases.

A model may have high Accuracy but poor Recall on imbalanced datasets.

------------------------------------------------------------------------

# 9. Advantages

-   Detects as many positive cases as possible.
-   Excellent for safety-critical applications.
-   Useful on imbalanced datasets.

------------------------------------------------------------------------

# 10. Limitations

-   Ignores False Positives.
-   Should be interpreted alongside Precision.
-   High Recall alone does not guarantee a good model.

------------------------------------------------------------------------

# 11. Python Implementation

``` python
from sklearn.metrics import recall_score

recall = recall_score(y_true, y_pred)

print(recall)
```

------------------------------------------------------------------------

# 12. Real-World Applications

-   Medical diagnosis
-   Fraud detection
-   Spam detection
-   Face recognition
-   Security monitoring

------------------------------------------------------------------------

# 13. Mini Project

1.  Train a classifier.
2.  Generate predictions.
3.  Compute Recall.
4.  Compare Precision and Recall.
5.  Explain which metric matters more for your problem.

------------------------------------------------------------------------

# 14. Interview Questions

### What is Recall?

The proportion of actual positive samples correctly identified.

### Formula?

``` text
TP / (TP + FN)
```

### When is Recall more important than Precision?

When missing positive cases is costly.

### Can Recall be 100%?

Yes. If every actual positive case is detected, Recall equals 1.0
(100%).

------------------------------------------------------------------------

# 15. Summary

You learned:

-   What Recall is.
-   How it is calculated.
-   Why False Negatives matter.
-   Difference between Recall and Precision.
-   Python implementation.

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 106 -- F1-Score**

You'll learn how the F1-Score combines Precision and Recall into a
single metric, why it is widely used on imbalanced datasets, and when it
is preferred over Accuracy.
