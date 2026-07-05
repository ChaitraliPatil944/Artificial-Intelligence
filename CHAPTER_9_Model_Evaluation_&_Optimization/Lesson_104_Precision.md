# Chapter 8 -- Model Evaluation & Optimization

# Lesson 104 -- Precision

> **Precision answers one simple but critical question: *Whenever the
> model predicts Positive, how often is it actually correct?* It is one
> of the most important evaluation metrics for classification problems
> where False Positives are expensive.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Precision is.
-   Learn how Precision is calculated.
-   Understand its relationship with the Confusion Matrix.
-   Learn when Precision is more important than Accuracy.
-   Compare Precision with Recall.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is Precision?
2.  Why Precision was Introduced
3.  Precision Formula
4.  Precision from the Confusion Matrix
5.  Intuition
6.  When Precision Matters
7.  Precision vs Accuracy
8.  Precision vs Recall
9.  Advantages
10. Limitations
11. Python Implementation
12. Real-World Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. What is Precision?

Precision measures the percentage of **predicted positive cases that are
actually positive**.

``` text
Predicted Positive
        │
How many were correct?
```

------------------------------------------------------------------------

# 2. Why Precision was Introduced

Accuracy treats every mistake equally.

Precision focuses only on **positive predictions**, making it useful
when false alarms are costly.

Example:

``` text
Email marked as Spam

↓

Was it really Spam?
```

------------------------------------------------------------------------

# 3. Precision Formula

``` text
          TP
Precision = --------
          TP + FP
```

Where:

-   TP = True Positives
-   FP = False Positives

------------------------------------------------------------------------

# 4. Precision from the Confusion Matrix

``` text
                    Actual
               Positive   Negative

Pred Positive      45         5

Pred Negative      10        40
```

``` text
Precision

= 45 / (45 + 5)

= 90%
```

Meaning:

Out of every 100 positive predictions, about 90 are correct.

------------------------------------------------------------------------

# 5. Intuition

Imagine a metal detector.

``` text
Alarm Rings
      │
Was there actually metal?
```

Precision measures how trustworthy the alarm is.

High Precision:

-   Few false alarms.

Low Precision:

-   Many false alarms.

------------------------------------------------------------------------

# 6. When Precision Matters

Choose Precision when **False Positives are expensive**.

Examples:

-   Spam filtering
-   Fraud alerts
-   Fake news detection
-   Search engine recommendations

------------------------------------------------------------------------

# 7. Precision vs Accuracy

  Accuracy                   Precision
  -------------------------- ----------------------------------------
  Measures all predictions   Measures only predicted positives
  Can hide class imbalance   Focuses on positive prediction quality

------------------------------------------------------------------------

# 8. Precision vs Recall

``` text
Precision

How correct were positive predictions?

Recall

How many actual positives were found?
```

High Precision:

-   Few False Positives.

High Recall:

-   Few False Negatives.

Often improving one reduces the other.

------------------------------------------------------------------------

# 9. Advantages

-   Excellent when false positives matter.
-   Easy to interpret.
-   Useful for imbalanced datasets.

------------------------------------------------------------------------

# 10. Limitations

-   Ignores False Negatives.
-   Should not be used alone.
-   Often balanced with Recall using the F1-score.

------------------------------------------------------------------------

# 11. Python Implementation

``` python
from sklearn.metrics import precision_score

precision = precision_score(y_true, y_pred)

print(precision)
```

------------------------------------------------------------------------

# 12. Real-World Applications

-   Spam filtering
-   Fraud detection
-   Search ranking
-   Recommendation systems
-   Malware detection

------------------------------------------------------------------------

# 13. Mini Project

1.  Train a classifier.
2.  Generate a confusion matrix.
3.  Compute Precision.
4.  Compare Accuracy and Precision.
5.  Explain which metric better reflects your problem.

------------------------------------------------------------------------

# 14. Interview Questions

### What is Precision?

The proportion of predicted positive samples that are actually positive.

### Formula?

``` text
TP / (TP + FP)
```

### When is Precision important?

When False Positives are costly.

### Can a model have high Accuracy but low Precision?

Yes, especially with imbalanced datasets.

------------------------------------------------------------------------

# 15. Summary

You learned:

-   What Precision is.
-   How it is calculated.
-   Why it matters.
-   When to prioritize it.
-   Python implementation.

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 105 -- Recall**

You'll learn how Recall measures the ability of a model to find all
positive cases, why it is critical in healthcare and fraud detection,
and how it complements Precision.
