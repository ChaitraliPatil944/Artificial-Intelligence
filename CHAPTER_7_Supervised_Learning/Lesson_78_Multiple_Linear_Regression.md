
# Chapter 6 – Supervised Learning

# Lesson 78 – Multiple Linear Regression

> **Most real-world problems depend on more than one factor. Multiple Linear Regression extends Linear Regression by learning the relationship between several input features and one continuous target variable.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand Multiple Linear Regression.
- Learn why it was developed.
- Understand the multivariable regression equation.
- Interpret regression coefficients.
- Learn about multicollinearity.
- Build a Multiple Linear Regression model using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Multiple Linear Regression?
2. Why Multiple Linear Regression?
3. History
4. Regression Equation
5. Key Terminology
6. How It Works
7. Coefficient Interpretation
8. Assumptions
9. Multicollinearity
10. Model Evaluation
11. Python Implementation
12. Advantages
13. Limitations
14. Real-World Applications
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

---

# 1. What is Multiple Linear Regression?

Multiple Linear Regression (MLR) predicts a **continuous numerical value** using **multiple input features**.

Instead of:

```
House Price = f(Area)
```

MLR learns:

```
House Price = f(Area, Bedrooms, Age, Location, Parking)
```

---

# 2. Why Multiple Linear Regression?

Most real-world outcomes depend on several variables.

Example:

House Price depends on:

- Area
- Number of Bedrooms
- Location
- Age of Property
- Nearby Facilities

Using only one feature often produces poor predictions.

---

# 3. History

Multiple Linear Regression evolved from Linear Regression as statisticians realized many problems involve several explanatory variables.

Today it is widely used in:

- Economics
- Finance
- Healthcare
- Marketing
- Engineering
- AI

---

# 4. Regression Equation

For one feature:

```
y = mx + c
```

For multiple features:

```
y = b₀ + b₁x₁ + b₂x₂ + ... + bₙxₙ
```

Where:

- y = Prediction
- b₀ = Intercept
- b₁...bₙ = Coefficients
- x₁...xₙ = Features

Example:

```
Price = 500000
      + 3000 × Area
      + 150000 × Bedrooms
      - 2500 × Age
```

---

# 5. Key Terminology

### Features (X)

Independent variables.

Examples:

- Area
- Bedrooms
- Age
- Income

### Target (y)

Value to predict.

Example:

- House Price

### Coefficient

Shows how much the prediction changes when one feature increases by one unit while other features remain constant.

---

# 6. How It Works

```
Training Data

Area
Bedrooms
Age

        │

Find Best Coefficients

        │

Regression Equation

        │

Predict Price
```

The model estimates the contribution of every feature.

---

# 7. Coefficient Interpretation

Example:

```
Price = 200000
      + 3500 × Area
      + 100000 × Bedrooms
```

Interpretation:

- Every additional square foot increases price by approximately ₹3,500.
- Every extra bedroom increases price by approximately ₹1,00,000.

This interpretation assumes all other features stay constant.

---

# 8. Assumptions

Multiple Linear Regression assumes:

- Linear relationship
- Independent observations
- Homoscedasticity
- Normally distributed residuals
- No strong multicollinearity
- Minimal influential outliers

---

# 9. Multicollinearity

Multicollinearity occurs when two or more features are highly correlated.

Example:

```
House Area

↓

Number of Rooms
```

Both may contain nearly identical information.

Problems:

- Unstable coefficients
- Difficult interpretation
- Reduced reliability

Detection methods:

- Correlation Matrix
- Variance Inflation Factor (VIF)

ASCII

```
Area  ─────────┐
               │ Strong Correlation
Rooms ─────────┘
```

---

# 10. Model Evaluation

Common metrics:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score
- Adjusted R²

Why Adjusted R²?

Adding useless features usually increases R² slightly.

Adjusted R² penalizes unnecessary features.

---

# 11. Python Implementation

```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

X = df[["Area", "Bedrooms", "Age"]]
y = df["Price"]

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)

print(model.coef_)
print(model.intercept_)
```

---

# 12. Advantages

- Uses multiple sources of information.
- More realistic than single-feature regression.
- Easy to interpret.
- Fast to train.
- Strong statistical foundation.

---

# 13. Limitations

- Assumes linear relationships.
- Sensitive to multicollinearity.
- Sensitive to outliers.
- Requires careful feature selection.

---

# 14. Real-World Applications

Real Estate

```
Area
Bedrooms
Age
Location

↓

House Price
```

Banking

```
Income
Credit Score
Existing Loans

↓

Loan Amount
```

Healthcare

```
Age
Weight
Blood Pressure

↓

Treatment Cost
```

Marketing

```
Advertising Budget
Season
Discount

↓

Sales Forecast
```

---

# 15. Mini Project

Build a house price prediction model.

Tasks:

1. Load a housing dataset.
2. Select multiple numerical features.
3. Train a Multiple Linear Regression model.
4. Print coefficients.
5. Evaluate using MAE, RMSE, and R².
6. Interpret each coefficient.

---

# 16. Interview Questions

### What is Multiple Linear Regression?

A regression algorithm that predicts a continuous value using multiple input features.

### What is the regression equation?

```
y = b₀ + b₁x₁ + b₂x₂ + ... + bₙxₙ
```

### What does a coefficient represent?

The expected change in the prediction when a feature increases by one unit while other features remain constant.

### What is multicollinearity?

A situation where independent variables are highly correlated.

### Why use Adjusted R²?

It penalizes adding irrelevant features and provides a fairer evaluation.

---

# 17. Summary

You learned:

- What Multiple Linear Regression is.
- Why multiple features improve predictions.
- Regression equation.
- Coefficient interpretation.
- Model assumptions.
- Multicollinearity.
- Evaluation metrics.
- Python implementation.

---

# 18. What's Next?

**Lesson 79 – Polynomial Regression**

You'll learn how regression models can capture curved relationships, why straight lines are sometimes insufficient, how polynomial features work, and when Polynomial Regression should be preferred over Linear Regression.
