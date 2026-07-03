
# Chapter 6 – Supervised Learning

# Lesson 83 – Naive Bayes

> **Naive Bayes is a probabilistic Machine Learning algorithm based on Bayes' Theorem. It predicts the most likely class by calculating probabilities and assumes that all input features are independent of each other. Although this assumption is rarely true in the real world, the algorithm performs surprisingly well in many applications such as spam filtering and text classification.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Naive Bayes is.
- Learn the history behind Bayes' Theorem.
- Understand conditional probability.
- Learn why the algorithm is called "Naive."
- Explore different types of Naive Bayes.
- Implement Naive Bayes using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Naive Bayes?
2. Why Naive Bayes was Invented
3. History
4. Bayes' Theorem Refresher
5. Conditional Probability
6. Why is it called "Naive"?
7. How Naive Bayes Works
8. Types of Naive Bayes
9. Laplace Smoothing
10. Advantages
11. Limitations
12. Python Implementation
13. Real-World Applications
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is Naive Bayes?

Naive Bayes is a **supervised classification algorithm** based on probability.

Instead of measuring distances or drawing decision boundaries, it answers:

> **"Given these features, which class is most probable?"**

```
Features
   │
   ▼
Calculate Probabilities
   │
   ▼
Choose Highest Probability
   │
   ▼
Prediction
```

---

# 2. Why Naive Bayes was Invented

Many problems involve uncertainty.

Examples:

- Is this email spam?
- Is this review positive?
- Does this patient have a disease?

Rather than creating complex rules, Naive Bayes estimates probabilities from historical data.

---

# 3. History

Naive Bayes is built on **Bayes' Theorem**, proposed by the English mathematician **Thomas Bayes** in the 18th century.

Timeline

```
Thomas Bayes
      │
Bayes' Theorem
      │
Probability Theory
      │
Naive Bayes Classifier
      │
Modern AI Applications
```

Today, Naive Bayes is widely used for NLP and document classification.

---

# 4. Bayes' Theorem Refresher

Bayes' Theorem updates the probability of an event after observing evidence.

Formula

```
             P(B|A) × P(A)
P(A|B) = -----------------------
               P(B)
```

Where:

- P(A|B) = Probability of A given B
- P(B|A) = Probability of B given A
- P(A) = Prior Probability
- P(B) = Evidence

Simple example:

```
Symptoms

↓

Disease Probability
```

The probability changes as new evidence becomes available.

---

# 5. Conditional Probability

Conditional probability asks:

> "What is the probability of an event after another event has occurred?"

Example:

```
Probability of Rain

Given

Dark Clouds
```

Instead of using overall probability, we use information already observed.

---

# 6. Why is it called "Naive"?

The algorithm assumes that **all features are independent**.

Example:

```
Age

Income

Education
```

Naive Bayes assumes these features do not influence one another.

In reality, they often do.

Despite this unrealistic assumption, the algorithm frequently performs very well.

---

# 7. How Naive Bayes Works

```
Training Data
      │
Estimate Probabilities
      │
Store Probabilities
      │
New Sample
      │
Calculate Posterior Probability
      │
Highest Probability Wins
```

Example

```
Email

Contains:
Free
Offer
Prize

↓

Spam Probability = 0.97

↓

Spam
```

---

# 8. Types of Naive Bayes

## Gaussian Naive Bayes

Used for continuous numerical features.

Examples:

- Height
- Weight
- Temperature

Assumes features follow a Gaussian (Normal) distribution.

---

## Multinomial Naive Bayes

Used for count-based data.

Examples:

- Word frequencies
- Document classification
- Spam detection

---

## Bernoulli Naive Bayes

Used for binary features.

Examples:

```
Word Exists?

Yes / No
```

Useful when features are only 0 or 1.

---

# 9. Laplace Smoothing

Problem:

If a word never appeared in training data, its probability becomes zero.

```
Probability = 0

↓

Entire Prediction = 0
```

Solution:

Laplace Smoothing adds a small value (usually 1) to every count.

Benefits:

- Prevents zero probabilities.
- Improves robustness.

---

# 10. Advantages

- Extremely fast.
- Easy to implement.
- Works well with high-dimensional data.
- Excellent for text classification.
- Requires relatively little training data.

---

# 11. Limitations

- Assumes feature independence.
- Probability estimates may not be perfectly calibrated.
- Performance may decrease when assumptions are heavily violated.

---

# 12. Python Implementation

```python
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()

model.fit(X_train, y_train)

predictions = model.predict(X_test)

probabilities = model.predict_proba(X_test)
```

For text classification:

```python
from sklearn.naive_bayes import MultinomialNB
```

---

# 13. Real-World Applications

Spam Filtering

```
Email
   │
Word Frequencies
   │
Spam?
```

Sentiment Analysis

```
Review
   │
Positive?
```

Medical Diagnosis

```
Symptoms
   │
Disease Probability
```

News Classification

```
Article
   │
Sports / Politics / Business
```

---

# 14. Mini Project

Build a spam email classifier.

1. Load an SMS spam dataset.
2. Convert text using CountVectorizer.
3. Train a Multinomial Naive Bayes model.
4. Predict new messages.
5. Evaluate Accuracy, Precision, Recall, and F1-score.

---

# 15. Interview Questions

### What is Naive Bayes?

A probabilistic classification algorithm based on Bayes' Theorem.

### Why is it called "Naive"?

Because it assumes all input features are independent.

### Name the three main types.

- Gaussian Naive Bayes
- Multinomial Naive Bayes
- Bernoulli Naive Bayes

### What is Laplace Smoothing?

A technique that prevents zero probabilities by adding a small value to feature counts.

### Where is Naive Bayes commonly used?

- Spam filtering
- Sentiment analysis
- Document classification
- News categorization

---

# 16. Summary

You learned:

- What Naive Bayes is.
- Bayes' Theorem.
- Conditional probability.
- The Naive assumption.
- Types of Naive Bayes.
- Laplace Smoothing.
- Python implementation.
- Real-world applications.

---

# 17. What's Next?

**Lesson 84 – Decision Trees**

You'll learn how Decision Trees make decisions using a series of questions, understand entropy and Gini impurity, information gain, tree construction, pruning, overfitting, and why Decision Trees remain one of the most interpretable Machine Learning algorithms.
