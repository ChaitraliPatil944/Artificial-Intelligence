
# Chapter 6 – Supervised Learning

# Lesson 76 – Regression

> **Regression is one of the oldest and most important Machine Learning techniques. It predicts continuous numerical values by learning relationships between variables. From predicting house prices to forecasting sales, regression is everywhere.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Regression is.
- Learn why Regression was invented.
- Explore its history and evolution.
- Understand how Regression works.
- Differentiate Regression from Classification.
- Learn common types of Regression.
- Prepare for interview questions.

---

# Table of Contents

1. What is Regression?
2. Why Regression was Invented
3. History of Regression
4. Key Terminology
5. How Regression Works
6. Types of Regression
7. Regression vs Classification
8. Regression Workflow
9. Assumptions of Regression
10. Advantages
11. Limitations
12. Real-World Applications
13. Python Example
14. Best Practices
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

---

# 1. What is Regression?

Regression is a supervised learning technique used to predict **continuous numerical values**.

Examples:

- House Price
- Salary
- Temperature
- Stock Demand
- Electricity Consumption

Example:

```
Input

House Size = 1800 sq.ft

↓

Prediction

₹ 85,00,000
```

Unlike classification, regression predicts a **number**, not a category.

---

# 2. Why Regression was Invented

Businesses and scientists have always wanted to answer questions like:

- How will sales change next month?
- What will a house cost?
- How much rainfall can be expected?
- What salary should be offered?

Writing rules manually is almost impossible.

Regression learns these relationships directly from historical data.

---

# 3. History of Regression

Regression originated in statistics.

In the late 1800s, **Sir Francis Galton** studied the relationship between the heights of parents and their children. He observed that extreme values tended to move closer to the average in the next generation, a phenomenon he called **"regression toward mediocrity"**, later known as **regression toward the mean**.

Evolution:

```
Statistics
     │
     ▼
Linear Regression
     │
     ▼
Multiple Regression
     │
     ▼
Polynomial Regression
     │
     ▼
Modern Machine Learning Regression
```

Today, regression powers countless AI applications.

---

# 4. Key Terminology

### Independent Variable (Feature)

Input used for prediction.

Examples:

- Area
- Age
- Experience

Represented as:

```
X
```

### Dependent Variable (Target)

Value the model predicts.

Examples:

- Price
- Salary
- Temperature

Represented as:

```
y
```

---

# 5. How Regression Works

```
Historical Data

X  →  y

↓

Find Relationship

↓

Regression Model

↓

New X

↓

Predicted y
```

Example:

```
Study Hours

↓

Exam Marks
```

The model learns the relationship and predicts marks for future students.

---

# 6. Types of Regression

Common regression algorithms:

- Linear Regression
- Multiple Linear Regression
- Polynomial Regression
- Ridge Regression
- Lasso Regression
- Elastic Net
- Decision Tree Regression
- Random Forest Regression
- Support Vector Regression (SVR)

The next few lessons focus on the first three.

---

# 7. Regression vs Classification

| Regression | Classification |
|------------|----------------|
| Predicts numbers | Predicts categories |
| Continuous output | Discrete output |
| Example: ₹52,00,000 | Example: Spam |

Examples:

Regression

```
Predict Salary

₹7,50,000
```

Classification

```
Predict Email

Spam
```

---

# 8. Regression Workflow

```
Collect Data
      │
      ▼
Preprocess Data
      │
      ▼
Split Train/Test
      │
      ▼
Train Regression Model
      │
      ▼
Evaluate
      │
      ▼
Predict New Values
```

---

# 9. Assumptions of Regression

Many regression models, especially Linear Regression, assume:

- Linear relationship between variables
- Independent observations
- Constant error variance (Homoscedasticity)
- Normally distributed residuals
- Minimal multicollinearity (for multiple regression)

These assumptions help produce reliable predictions.

---

# 10. Advantages

- Easy to understand.
- Highly interpretable.
- Fast to train.
- Useful baseline model.
- Strong statistical foundation.

---

# 11. Limitations

- Some models assume linear relationships.
- Sensitive to outliers.
- Can underperform on highly complex patterns.
- Depends heavily on feature quality.

---

# 12. Real-World Applications

House Price Prediction

```
Area
Bedrooms
Location

↓

Predicted Price
```

Retail

```
Past Sales

↓

Sales Forecast
```

Healthcare

```
Patient Features

↓

Hospital Stay Duration
```

Manufacturing

```
Sensor Data

↓

Machine Lifetime
```

---

# 13. Python Example

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Important methods:

- fit()
- predict()
- score()

---

# 14. Best Practices

- Clean data before training.
- Handle outliers carefully.
- Scale features when appropriate.
- Check assumptions.
- Evaluate using regression metrics rather than accuracy.

---

# 15. Mini Project

Build a house price predictor.

Tasks:

1. Load a housing dataset.
2. Split into train and test sets.
3. Train a Linear Regression model.
4. Predict house prices.
5. Evaluate the predictions.

---

# 16. Interview Questions

### What is Regression?

A supervised learning technique used to predict continuous numerical values.

### Give examples of Regression problems.

- House prices
- Salary prediction
- Sales forecasting
- Temperature prediction

### What is the difference between Regression and Classification?

Regression predicts numbers, while Classification predicts categories.

### Name common Regression algorithms.

- Linear Regression
- Polynomial Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regression

### Which library provides Linear Regression in Python?

```python
from sklearn.linear_model import LinearRegression
```

---

# 17. Summary

You learned:

- What Regression is.
- Why it was invented.
- Its historical origins.
- Key terminology.
- Regression workflow.
- Types of Regression.
- Advantages and limitations.
- Real-world applications.

---

# 18. What's Next?

**Lesson 77 – Linear Regression**

You'll learn the mathematics behind the simplest and most influential regression algorithm, including the equation of a line, slope, intercept, cost function, Ordinary Least Squares (OLS), and how Linear Regression actually learns from data.
