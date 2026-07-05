# Chapter 8 -- Model Evaluation & Optimization

# Lesson 103 -- Accuracy

> **Accuracy is the simplest and most widely recognized evaluation
> metric for classification models. It measures the percentage of
> predictions a model gets correct. While easy to understand, it can
> also be one of the most misleading metrics when used without
> context.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Accuracy is.
-   Learn how Accuracy is calculated.
-   Understand its relationship with the Confusion Matrix.
-   Learn when Accuracy is useful and when it fails.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is Accuracy?
2.  Why Accuracy was Introduced
3.  Accuracy Formula
4.  Accuracy from the Confusion Matrix
5.  Binary vs Multi-Class Accuracy
6.  When Accuracy Works Well
7.  When Accuracy Fails
8.  Advantages
9.  Limitations
10. Python Implementation
11. Real-World Applications
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

------------------------------------------------------------------------

# 1. What is Accuracy?

Accuracy measures the proportion of correct predictions made by a model.

``` text
Correct Predictions
-------------------
Total Predictions
```

Example:

``` text
100 Predictions

95 Correct

Accuracy = 95%
```

------------------------------------------------------------------------

# 2. Why Accuracy was Introduced

It provides a quick, intuitive measure of performance.

If a model predicts most samples correctly, its accuracy is high.

However, this assumes all mistakes are equally important.

------------------------------------------------------------------------

# 3. Accuracy Formula

``` text
Accuracy

= (TP + TN)
------------
TP + TN + FP + FN
```

Where:

-   TP = True Positives
-   TN = True Negatives
-   FP = False Positives
-   FN = False Negatives

------------------------------------------------------------------------

# 4. Accuracy from the Confusion Matrix

``` text
                    Actual
               Positive   Negative

Pred Positive      40         10
Pred Negative       5         45
```

Correct predictions:

``` text
TP + TN = 40 + 45 = 85
```

Total predictions:

``` text
40 + 10 + 5 + 45 = 100
```

Accuracy:

``` text
85 / 100 = 85%
```

------------------------------------------------------------------------

# 5. Binary vs Multi-Class Accuracy

Binary Classification:

``` text
Spam

vs

Not Spam
```

Multi-Class Classification:

``` text
Cat
Dog
Horse
Bird
```

The same formula applies. We simply count how many predictions are
correct.

------------------------------------------------------------------------

# 6. When Accuracy Works Well

Accuracy is appropriate when:

-   Classes are balanced.
-   All errors have similar consequences.

Examples:

-   Handwritten digit recognition
-   Product category prediction
-   Document classification with balanced classes

------------------------------------------------------------------------

# 7. When Accuracy Fails

Consider fraud detection.

``` text
10,000 Transactions

9,900 Normal
100 Fraud
```

Model predicts:

``` text
Everything = Normal
```

Accuracy:

``` text
9,900 / 10,000 = 99%
```

Frauds detected:

``` text
0
```

The model appears excellent but is actually useless.

This is why we also use:

-   Precision
-   Recall
-   F1-Score

------------------------------------------------------------------------

# 8. Advantages

-   Easy to understand.
-   Simple to calculate.
-   Good for balanced datasets.
-   Useful as a baseline metric.

------------------------------------------------------------------------

# 9. Limitations

-   Misleading for imbalanced datasets.
-   Doesn't distinguish between FP and FN.
-   Ignores the cost of different errors.

------------------------------------------------------------------------

# 10. Python Implementation

``` python
from sklearn.metrics import accuracy_score

acc = accuracy_score(y_true, y_pred)

print(acc)
```

Using a classifier:

``` python
print(model.score(X_test, y_test))
```

------------------------------------------------------------------------

# 11. Real-World Applications

Suitable for:

-   Balanced image classification
-   OCR
-   Basic document classification

Not sufficient alone for:

-   Cancer detection
-   Fraud detection
-   Intrusion detection

------------------------------------------------------------------------

# 12. Mini Project

1.  Train a Decision Tree classifier.
2.  Predict the test set.
3.  Compute accuracy.
4.  Generate the confusion matrix.
5.  Explain why accuracy alone may not tell the whole story.

------------------------------------------------------------------------

# 13. Interview Questions

### What is Accuracy?

The percentage of correct predictions.

### What is the formula?

``` text
(TP + TN) / (TP + TN + FP + FN)
```

### Is high accuracy always good?

No. It can be misleading on imbalanced datasets.

### Which metric should accompany Accuracy?

-   Precision
-   Recall
-   F1-Score
-   ROC-AUC

------------------------------------------------------------------------

# 14. Summary

You learned:

-   What Accuracy is.
-   How it is calculated.
-   Its strengths and weaknesses.
-   Why class imbalance makes it unreliable.
-   Python implementation.

------------------------------------------------------------------------

# 15. What's Next?

**Lesson 104 -- Precision**

You'll learn why correctly predicting positive cases matters, how
Precision is calculated, where it is most useful, and why spam filters
and fraud detection systems often optimize Precision instead of
Accuracy.
