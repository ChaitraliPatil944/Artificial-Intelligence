
# Chapter 7 – Unsupervised Learning

# Lesson 95 – DBSCAN

> **DBSCAN (Density-Based Spatial Clustering of Applications with Noise) is a density-based clustering algorithm that discovers clusters of arbitrary shapes while automatically identifying outliers. Unlike K-Means, it does not require the number of clusters to be specified beforehand.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what DBSCAN is.
- Learn why DBSCAN was developed.
- Understand density-based clustering.
- Learn Core, Border, and Noise points.
- Understand ε (epsilon) and MinPts.
- Implement DBSCAN in Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is DBSCAN?
2. Why DBSCAN was Invented
3. History
4. Density-Based Clustering
5. Core, Border & Noise Points
6. Epsilon (ε) and MinPts
7. How DBSCAN Works
8. Choosing Parameters
9. DBSCAN vs K-Means vs Hierarchical
10. Time Complexity
11. Python Implementation
12. Advantages
13. Limitations
14. Real-World Applications
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

---

# 1. What is DBSCAN?

DBSCAN groups together points that are **densely packed** and labels isolated points as **noise**.

```
● ● ● ●

● ● ●

        ○ ○ ○

★

Noise
```

Unlike K-Means, clusters can have irregular shapes.

---

# 2. Why DBSCAN was Invented

Traditional clustering algorithms have limitations:

- K-Means assumes spherical clusters.
- K-Means requires K beforehand.
- Outliers distort centroids.

DBSCAN overcomes these problems using density.

---

# 3. History

DBSCAN was introduced in 1996 by researchers Martin Ester, Hans-Peter Kriegel, Jörg Sander, and Xiaowei Xu.

```
K-Means
    │
Density-Based Clustering
    │
DBSCAN
    │
Modern Spatial Data Mining
```

---

# 4. Density-Based Clustering

Clusters are regions where many points lie close together.

```
Dense Region

● ● ●
● ● ●

Sparse Region

      ●

Noise

           ★
```

---

# 5. Core, Border & Noise Points

## Core Point

Has at least **MinPts** neighbors within ε.

```
● ● ●
 ●C●
● ● ●
```

## Border Point

Near a core point but has too few neighbors.

```
C ●
  ○
```

## Noise Point

Not connected to any cluster.

```
★
```

---

# 6. Epsilon (ε) and MinPts

### ε (Epsilon)

Maximum neighborhood radius.

```
      ●

   ( ε )

      C
```

### MinPts

Minimum neighbors required to become a Core Point.

Typical choice:

```
MinPts = 4 or more
```

---

# 7. How DBSCAN Works

```
Choose ε and MinPts
        │
Pick a Point
        │
Core Point?
   │          │
 Yes         No
 │            │
Expand      Border/Noise
Cluster
```

Repeat until every point has been processed.

---

# 8. Choosing Parameters

### Choosing ε

- Too small → Many noise points
- Too large → Clusters merge together

### Choosing MinPts

General guideline:

```
MinPts ≥ Number of Features + 1
```

A k-distance graph is often used to estimate ε.

---

# 9. DBSCAN vs K-Means vs Hierarchical

| Feature | DBSCAN | K-Means | Hierarchical |
|---------|---------|----------|--------------|
| Need K | ❌ | ✅ | ❌ |
| Detect Outliers | ✅ | ❌ | Limited |
| Irregular Clusters | ✅ | ❌ | ✅ |
| Spherical Assumption | ❌ | ✅ | ❌ |
| Large Data | Good | Excellent | Moderate |

---

# 10. Time Complexity

Using efficient indexing:

```
O(n log n)
```

Without indexing:

```
O(n²)
```

---

# 11. Python Implementation

```python
from sklearn.cluster import DBSCAN

model = DBSCAN(
    eps=0.5,
    min_samples=5
)

labels = model.fit_predict(X)

print(labels)
```

Noise points receive label:

```python
-1
```

---

# 12. Advantages

- No need to specify K.
- Detects outliers naturally.
- Finds arbitrary-shaped clusters.
- Robust to noise.

---

# 13. Limitations

- Sensitive to ε and MinPts.
- Struggles with varying densities.
- Performance drops in very high-dimensional data.

---

# 14. Real-World Applications

- GPS trajectory analysis
- Fraud detection
- Network intrusion detection
- Image segmentation
- Astronomical object discovery

---

# 15. Mini Project

1. Load a spatial dataset.
2. Scale the features.
3. Apply DBSCAN.
4. Experiment with ε and MinPts.
5. Visualize clusters and outliers.
6. Compare with K-Means.

---

# 16. Interview Questions

### What is DBSCAN?

A density-based clustering algorithm.

### Does DBSCAN require K?

No.

### What are Core, Border, and Noise points?

Core points have sufficient neighbors, Border points are attached to a cluster, and Noise points belong to none.

### What does ε represent?

The neighborhood radius.

### What label is assigned to noise?

`-1`

---

# 17. Summary

You learned:

- DBSCAN fundamentals.
- Density-based clustering.
- Core, Border, and Noise points.
- ε and MinPts.
- Parameter selection.
- Python implementation.
- Real-world applications.

---

# 18. What's Next?

**Lesson 96 – Dimensionality Reduction**

You'll learn why high-dimensional data creates challenges, understand the Curse of Dimensionality, feature extraction vs feature selection, visualization, compression, and how dimensionality reduction prepares the way for PCA, t-SNE, and UMAP.
