
# Chapter 6 – Supervised Learning

# Lesson 85 – Random Forest

> **Random Forest is an ensemble learning algorithm that combines many Decision Trees to produce a stronger, more accurate, and more stable model. Instead of relying on a single tree, it lets hundreds of trees vote together, reducing overfitting and improving generalization.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Random Forest is.
- Learn why it was developed.
- Understand Ensemble Learning and Bagging.
- Learn Bootstrap Sampling and Random Feature Selection.
- Understand Out-of-Bag (OOB) Error.
- Learn Feature Importance.
- Implement Random Forest using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Random Forest?
2. Why Random Forest was Invented
3. History
4. Ensemble Learning
5. How Random Forest Works
6. Bootstrap Sampling (Bagging)
7. Random Feature Selection
8. Voting & Averaging
9. Out-of-Bag (OOB) Error
10. Feature Importance
11. Hyperparameters
12. Python Implementation
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is Random Forest?

Random Forest is a supervised learning algorithm that builds **many Decision Trees** and combines their predictions.

For classification:

```
Tree 1 → Cat
Tree 2 → Cat
Tree 3 → Dog
Tree 4 → Cat

↓

Majority Vote

↓

Cat
```

For regression:

```
Tree Predictions

50
54
52
56

↓

Average

↓

53
```

---

# 2. Why Random Forest was Invented

A single Decision Tree is easy to understand but often **overfits**.

Random Forest solves this by combining many trees.

```
One Tree

↓

High Variance

Many Trees

↓

Stable Prediction
```

---

# 3. History

Random Forest was introduced by **entity["people","Leo Breiman","Statistician and creator of Random Forest"]** in 2001.

It combines ideas from:

- Decision Trees
- Bootstrap Sampling
- Ensemble Learning
- Random Feature Selection

Today it is one of the most widely used ML algorithms.

---

# 4. Ensemble Learning

Ensemble Learning combines multiple models to create a stronger model.

```
Weak Learners

Tree
Tree
Tree
Tree

↓

Combine

↓

Strong Learner
```

Two common approaches:

- Bagging
- Boosting

Random Forest uses **Bagging**.

---

# 5. How Random Forest Works

```
Training Data
      │
Bootstrap Samples
      │
Build Many Trees
      │
Random Feature Selection
      │
Individual Predictions
      │
Combine Results
      │
Final Prediction
```

Each tree is trained independently.

---

# 6. Bootstrap Sampling (Bagging)

Bootstrap sampling randomly selects training examples **with replacement**.

Example:

Original:

```
A B C D E
```

Bootstrap Sample:

```
A C C D E
```

Notice that:

- Some samples repeat.
- Some samples are left out.

Each tree gets a different dataset.

---

# 7. Random Feature Selection

Each split considers only a random subset of features.

```
Available Features

Age
Income
Score
Education
Experience

↓

Random Choice

Income
Score
```

This makes trees more diverse and reduces correlation.

---

# 8. Voting & Averaging

### Classification

```
Tree Votes

✔
✔
✖
✔
✔

↓

Majority Vote
```

### Regression

```
Predictions

120
118
125
122

↓

Average = 121.25
```

---

# 9. Out-of-Bag (OOB) Error

Some training samples are not selected in a bootstrap sample.

These are called **Out-of-Bag** samples.

```
Training Data

A B C D E

↓

Tree Sample

A C C D

↓

OOB

B E
```

OOB samples can estimate model performance without a separate validation set.

Python:

```python
RandomForestClassifier(
    oob_score=True
)
```

---

# 10. Feature Importance

Random Forest estimates how useful each feature is.

Example:

```
Income        0.42
Credit Score  0.31
Age           0.18
Education     0.09
```

Higher importance indicates greater contribution.

---

# 11. Hyperparameters

Important parameters:

| Hyperparameter | Purpose |
|----------------|---------|
| `n_estimators` | Number of trees |
| `max_depth` | Maximum tree depth |
| `max_features` | Features considered at each split |
| `min_samples_split` | Minimum samples to split |
| `min_samples_leaf` | Minimum samples in a leaf |
| `bootstrap` | Enable bootstrap sampling |
| `oob_score` | Calculate OOB accuracy |

---

# 12. Python Implementation

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    max_depth=10,
    random_state=42,
    oob_score=True
)

model.fit(X_train, y_train)

predictions = model.predict(X_test)

print(model.score(X_test, y_test))
print(model.oob_score_)
print(model.feature_importances_)
```

---

# 13. Advantages

- High accuracy.
- Reduces overfitting.
- Handles missing values reasonably well.
- Works with numerical and categorical features.
- Estimates feature importance.
- Robust to noisy data.

---

# 14. Limitations

- Less interpretable than a single Decision Tree.
- Slower to train.
- Uses more memory.
- Large forests may increase prediction time.

---

# 15. Real-World Applications

Fraud Detection

```
Customer Data
      │
Random Forest
      │
Fraud?
```

Healthcare

```
Patient Records
      │
Disease Prediction
```

Finance

```
Credit History
      │
Loan Approval
```

Agriculture

```
Weather + Soil
      │
Crop Yield Prediction
```

---

# 16. Mini Project

Predict customer churn.

1. Load a customer dataset.
2. Train a Decision Tree.
3. Train a Random Forest.
4. Compare Accuracy, Precision, Recall, and F1-score.
5. Display feature importance.
6. Tune `n_estimators` and `max_depth`.

---

# 17. Interview Questions

### What is Random Forest?

An ensemble learning algorithm that combines many Decision Trees.

### Why is Random Forest better than a single Decision Tree?

It reduces overfitting and improves generalization.

### What is Bagging?

Training multiple models on different bootstrap samples and combining their predictions.

### What is Bootstrap Sampling?

Sampling training data with replacement.

### What is OOB Error?

Performance estimated using samples not selected during bootstrap sampling.

### How are predictions combined?

- Majority vote (classification)
- Average (regression)

---

# 18. Summary

You learned:

- What Random Forest is.
- Ensemble Learning.
- Bagging.
- Bootstrap Sampling.
- Random Feature Selection.
- OOB Error.
- Feature Importance.
- Hyperparameters.
- Python implementation.

---

# 19. What's Next?

**Lesson 86 – Support Vector Machines (SVM)**

You'll learn how SVM finds the optimal decision boundary, understand margins, support vectors, kernels, the kernel trick, hard vs soft margins, and why SVM performs exceptionally well on high-dimensional datasets.
