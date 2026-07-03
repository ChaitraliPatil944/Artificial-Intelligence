
# Chapter 6 – Supervised Learning

# Lesson 89 – LightGBM

> **LightGBM (Light Gradient Boosting Machine) is a high-performance Gradient Boosting framework developed by Microsoft. It is designed to train faster, use less memory, and scale efficiently to millions of samples while maintaining excellent prediction accuracy.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what LightGBM is.
- Learn why it was developed.
- Understand histogram-based learning.
- Learn Leaf-wise tree growth.
- Understand GOSS and EFB.
- Compare LightGBM with XGBoost.
- Build a LightGBM model in Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is LightGBM?
2. Why LightGBM was Invented
3. History
4. Gradient Boosting Refresher
5. Histogram-Based Learning
6. Leaf-wise vs Level-wise Growth
7. GOSS
8. EFB
9. Important Hyperparameters
10. LightGBM vs XGBoost
11. Python Implementation
12. Advantages
13. Limitations
14. Real-World Applications
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

---

# 1. What is LightGBM?

LightGBM is an optimized implementation of Gradient Boosting Decision Trees (GBDT).

It focuses on:

- Faster training
- Lower memory usage
- Better scalability
- High accuracy

```
Training Data
      │
Gradient Boosting
      │
Optimized Learning
      │
Fast Predictions
```

---

# 2. Why LightGBM was Invented

Traditional Gradient Boosting and even XGBoost can become slow on very large datasets.

Microsoft developed LightGBM to:

- Reduce training time
- Reduce memory consumption
- Handle massive datasets efficiently

---

# 3. History

LightGBM was released by **Microsoft** in 2017 as an open-source machine learning framework.

It quickly became popular for Kaggle competitions and industrial ML systems.

```
GBDT
 │
 ▼
XGBoost
 │
 ▼
LightGBM
```

---

# 4. Gradient Boosting Refresher

LightGBM is still a boosting algorithm.

```
Tree 1

↓

Correct Errors

↓

Tree 2

↓

Correct Errors

↓

Tree 3

↓

Final Model
```

Each tree improves the predictions of the previous ensemble.

---

# 5. Histogram-Based Learning

Instead of evaluating every possible split value, LightGBM groups values into **bins**.

```
Original Values

1 2 3 4 5 6 7 8 9

↓

Bins

[1-3] [4-6] [7-9]
```

Benefits:

- Faster split search
- Lower memory usage
- Efficient training

---

# 6. Leaf-wise vs Level-wise Growth

### Level-wise (Traditional)

```
      ●
     / \
    ●   ●
   / \ / \
```

Every level grows together.

### Leaf-wise (LightGBM)

```
      ●
     /
    ●
   /
  ●
```

The leaf with the largest reduction in loss grows first.

Advantages:

- Faster convergence
- Better accuracy

Disadvantage:

- Higher risk of overfitting if not controlled.

---

# 7. GOSS

**Gradient-based One-Side Sampling (GOSS)** keeps samples with large gradients and randomly samples those with small gradients.

```
Large Errors

✔ Keep

Small Errors

Random Sample
```

This speeds up training while preserving useful information.

---

# 8. EFB

**Exclusive Feature Bundling (EFB)** combines mutually exclusive sparse features into one feature.

```
Feature A

10000

Feature B

00001

↓

Bundled Feature
```

Benefits:

- Fewer features
- Lower memory
- Faster computation

---

# 9. Important Hyperparameters

| Hyperparameter | Purpose |
|----------------|---------|
| learning_rate | Learning speed |
| n_estimators | Number of trees |
| num_leaves | Maximum leaves per tree |
| max_depth | Maximum depth |
| feature_fraction | Fraction of features used |
| bagging_fraction | Fraction of samples used |
| min_data_in_leaf | Minimum samples in a leaf |

---

# 10. LightGBM vs XGBoost

| Feature | LightGBM | XGBoost |
|---------|----------|----------|
| Tree Growth | Leaf-wise | Level-wise |
| Speed | Faster on large data | Fast |
| Memory | Lower | Higher |
| Small datasets | Good | Excellent |
| Very large datasets | Excellent | Very Good |

General guideline:

- XGBoost: great default choice.
- LightGBM: shines on very large datasets.

---

# 11. Python Implementation

Install:

```bash
pip install lightgbm
```

Train:

```python
from lightgbm import LGBMClassifier

model = LGBMClassifier(
    n_estimators=200,
    learning_rate=0.05,
    num_leaves=31,
    random_state=42
)

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Feature importance:

```python
print(model.feature_importances_)
```

---

# 12. Advantages

- Extremely fast training.
- Low memory usage.
- Excellent scalability.
- Handles large datasets well.
- Supports parallel and GPU training.

---

# 13. Limitations

- Can overfit on small datasets.
- Many hyperparameters.
- Less interpretable than a single tree.
- Leaf-wise growth requires careful tuning.

---

# 14. Real-World Applications

Finance

```
Credit History
      │
LightGBM
      │
Risk Score
```

Recommendation Systems

```
User Behavior
      │
Purchase Prediction
```

Healthcare

```
Patient Records
      │
Disease Prediction
```

Advertising

```
User Data
      │
Click Prediction
```

---

# 15. Mini Project

Predict customer churn.

1. Load a churn dataset.
2. Train an LGBMClassifier.
3. Tune `num_leaves`, `learning_rate`, and `feature_fraction`.
4. Compare results with XGBoost.
5. Plot feature importance.

---

# 16. Interview Questions

### What is LightGBM?

A fast Gradient Boosting framework developed by Microsoft.

### Why is LightGBM faster?

It uses histogram-based learning, GOSS, EFB, and leaf-wise tree growth.

### What is GOSS?

Gradient-based One-Side Sampling that keeps informative samples and reduces computation.

### What is EFB?

Exclusive Feature Bundling that combines sparse mutually exclusive features.

### Difference between LightGBM and XGBoost?

LightGBM grows trees leaf-wise and is generally faster on very large datasets.

---

# 17. Summary

You learned:

- What LightGBM is.
- Histogram-based learning.
- Leaf-wise tree growth.
- GOSS.
- EFB.
- Important hyperparameters.
- Comparison with XGBoost.
- Python implementation.

---

# 18. What's Next?

**Lesson 90 – CatBoost**

You'll learn Yandex's Gradient Boosting algorithm designed for categorical data, including ordered boosting, native categorical feature handling, target statistics, overfitting prevention, and why CatBoost often performs exceptionally well with mixed numerical and categorical datasets.
