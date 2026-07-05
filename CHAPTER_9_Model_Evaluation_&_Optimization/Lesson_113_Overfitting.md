# Chapter 8 -- Model Evaluation & Optimization

# Lesson 113 -- Overfitting

> **Overfitting occurs when a machine learning model learns not only the
> real patterns in the training data but also the random noise. As a
> result, it performs extremely well on the training dataset but poorly
> on unseen data. High Variance is the hallmark of an overfitted
> model.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Overfitting.
-   Learn why it happens.
-   Understand High Variance.
-   Interpret learning curves.
-   Learn techniques to prevent Overfitting.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Overfitting?
2.  Why Overfitting Happens
3.  Characteristics
4.  High Variance Relationship
5.  Learning Curves
6.  Common Causes
7.  Detecting Overfitting
8.  Preventing Overfitting
9.  Practical Examples
10. Python Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Overfitting?

An overfitted model memorizes the training data instead of learning
general patterns.

``` text
Training Data
      │
Memorization
      │
Poor Generalization
```

The model performs well during training but struggles with new data.

------------------------------------------------------------------------

# 2. Why Overfitting Happens

Common reasons include:

-   Model is too complex.
-   Too many features.
-   Small training dataset.
-   Training for too many epochs.
-   Noise in the data.

------------------------------------------------------------------------

# 3. Characteristics

-   Very high training accuracy.
-   Low testing accuracy.
-   Large gap between training and validation performance.
-   High Variance.

------------------------------------------------------------------------

# 4. Relationship with Variance

``` text
Complex Model
      │
High Variance
      │
Overfitting
```

Small changes in training data may produce large changes in the model.

------------------------------------------------------------------------

# 5. Learning Curves

``` text
Error ↑

Validation
    \______
           \
            \

Training
\
 \
  \________

Samples →
```

Training error stays very low while validation error remains much
higher.

------------------------------------------------------------------------

# 6. Common Causes

-   Deep decision trees.
-   Very large neural networks.
-   Insufficient training data.
-   Weak regularization.
-   Excessive training.

------------------------------------------------------------------------

# 7. Detecting Overfitting

Typical signs:

-   Excellent training performance.
-   Poor validation performance.
-   Large train-test accuracy gap.
-   Unstable predictions on unseen data.

------------------------------------------------------------------------

# 8. Preventing Overfitting

### Regularization

Penalize overly complex models.

### Pruning

Reduce unnecessary tree branches.

### Early Stopping

Stop training before memorization begins.

### Dropout

Randomly disable neurons during neural network training.

### Data Augmentation

Generate more training examples.

### Cross Validation

Estimate generalization more reliably.

``` text
Too Complex
     │
Simplify / Regularize
     │
Better Generalization
```

------------------------------------------------------------------------

# 9. Practical Examples

### Example 1

A polynomial curve passing through every training point.

``` text
Data

*   *  *

Curve

~~~~~~~~~~~~
```

The curve captures noise instead of the true relationship.

### Example 2

A Decision Tree with no depth limit.

It memorizes every training sample.

------------------------------------------------------------------------

# 10. Python Example

``` python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(max_depth=None)

model.fit(X_train, y_train)

print("Train:", model.score(X_train, y_train))
print("Test :", model.score(X_test, y_test))
```

A large gap between training and testing accuracy indicates possible
overfitting.

------------------------------------------------------------------------

# 11. Mini Project

1.  Train a deep Decision Tree.
2.  Measure training and testing accuracy.
3.  Apply `max_depth`.
4.  Compare performance.
5.  Explain how pruning improves generalization.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Overfitting?

When a model memorizes training data instead of learning general
patterns.

### Is Overfitting related to Bias or Variance?

High Variance.

### How do you detect Overfitting?

High training performance but poor validation or test performance.

### Name techniques to reduce Overfitting.

-   Regularization
-   Pruning
-   Early Stopping
-   Dropout
-   Data Augmentation
-   Cross Validation

------------------------------------------------------------------------

# 13. Summary

You learned:

-   What Overfitting is.
-   Why it occurs.
-   Learning curve interpretation.
-   High Variance.
-   Practical prevention techniques.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 114 -- Regularization**

You'll learn how L1 (Lasso), L2 (Ridge), and Elastic Net regularization
reduce overfitting, control model complexity, and improve generalization
in machine learning models.
