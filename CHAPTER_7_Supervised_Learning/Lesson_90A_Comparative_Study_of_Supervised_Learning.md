# Chapter 6 – Supervised Learning

# Lesson 90A – Comparative Study of Supervised Learning Algorithms

> **Knowing how an algorithm works is only half the battle. Knowing *when* to use it is what separates a student from an AI engineer. This lesson compares every supervised learning algorithm covered in this chapter from an interview and industry perspective.**

---

# Learning Objectives

By the end of this lesson, you will:

- Compare all supervised learning algorithms.
- Know when to choose each algorithm.
- Understand strengths, weaknesses, and trade-offs.
- Prepare for interview decision-making questions.
- Build an intuition for real-world model selection.

---

# Table of Contents

1. Why Comparative Study Matters
2. Supervised Learning Family Tree
3. Regression vs Classification
4. Master Comparison Table
5. Algorithm Comparison
6. Feature Scaling Requirements
7. Missing Values & Categorical Data
8. Speed & Complexity
9. Bias vs Variance
10. Explainability
11. Interview Decision Tree
12. Industry Use Cases
13. Cheat Sheet
14. Interview Questions
15. Chapter Summary

---

# 1. Why Comparative Study Matters

Interviews rarely stop at:

> "What is Random Forest?"

They usually continue with:

- Why not XGBoost?
- Why not SVM?
- When would you choose Logistic Regression?
- Which model is easiest to explain?

This lesson answers those questions.

---

# 2. Supervised Learning Family Tree

```
                 Supervised Learning
                        │
          ┌─────────────┴─────────────┐
          │                           │
     Regression                 Classification
          │                           │
  Linear Regression           Logistic Regression
  Multiple Linear             KNN
  Polynomial                  Naive Bayes
                              Decision Tree
                              Random Forest
                              SVM
                              XGBoost
                              LightGBM
                              CatBoost
```

---

# 3. Regression vs Classification

| Aspect | Regression | Classification |
|--------|------------|----------------|
| Output | Continuous value | Category |
| Example | House Price | Spam Detection |
| Metrics | MAE, RMSE, R² | Accuracy, Precision, Recall, F1 |

---

# 4. Master Comparison Table

| Algorithm | Task | Scaling | Non-linear | Missing Values | Explainable | Speed | Overfitting |
|-----------|------|---------|------------|----------------|-------------|-------|-------------|
| Linear Regression | Regression | Sometimes | ❌ | ❌ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Low |
| Logistic Regression | Classification | ✅ | ❌ | ❌ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Low |
| KNN | Both | ✅ | ✅ | ❌ | ⭐⭐⭐ | Slow Prediction | Medium |
| Naive Bayes | Classification | ❌ | Limited | ❌ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Low |
| Decision Tree | Both | ❌ | ✅ | Limited | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | High |
| Random Forest | Both | ❌ | ✅ | Limited | ⭐⭐⭐ | ⭐⭐⭐ | Low |
| SVM | Both (SVR/SVC) | ✅ | ✅ | ❌ | ⭐⭐ | Medium | Medium |
| XGBoost | Both | ❌ | ✅ | ✅ | ⭐⭐ | ⭐⭐⭐⭐ | Low |
| LightGBM | Both | ❌ | ✅ | ✅ | ⭐⭐ | ⭐⭐⭐⭐⭐ | Medium |
| CatBoost | Both | ❌ | ✅ | ✅ | ⭐⭐⭐ | ⭐⭐⭐⭐ | Low |

---

# 5. Algorithm Comparison

## Linear Regression
Best for:
- Linear numerical prediction
- Simple baseline models

Avoid when:
- Relationship is highly non-linear.

## Logistic Regression
Best for:
- Binary classification
- Interpretable probability estimates

Avoid when:
- Complex decision boundaries exist.

## KNN
Best for:
- Small datasets
- Simple similarity-based problems

Avoid when:
- Dataset is huge or high-dimensional.

## Naive Bayes
Best for:
- Text classification
- Spam filtering

Avoid when:
- Strong feature dependencies dominate.

## Decision Tree
Best for:
- Explainable decisions
- Mixed feature types

Avoid when:
- High predictive stability is required.

## Random Forest
Best for:
- Strong baseline on tabular data
- Reducing overfitting

## SVM
Best for:
- Small to medium datasets
- High-dimensional data

## XGBoost
Best for:
- Structured/tabular data
- Kaggle competitions
- High accuracy

## LightGBM
Best for:
- Massive datasets
- Fast training

## CatBoost
Best for:
- Many categorical columns
- Minimal preprocessing

---

# 6. Feature Scaling Requirements

```
Needs Scaling

✔ Logistic Regression
✔ KNN
✔ SVM

Usually Doesn't

✔ Decision Tree
✔ Random Forest
✔ XGBoost
✔ LightGBM
✔ CatBoost
✔ Naive Bayes
```

---

# 7. Missing Values & Categorical Data

| Algorithm | Missing Values | Native Categorical Support |
|-----------|----------------|----------------------------|
| Linear/Logistic | ❌ | ❌ |
| KNN | ❌ | ❌ |
| Decision Tree | Limited | Yes (after encoding in many libraries) |
| Random Forest | Limited | Yes (depends on implementation) |
| XGBoost | ✅ | ❌ |
| LightGBM | ✅ | Limited |
| CatBoost | ✅ | ✅ |

---

# 8. Speed & Complexity

| Algorithm | Train | Predict |
|-----------|------:|---------:|
| Linear Regression | Very Fast | Very Fast |
| Logistic Regression | Very Fast | Very Fast |
| KNN | Very Fast | Slow |
| Decision Tree | Fast | Fast |
| Random Forest | Medium | Medium |
| SVM | Slow (large data) | Medium |
| XGBoost | Fast | Fast |
| LightGBM | Very Fast | Fast |
| CatBoost | Fast | Fast |

---

# 9. Bias vs Variance

```
High Bias
│
Linear Models
│
Decision Tree (deep) → High Variance
│
Random Forest ↓ Variance
│
Boosting ↓ Bias
```

---

# 10. Explainability

Most Explainable:
1. Linear Regression
2. Logistic Regression
3. Decision Tree

Moderately Explainable:
- Random Forest
- Naive Bayes

Least Explainable:
- XGBoost
- LightGBM
- CatBoost

---

# 11. Interview Decision Tree

```
               New Problem
                    │
          Labels Available?
             │          │
            Yes        No
             │
     Regression or Classification?
         │                    │
    Numerical             Categories
         │                    │
 Linear relation?       Dataset Size?
    │        │           │         │
  Yes       No       Small      Large
   │         │         │           │
Linear   Polynomial   SVM/KNN   XGBoost
   │
Multiple Features?
   │
Multiple Linear Regression
```

---

# 12. Industry Use Cases

| Problem | Recommended Algorithm |
|---------|-----------------------|
| House Price | Multiple Linear Regression / XGBoost |
| Loan Approval | Random Forest / XGBoost |
| Fraud Detection | XGBoost |
| Customer Churn | CatBoost / XGBoost |
| Email Spam | Naive Bayes |
| Medical Diagnosis | Random Forest |
| Credit Risk | LightGBM |
| Demand Forecasting | Linear Regression / XGBoost |

---

# 13. One-Page Cheat Sheet

```
Need interpretability?
    ↓
Linear / Logistic / Decision Tree

Highest accuracy on tabular data?
    ↓
XGBoost

Huge dataset?
    ↓
LightGBM

Many categorical columns?
    ↓
CatBoost

Small dataset?
    ↓
SVM or KNN

Quick baseline?
    ↓
Logistic Regression / Random Forest
```

---

# 14. Interview Questions

- Why choose Random Forest over Decision Tree?
- When is XGBoost preferred?
- Why does KNN require scaling?
- Why is Logistic Regression used for classification?
- Which algorithm naturally handles categorical features?
- Which algorithm is easiest to explain to business stakeholders?

---

# 15. Chapter Summary

You now know not only **how** each supervised learning algorithm works, but also **when** to use it.

This comparison chapter serves as a quick revision guide before interviews and helps you choose the right algorithm based on:
- Data size
- Feature types
- Interpretability
- Accuracy requirements
- Training speed
- Deployment constraints

Keep returning to this lesson whenever you're unsure which algorithm fits a new problem. Choosing the right model is often more valuable than squeezing another 0.5% accuracy out of the wrong one.
