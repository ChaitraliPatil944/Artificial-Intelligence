# Chapter 8 -- Model Evaluation & Optimization

# Lesson 112 -- Underfitting

> **Underfitting occurs when a machine learning model is too simple to
> learn the underlying patterns in the data. Such models perform poorly
> on both the training data and unseen test data because they fail to
> capture the true relationships.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Underfitting.
-   Learn why it occurs.
-   Identify High Bias models.
-   Read learning curves.
-   Learn practical techniques to fix Underfitting.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Underfitting?
2.  Why Underfitting Happens
3.  Characteristics
4.  High Bias Relationship
5.  Learning Curves
6.  Causes
7.  Detecting Underfitting
8.  Fixing Underfitting
9.  Practical Examples
10. Python Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Underfitting?

Underfitting means the model cannot learn the important patterns.

``` text
Complex Pattern

~~~~~~~~~~~~

Simple Model

----------
```

The model is **too simple**.

------------------------------------------------------------------------

# 2. Why Underfitting Happens

Typical reasons:

-   Model is too simple.
-   Important features are missing.
-   Training stopped too early.
-   Excessive regularization.
-   Insufficient feature engineering.

------------------------------------------------------------------------

# 3. Characteristics

-   High training error.
-   High validation error.
-   Poor predictions.
-   High Bias.
-   Low Variance.

------------------------------------------------------------------------

# 4. Relationship with Bias

``` text
Simple Model
      │
High Bias
      │
Underfitting
```

The model makes overly simplistic assumptions.

------------------------------------------------------------------------

# 5. Learning Curves

``` text
Error ↑

Training  ---------

Validation ---------

Samples →
```

Both errors remain high and close together.

This is the classic sign of Underfitting.

------------------------------------------------------------------------

# 6. Common Causes

-   Linear model for non-linear data.
-   Too few training epochs.
-   Very shallow decision trees.
-   Strong L1/L2 regularization.
-   Poor feature representation.

------------------------------------------------------------------------

# 7. Detecting Underfitting

Signs include:

-   Low training accuracy.
-   Low testing accuracy.
-   Similar training and validation errors.
-   Poor performance even after more data.

------------------------------------------------------------------------

# 8. How to Fix Underfitting

-   Increase model complexity.
-   Add informative features.
-   Reduce regularization.
-   Train longer.
-   Use non-linear algorithms.
-   Improve feature engineering.

``` text
Too Simple
     │
Increase Complexity
     │
Better Fit
```

------------------------------------------------------------------------

# 9. Practical Examples

### Example 1

Predicting curved data with a straight line.

``` text
Curved Data

~~~~~~~

Linear Model

---------
```

### Example 2

Using a Decision Tree with `max_depth = 1`.

The tree cannot capture meaningful patterns.

------------------------------------------------------------------------

# 10. Python Example

``` python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(max_depth=1)

model.fit(X_train, y_train)

print(model.score(X_train, y_train))
print(model.score(X_test, y_test))
```

If both scores are low, the model is likely underfitting.

------------------------------------------------------------------------

# 11. Mini Project

1.  Train a shallow Decision Tree.
2.  Measure training accuracy.
3.  Measure testing accuracy.
4.  Increase `max_depth`.
5.  Compare the results.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Underfitting?

A model that is too simple to learn the data.

### Which error is high?

Both training and testing errors.

### Is Underfitting related to Bias or Variance?

High Bias.

### How can you reduce Underfitting?

Increase model complexity, improve features, reduce regularization, or
train longer.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   What Underfitting is.
-   Why it occurs.
-   Learning curve interpretation.
-   High Bias relationship.
-   Practical solutions.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 113 -- Overfitting**

You'll learn why models sometimes memorize the training data, how to
recognize High Variance, interpret learning curves, and apply techniques
like regularization, pruning, and dropout to improve generalization.
