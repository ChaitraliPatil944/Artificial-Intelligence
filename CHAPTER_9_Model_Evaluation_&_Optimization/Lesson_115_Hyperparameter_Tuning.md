# Chapter 8 -- Model Evaluation & Optimization

# Lesson 115 -- Hyperparameter Tuning

> **Hyperparameter Tuning is the process of selecting the best values
> for a model's hyperparameters before or during training to maximize
> its performance on unseen data. Well-chosen hyperparameters can
> dramatically improve accuracy, generalization, and training
> efficiency.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand parameters vs hyperparameters.
-   Learn why hyperparameter tuning is important.
-   Identify common hyperparameters for popular ML algorithms.
-   Learn manual tuning strategies.
-   Prepare for Grid Search, Random Search, and Bayesian Optimization.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Hyperparameter Tuning?
2.  Parameters vs Hyperparameters
3.  Why Hyperparameter Tuning?
4.  Common Hyperparameters
5.  Manual Tuning
6.  Search Space
7.  Validation-Based Tuning
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Hyperparameter Tuning?

Hyperparameter tuning is the process of choosing the **best
configuration** for a machine learning model.

``` text
Model
  │
Choose Hyperparameters
  │
Train
  │
Evaluate
  │
Best Model
```

Unlike model parameters, hyperparameters are set **before training
begins**.

------------------------------------------------------------------------

# 2. Parameters vs Hyperparameters

  Parameters                Hyperparameters
  ------------------------- ------------------------
  Learned during training   Chosen before training
  Updated by optimization   Controlled by the user
  Example: weights          Example: learning rate

Examples:

### Parameters

-   Neural network weights
-   Linear regression coefficients

### Hyperparameters

-   Learning rate
-   Number of trees
-   Maximum tree depth
-   K in KNN
-   Batch size
-   Number of epochs

------------------------------------------------------------------------

# 3. Why Hyperparameter Tuning?

Poor hyperparameters may cause:

-   Underfitting
-   Overfitting
-   Slow training
-   Poor generalization

Good hyperparameters improve model performance.

------------------------------------------------------------------------

# 4. Common Hyperparameters

### Decision Tree

-   max_depth
-   min_samples_split
-   criterion

### Random Forest

-   n_estimators
-   max_depth
-   max_features

### KNN

-   n_neighbors
-   distance metric

### SVM

-   C
-   gamma
-   kernel

### XGBoost

-   learning_rate
-   max_depth
-   subsample
-   n_estimators

### Neural Networks

-   Learning rate
-   Epochs
-   Batch size
-   Number of layers
-   Number of neurons
-   Optimizer

------------------------------------------------------------------------

# 5. Manual Tuning

Example:

``` text
Train

↓

Accuracy = 82%

↓

Increase max_depth

↓

Accuracy = 88%
```

Manual tuning is simple but becomes inefficient as the number of
hyperparameters grows.

------------------------------------------------------------------------

# 6. Search Space

Example:

``` text
Learning Rate

0.1
0.01
0.001
```

``` text
Tree Depth

3
5
7
9
```

Every possible combination forms the search space.

------------------------------------------------------------------------

# 7. Validation-Based Tuning

Typical workflow:

``` text
Training Data
      │
Train Model
      │
Validation Data
      │
Adjust Hyperparameters
      │
Repeat
```

Cross Validation is commonly used for more reliable tuning.

------------------------------------------------------------------------

# 8. Common Mistakes

-   Tuning on the test set.
-   Ignoring Cross Validation.
-   Using an unnecessarily large search space.
-   Optimizing only one metric.
-   Forgetting random seeds for reproducibility.

------------------------------------------------------------------------

# 9. Python Example

``` python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=200,
    max_depth=10,
    random_state=42
)

model.fit(X_train, y_train)
```

These values are hyperparameters chosen before training.

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a Random Forest.
2.  Change `n_estimators`.
3.  Change `max_depth`.
4.  Compare validation accuracy.
5.  Identify the best configuration.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a hyperparameter?

A value chosen before training that controls how the model learns.

### Difference between parameters and hyperparameters?

Parameters are learned during training, while hyperparameters are
selected beforehand.

### Why tune hyperparameters?

To improve generalization and model performance.

### Give examples of hyperparameters.

-   Learning rate
-   Batch size
-   Epochs
-   Tree depth
-   Number of neighbors

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Parameters vs Hyperparameters.
-   Common hyperparameters.
-   Manual tuning.
-   Search space.
-   Validation-based tuning.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 116 -- Grid Search**

You'll learn how Grid Search systematically evaluates every
hyperparameter combination, understand exhaustive search, Cross
Validation integration, computational complexity, and when Grid Search
is appropriate.
