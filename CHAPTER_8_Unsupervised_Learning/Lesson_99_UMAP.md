# Chapter 7 -- Unsupervised Learning

# Lesson 99 -- UMAP (Uniform Manifold Approximation and Projection)

> **UMAP is a modern non-linear dimensionality reduction algorithm
> designed for visualization and feature embedding. It preserves both
> local and global data structure better than many traditional methods
> while being significantly faster than t-SNE on large datasets.**

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will:

-   Understand what UMAP is.
-   Learn why UMAP was developed.
-   Understand manifold learning.
-   Learn how UMAP constructs graphs.
-   Compare UMAP with PCA and t-SNE.
-   Implement UMAP in Python.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is UMAP?
2.  Why UMAP was Invented
3.  History
4.  Manifold Learning Intuition
5.  How UMAP Works
6.  Important Hyperparameters
7.  UMAP vs PCA vs t-SNE
8.  Advantages
9.  Limitations
10. Python Implementation
11. Real-World Applications
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

------------------------------------------------------------------------

# 1. What is UMAP?

UMAP (Uniform Manifold Approximation and Projection) is a **non-linear
dimensionality reduction** technique.

``` text
High-Dimensional Data
         │
       UMAP
         │
         ▼
2D / 3D Embedding
```

It is widely used to visualize complex datasets.

------------------------------------------------------------------------

# 2. Why UMAP was Invented

Researchers wanted an algorithm that:

-   Preserved local neighborhoods.
-   Preserved more global structure than t-SNE.
-   Scaled to millions of samples.
-   Ran significantly faster.

UMAP addresses these goals.

------------------------------------------------------------------------

# 3. History

UMAP was introduced in 2018 by **Leland McInnes**, **John Healy**, and
**James Melville**.

``` text
PCA
 │
t-SNE
 │
UMAP
 │
Modern AI Visualization
```

------------------------------------------------------------------------

# 4. Manifold Learning Intuition

Imagine a sheet of paper rolled into a cylinder.

``` text
Flat Sheet

────────────

↓

Rolled

( Cylinder )
```

Although the shape changes, the paper's surface is still the same.

UMAP assumes high-dimensional data lies on a lower-dimensional
**manifold** and tries to recover that structure.

------------------------------------------------------------------------

# 5. How UMAP Works

``` text
High-Dimensional Data
        │
Find Nearest Neighbors
        │
Build Graph
        │
Optimize Low-Dimensional Graph
        │
2D / 3D Embedding
```

Instead of preserving exact distances, UMAP preserves neighborhood
relationships.

------------------------------------------------------------------------

# 6. Important Hyperparameters

### n_neighbors

Controls how much local versus global structure is preserved.

-   Small value → more local detail.
-   Large value → more global structure.

### min_dist

Controls how tightly points are packed.

-   Small → compact clusters.
-   Large → spread-out clusters.

### metric

Distance function used to measure similarity.

Examples:

-   Euclidean
-   Manhattan
-   Cosine

------------------------------------------------------------------------

# 7. UMAP vs PCA vs t-SNE

  Feature            PCA         t-SNE       UMAP
  ------------------ ----------- ----------- -----------
  Linear             ✅          ❌          ❌
  Visualization      Good        Excellent   Excellent
  Speed              Very Fast   Slow        Fast
  Local Structure    Moderate    Excellent   Excellent
  Global Structure   Good        Limited     Better
  Large Datasets     Good        Limited     Excellent

------------------------------------------------------------------------

# 8. Advantages

-   Fast.
-   Scales well.
-   Excellent visualizations.
-   Preserves local relationships.
-   Better global preservation than t-SNE.
-   Works well with large datasets.

------------------------------------------------------------------------

# 9. Limitations

-   Hyperparameter tuning affects results.
-   Mainly intended for visualization.
-   Embeddings are not always directly interpretable.

------------------------------------------------------------------------

# 10. Python Implementation

Install:

``` bash
pip install umap-learn
```

Example:

``` python
import umap

reducer = umap.UMAP(
    n_neighbors=15,
    min_dist=0.1,
    random_state=42
)

X_embedded = reducer.fit_transform(X)
```

------------------------------------------------------------------------

# 11. Real-World Applications

-   Visualizing image embeddings
-   NLP embedding visualization
-   Single-cell RNA sequencing
-   Customer segmentation
-   Recommendation systems

------------------------------------------------------------------------

# 12. Mini Project

1.  Load the MNIST dataset.
2.  Apply UMAP.
3.  Visualize the 2D embedding.
4.  Compare with PCA and t-SNE.
5.  Observe cluster separation.

------------------------------------------------------------------------

# 13. Interview Questions

### What is UMAP?

A non-linear dimensionality reduction algorithm for visualization and
embedding.

### Why is UMAP often preferred over t-SNE?

It is generally faster, scales better, and preserves more global
structure.

### What does `n_neighbors` control?

The balance between local and global structure.

### What does `min_dist` control?

How closely points are packed together in the embedding.

------------------------------------------------------------------------

# 14. Summary

You learned:

-   What UMAP is.
-   Manifold learning intuition.
-   Graph-based optimization.
-   Important hyperparameters.
-   Comparison with PCA and t-SNE.
-   Python implementation.

------------------------------------------------------------------------

# 15. What's Next?

**Lesson 100 -- Association Rule Mining**

You'll learn how machines discover relationships such as "customers who
buy bread often buy butter", understand support, confidence, lift, and
prepare for the Apriori algorithm.
