
# Chapter 6 – Supervised Learning

# Lesson 82 – K-Nearest Neighbors (KNN)

> **K-Nearest Neighbors (KNN) is one of the simplest Machine Learning algorithms. Instead of learning a mathematical equation during training, it makes predictions by looking at the most similar examples it has already seen.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what KNN is.
- Learn why KNN was developed.
- Understand Lazy Learning.
- Learn distance metrics.
- Choose an appropriate value of K.
- Understand weighted voting.
- Implement KNN using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is KNN?
2. Why KNN was Invented
3. History
4. Lazy Learning vs Eager Learning
5. How KNN Works
6. Distance Metrics
7. Choosing the Value of K
8. Voting Mechanism
9. Weighted KNN
10. Feature Scaling
11. Time & Space Complexity
12. Python Implementation
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is KNN?

K-Nearest Neighbors (KNN) is a supervised learning algorithm used for both **classification** and **regression**.

For classification, KNN predicts the class of a new sample by looking at the **K closest training samples**.

```
New Point

     ?

Nearby Neighbors

● ● ● ○ ○

↓

Majority = ●

Prediction = ●
```

---

# 2. Why KNN was Invented

Some datasets have complex decision boundaries that are difficult to describe with equations.

Instead of learning a formula, KNN stores the training data and compares new samples directly with previously seen examples.

Think of it like asking:

> "Who are my closest neighbors, and what do they look like?"

---

# 3. History

KNN originated in **pattern recognition** research during the 1950s and 1960s.

It became popular because:

- It is simple.
- It requires almost no training.
- It works surprisingly well on many small and medium-sized datasets.

Today it is used in recommendation systems, image recognition, medical diagnosis, and anomaly detection.

---

# 4. Lazy Learning vs Eager Learning

### Eager Learning

Algorithms such as:

- Linear Regression
- Logistic Regression
- Decision Trees

learn a model during training.

```
Training Data
      │
      ▼
Learn Model
      │
      ▼
Prediction
```

### Lazy Learning

KNN does **not** build a model.

It simply stores the training data.

```
Training Data

↓

Store Data

↓

Prediction Time

↓

Find Nearest Neighbors
```

Training is fast.

Prediction is slower.

---

# 5. How KNN Works

Suppose:

```
K = 3
```

Training data:

```
● ● ○ ● ○
```

New sample:

```
?
```

Find the 3 nearest neighbors.

```
Nearest:

●
●
○
```

Majority vote:

```
Prediction = ●
```

Workflow:

```
Training Data
      │
Store Examples
      │
New Sample
      │
Calculate Distances
      │
Select K Neighbors
      │
Vote
      │
Prediction
```

---

# 6. Distance Metrics

KNN decides "closeness" using distance.

### Euclidean Distance

Straight-line distance.

Formula:

```
√((x₂-x₁)² + (y₂-y₁)²)
```

ASCII:

```
A *

   \
    \
     *

      B
```

---

### Manhattan Distance

Moves horizontally and vertically.

```
+-----+
|     |
+-----+
```

Formula:

```
|x₂-x₁| + |y₂-y₁|
```

---

### Minkowski Distance

A generalized distance measure.

When:

- p = 1 → Manhattan
- p = 2 → Euclidean

---

# 7. Choosing the Value of K

Small K:

```
K = 1
```

- Sensitive to noise
- May overfit

Large K:

```
K = 25
```

- Smoother predictions
- May underfit

General guideline:

```
Start with

K ≈ √N
```

where **N** is the number of training samples.

Choose the best value using cross-validation.

---

# 8. Voting Mechanism

### Majority Voting

```
Neighbors

●
●
○
●
○

↓

Prediction = ●
```

Every neighbor gets one vote.

---

# 9. Weighted KNN

Closer neighbors receive more influence.

Example:

```
Neighbor A

Distance = 1

Weight = High

Neighbor B

Distance = 10

Weight = Low
```

This often improves performance.

---

# 10. Feature Scaling

KNN depends entirely on distances.

Features with larger values dominate.

Example:

| Feature | Value |
|---------|------:|
| Age | 25 |
| Salary | 900000 |

Salary overwhelms Age.

Always apply:

- Standardization
or
- Normalization

before training KNN.

---

# 11. Time & Space Complexity

Training:

```
Very Fast

Store Data
```

Prediction:

```
Slow

Compare with Every Training Sample
```

Complexities:

- Training: O(1) (mostly storing data)
- Prediction: O(n × d)

where:

- n = number of samples
- d = number of features

Memory usage increases with dataset size.

---

# 12. Python Implementation

```python
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(
    n_neighbors=5
)

model.fit(X_train, y_train)

predictions = model.predict(X_test)

print(model.score(X_test, y_test))
```

Weighted KNN:

```python
KNeighborsClassifier(
    n_neighbors=5,
    weights="distance"
)
```

---

# 13. Advantages

- Easy to understand.
- No explicit training phase.
- Naturally handles multiclass classification.
- Works well on small datasets.
- Simple to implement.

---

# 14. Limitations

- Slow prediction for large datasets.
- Requires feature scaling.
- Sensitive to noisy data.
- Memory intensive.
- Performance decreases in very high-dimensional data (Curse of Dimensionality).

---

# 15. Real-World Applications

Medical Diagnosis

```
Patient Symptoms
      │
Compare Similar Patients
      │
Diagnosis
```

Recommendation Systems

```
Similar Users
      │
Recommend Products
```

Computer Vision

```
Image Features
      │
Nearest Images
      │
Prediction
```

Fraud Detection

```
Transaction
      │
Similar Transactions
      │
Fraud?
```

---

# 16. Mini Project

Build an Iris flower classifier.

1. Load the Iris dataset.
2. Scale the features.
3. Train KNN models with K = 3, 5, and 7.
4. Compare accuracy.
5. Plot the effect of different K values.

---

# 17. Interview Questions

### What is KNN?

A supervised learning algorithm that predicts using the K nearest training samples.

### Why is KNN called a Lazy Learning algorithm?

Because it stores training data and delays computation until prediction time.

### Why is feature scaling important for KNN?

Because KNN uses distance calculations, and large-valued features can dominate.

### What happens if K is too small?

The model may overfit and become sensitive to noise.

### What happens if K is too large?

The model may underfit and ignore local patterns.

### Name three distance metrics.

- Euclidean
- Manhattan
- Minkowski

---

# 18. Summary

You learned:

- What KNN is.
- Lazy Learning.
- Distance metrics.
- Choosing K.
- Voting mechanisms.
- Feature scaling.
- Complexity.
- Python implementation.
- Real-world applications.

---

# 19. What's Next?

**Lesson 83 – Naive Bayes**

You'll learn how probability theory powers one of the fastest classification algorithms, including Bayes' Theorem, conditional probability, the Naive assumption, different Naive Bayes variants, and practical applications in spam filtering and text classification.
