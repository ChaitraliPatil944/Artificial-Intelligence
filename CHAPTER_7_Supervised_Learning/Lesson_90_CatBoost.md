
# Chapter 6 – Supervised Learning

# Lesson 90 – CatBoost

> **CatBoost (Categorical Boosting) is a Gradient Boosting algorithm developed by Yandex. It is specifically designed to work exceptionally well with categorical features while reducing overfitting and requiring minimal data preprocessing.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what CatBoost is.
- Learn why CatBoost was developed.
- Understand Ordered Boosting.
- Learn how CatBoost handles categorical features.
- Explore Oblivious (Symmetric) Decision Trees.
- Compare CatBoost with XGBoost and LightGBM.
- Build a CatBoost model in Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is CatBoost?
2. Why CatBoost was Invented
3. History
4. Gradient Boosting Refresher
5. Native Categorical Feature Handling
6. Ordered Boosting
7. Target Statistics (CTR Features)
8. Oblivious Decision Trees
9. Important Hyperparameters
10. CatBoost vs XGBoost vs LightGBM
11. Python Implementation
12. Advantages
13. Limitations
14. Real-World Applications
15. Mini Project
16. Interview Questions
17. Summary
18. Chapter Recap
19. What's Next?

---

# 1. What is CatBoost?

CatBoost stands for **Categorical Boosting**.

It is a Gradient Boosting algorithm optimized for datasets containing categorical variables.

```
Mixed Dataset
(Numerical + Categorical)
          │
          ▼
CatBoost
          │
          ▼
Prediction
```

Unlike many algorithms, CatBoost can directly use categorical columns.

---

# 2. Why CatBoost was Invented

Traditional boosting algorithms require encoding categorical variables before training.

Problems:

- Extra preprocessing
- Risk of target leakage
- Increased complexity

CatBoost solves these by handling categorical data internally.

---

# 3. History

CatBoost was introduced by **Yandex** in 2017.

Goals:

- Better handling of categorical data
- Reduced overfitting
- High accuracy with minimal preprocessing

```
Gradient Boosting
        │
        ▼
XGBoost
LightGBM
CatBoost
```

---

# 4. Gradient Boosting Refresher

CatBoost follows the boosting philosophy.

```
Tree 1
   │
Errors
   │
Tree 2
   │
Errors
   │
Tree 3
   │
Final Prediction
```

Each tree improves on the mistakes of the previous trees.

---

# 5. Native Categorical Feature Handling

Example dataset:

| City | Income | Purchased |
|------|--------|-----------|
| Pune | 55000 | Yes |
| Delhi | 48000 | No |

Most algorithms require:

```
City

↓

One-Hot Encoding

↓

Train Model
```

CatBoost:

```
City

↓

CatBoost

↓

Train Directly
```

Benefits:

- Less preprocessing
- Lower leakage risk
- Better performance on categorical data

---

# 6. Ordered Boosting

Traditional boosting can accidentally use future target information.

CatBoost introduces **Ordered Boosting**.

```
Training Data
      │
Sequential Processing
      │
Avoid Leakage
      │
Better Generalization
```

This makes training more reliable.

---

# 7. Target Statistics (CTR Features)

CatBoost converts categorical values into numerical representations using target statistics.

Example:

```
City

Pune
Delhi
Mumbai

↓

Numerical Statistics
```

Unlike naive target encoding, CatBoost computes these values carefully to reduce overfitting.

---

# 8. Oblivious (Symmetric) Decision Trees

CatBoost builds **symmetric trees**.

```
        Root
       /    \
      A      A
     / \    / \
    B   B  B   B
```

Every level uses the same splitting feature.

Advantages:

- Faster prediction
- Balanced trees
- Efficient implementation

---

# 9. Important Hyperparameters

| Hyperparameter | Purpose |
|----------------|---------|
| iterations | Number of trees |
| learning_rate | Learning speed |
| depth | Tree depth |
| l2_leaf_reg | L2 regularization |
| loss_function | Optimization objective |
| eval_metric | Evaluation metric |
| random_seed | Reproducibility |

General advice:

- Lower `learning_rate` often improves generalization.
- Increase `iterations` when using a smaller learning rate.

---

# 10. CatBoost vs XGBoost vs LightGBM

| Feature | CatBoost | XGBoost | LightGBM |
|---------|----------|----------|----------|
| Native categorical support | ✅ | ❌ | Limited |
| Ordered Boosting | ✅ | ❌ | ❌ |
| Leaf-wise growth | ❌ | ❌ | ✅ |
| Histogram learning | ✅ | ✅ | ✅ |
| Preprocessing required | Minimal | More | Moderate |

Choose:

- **CatBoost**: many categorical features
- **XGBoost**: strong all-round choice
- **LightGBM**: very large datasets

---

# 11. Python Implementation

Install:

```bash
pip install catboost
```

Train:

```python
from catboost import CatBoostClassifier

model = CatBoostClassifier(
    iterations=300,
    learning_rate=0.05,
    depth=6,
    verbose=0,
    random_seed=42
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

- Handles categorical features directly.
- Excellent accuracy.
- Reduces target leakage.
- Minimal preprocessing.
- Strong default hyperparameters.
- Robust against overfitting.

---

# 13. Limitations

- Can train slower than LightGBM.
- Larger models for some tasks.
- Many hyperparameters for advanced tuning.

---

# 14. Real-World Applications

Banking

```
Customer Data
      │
CatBoost
      │
Loan Approval
```

E-commerce

```
Customer History
      │
Purchase Prediction
```

Insurance

```
Policy Details
      │
Risk Prediction
```

Healthcare

```
Patient Records
      │
Disease Prediction
```

---

# 15. Mini Project

Build a customer purchase predictor.

1. Load a retail dataset with categorical columns.
2. Train CatBoost without manual encoding.
3. Compare with XGBoost using encoded features.
4. Evaluate Accuracy, Precision, Recall, F1-score, and ROC-AUC.
5. Display feature importance.

---

# 16. Interview Questions

### What is CatBoost?

A Gradient Boosting algorithm optimized for categorical features.

### Why is CatBoost popular?

Because it handles categorical variables directly and reduces preprocessing.

### What is Ordered Boosting?

A training strategy that minimizes target leakage and improves generalization.

### What are Oblivious Trees?

Symmetric trees where every level uses the same splitting rule.

### When should you choose CatBoost?

When datasets contain many categorical features.

---

# 17. Summary

You learned:

- What CatBoost is.
- Ordered Boosting.
- Native categorical handling.
- Target statistics.
- Oblivious trees.
- Hyperparameters.
- Python implementation.
- Real-world applications.

---

# 18. Chapter Recap

In **Chapter 6 – Supervised Learning**, you learned:

- Supervised Learning
- Regression
- Linear Regression
- Multiple Linear Regression
- Polynomial Regression
- Logistic Regression
- Classification
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Decision Trees
- Random Forest
- Support Vector Machines (SVM)
- Ensemble Learning
- XGBoost
- LightGBM
- CatBoost

You now have a strong foundation in the most important supervised learning algorithms used in academia and industry.

---

# 19. What's Next?

🎉 **Chapter 6 is complete!**

The next lesson begins **Chapter 7 – Unsupervised Learning**.

**Lesson 91 – Unsupervised Learning**

You'll learn how machines discover hidden patterns without labels, covering clustering, dimensionality reduction, anomaly detection, association rule mining, real-world applications, and why unsupervised learning is essential for exploratory data analysis.
