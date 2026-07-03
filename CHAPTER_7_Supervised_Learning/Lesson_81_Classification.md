
# Chapter 6 – Supervised Learning

# Lesson 81 – Classification

> **Classification is a supervised learning task where a model predicts categories instead of continuous values. It is used whenever the answer belongs to one or more predefined classes, such as spam detection, disease diagnosis, or image recognition.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Classification is.
- Learn why Classification is important.
- Explore different types of classification problems.
- Understand the complete classification workflow.
- Learn common classification algorithms.
- Prepare for interview questions.

---

# Table of Contents

1. What is Classification?
2. Why Classification was Invented
3. History of Classification
4. How Classification Works
5. Types of Classification
6. Decision Boundaries
7. Classification Workflow
8. Popular Classification Algorithms
9. Evaluation Overview
10. Advantages
11. Limitations
12. Real-World Applications
13. Python Example
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is Classification?

Classification is a supervised learning technique where the goal is to predict a **category (class)** instead of a numerical value.

Examples:

- Spam / Not Spam
- Fraud / Genuine
- Cat / Dog
- Pass / Fail

```
Features
   │
   ▼
Classifier
   │
   ▼
Predicted Class
```

Unlike regression, the output is a label.

---

# 2. Why Classification was Invented

Many real-world problems require making decisions rather than predicting numbers.

Examples:

- Should a loan be approved?
- Is an email spam?
- Does a patient have a disease?
- Is a transaction fraudulent?

Writing thousands of manual rules is impractical. Classification algorithms learn these decision patterns from historical labeled data.

---

# 3. History of Classification

Classification evolved from statistics and pattern recognition.

Timeline:

```
Statistics
     │
     ▼
Logistic Regression
     │
     ▼
Decision Trees
     │
     ▼
Support Vector Machines
     │
     ▼
Ensemble Learning
     │
     ▼
Deep Learning
```

Today, classification powers many AI systems.

---

# 4. How Classification Works

```
Historical Data

Features + Labels
        │
        ▼
Train Classifier
        │
        ▼
Learn Decision Pattern
        │
        ▼
New Sample
        │
        ▼
Predict Class
```

Example:

```
Age
Income
Credit Score

↓

Loan Approved
```

---

# 5. Types of Classification

## Binary Classification

Two possible classes.

Examples:

- Yes / No
- Spam / Not Spam

```
○  ●
```

---

## Multiclass Classification

More than two classes.

Examples:

- Cat
- Dog
- Horse

```
○  ●  ▲
```

---

## Multi-label Classification

One sample can belong to multiple classes.

Example:

A movie can be:

- Action
- Comedy
- Adventure

at the same time.

```
Movie

↓

Action ✔
Comedy ✔
Drama ✖
```

---

# 6. Decision Boundaries

A classifier separates different classes using a decision boundary.

```
○ ○ ○ ○

-----------

● ● ● ●
```

Simple models produce simple boundaries.

Complex models can learn curved boundaries.

---

# 7. Classification Workflow

```
Collect Data
      │
      ▼
Preprocess Data
      │
      ▼
Train-Test Split
      │
      ▼
Train Classifier
      │
      ▼
Evaluate
      │
      ▼
Deploy
      │
      ▼
Predict
```

---

# 8. Popular Classification Algorithms

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Decision Trees
- Random Forest
- Support Vector Machine (SVM)
- XGBoost
- LightGBM
- CatBoost
- Neural Networks

Upcoming lessons explore each in detail.

---

# 9. Evaluation Overview

Common metrics include:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC Curve
- AUC
- Confusion Matrix

These will be covered in depth later.

---

# 10. Advantages

- Easy to automate decision making.
- Handles many real-world problems.
- Supports probability estimation (some models).
- Large ecosystem of algorithms.

---

# 11. Limitations

- Requires labeled data.
- Can suffer from class imbalance.
- Performance depends on data quality.
- Some algorithms struggle with highly complex patterns.

---

# 12. Real-World Applications

Healthcare

```
Patient Data
      │
Disease?
```

Finance

```
Customer Details
      │
Loan Approval?
```

Cybersecurity

```
Network Traffic
      │
Attack?
```

Computer Vision

```
Image
      │
Cat / Dog / Bird
```

---

# 13. Python Example

```python
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = DecisionTreeClassifier()

model.fit(X_train, y_train)

predictions = model.predict(X_test)

print(model.score(X_test, y_test))
```

---

# 14. Mini Project

Build an email spam classifier.

1. Load a labeled email dataset.
2. Clean and preprocess the data.
3. Split into training and testing sets.
4. Train a classifier.
5. Evaluate using Accuracy, Precision, Recall, and F1 Score.

---

# 15. Interview Questions

### What is Classification?

A supervised learning task that predicts categorical labels.

### Difference between Regression and Classification?

Regression predicts continuous values, while Classification predicts categories.

### Name the three major types of Classification.

- Binary
- Multiclass
- Multi-label

### Give examples of Classification.

- Spam detection
- Disease diagnosis
- Fraud detection
- Image recognition

### Name common classification algorithms.

- Logistic Regression
- KNN
- Naive Bayes
- Decision Tree
- Random Forest
- SVM

---

# 16. Summary

You learned:

- What Classification is.
- Why it is important.
- Types of classification.
- Decision boundaries.
- Workflow.
- Popular algorithms.
- Applications.

---

# 17. What's Next?

**Lesson 82 – K-Nearest Neighbors (KNN)**

You'll learn one of the simplest yet surprisingly powerful classification algorithms, including distance metrics, choosing K, voting mechanisms, computational complexity, advantages, limitations, and practical implementation.
