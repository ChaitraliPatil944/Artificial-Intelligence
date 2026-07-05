# Chapter 7 – Unsupervised Learning

# Lesson 92 – Clustering

> **Clustering is one of the most important techniques in Unsupervised Learning. It groups similar data points together without using labels, allowing machines to discover hidden patterns that humans may not immediately notice.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Clustering is.
- Learn why Clustering was invented.
- Explore similarity and distance measures.
- Understand different types of clustering.
- Learn how cluster quality is evaluated.
- Prepare for interview questions.

---

# Table of Contents

1. What is Clustering?
2. Why Clustering was Invented
3. History
4. How Clustering Works
5. Similarity and Distance
6. Types of Clustering
7. Good vs Bad Clusters
8. Choosing the Number of Clusters
9. Cluster Evaluation
10. Advantages
11. Limitations
12. Real-World Applications
13. Python Example
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is Clustering?

Clustering is an **unsupervised learning** technique that groups similar data points into clusters.

Unlike classification:

```
Classification

Data
↓
Known Labels
↓
Prediction
```

Clustering:

```
Data
↓
Find Similarity
↓
Automatic Groups
```

Example:

```
● ● ●

○ ○ ○

▲ ▲ ▲
```

---

# 2. Why Clustering was Invented

Many real-world datasets have no labels.

Clustering discovers hidden groups automatically.

Examples:

- Customer segmentation
- Market basket grouping
- Social network communities
- Gene grouping

---

# 3. History

```
Statistics
    │
Pattern Recognition
    │
Hierarchical Clustering
    │
K-Means
    │
Density-Based Clustering
    │
Modern AI
```

---

# 4. How Clustering Works

```
Raw Data
    │
Measure Similarity
    │
Group Similar Points
    │
Clusters
```

---

# 5. Similarity and Distance

### Euclidean Distance

Straight-line distance.

```
√((x₂-x₁)² + (y₂-y₁)²)
```

### Manhattan Distance

```
|x₂-x₁| + |y₂-y₁|
```

### Cosine Similarity

Measures the angle between vectors.

Best for:

- Documents
- NLP
- Recommendation Systems

---

# 6. Types of Clustering

## Partition-Based

- K-Means
- K-Medoids

## Hierarchical

Creates a tree of clusters.

## Density-Based

- DBSCAN

Groups dense regions.

## Model-Based

- Gaussian Mixture Models

---

# 7. Good vs Bad Clusters

Good:

```
● ● ●

     ○ ○ ○

          ▲ ▲ ▲
```

Bad:

```
● ○ ▲
○ ● ▲
▲ ○ ●
```

---

# 8. Choosing the Number of Clusters

Methods:

- Elbow Method
- Silhouette Score
- Domain Knowledge

---

# 9. Cluster Evaluation

- Silhouette Score (higher is better)
- Davies-Bouldin Index (lower is better)
- Calinski-Harabasz Index (higher is better)

---

# 10. Advantages

- No labels required.
- Discovers hidden structure.
- Useful for exploratory analysis.
- Powerful for segmentation.

---

# 11. Limitations

- Hard to evaluate.
- Sensitive to preprocessing.
- Number of clusters may be unknown.
- Results depend on algorithm.

---

# 12. Real-World Applications

- Customer Segmentation
- Image Segmentation
- Fraud Detection
- Recommendation Systems
- Bioinformatics

---

# 13. Python Example

```python
from sklearn.cluster import KMeans

model = KMeans(n_clusters=3, random_state=42)

model.fit(X)

labels = model.labels_
```

---

# 14. Mini Project

1. Load the Mall Customers dataset.
2. Standardize the features.
3. Apply K-Means.
4. Use the Elbow Method.
5. Visualize the clusters.

---

# 15. Interview Questions

### What is Clustering?

An unsupervised learning technique that groups similar data points.

### Does Clustering require labels?

No.

### Name common clustering algorithms.

- K-Means
- Hierarchical Clustering
- DBSCAN
- Gaussian Mixture Models

### Why is distance important?

It determines how similarity is measured.

---

# 16. Summary

You learned:

- What Clustering is.
- Distance metrics.
- Types of clustering.
- Evaluation methods.
- Applications.

---

# 17. What's Next?

**Lesson 93 – K-Means Clustering**

You'll study centroids, initialization, inertia, convergence, the Elbow Method, and complete Scikit-Learn implementation.
