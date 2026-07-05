# Chapter 8 -- Model Evaluation & Optimization

# Lesson 111 -- Bias vs Variance

> **The Bias--Variance Trade-off is one of the most fundamental concepts
> in Machine Learning. It explains why some models are too simple to
> learn useful patterns while others memorize the training data and fail
> on new data. The goal of every ML practitioner is to find the balance
> between these two extremes.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Bias and Variance.
-   Learn why the trade-off exists.
-   Understand Underfitting and Overfitting.
-   Learn how model complexity affects performance.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Bias?
2.  What is Variance?
3.  Why the Trade-off Exists
4.  Underfitting vs Overfitting
5.  Error Decomposition
6.  Learning Curves
7.  Reducing Bias
8.  Reducing Variance
9.  Practical Examples
10. Python Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Bias?

Bias is the error caused by **overly simple assumptions**.

``` text
Simple Model
     │
Cannot Learn Pattern
     │
High Bias
```

Characteristics:

-   Too simple
-   Misses important relationships
-   Poor performance on training and test data

------------------------------------------------------------------------

# 2. What is Variance?

Variance measures how much a model changes when trained on different
datasets.

``` text
Complex Model
      │
Memorizes Training Data
      │
High Variance
```

Characteristics:

-   Very complex
-   Excellent training accuracy
-   Poor test accuracy

------------------------------------------------------------------------

# 3. Why the Trade-off Exists

As model complexity increases:

``` text
Bias
High  \
       \
        \
         \
          \____

Variance
      ____/
     /
    /
___/

Model Complexity →
```

Reducing Bias usually increases Variance, and reducing Variance usually
increases Bias.

------------------------------------------------------------------------

# 4. Underfitting vs Overfitting

  Underfitting             Overfitting
  ------------------------ -----------------------------
  High Bias                High Variance
  Simple model             Complex model
  Poor training accuracy   Excellent training accuracy
  Poor testing accuracy    Poor testing accuracy

------------------------------------------------------------------------

# 5. Error Decomposition

Prediction Error can be viewed as:

``` text
Total Error

=

Bias²
+
Variance
+
Irreducible Noise
```

-   **Bias²**: Error from simplifying assumptions.
-   **Variance**: Error from sensitivity to training data.
-   **Noise**: Random variation that no model can eliminate.

------------------------------------------------------------------------

# 6. Learning Curves

``` text
Error ↑

Training Error
\
 \
  \____

Validation Error
 \____
      \
       \

Samples →
```

Learning curves help diagnose:

-   Underfitting
-   Overfitting
-   Need for more data

------------------------------------------------------------------------

# 7. Reducing Bias

-   Increase model complexity.
-   Add more informative features.
-   Train longer.
-   Reduce regularization.

------------------------------------------------------------------------

# 8. Reducing Variance

-   Collect more data.
-   Use regularization.
-   Reduce model complexity.
-   Apply Cross Validation.
-   Use Ensemble methods.

------------------------------------------------------------------------

# 9. Practical Examples

## High Bias

``` text
Straight Line

×

Curved Data
```

The model is too simple.

## High Variance

``` text
Curve

Follows Every Point

~~~~~~~~~~~~~~
```

The model memorizes noise.

------------------------------------------------------------------------

# 10. Python Example

``` python
from sklearn.model_selection import learning_curve
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier()

train_sizes, train_scores, test_scores = learning_curve(
    model,
    X,
    y,
    cv=5
)
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Train a shallow Decision Tree.
2.  Train a very deep Decision Tree.
3.  Compare training and testing accuracy.
4.  Explain Bias and Variance.
5.  Apply pruning and compare results.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Bias?

Error caused by overly simple assumptions.

### What is Variance?

Sensitivity of a model to changes in training data.

### What is the Bias--Variance Trade-off?

Balancing model simplicity and complexity to achieve the best
generalization.

### Can a model have both high Bias and high Variance?

Yes, although many practical models mainly suffer from one more than the
other.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Bias
-   Variance
-   Trade-off
-   Error decomposition
-   Learning curves
-   How to reduce Bias and Variance

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 112 -- Underfitting**

You'll explore underfitting in depth, learn how to recognize it from
learning curves, understand its causes, and discover practical
techniques to fix it.
