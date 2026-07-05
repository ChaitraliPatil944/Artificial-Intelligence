# Chapter 8 -- Model Evaluation & Optimization

# Lesson 114 -- Regularization

> **Regularization is a technique used to reduce overfitting by
> discouraging a machine learning model from becoming unnecessarily
> complex. It works by adding a penalty to the model's cost function,
> encouraging simpler models that generalize better to unseen data.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Regularization.
-   Learn why it was invented.
-   Understand L1 (Lasso), L2 (Ridge), and Elastic Net.
-   Learn the role of λ (lambda).
-   Understand the Bias--Variance trade-off.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is Regularization?
2.  Why Regularization?
3.  Cost Function with Regularization
4.  L1 Regularization (Lasso)
5.  L2 Regularization (Ridge)
6.  Elastic Net
7.  Lambda (λ)
8.  Geometric Intuition
9.  Bias vs Variance
10. Regularization vs Dropout
11. Python Implementation
12. Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. What is Regularization?

Regularization penalizes large model weights to prevent overfitting.

``` text
Complex Model
      │
Penalty
      │
Simpler Model
```

The goal is **better generalization**, not perfect training accuracy.

------------------------------------------------------------------------

# 2. Why Regularization?

Without regularization:

-   Model memorizes noise.
-   High Variance.
-   Poor test performance.

With regularization:

-   Simpler model.
-   Better generalization.
-   Lower variance.

------------------------------------------------------------------------

# 3. Cost Function with Regularization

Original loss:

``` text
Loss
```

Regularized loss:

``` text
Loss + Penalty
```

General form:

``` text
Cost = Loss + λ × Penalty
```

Where:

-   **Loss** measures prediction error.
-   **Penalty** discourages large weights.
-   **λ (lambda)** controls penalty strength.

------------------------------------------------------------------------

# 4. L1 Regularization (Lasso)

Penalty:

``` text
|w₁| + |w₂| + ... + |wₙ|
```

Characteristics:

-   Produces sparse models.
-   Can reduce some weights exactly to zero.
-   Performs feature selection automatically.

Best when many features are irrelevant.

------------------------------------------------------------------------

# 5. L2 Regularization (Ridge)

Penalty:

``` text
w₁² + w₂² + ... + wₙ²
```

Characteristics:

-   Shrinks weights.
-   Rarely makes weights exactly zero.
-   Keeps all features.

Best when most features contribute useful information.

------------------------------------------------------------------------

# 6. Elastic Net

Elastic Net combines both penalties.

``` text
L1 + L2
```

Advantages:

-   Performs feature selection.
-   Handles correlated features well.
-   Balances Lasso and Ridge.

------------------------------------------------------------------------

# 7. Lambda (λ)

Lambda controls how strong the penalty is.

``` text
λ = 0

No Regularization
```

``` text
Large λ

Very Strong Penalty
```

Effects:

-   Small λ → More complex model.
-   Large λ → Simpler model.

Choosing λ is a hyperparameter tuning problem.

------------------------------------------------------------------------

# 8. Geometric Intuition

Imagine stretching a rubber band.

Without constraints, weights can grow very large.

Regularization pulls weights toward zero.

``` text
Large Weights

↓

Penalty

↓

Smaller Weights
```

------------------------------------------------------------------------

# 9. Bias vs Variance

Increasing regularization:

``` text
Bias ↑

Variance ↓
```

Too much regularization:

-   Underfitting.

Too little regularization:

-   Overfitting.

The goal is the right balance.

------------------------------------------------------------------------

# 10. Regularization vs Dropout

  Regularization              Dropout
  --------------------------- -------------------------------
  Works with many ML models   Mainly Neural Networks
  Penalizes weights           Randomly disables neurons
  Controls complexity         Prevents neuron co-adaptation

------------------------------------------------------------------------

# 11. Python Implementation

### Ridge Regression

``` python
from sklearn.linear_model import Ridge

model = Ridge(alpha=1.0)
```

### Lasso Regression

``` python
from sklearn.linear_model import Lasso

model = Lasso(alpha=0.1)
```

### Elastic Net

``` python
from sklearn.linear_model import ElasticNet

model = ElasticNet(alpha=0.1, l1_ratio=0.5)
```

------------------------------------------------------------------------

# 12. Applications

-   Linear Regression
-   Logistic Regression
-   Neural Networks
-   Financial forecasting
-   Medical prediction
-   Image classification

------------------------------------------------------------------------

# 13. Mini Project

1.  Train Linear Regression.
2.  Train Ridge Regression.
3.  Train Lasso Regression.
4.  Compare coefficients.
5.  Compare train/test performance.

------------------------------------------------------------------------

# 14. Interview Questions

### What is Regularization?

A technique that reduces overfitting by penalizing large model weights.

### Difference between L1 and L2?

-   L1 performs feature selection.
-   L2 shrinks weights but usually keeps all features.

### What does λ control?

The strength of the regularization penalty.

### What happens if λ is too large?

The model becomes too simple and may underfit.

------------------------------------------------------------------------

# 15. Summary

You learned:

-   Regularization fundamentals.
-   L1 (Lasso).
-   L2 (Ridge).
-   Elastic Net.
-   Lambda.
-   Bias--Variance effects.
-   Python implementation.

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 115 -- Hyperparameter Tuning**

You'll learn the difference between parameters and hyperparameters,
understand why tuning is critical, explore common hyperparameters for
popular algorithms, and prepare for Grid Search, Random Search, and
Bayesian Optimization.
