# Chapter 8 -- Model Evaluation & Optimization

# Lesson 109 -- Regression Metrics

> **Classification metrics tell us whether a prediction belongs to the
> correct class. Regression metrics tell us *how far* a prediction is
> from the actual value. Since regression predicts continuous values, we
> evaluate the magnitude of prediction errors rather than counting
> correct or incorrect predictions.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand why regression needs different evaluation metrics.
-   Learn MAE, MSE, RMSE, MAPE, R² Score, and Adjusted R².
-   Understand residuals and prediction errors.
-   Learn when each metric should be used.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  Why Regression Metrics?
2.  Prediction Error
3.  Residuals
4.  Mean Absolute Error (MAE)
5.  Mean Squared Error (MSE)
6.  Root Mean Squared Error (RMSE)
7.  Mean Absolute Percentage Error (MAPE)
8.  R² Score
9.  Adjusted R²
10. Comparison Table
11. Python Implementation
12. Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. Why Regression Metrics?

Classification:

``` text
Cat

Correct / Wrong
```

Regression:

``` text
Predicted House Price

₹49,50,000

Actual

₹50,00,000
```

The prediction is close, but not exactly correct.

We measure **how large the error is**.

------------------------------------------------------------------------

# 2. Prediction Error

``` text
Error

=

Actual − Predicted
```

Example:

``` text
Actual = 100

Predicted = 92

Error = 8
```

------------------------------------------------------------------------

# 3. Residuals

A residual is the prediction error for one observation.

``` text
Actual
  ●
  │
  │
  × Prediction

Residual
```

Residual plots help identify systematic errors.

------------------------------------------------------------------------

# 4. Mean Absolute Error (MAE)

Formula:

``` text
MAE = Average(|Actual − Predicted|)
```

Characteristics:

-   Easy to understand.
-   Every error is treated equally.
-   Less sensitive to outliers.

------------------------------------------------------------------------

# 5. Mean Squared Error (MSE)

Formula:

``` text
MSE = Average((Actual − Predicted)²)
```

Characteristics:

-   Squares every error.
-   Penalizes large errors heavily.
-   Smooth for optimization.

------------------------------------------------------------------------

# 6. Root Mean Squared Error (RMSE)

Formula:

``` text
RMSE = √MSE
```

Advantages:

-   Same units as target variable.
-   Easier to interpret than MSE.
-   Penalizes large errors.

------------------------------------------------------------------------

# 7. Mean Absolute Percentage Error (MAPE)

Formula:

``` text
MAPE

=

Average(
|Actual - Predicted|
-------------------
Actual
)
×100%
```

Useful when expressing error as a percentage.

Limitation:

Not suitable when actual values are zero.

------------------------------------------------------------------------

# 8. R² Score

Also called the **Coefficient of Determination**.

Measures how much variance the model explains.

Range:

``` text
1.0 → Perfect

0.0 → Same as predicting the mean

<0 → Worse than predicting the mean
```

Higher is better.

------------------------------------------------------------------------

# 9. Adjusted R²

Adjusted R² penalizes unnecessary features.

Unlike R², it does not always increase when more features are added.

Useful in Multiple Linear Regression.

------------------------------------------------------------------------

# 10. Comparison Table

  Metric        Lower / Higher Better   Sensitive to Outliers
  ------------- ----------------------- -----------------------
  MAE           Lower                   Low
  MSE           Lower                   High
  RMSE          Lower                   High
  MAPE          Lower                   Moderate
  R²            Higher                  Indirectly
  Adjusted R²   Higher                  Indirectly

------------------------------------------------------------------------

# 11. Python Implementation

``` python
from sklearn.metrics import (
    mean_absolute_error,
    mean_squared_error,
    r2_score
)

mae = mean_absolute_error(y_true, y_pred)

mse = mean_squared_error(y_true, y_pred)

rmse = mean_squared_error(
    y_true,
    y_pred,
    squared=False
)

r2 = r2_score(y_true, y_pred)
```

------------------------------------------------------------------------

# 12. Applications

-   House price prediction
-   Stock price forecasting
-   Weather prediction
-   Sales forecasting
-   Energy demand estimation

------------------------------------------------------------------------

# 13. Mini Project

1.  Train a Linear Regression model.
2.  Predict test values.
3.  Compute MAE, MSE, RMSE, and R².
4.  Compare the metrics.
5.  Explain which metric is most suitable.

------------------------------------------------------------------------

# 14. Interview Questions

### Why can't Accuracy evaluate regression?

Because regression predicts continuous values instead of discrete
classes.

### Difference between MAE and RMSE?

RMSE penalizes large errors more strongly.

### What does R² measure?

The proportion of variance explained by the model.

### When use Adjusted R²?

When comparing regression models with different numbers of features.

------------------------------------------------------------------------

# 15. Summary

You learned:

-   Prediction error.
-   Residuals.
-   MAE, MSE, RMSE.
-   MAPE.
-   R² and Adjusted R².
-   Python implementation.

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 110 -- Cross Validation**

You'll learn why a single train-test split can be misleading, understand
K-Fold, Stratified K-Fold, Leave-One-Out Cross Validation (LOOCV), and
how cross-validation produces more reliable estimates of model
performance.
