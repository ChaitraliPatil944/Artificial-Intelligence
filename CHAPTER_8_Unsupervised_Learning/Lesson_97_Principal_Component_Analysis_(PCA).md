# Chapter 7 -- Unsupervised Learning

# Lesson 97 -- Principal Component Analysis (PCA)

> **Principal Component Analysis (PCA)** is one of the most important
> dimensionality reduction techniques in Machine Learning. It transforms
> high-dimensional data into a smaller set of new features called
> **Principal Components** while preserving as much information
> (variance) as possible.

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will:

-   Understand why PCA was invented.
-   Connect PCA with Linear Algebra.
-   Understand variance, covariance, eigenvalues, and eigenvectors.
-   Learn how PCA works step by step.
-   Apply PCA using Scikit-Learn.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is PCA?
2.  Why PCA was Invented
3.  History
4.  Intuition Behind PCA
5.  Why Variance Matters
6.  Covariance
7.  Covariance Matrix
8.  Eigenvalues & Eigenvectors
9.  Principal Components
10. Explained Variance
11. PCA Algorithm
12. Geometric Interpretation
13. PCA vs Feature Selection
14. Advantages
15. Limitations
16. Python Implementation
17. Real-World Applications
18. Mini Project
19. Interview Questions
20. Cheat Sheet
21. Summary
22. What's Next?

------------------------------------------------------------------------

# 1. What is PCA?

PCA reduces the number of features while preserving the maximum amount
of useful information.

``` text
100 Features
      │
      ▼
     PCA
      │
      ▼
10 Principal Components
```

Unlike Feature Selection, PCA **creates new features** instead of
selecting existing ones.

------------------------------------------------------------------------

# 2. Why PCA was Invented

Real-world datasets often contain:

-   Hundreds of features
-   Correlated variables
-   Redundant information
-   Noise

Problems caused:

-   Slow training
-   Overfitting
-   Difficult visualization

PCA solves these by projecting data into a lower-dimensional space.

------------------------------------------------------------------------

# 3. History

PCA was introduced by **Karl Pearson (1901)** and later generalized by
**Harold Hotelling**.

``` text
Linear Algebra
      │
Statistics
      │
Karl Pearson
      │
PCA
      │
Modern Machine Learning
```

------------------------------------------------------------------------

# 4. Intuition Behind PCA

Imagine a cloud of points.

``` text
      *  *
   *      *
 *          *
    *    *
```

Instead of measuring in the original X and Y directions, PCA finds the
direction where the data spreads the most.

------------------------------------------------------------------------

# 5. Why Variance Matters

Variance tells us how much information a feature carries.

``` text
Low Variance

●●●●

High Variance

●     ●      ●      ●
```

PCA keeps directions with **maximum variance**.

------------------------------------------------------------------------

# 6. Covariance

Covariance measures how two variables change together.

-   Positive covariance → move together
-   Negative covariance → move opposite
-   Zero covariance → unrelated

------------------------------------------------------------------------

# 7. Covariance Matrix

For two features:

``` text
        X      Y
X   Cov(X,X) Cov(X,Y)
Y   Cov(Y,X) Cov(Y,Y)
```

The covariance matrix summarizes relationships between all features.

------------------------------------------------------------------------

# 8. Eigenvalues & Eigenvectors

This is where Chapter 3 becomes useful.

-   **Eigenvector** = Direction of maximum variance.
-   **Eigenvalue** = Amount of variance in that direction.

``` text
Cloud of Data

\\\\\\\\

Principal Direction
────────────►
```

The first principal component is the eigenvector with the largest
eigenvalue.

------------------------------------------------------------------------

# 9. Principal Components

Principal Components are new axes.

``` text
Original Axes

X
│
│
└──── Y

↓

Rotated Axes

PC1
↗

PC2
↘
```

PC1 captures the most information.

PC2 captures the next most information and is perpendicular to PC1.

------------------------------------------------------------------------

# 10. Explained Variance

Explained Variance Ratio tells us how much information each component
keeps.

Example:

  Component     Explained Variance
  ----------- --------------------
  PC1                          72%
  PC2                          18%
  PC3                           6%
  Others                        4%

Keeping PC1 and PC2 preserves **90%** of the information.

------------------------------------------------------------------------

# 11. PCA Algorithm

``` text
Standardize Data
      │
Compute Covariance Matrix
      │
Find Eigenvalues & Eigenvectors
      │
Sort by Eigenvalues
      │
Choose Top Components
      │
Project Data
```

------------------------------------------------------------------------

# 12. Geometric Interpretation

PCA rotates the coordinate system to align with the direction of maximum
variance.

``` text
Original Axes
     │
Rotate
     ▼
Principal Axes
```

------------------------------------------------------------------------

# 13. PCA vs Feature Selection

  PCA                           Feature Selection
  ----------------------------- -------------------------------
  Creates new features          Keeps existing features
  Compresses information        Removes unnecessary features
  Components are combinations   Features remain interpretable

------------------------------------------------------------------------

# 14. Advantages

-   Reduces dimensionality
-   Faster training
-   Lower memory usage
-   Removes redundancy
-   Useful for visualization

------------------------------------------------------------------------

# 15. Limitations

-   Components are difficult to interpret
-   Information is lost
-   Assumes linear relationships
-   Sensitive to feature scaling

------------------------------------------------------------------------

# 16. Python Implementation

``` python
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA

X_scaled = StandardScaler().fit_transform(X)

pca = PCA(n_components=2)

X_reduced = pca.fit_transform(X_scaled)

print(pca.explained_variance_ratio_)
```

------------------------------------------------------------------------

# 17. Real-World Applications

-   Face Recognition
-   Image Compression
-   Gene Expression Analysis
-   Financial Risk Analysis
-   Data Visualization

------------------------------------------------------------------------

# 18. Mini Project

1.  Load the Breast Cancer dataset.
2.  Standardize features.
3.  Apply PCA (2 components).
4.  Plot the transformed data.
5.  Compare classifier performance before and after PCA.

------------------------------------------------------------------------

# 19. Interview Questions

### What is PCA?

A dimensionality reduction technique that preserves maximum variance.

### Why is feature scaling important?

Because PCA depends on variance and covariance.

### What are Principal Components?

New orthogonal axes that capture maximum variance.

### What do Eigenvalues represent?

The amount of variance captured by each principal component.

### What is Explained Variance Ratio?

The percentage of information retained by each component.

------------------------------------------------------------------------

# 20. Cheat Sheet

``` text
Many Features
      │
Standardize
      │
Covariance Matrix
      │
Eigenvalues + Eigenvectors
      │
Choose Top Components
      │
Reduced Dataset
```

------------------------------------------------------------------------

# 21. Summary

You learned:

-   Why PCA exists
-   Variance and covariance
-   Covariance Matrix
-   Eigenvalues
-   Eigenvectors
-   Principal Components
-   Explained Variance
-   PCA workflow
-   Python implementation

------------------------------------------------------------------------

# 22. What's Next?

**Lesson 98 -- t-SNE**

You'll learn how t-SNE visualizes high-dimensional data while preserving
local neighborhood structure and why it has become one of the most
popular visualization techniques in Machine Learning.
