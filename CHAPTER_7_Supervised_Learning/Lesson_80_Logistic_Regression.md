
# Chapter 6 – Supervised Learning

# Lesson 80 – Logistic Regression

> **Despite its name, Logistic Regression is a classification algorithm. It predicts probabilities and uses them to classify data into categories, making it one of the most widely used algorithms in Machine Learning.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Logistic Regression is.
- Learn why it was developed.
- Understand the Sigmoid Function.
- Learn Odds, Log-Odds and Probability.
- Understand Decision Boundaries.
- Learn Binary and Multiclass Logistic Regression.
- Build a Logistic Regression model in Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is Logistic Regression?
2. Why Logistic Regression was Invented
3. Why is it called "Regression"?
4. Linear vs Logistic Regression
5. The Sigmoid Function
6. Odds and Log-Odds
7. Decision Boundary
8. Binary vs Multiclass Classification
9. Cost Function (Log Loss)
10. Maximum Likelihood Estimation (MLE)
11. Regularization
12. Python Implementation
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is Logistic Regression?

Logistic Regression is a **supervised learning classification algorithm** used to predict the probability that an input belongs to a particular class.

Examples:

- Spam or Not Spam
- Fraud or Genuine
- Disease or Healthy
- Pass or Fail

Instead of predicting a number like Linear Regression, it predicts a **probability**.

```
Input Features
      │
      ▼
Probability

0.92

      │
      ▼
Class = Positive
```

---

# 2. Why Logistic Regression was Invented

Linear Regression can predict values below 0 or above 1.

Example:

```
Probability = 1.35 ❌

Probability = -0.42 ❌
```

Probabilities must always remain between **0 and 1**.

Logistic Regression solves this using the **Sigmoid Function**.

---

# 3. Why is it called "Regression"?

The algorithm models the **log-odds** using a linear equation.

```
Linear Equation

↓

Log-Odds

↓

Sigmoid Function

↓

Probability

↓

Classification
```

Although the final goal is classification, the underlying mathematical model is based on regression.

---

# 4. Linear vs Logistic Regression

| Linear Regression | Logistic Regression |
|-------------------|--------------------|
| Predicts numbers | Predicts probabilities |
| Output can be any value | Output is between 0 and 1 |
| Used for Regression | Used for Classification |

Example:

Linear Regression

```
Salary = ₹7,80,000
```

Logistic Regression

```
Probability = 0.94

↓

Approved
```

---

# 5. The Sigmoid Function

The Sigmoid (Logistic) Function converts any real number into a value between **0 and 1**.

Formula:

```
           1
P = ----------------
    1 + e^(-z)
```

Where:

- P = Probability
- e = Euler's Number
- z = Linear combination of features

Shape:

```
Probability

1.0 |             ______
    |          __/
0.5 |--------/
    |      /
0.0 |_____/
        z
```

Properties:

- Output always between 0 and 1.
- Smooth and differentiable.
- Ideal for probability estimation.

---

# 6. Odds and Log-Odds

Odds measure the chance of success relative to failure.

```
Odds = P / (1 - P)
```

Log-Odds (Logit):

```
log(P / (1 - P))
```

The model learns a linear relationship in terms of log-odds rather than probabilities directly.

---

# 7. Decision Boundary

After computing a probability, the model converts it into a class.

Common threshold:

```
Probability ≥ 0.5

↓

Positive Class

Probability < 0.5

↓

Negative Class
```

The threshold can be adjusted depending on the application.

Example:

Medical diagnosis may use **0.3** to reduce missed disease cases.

---

# 8. Binary vs Multiclass Classification

### Binary Classification

Two classes.

Examples:

- Yes / No
- Spam / Not Spam
- Fraud / Genuine

### Multiclass Classification

More than two classes.

Examples:

- Cat
- Dog
- Horse

Scikit-Learn supports multiclass Logistic Regression using strategies like **One-vs-Rest (OvR)** and multinomial classification.

---

# 9. Cost Function (Log Loss)

Unlike Linear Regression, Logistic Regression does **not** use Mean Squared Error.

It uses **Log Loss (Binary Cross-Entropy)**.

Formula:

```
Loss = -[y log(p) + (1-y) log(1-p)]
```

Characteristics:

- Penalizes confident wrong predictions heavily.
- Suitable for probability outputs.

Goal:

```
Lower Log Loss

↓

Better Model
```

---

# 10. Maximum Likelihood Estimation (MLE)

Instead of minimizing squared errors, Logistic Regression estimates parameters using **Maximum Likelihood Estimation**.

Idea:

```
Choose Parameters

↓

Highest Probability of Observing Training Data
```

MLE selects coefficients that make the observed data most likely.

---

# 11. Regularization

Regularization reduces overfitting.

### L1 Regularization (Lasso)

- Encourages sparse models.
- Can eliminate unnecessary features.

### L2 Regularization (Ridge)

- Reduces coefficient magnitudes.
- Most commonly used with Logistic Regression.

Python:

```python
LogisticRegression(penalty="l2")
```

---

# 12. Python Implementation

```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = LogisticRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)

probabilities = model.predict_proba(X_test)
```

Useful methods:

- fit()
- predict()
- predict_proba()
- score()

---

# 13. Advantages

- Simple and fast.
- Produces probability estimates.
- Easy to interpret.
- Works well for linearly separable data.
- Strong baseline classifier.

---

# 14. Limitations

- Assumes linear decision boundary.
- Sensitive to outliers.
- May struggle with highly complex relationships.
- Requires feature engineering for non-linear problems.

---

# 15. Real-World Applications

Healthcare

```
Patient Data

↓

Disease Probability
```

Finance

```
Customer Profile

↓

Loan Approval
```

Cybersecurity

```
Network Activity

↓

Attack / Normal
```

Email

```
Incoming Email

↓

Spam Detection
```

---

# 16. Mini Project

Build a loan approval classifier.

1. Load a loan dataset.
2. Encode categorical variables.
3. Split train and test data.
4. Train a Logistic Regression model.
5. Predict approval probabilities.
6. Evaluate using Accuracy, Precision, Recall, F1, and Confusion Matrix.

---

# 17. Interview Questions

### What is Logistic Regression?

A supervised classification algorithm that predicts probabilities for categorical outcomes.

### Why is Logistic Regression used instead of Linear Regression for classification?

Because its output is always between 0 and 1, making it suitable for probabilities.

### What is the Sigmoid Function?

A mathematical function that maps any real value to the range 0–1.

### What cost function does Logistic Regression use?

Log Loss (Binary Cross-Entropy).

### What is the default decision threshold?

Typically **0.5**, though it can be adjusted.

### What is the difference between `predict()` and `predict_proba()`?

- `predict()` returns the predicted class.
- `predict_proba()` returns the probability of each class.

---

# 18. Summary

You learned:

- What Logistic Regression is.
- Why it is used for classification.
- The Sigmoid Function.
- Odds and Log-Odds.
- Decision boundaries.
- Log Loss and MLE.
- Regularization.
- Python implementation.
- Real-world applications.

---

# 19. What's Next?

**Lesson 81 – Classification**

You'll learn the broader concept of classification, different types of classification problems, evaluation methods, decision boundaries, and how algorithms such as KNN, Decision Trees, Naive Bayes, and SVM solve classification tasks.
