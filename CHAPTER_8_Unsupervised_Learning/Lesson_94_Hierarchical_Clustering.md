
# Chapter 7 – Unsupervised Learning

# Lesson 94 – Hierarchical Clustering

> **Hierarchical Clustering builds a hierarchy of clusters instead of creating a fixed number of groups immediately. It reveals how data points are related at different levels, making it one of the most interpretable clustering techniques.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand Hierarchical Clustering.
- Learn Agglomerative and Divisive approaches.
- Understand dendrograms.
- Learn linkage methods.
- Compare Hierarchical Clustering with K-Means.
- Implement Hierarchical Clustering in Python.
- Prepare for interviews.

---

# Table of Contents

1. What is Hierarchical Clustering?
2. Why was it Invented?
3. History
4. Types of Hierarchical Clustering
5. Dendrogram
6. Linkage Methods
7. Distance Matrix
8. Choosing the Number of Clusters
9. Hierarchical vs K-Means
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

# 1. What is Hierarchical Clustering?

Hierarchical Clustering groups data into a tree-like hierarchy.

```
        All Data
        /      \
    Group A   Group B
     /   \      /   \
   A1    A2   B1    B2
```

Unlike K-Means, you do not have to decide the final number of clusters at the beginning.

---

# 2. Why was it Invented?

Sometimes we want to understand **relationships** between clusters, not just the final groups.

Examples:

- Evolutionary biology
- Document organization
- Customer segmentation
- Gene analysis

---

# 3. History

```
Statistics
     │
Taxonomy
     │
Hierarchical Clustering
     │
Modern Data Mining
```

It has been widely used in biology long before modern AI.

---

# 4. Types of Hierarchical Clustering

## Agglomerative (Bottom-Up)

Every point starts as its own cluster.

```
A B C D

↓

AB   CD

↓

ABCD
```

This is the most common approach.

### Divisive (Top-Down)

Start with one large cluster.

```
ABCD

↓

AB   CD

↓

A B C D
```

---

# 5. Dendrogram

A dendrogram is a tree showing how clusters merge.

```
      ______
     |      |
   __|__    |
  |     |   |
 A      B   C
```

The height where branches join represents the distance between clusters.

Cutting the dendrogram at different heights produces different numbers of clusters.

---

# 6. Linkage Methods

### Single Linkage

Uses the closest pair of points.

### Complete Linkage

Uses the farthest pair of points.

### Average Linkage

Uses the average distance.

### Ward Linkage

Minimizes the increase in variance after merging.

Ward linkage is often the default choice.

---

# 7. Distance Matrix

Hierarchical clustering first computes pairwise distances.

```
      A  B  C
A     0  2  5
B     2  0  3
C     5  3  0
```

The algorithm repeatedly merges the closest clusters.

---

# 8. Choosing the Number of Clusters

Instead of specifying K initially:

```
Build Dendrogram

↓

Choose Cut Height

↓

Clusters
```

This gives flexibility during analysis.

---

# 9. Hierarchical vs K-Means

| Feature | Hierarchical | K-Means |
|---------|--------------|---------|
| Need K beforehand | No | Yes |
| Output | Dendrogram | Flat clusters |
| Cluster Shape | Flexible | Mostly spherical |
| Speed | Slower | Faster |
| Large datasets | Less suitable | Excellent |

---

# 10. Time Complexity

Hierarchical Clustering is computationally expensive.

Approximate complexity:

```
O(n² log n)
```

or worse depending on implementation.

Best suited for small and medium datasets.

---

# 11. Python Implementation

```python
from sklearn.cluster import AgglomerativeClustering

model = AgglomerativeClustering(
    n_clusters=3,
    linkage="ward"
)

labels = model.fit_predict(X)
```

Plotting a dendrogram:

```python
from scipy.cluster.hierarchy import dendrogram, linkage

Z = linkage(X, method="ward")
dendrogram(Z)
```

---

# 12. Advantages

- No need to choose K initially.
- Produces an interpretable hierarchy.
- Flexible cluster exploration.
- Works with different distance measures.

---

# 13. Limitations

- Computationally expensive.
- Difficult to scale to very large datasets.
- Once clusters merge, they cannot be split later.

---

# 14. Real-World Applications

- Gene expression analysis
- Customer segmentation
- Taxonomy
- Document clustering
- Image organization

---

# 15. Mini Project

1. Load the Iris dataset.
2. Standardize features.
3. Build a dendrogram.
4. Choose a cut height.
5. Train Agglomerative Clustering.
6. Compare with K-Means.

---

# 16. Interview Questions

### What is Hierarchical Clustering?

An unsupervised algorithm that creates a hierarchy of clusters.

### Difference between Agglomerative and Divisive?

Agglomerative merges clusters from the bottom up, while Divisive splits clusters from the top down.

### What is a dendrogram?

A tree diagram showing how clusters merge.

### What is Ward linkage?

A linkage method that minimizes within-cluster variance.

### Does Hierarchical Clustering require K initially?

No.

---

# 17. Summary

You learned:

- Hierarchical Clustering
- Agglomerative vs Divisive
- Dendrograms
- Linkage methods
- Distance matrices
- Comparison with K-Means

---

# 18. What's Next?

**Lesson 95 – DBSCAN**

You'll learn density-based clustering, core points, border points, noise detection, epsilon (ε), MinPts, and why DBSCAN excels at finding irregularly shaped clusters while automatically detecting outliers.
