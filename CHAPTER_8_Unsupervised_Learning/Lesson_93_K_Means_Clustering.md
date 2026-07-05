
# Chapter 7 – Unsupervised Learning

# Lesson 93 – K-Means Clustering

> **K-Means is the most popular clustering algorithm in Machine Learning. It groups similar data points into K clusters by repeatedly assigning points to the nearest centroid and updating the centroid positions until the clusters stabilize.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what K-Means is.
- Learn why K-Means was invented.
- Understand centroids and cluster formation.
- Learn the complete K-Means algorithm.
- Understand inertia, convergence, and the Elbow Method.
- Implement K-Means using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is K-Means?
2. Why K-Means was Invented
3. History
4. Key Terminology
5. How K-Means Works
6. Initialization Methods
7. Assignment Step
8. Update Step
9. Convergence
10. Inertia
11. Choosing K (Elbow Method)
12. Silhouette Score
13. Time Complexity
14. Python Implementation
15. Advantages
16. Limitations
17. Real-World Applications
18. Mini Project
19. Interview Questions
20. Summary
21. What's Next?

---

# 1. What is K-Means?

K-Means is an **unsupervised clustering algorithm** that partitions data into **K clusters**.

```
Raw Data
   │
Choose K
   │
Assign Points
   │
Update Centers
   │
Repeat
   │
Clusters
```

---

# 2. Why K-Means was Invented

Organizations often have data but no labels.

Examples:

- Customer segmentation
- Product grouping
- Image compression

K-Means automatically discovers natural groups.

---

# 3. History

K-Means became popular through work by Stuart Lloyd in the 1950s and later improvements by researchers in statistics and pattern recognition.

```
Pattern Recognition
        │
   Lloyd's Algorithm
        │
     K-Means
        │
 Modern Data Mining
```

---

# 4. Key Terminology

### Cluster

A group of similar data points.

### Centroid

The center of a cluster.

```
● ● ●
  X
● ●
```

`X` represents the centroid.

### K

The number of clusters chosen before training.

---

# 5. How K-Means Works

```
Step 1: Choose K

↓

Step 2: Initialize K Centroids

↓

Step 3: Assign each point to nearest centroid

↓

Step 4: Compute new centroids

↓

Repeat until centroids stop moving
```

---

# 6. Initialization Methods

## Random Initialization

Randomly choose K points.

Simple but may produce poor clusters.

## K-Means++

Chooses initial centroids more intelligently.

Benefits:

- Faster convergence
- Better final clusters

Scikit-Learn uses **K-Means++** by default.

---

# 7. Assignment Step

Each point joins the nearest centroid.

```
Centroid A

● ● ●

Centroid B

○ ○ ○

New Point

↓

Nearest = A
```

Distance is usually measured using Euclidean distance.

---

# 8. Update Step

After assignment:

```
Old Centroid

↓

Average of Cluster Points

↓

New Centroid
```

The centroid moves to the center of its assigned points.

---

# 9. Convergence

The algorithm stops when:

- Centroids no longer move.
- Maximum iterations reached.
- Improvement becomes negligible.

```
Iteration 1

↓

Iteration 2

↓

Iteration 3

↓

Stable
```

---

# 10. Inertia

Inertia is the **Within-Cluster Sum of Squares (WCSS)**.

It measures how close data points are to their centroids.

```
Lower Inertia

↓

Better Compact Clusters
```

Goal:

Minimize inertia.

---

# 11. Choosing K (Elbow Method)

Run K-Means with different values of K.

Plot:

```
Inertia
|
|| |  |   \__
|      \____
+-------------> K
```

The "elbow" indicates a good value of K.

---

# 12. Silhouette Score

Measures cluster quality.

Range:

```
-1  --------  0 -------- +1
```

- Close to +1 → Good clusters
- Around 0 → Overlapping clusters
- Below 0 → Poor clustering

---

# 13. Time Complexity

Approximate complexity:

```
O(n × k × i × d)
```

Where:

- n = samples
- k = clusters
- i = iterations
- d = features

---

# 14. Python Implementation

```python
from sklearn.cluster import KMeans

model = KMeans(
    n_clusters=3,
    init="k-means++",
    random_state=42
)

model.fit(X)

labels = model.labels_
centroids = model.cluster_centers_

print(model.inertia_)
```

---

# 15. Advantages

- Easy to understand.
- Fast.
- Scales well.
- Works well for compact clusters.

---

# 16. Limitations

- Must choose K beforehand.
- Sensitive to outliers.
- Assumes roughly spherical clusters.
- Depends on initialization.

---

# 17. Real-World Applications

- Customer segmentation
- Image compression
- Document clustering
- Market segmentation
- Recommendation systems

---

# 18. Mini Project

1. Load the Mall Customers dataset.
2. Scale the features.
3. Try K = 2 to 10.
4. Plot the Elbow Curve.
5. Train the final model.
6. Visualize the clusters.

---

# 19. Interview Questions

### What is K-Means?

An unsupervised clustering algorithm that partitions data into K groups.

### Why is K-Means called "K-Means"?

Because it creates **K** clusters whose centers are the **means** of their assigned points.

### What is a centroid?

The average position of all points in a cluster.

### What is inertia?

The total squared distance between data points and their assigned centroids.

### What is the Elbow Method?

A technique to choose an appropriate value of K by analyzing inertia.

### What is K-Means++?

An improved centroid initialization strategy.

---

# 20. Summary

You learned:

- What K-Means is.
- Centroids.
- Assignment and update steps.
- Convergence.
- Inertia.
- Elbow Method.
- Silhouette Score.
- Python implementation.

---

# 21. What's Next?

**Lesson 94 – Hierarchical Clustering**

You'll learn how hierarchical clustering builds nested clusters, understand dendrograms, agglomerative vs divisive clustering, linkage methods, and how it differs from K-Means.
