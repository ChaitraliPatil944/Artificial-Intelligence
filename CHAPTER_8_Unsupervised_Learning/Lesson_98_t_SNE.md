# Chapter 7 -- Unsupervised Learning

# Lesson 98 -- t-SNE (t-Distributed Stochastic Neighbor Embedding)

> **t-SNE is a non-linear dimensionality reduction algorithm designed
> primarily for visualizing high-dimensional data in 2D or 3D. Instead
> of preserving global distances, it focuses on preserving local
> neighborhood relationships, making hidden clusters easier to see.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what t-SNE is.
-   Learn why it was invented.
-   Understand local vs global structure.
-   Learn the intuition behind probability-based embeddings.
-   Compare PCA and t-SNE.
-   Implement t-SNE in Python.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is t-SNE?
2.  Why was it Invented?
3.  History
4.  Intuition
5.  Local vs Global Structure
6.  How t-SNE Works
7.  Important Hyperparameters
8.  PCA vs t-SNE
9.  Advantages
10. Limitations
11. Python Implementation
12. Real-World Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. What is t-SNE?

t-SNE is a **non-linear dimensionality reduction** technique used mainly
for visualization.

``` text
100 Features
      │
    t-SNE
      │
      ▼
2D Plot
```

It does **not** create features for prediction. It creates embeddings
for visualization.

------------------------------------------------------------------------

# 2. Why was it Invented?

PCA preserves maximum variance but often fails to reveal complex
non-linear clusters.

t-SNE was created to preserve **local neighborhoods**, making similar
points stay close together.

------------------------------------------------------------------------

# 3. History

t-SNE was introduced in 2008 by **Laurens van der Maaten** and
**Geoffrey Hinton**.

``` text
PCA
 │
SNE
 │
t-SNE
 │
Modern Data Visualization
```

------------------------------------------------------------------------

# 4. Intuition

Imagine thousands of students in a school.

Instead of preserving the exact distance between every pair of students,
t-SNE focuses on ensuring that **friends remain close together** in the
final map.

``` text
High-Dimensional Space

A B C     X Y Z

↓

2D Map

A B C

        X Y Z
```

------------------------------------------------------------------------

# 5. Local vs Global Structure

PCA:

-   Preserves global variance.

t-SNE:

-   Preserves local neighborhoods.

``` text
Nearby Points
     │
Stay Nearby
```

The exact distance between distant clusters is not always meaningful.

------------------------------------------------------------------------

# 6. How t-SNE Works

``` text
High-Dimensional Data
        │
Compute Pairwise Similarities
        │
Convert to Probabilities
        │
Random Low-Dimensional Initialization
        │
Optimize Positions
        │
2D / 3D Embedding
```

t-SNE minimizes the difference between high-dimensional and
low-dimensional probability distributions.

------------------------------------------------------------------------

# 7. Important Hyperparameters

### Perplexity

Controls the effective number of neighbors.

Typical values:

-   5
-   30
-   50

### Learning Rate

Too low:

-   Slow convergence

Too high:

-   Unstable visualization

### Number of Iterations

More iterations generally produce a better embedding.

------------------------------------------------------------------------

# 8. PCA vs t-SNE

  Feature                     PCA       t-SNE
  --------------------------- --------- -----------
  Linear                      ✅        ❌
  Visualization               Good      Excellent
  Fast                        ✅        ❌
  Preserves Variance          ✅        ❌
  Preserves Local Structure   Limited   ✅
  Suitable for ML Pipeline    ✅        Mostly No

------------------------------------------------------------------------

# 9. Advantages

-   Excellent visualization.
-   Reveals hidden clusters.
-   Works well for image and text embeddings.
-   Captures complex non-linear relationships.

------------------------------------------------------------------------

# 10. Limitations

-   Computationally expensive.
-   Slow on large datasets.
-   Results vary with hyperparameters.
-   Not suitable for predictive feature extraction.

------------------------------------------------------------------------

# 11. Python Implementation

``` python
from sklearn.manifold import TSNE

tsne = TSNE(
    n_components=2,
    perplexity=30,
    random_state=42
)

X_embedded = tsne.fit_transform(X)
```

------------------------------------------------------------------------

# 12. Real-World Applications

-   Visualizing image embeddings
-   Word embedding visualization
-   Single-cell genomics
-   Customer segmentation
-   Anomaly exploration

------------------------------------------------------------------------

# 13. Mini Project

1.  Load the MNIST dataset.
2.  Apply PCA to 50 components (optional).
3.  Apply t-SNE to 2 components.
4.  Plot the digits.
5.  Observe natural clusters.

------------------------------------------------------------------------

# 14. Interview Questions

### What is t-SNE?

A non-linear dimensionality reduction algorithm mainly used for
visualization.

### Does t-SNE preserve global distances?

No. It prioritizes local neighborhoods.

### Is t-SNE used before model training?

Usually no. It is mainly an exploratory visualization tool.

### Why apply PCA before t-SNE?

To reduce noise and computation on very high-dimensional datasets.

------------------------------------------------------------------------

# 15. Summary

You learned:

-   Why t-SNE exists.
-   Local vs global structure.
-   Important hyperparameters.
-   PCA vs t-SNE.
-   Python implementation.
-   Applications.

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 99 -- UMAP**

You'll learn how UMAP provides fast, scalable non-linear dimensionality
reduction while preserving both local and global structure, and why it
has become a popular alternative to t-SNE.
