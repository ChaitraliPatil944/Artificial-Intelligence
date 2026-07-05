
# Chapter 7 – Unsupervised Learning

# Lesson 96 – Dimensionality Reduction

> **Dimensionality Reduction is the process of reducing the number of input features while preserving as much useful information as possible. It makes machine learning models faster, easier to visualize, less prone to overfitting, and often more accurate.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Dimensionality Reduction is.
- Learn why it was invented.
- Understand the Curse of Dimensionality.
- Learn Feature Selection vs Feature Extraction.
- Understand data compression and visualization.
- Prepare for PCA, t-SNE, and UMAP.
- Prepare for interviews.

---

# Table of Contents

1. What is Dimensionality Reduction?
2. Why was it Invented?
3. History
4. The Curse of Dimensionality
5. Why High Dimensions are a Problem
6. Feature Selection vs Feature Extraction
7. Types of Dimensionality Reduction
8. Benefits
9. Limitations
10. Real-World Applications
11. Python Example
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

---

# 1. What is Dimensionality Reduction?

Dimensionality Reduction is the process of transforming data with many features into a smaller set of features while preserving important information.

```
100 Features
      │
      ▼
Dimensionality Reduction
      │
      ▼
10 Important Features
```

The goal is to simplify data without losing meaningful patterns.

---

# 2. Why was it Invented?

Modern datasets often contain hundreds or thousands of features.

Examples:

- Images contain thousands of pixels.
- Medical datasets contain hundreds of measurements.
- Text datasets contain thousands of words.

Problems:

- Slow training
- High memory usage
- Overfitting
- Difficult visualization

Dimensionality Reduction addresses these issues.

---

# 3. History

The idea originated in statistics and linear algebra.

```
Linear Algebra
      │
Statistics
      │
Principal Component Analysis (PCA)
      │
Modern Visualization Techniques
```

Today, it is widely used in AI, computer vision, NLP, and bioinformatics.

---

# 4. The Curse of Dimensionality

As the number of features increases:

- Data becomes sparse.
- Distance calculations become less meaningful.
- Models require more data.
- Computation becomes expensive.

```
2 Dimensions

● ● ● ●

Easy to analyze

↓

1000 Dimensions

Data becomes sparse
```

This phenomenon is known as the **Curse of Dimensionality**.

---

# 5. Why High Dimensions are a Problem

Problems include:

- Increased training time.
- More memory usage.
- Higher risk of overfitting.
- Harder visualization.
- Reduced performance of distance-based algorithms like KNN and K-Means.

---

# 6. Feature Selection vs Feature Extraction

## Feature Selection

Choose existing features.

```
Original

Age
Salary
Height
Weight

↓

Select

Age
Salary
```

Examples:

- Correlation filtering
- Recursive Feature Elimination (RFE)

---

## Feature Extraction

Create new features by combining old ones.

```
100 Features

↓

PCA

↓

10 New Features
```

The new features may not have direct physical meaning but preserve most of the information.

---

# 7. Types of Dimensionality Reduction

### Linear Methods

- PCA
- SVD

### Non-linear Methods

- t-SNE
- UMAP

### Feature Selection Methods

- Filter Methods
- Wrapper Methods
- Embedded Methods

---

# 8. Benefits

- Faster training.
- Lower memory usage.
- Better visualization.
- Less overfitting.
- Removes redundant information.
- Improves model performance.

---

# 9. Limitations

- Some information is lost.
- Reduced interpretability.
- Choosing the right technique can be difficult.
- Poor reduction may reduce accuracy.

---

# 10. Real-World Applications

Image Compression

```
High Resolution Image
        │
PCA
        │
Smaller Representation
```

Medical Diagnosis

```
Hundreds of Features
        │
Feature Reduction
        │
Disease Prediction
```

Data Visualization

```
100 Features
        │
2 Dimensions
        │
Scatter Plot
```

Recommendation Systems

```
User Preferences
        │
Reduced Features
        │
Recommendations
```

---

# 11. Python Example

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)

X_reduced = pca.fit_transform(X)

print(X_reduced.shape)
```

---

# 12. Mini Project

1. Load the Breast Cancer dataset.
2. Standardize the data.
3. Apply PCA with 2 components.
4. Visualize the transformed data.
5. Compare classification accuracy before and after PCA.

---

# 13. Interview Questions

### What is Dimensionality Reduction?

Reducing the number of input features while preserving important information.

### Why is it needed?

To reduce computation, memory usage, and overfitting while improving visualization.

### What is the Curse of Dimensionality?

As dimensions increase, data becomes sparse and learning becomes more difficult.

### Difference between Feature Selection and Feature Extraction?

Feature Selection keeps existing features, while Feature Extraction creates new ones.

### Name common Dimensionality Reduction algorithms.

- PCA
- SVD
- t-SNE
- UMAP

---

# 14. Summary

You learned:

- What Dimensionality Reduction is.
- Why it is important.
- Curse of Dimensionality.
- Feature Selection vs Feature Extraction.
- Benefits and limitations.
- Python implementation.

---

# 15. What's Next?

**Lesson 97 – Principal Component Analysis (PCA)**

You'll learn the mathematics behind PCA, eigenvectors, eigenvalues, principal components, explained variance, covariance matrices, and how PCA reduces dimensions while preserving the maximum amount of information.
