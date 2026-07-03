
# Chapter 6 – Supervised Learning

# Lesson 79 – Polynomial Regression

> **Not every relationship in the real world is a straight line. Polynomial Regression allows Machine Learning models to capture curved patterns while still using the principles of Linear Regression.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Polynomial Regression is.
- Learn why it was developed.
- Differentiate linear and non-linear relationships.
- Understand polynomial equations.
- Learn about polynomial features.
- Understand underfitting and overfitting.
- Build a Polynomial Regression model in Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is Polynomial Regression?
2. Why Polynomial Regression?
3. Linear vs Non-Linear Relationships
4. Polynomial Equation
5. Degree of a Polynomial
6. How Polynomial Regression Works
7. Polynomial Features
8. Choosing the Right Degree
9. Underfitting vs Overfitting
10. Python Implementation
11. Advantages
12. Limitations
13. Real-World Applications
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is Polynomial Regression?

Polynomial Regression is a supervised learning algorithm used to model **curved relationships** between features and a continuous target.

Although the fitted curve is non-linear, the model remains **linear in its coefficients**.

Example:

```
Study Hours

↓

Exam Score

Curved Relationship
```

---

# 2. Why Polynomial Regression?

Linear Regression assumes data follows a straight line.

Many real-world problems do not.

Example:

```
Plant Growth

^

|          *
|       *
|    *
| *
+-------------------->
Time
```

A straight line cannot accurately represent this curve.

---

# 3. Linear vs Non-Linear Relationships

Linear

```
*
  *
    *
      *
```

Polynomial

```
*
  *
     *
       *
        *
      *
   *
```

Examples of non-linear data:

- Population growth
- Product demand
- Chemical reactions
- Vehicle braking distance

---

# 4. Polynomial Equation

Linear Regression:

```
y = b₀ + b₁x
```

Polynomial Regression:

```
y = b₀ + b₁x + b₂x² + b₃x³ + ...
```

Example:

```
Price = 20
      + 5x
      + 2x²
```

The squared term allows the model to learn curves.

---

# 5. Degree of a Polynomial

The **degree** is the highest power of x.

Examples:

```
x          Degree 1

x²         Degree 2

x³         Degree 3

x⁴         Degree 4
```

Higher degrees increase flexibility but also the risk of overfitting.

---

# 6. How Polynomial Regression Works

```
Original Feature

x

     │

Generate

x²
x³
x⁴

     │

Linear Regression

     │

Curved Prediction
```

Polynomial Regression first creates new polynomial features, then applies Linear Regression.

---

# 7. Polynomial Features

Scikit-Learn generates additional features automatically.

Original:

| x |
|---|
|2|

Degree 3 becomes:

| x | x² | x³ |
|---|----|----|
|2|4|8|

Python:

```python
from sklearn.preprocessing import PolynomialFeatures

poly = PolynomialFeatures(degree=2)

X_poly = poly.fit_transform(X)
```

---

# 8. Choosing the Right Degree

```
Degree 1

Too Simple

↓

Degree 2 or 3

Often Good

↓

Degree 10+

May Memorize Noise
```

General guideline:

- Start with degree 2.
- Evaluate using validation data.
- Increase complexity only if needed.

---

# 9. Underfitting vs Overfitting

Underfitting

```
Data

*   *    *

Straight Line

---------
```

Model misses important patterns.

Overfitting

```
*~~*~~~*~~*~
```

Model memorizes noise instead of learning the true trend.

Goal:

```
Balanced Complexity
```

Use cross-validation to choose the best degree.

---

# 10. Python Implementation

```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
from sklearn.pipeline import Pipeline

model = Pipeline([
    ("poly", PolynomialFeatures(degree=2)),
    ("linear", LinearRegression())
])

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Visualization:

```python
import matplotlib.pyplot as plt

plt.scatter(X, y)
plt.plot(X, model.predict(X), color="red")
plt.show()
```

---

# 11. Advantages

- Captures curved relationships.
- Easy to implement.
- Builds on Linear Regression.
- Useful for moderate non-linear patterns.

---

# 12. Limitations

- Can overfit with high degrees.
- Sensitive to outliers.
- Becomes harder to interpret.
- High-degree models may generalize poorly.

---

# 13. Real-World Applications

Agriculture

```
Rainfall

↓

Crop Yield
```

Economics

```
Price

↓

Demand
```

Healthcare

```
Medicine Dose

↓

Patient Response
```

Manufacturing

```
Temperature

↓

Production Quality
```

---

# 14. Mini Project

Predict fuel efficiency.

Steps:

1. Load a vehicle dataset.
2. Train a Linear Regression model.
3. Train Polynomial Regression models (degree 2 and 3).
4. Compare MSE and R².
5. Plot the fitted curves.
6. Decide which degree performs best.

---

# 15. Interview Questions

### What is Polynomial Regression?

A regression technique that models non-linear relationships by adding polynomial features.

### Is Polynomial Regression a linear model?

Yes. It is linear with respect to its coefficients, even though the prediction curve is non-linear.

### What is the degree of a polynomial?

The highest exponent of the feature.

### Why not always use a high-degree polynomial?

Because it may overfit the training data and perform poorly on unseen data.

### Which Scikit-Learn class creates polynomial features?

```python
from sklearn.preprocessing import PolynomialFeatures
```

---

# 16. Summary

You learned:

- What Polynomial Regression is.
- Why it was introduced.
- Polynomial equations.
- Degree of a polynomial.
- Polynomial features.
- Underfitting vs overfitting.
- Python implementation.
- Real-world applications.

---

# 17. What's Next?

**Lesson 80 – Logistic Regression**

You'll learn why Logistic Regression is used for classification instead of regression, how the sigmoid function works, probability-based predictions, decision boundaries, and why it remains one of the most widely used classification algorithms.
