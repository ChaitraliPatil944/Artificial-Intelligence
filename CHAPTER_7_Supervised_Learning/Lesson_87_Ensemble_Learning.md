
# Chapter 6 – Supervised Learning

# Lesson 87 – Ensemble Learning

> **Ensemble Learning combines multiple Machine Learning models to create one stronger model. Just as a committee often makes better decisions than a single individual, ensemble methods improve prediction accuracy by combining the strengths of several learners while reducing their weaknesses.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Ensemble Learning is.
- Learn why Ensemble Learning was developed.
- Understand Weak vs Strong Learners.
- Learn Bagging, Boosting, Voting, and Stacking.
- Understand the Bias-Variance tradeoff.
- Implement ensemble models in Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Ensemble Learning?
2. Why Ensemble Learning?
3. History
4. Weak vs Strong Learners
5. How Ensemble Learning Works
6. Types of Ensemble Learning
7. Bagging
8. Boosting
9. Voting
10. Stacking
11. Bias-Variance Tradeoff
12. Python Implementation
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is Ensemble Learning?

Ensemble Learning is a Machine Learning technique that combines multiple models to produce a better final prediction.

Instead of trusting one model:

```
One Model

↓

Prediction
```

we combine many models:

```
Model 1
Model 2
Model 3
Model 4

↓

Combined Prediction
```

The combined model is usually more accurate and robust.

---

# 2. Why Ensemble Learning?

Every algorithm has strengths and weaknesses.

Example:

- Decision Trees can overfit.
- Linear models may underfit.
- KNN can struggle with large datasets.

Combining several models often balances these weaknesses.

---

# 3. History

Ensemble methods became popular when researchers found that combining multiple "weak" models consistently outperformed a single complex model.

Evolution:

```
Decision Trees
      │
      ▼
Bagging
      │
      ▼
Boosting
      │
      ▼
Stacking
      │
      ▼
Modern AI Competitions
```

Many winning solutions in ML competitions rely on ensembles.

---

# 4. Weak vs Strong Learners

### Weak Learner

Performs only slightly better than random guessing.

Examples:

- Small Decision Tree
- Decision Stump

### Strong Learner

Produces highly accurate predictions.

```
Weak Learners

🌱 🌱 🌱

↓

Combine

↓

🌳 Strong Learner
```

---

# 5. How Ensemble Learning Works

```
Training Data
      │
      ▼
Train Multiple Models
      │
      ▼
Combine Predictions
      │
      ▼
Final Prediction
```

The combination reduces errors that individual models make.

---

# 6. Types of Ensemble Learning

The four major ensemble techniques are:

- Bagging
- Boosting
- Voting
- Stacking

Each uses a different strategy for combining models.

---

# 7. Bagging

**Bagging (Bootstrap Aggregating)** trains many models independently using different bootstrap samples.

```
Training Data
      │
Bootstrap Samples
      │
Tree  Tree  Tree
      │
Majority Vote
```

Characteristics:

- Models are trained in parallel.
- Reduces variance.
- Example: Random Forest.

---

# 8. Boosting

Boosting trains models **sequentially**.

Each new model focuses on correcting the mistakes of previous models.

```
Model 1

↓

Errors

↓

Model 2

↓

Errors

↓

Model 3
```

Characteristics:

- Reduces bias.
- Learners depend on previous learners.
- Examples:
  - AdaBoost
  - Gradient Boosting
  - XGBoost
  - LightGBM
  - CatBoost

---

# 9. Voting

Voting combines predictions from multiple independent models.

### Hard Voting

Each model votes for a class.

```
Cat
Cat
Dog

↓

Cat
```

### Soft Voting

Uses prediction probabilities.

```
Model A

Cat = 0.90

Model B

Cat = 0.70

↓

Average Probability

↓

Cat
```

---

# 10. Stacking

Stacking combines different algorithms using another model called a **Meta Learner**.

```
Decision Tree

Random Forest

SVM

↓

Meta Model

↓

Final Prediction
```

The Meta Learner discovers how to best combine the base models.

---

# 11. Bias-Variance Tradeoff

```
High Bias

↓

Underfitting

Balanced

↓

Best Performance

High Variance

↓

Overfitting
```

Bagging mainly reduces **variance**.

Boosting mainly reduces **bias**.

---

# 12. Python Implementation

## Random Forest (Bagging)

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100
)
```

## AdaBoost

```python
from sklearn.ensemble import AdaBoostClassifier

model = AdaBoostClassifier()
```

## Voting Classifier

```python
from sklearn.ensemble import VotingClassifier
```

## Stacking Classifier

```python
from sklearn.ensemble import StackingClassifier
```

---

# 13. Advantages

- Higher predictive accuracy.
- Better generalization.
- More robust to noise.
- Reduces overfitting (Bagging).
- Reduces underfitting (Boosting).

---

# 14. Limitations

- Increased training time.
- Higher memory usage.
- Harder to interpret.
- More hyperparameters to tune.

---

# 15. Real-World Applications

Fraud Detection

```
Transaction Data
      │
Ensemble Models
      │
Fraud?
```

Healthcare

```
Medical Records
      │
Ensemble
      │
Diagnosis
```

Finance

```
Customer Data
      │
Credit Risk
```

Computer Vision

```
Image Features
      │
Multiple Models
      │
Object Class
```

---

# 16. Mini Project

Predict customer churn.

1. Train a Decision Tree.
2. Train a Random Forest.
3. Train AdaBoost.
4. Compare Accuracy, Precision, Recall, and F1-score.
5. Build a Voting Classifier.
6. Compare all models.

---

# 17. Interview Questions

### What is Ensemble Learning?

A technique that combines multiple models to improve prediction performance.

### What is the difference between Bagging and Boosting?

Bagging trains models independently in parallel.

Boosting trains models sequentially, each correcting previous mistakes.

### What is Voting?

Combining predictions from multiple models using majority vote or averaged probabilities.

### What is Stacking?

An ensemble technique where a Meta Learner combines predictions from multiple base models.

### Which algorithm is an example of Bagging?

Random Forest.

### Which algorithms are examples of Boosting?

- AdaBoost
- Gradient Boosting
- XGBoost
- LightGBM
- CatBoost

---

# 18. Summary

You learned:

- What Ensemble Learning is.
- Weak vs Strong Learners.
- Bagging.
- Boosting.
- Voting.
- Stacking.
- Bias-Variance tradeoff.
- Python implementations.
- Real-world applications.

---

# 19. What's Next?

**Lesson 88 – XGBoost**

You'll learn one of the most successful machine learning algorithms ever created, including gradient boosting, boosting iterations, regularization, tree pruning, handling missing values, and why XGBoost dominates many structured data competitions.
