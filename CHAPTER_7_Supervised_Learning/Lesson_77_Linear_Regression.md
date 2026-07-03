
# Chapter 6 – Supervised Learning

# Lesson 77 – Linear Regression

> **Linear Regression is the foundation of predictive Machine Learning. It learns the best straight-line relationship between input variables and a numerical target, making it one of the first algorithms every AI engineer should master.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Linear Regression is.
- Learn its history and motivation.
- Understand the equation of a line.
- Learn how the best-fit line is found.
- Understand residuals, cost functions, and Ordinary Least Squares (OLS).
- Build your first Linear Regression model in Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is Linear Regression?
2. Why Linear Regression was Invented
3. History
4. Equation of a Line
5. Key Terminology
6. How Linear Regression Works
7. Best-Fit Line
8. Residuals and Error
9. Cost Function (MSE)
10. Ordinary Least Squares (OLS)
11. Assumptions
12. Python Implementation
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is Linear Regression?

Linear Regression is a supervised learning algorithm used to predict **continuous numerical values** by fitting the best possible straight line through data.

Examples:

- House Price
- Salary
- Sales
- Temperature

```
Data Points

*
   *
      *
         *

Best Fit Line

-------------------------
```

---

# 2. Why Linear Regression was Invented

Researchers wanted a mathematical way to describe relationships.

Examples:

- Does more experience increase salary?
- Does house size affect price?
- Do study hours improve marks?

Instead of guessing, Linear Regression measures these relationships mathematically.

---

# 3. History

Linear Regression has its roots in statistics.

Important contributors include:

- Sir Francis Galton
- Karl Pearson
- Adrien-Marie Legendre
- Carl Friedrich Gauss

Their work eventually led to **Ordinary Least Squares (OLS)**, which is still widely used today.

---

# 4. Equation of a Line

Linear Regression uses:

```
y = mx + c
```

Where:

```
y → Prediction

x → Input Feature

m → Slope

c → Intercept
```

Example:

```
Marks = 5 × StudyHours + 20
```

If a student studies 8 hours:

```
Marks = 5 × 8 + 20

Marks = 60
```

---

# 5. Key Terminology

### Feature (X)

Input variable.

### Target (y)

Value to predict.

### Slope (m)

How much **y** changes when **x** changes.

```
Large Slope

    /

Small Slope

  /
```

### Intercept (c)

Where the line crosses the Y-axis.

---

# 6. How Linear Regression Works

```
Training Data

(X, y)

      │

Find Best Line

      │

Minimize Error

      │

Regression Equation

      │

Predict New Values
```

The algorithm searches for values of **m** and **c** that produce the smallest prediction error.

---

# 7. Best-Fit Line

Imagine many possible lines.

```
Wrong

\

Wrong

/

Correct

---------
```

The **best-fit line** minimizes the distance between actual data points and predicted values.

---

# 8. Residuals and Error

Residual:

```
Residual

Actual Value

*

|

|

Prediction
```

Formula:

```
Residual = Actual − Predicted
```

Smaller residuals indicate better predictions.

---

# 9. Cost Function (MSE)

The model measures total error using **Mean Squared Error (MSE)**.

Formula:

```
      Σ(Actual − Predicted)²
MSE = -----------------------
             n
```

Why square errors?

- Removes negative signs.
- Penalizes large mistakes.
- Produces a smooth function for optimization.

Goal:

```
Lower MSE

↓

Better Model
```

---

# 10. Ordinary Least Squares (OLS)

OLS finds the line that minimizes the **sum of squared residuals**.

```
Data

*

   *

      *

-----------------

↓

Calculate Total Squared Error

↓

Choose Line with Smallest Error
```

This is the mathematical heart of Linear Regression.

---

# 11. Assumptions

Linear Regression assumes:

- Linear relationship
- Independent observations
- Homoscedasticity (constant variance)
- Normally distributed residuals
- Low multicollinearity (for multiple regression)

Violating these assumptions may reduce model quality.

---

# 12. Python Implementation

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)

score = model.score(X_test, y_test)

print(score)
```

Visualize:

```python
import matplotlib.pyplot as plt

plt.scatter(X, y)
plt.plot(X, model.predict(X), color="red")
plt.show()
```

---

# 13. Advantages

- Simple
- Fast
- Interpretable
- Excellent baseline model
- Easy to explain to business stakeholders

---

# 14. Limitations

- Assumes linear relationships.
- Sensitive to outliers.
- Can underfit complex patterns.
- Performance depends on feature quality.

---

# 15. Real-World Applications

House Prices

```
Area

↓

Price
```

Salary Prediction

```
Experience

↓

Salary
```

Retail

```
Past Sales

↓

Future Sales
```

Healthcare

```
Patient Data

↓

Recovery Time
```

---

# 16. Mini Project

Predict house prices.

Steps:

1. Load a housing dataset.
2. Visualize Area vs Price.
3. Train a Linear Regression model.
4. Plot the best-fit line.
5. Calculate MSE and R² Score.
6. Predict prices for new houses.

---

# 17. Interview Questions

### What is Linear Regression?

A supervised learning algorithm that predicts continuous numerical values using a straight-line relationship.

### What is the equation?

```
y = mx + c
```

### What is the slope?

The rate at which **y** changes with **x**.

### What is OLS?

Ordinary Least Squares finds the line with the minimum sum of squared residuals.

### Why is MSE squared?

To penalize large errors and prevent positive and negative errors from cancelling out.

### Give real-world applications.

- House price prediction
- Sales forecasting
- Salary estimation
- Demand forecasting

---

# 18. Summary

You learned:

- What Linear Regression is.
- History and motivation.
- Equation of a straight line.
- Slope and intercept.
- Residuals.
- MSE.
- OLS.
- Assumptions.
- Python implementation.
- Real-world applications.

---

# 19. What's Next?

**Lesson 78 – Multiple Linear Regression**

You'll learn how Linear Regression is extended to use multiple input features, understand the multivariable regression equation, feature interactions, multicollinearity, coefficient interpretation, and practical implementation with Scikit-Learn.
