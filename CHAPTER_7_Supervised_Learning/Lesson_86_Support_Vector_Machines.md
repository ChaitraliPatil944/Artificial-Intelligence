
# Chapter 6 – Supervised Learning

# Lesson 86 – Support Vector Machines (SVM)

> **Support Vector Machines (SVM) are powerful supervised learning algorithms that find the optimal boundary between classes by maximizing the margin between them. SVMs are especially effective in high-dimensional spaces and remain one of the most important classification algorithms in Machine Learning.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what SVM is.
- Learn why SVM was invented.
- Understand hyperplanes and support vectors.
- Learn hard margin vs soft margin.
- Understand kernels and the Kernel Trick.
- Implement SVM using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is SVM?
2. Why SVM was Invented
3. History
4. How SVM Works
5. Hyperplanes
6. Support Vectors
7. Maximum Margin Classifier
8. Hard Margin vs Soft Margin
9. The Kernel Trick
10. Types of Kernels
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

# 1. What is SVM?

Support Vector Machine (SVM) is a supervised learning algorithm used for:

- Classification
- Regression (SVR)
- Outlier Detection

Its main objective is to find the **best decision boundary** that separates different classes.

```
○ ○ ○ ○

==============

● ● ● ●
```

The boundary is chosen to maximize the distance from both classes.

---

# 2. Why SVM was Invented

Simple classifiers often struggle when classes overlap or when datasets contain many features.

SVM addresses this by finding the boundary with the **largest possible margin**, improving generalization.

Applications include:

- Face recognition
- Text classification
- Bioinformatics
- Handwriting recognition

---

# 3. History

SVM was introduced in the 1990s by **entity["people","Vladimir Vapnik","Machine learning researcher"]** and colleagues.

Timeline:

```
Statistical Learning Theory
          │
          ▼
Support Vector Machines
          │
          ▼
Kernel Methods
          │
          ▼
Modern AI
```

---

# 4. How SVM Works

```
Training Data
      │
Find Best Hyperplane
      │
Maximize Margin
      │
Support Vectors
      │
Prediction
```

Instead of any separating line, SVM searches for the optimal one.

---

# 5. Hyperplanes

A hyperplane separates classes.

In:

- 2D → a line
- 3D → a plane
- Higher dimensions → a hyperplane

```
○ ○ ○

-----------

● ● ●
```

---

# 6. Support Vectors

Support vectors are the training samples closest to the decision boundary.

```
○   ○

○

==========

●

●   ●
```

Only these critical points determine the position of the hyperplane.

Removing distant points usually has little effect.

---

# 7. Maximum Margin Classifier

Margin = distance between the hyperplane and the nearest samples.

```
○ ○

| Margin |

==========

| Margin |

● ●
```

Larger margin generally leads to better generalization.

---

# 8. Hard Margin vs Soft Margin

## Hard Margin

- No classification errors allowed.
- Requires perfectly separable data.

```
○ ○ ○

----------

● ● ●
```

## Soft Margin

Allows some misclassification to improve robustness.

```
○ ○

---x------

● ●
```

The trade-off is controlled by parameter **C**.

---

# 9. The Kernel Trick

Real-world data is often not linearly separable.

Instead of explicitly transforming data into higher dimensions, SVM uses the **Kernel Trick**.

```
Original Data

✦ ✦ ○ ○

↓

Kernel Transformation

↓

Higher Dimension

↓

Linear Separation
```

This avoids expensive computations.

---

# 10. Types of Kernels

### Linear Kernel

Best for linearly separable data.

```python
kernel="linear"
```

### Polynomial Kernel

Captures polynomial relationships.

```python
kernel="poly"
```

### RBF (Gaussian) Kernel

Most commonly used.

```python
kernel="rbf"
```

Handles complex non-linear boundaries.

### Sigmoid Kernel

Inspired by neural networks.

```python
kernel="sigmoid"
```

---

# 11. Hyperparameters

| Hyperparameter | Purpose |
|----------------|---------|
| `C` | Controls margin vs classification errors |
| `kernel` | Type of kernel |
| `gamma` | Controls influence of training samples (RBF/Poly/Sigmoid) |
| `degree` | Degree of polynomial kernel |

### Parameter C

Small C

```
Larger Margin

More Errors
```

Large C

```
Smaller Margin

Fewer Training Errors
```

### Gamma

Small gamma

- Smooth boundary

Large gamma

- Complex boundary
- Higher overfitting risk

---

# 12. Python Implementation

```python
from sklearn.svm import SVC

model = SVC(
    kernel="rbf",
    C=1.0,
    gamma="scale"
)

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Probability estimates:

```python
model = SVC(probability=True)
```

---

# 13. Advantages

- Effective in high-dimensional spaces.
- Powerful for complex decision boundaries.
- Memory efficient.
- Works well with small and medium datasets.
- Flexible through kernels.

---

# 14. Limitations

- Slow on very large datasets.
- Sensitive to parameter tuning.
- Requires feature scaling.
- Less interpretable than Decision Trees.

---

# 15. Real-World Applications

Face Recognition

```
Face Features
      │
SVM
      │
Identity
```

Spam Detection

```
Email
      │
Spam?
```

Medical Diagnosis

```
Patient Data
      │
Disease?
```

Image Classification

```
Image Features
      │
Object Class
```

---

# 16. Mini Project

Build a handwritten digit classifier.

1. Load the Digits dataset.
2. Standardize features.
3. Train Linear and RBF SVMs.
4. Compare accuracy.
5. Tune `C` and `gamma`.
6. Visualize the confusion matrix.

---

# 17. Interview Questions

### What is SVM?

A supervised learning algorithm that finds the optimal decision boundary by maximizing the margin between classes.

### What is a support vector?

The training sample closest to the decision boundary.

### Why maximize the margin?

Larger margins usually improve generalization.

### What is the Kernel Trick?

A method that allows SVM to solve non-linear problems without explicitly transforming data into higher dimensions.

### Name common kernels.

- Linear
- Polynomial
- RBF
- Sigmoid

### Why is feature scaling important?

Because SVM relies on distance calculations and optimization.

---

# 18. Summary

You learned:

- What SVM is.
- Hyperplanes.
- Support vectors.
- Maximum margin.
- Hard vs soft margins.
- Kernel Trick.
- Common kernels.
- Hyperparameters.
- Python implementation.

---

# 19. What's Next?

**Lesson 87 – Ensemble Learning**

You'll learn the philosophy behind combining multiple models, explore Bagging, Boosting, and Stacking, and understand why ensemble methods consistently outperform many individual machine learning algorithms.
