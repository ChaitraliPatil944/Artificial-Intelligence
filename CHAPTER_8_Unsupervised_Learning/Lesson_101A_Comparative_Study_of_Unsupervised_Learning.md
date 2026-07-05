# Chapter 7 -- Unsupervised Learning

# Lesson 101A -- Comparative Study of Unsupervised Learning

> **Learning individual algorithms is useful. Knowing exactly when to
> use each one is what interviewers and real-world projects actually
> demand. This lesson compares every major unsupervised learning
> technique covered in Chapter 7.**

------------------------------------------------------------------------

# Learning Objectives

-   Compare clustering, dimensionality reduction, and association rule
    mining.
-   Learn when each algorithm should be used.
-   Understand strengths, weaknesses, and trade-offs.
-   Prepare for interview decision-making questions.

------------------------------------------------------------------------

# Table of Contents

1.  Why Comparative Study Matters
2.  Unsupervised Learning Family Tree
3.  Algorithm Categories
4.  Master Comparison Table
5.  Clustering Comparison
6.  Dimensionality Reduction Comparison
7.  Association Rule Mining
8.  Algorithm Selection Guide
9.  Time & Space Complexity
10. Industry Use Cases
11. Interview Decision Tree
12. Cheat Sheet
13. Interview Questions
14. Chapter Summary

------------------------------------------------------------------------

# 1. Why Comparative Study Matters

Real interview questions are usually:

-   Why choose DBSCAN over K-Means?
-   When is PCA better than t-SNE?
-   Why use UMAP instead of t-SNE?
-   When should Apriori be used?

Knowing **when** is as important as knowing **how**.

------------------------------------------------------------------------

# 2. Unsupervised Learning Family Tree

``` text
                 Unsupervised Learning
                         │
      ┌──────────────────┼──────────────────┐
      │                  │                  │
 Clustering     Dimensional Reduction  Association Rules
      │                  │                  │
 K-Means              PCA             Apriori
 Hierarchical         t-SNE
 DBSCAN               UMAP
```

------------------------------------------------------------------------

# 3. Algorithm Categories

  Category                   Goal                    Algorithms
  -------------------------- ----------------------- -------------------------------
  Clustering                 Group similar samples   K-Means, Hierarchical, DBSCAN
  Dimensionality Reduction   Reduce features         PCA, t-SNE, UMAP
  Association Mining         Find relationships      Apriori

------------------------------------------------------------------------

# 4. Master Comparison Table

  --------------------------------------------------------------------------------------
  Algorithm      Needs       Main Purpose    Handles         Visualization   Large Data
                 Labels                      Outliers                        
  -------------- ----------- --------------- --------------- --------------- -----------
  K-Means        ❌          Clustering      ❌              Moderate        Excellent

  Hierarchical   ❌          Clustering      Limited         Good            Moderate

  DBSCAN         ❌          Density         ✅              Good            Good
                             Clustering                                      

  PCA            ❌          Feature         ❌              Good            Excellent
                             Reduction                                       

  t-SNE          ❌          Visualization   Limited         Excellent       Moderate

  UMAP           ❌          Visualization & Limited         Excellent       Excellent
                             Embedding                                       

  Apriori        ❌          Association     N/A             N/A             Moderate
                             Rules                                           
  --------------------------------------------------------------------------------------

------------------------------------------------------------------------

# 5. Clustering Comparison

  Feature            K-Means            Hierarchical     DBSCAN
  ------------------ ------------------ ---------------- ----------------
  Need K             ✅                 ❌               ❌
  Arbitrary Shapes   ❌                 Moderate         ✅
  Detect Noise       ❌                 Limited          ✅
  Speed              Fast               Slow             Fast
  Best For           Compact clusters   Small datasets   Noisy datasets

------------------------------------------------------------------------

# 6. Dimensionality Reduction Comparison

  Feature            PCA         t-SNE       UMAP
  ------------------ ----------- ----------- -----------
  Linear             ✅          ❌          ❌
  Speed              Very Fast   Slow        Fast
  Visualization      Good        Excellent   Excellent
  Global Structure   Excellent   Limited     Good
  Local Structure    Moderate    Excellent   Excellent
  ML Pipeline        ✅          Rarely      Sometimes

------------------------------------------------------------------------

# 7. Association Rule Mining

Use Apriori when the goal is **relationships between items**, not
clustering.

``` text
Bread → Butter
Laptop → Mouse
Coffee → Sugar
```

------------------------------------------------------------------------

# 8. Algorithm Selection Guide

``` text
Need groups?
      │
      ├── Compact clusters → K-Means
      ├── Unknown shapes → DBSCAN
      └── Cluster hierarchy → Hierarchical

Need fewer features?
      │
      ├── Model preprocessing → PCA
      ├── Visualization → t-SNE
      └── Large visualization → UMAP

Need shopping patterns?
      │
      └── Apriori
```

------------------------------------------------------------------------

# 9. Time & Space Complexity

  Algorithm      Typical Complexity
  -------------- ------------------------
  K-Means        O(n × k × i × d)
  Hierarchical   O(n² log n)
  DBSCAN         O(n log n) (indexed)
  PCA            O(min(n²d, nd²))
  t-SNE          High / Expensive
  UMAP           Faster than t-SNE
  Apriori        Exponential worst case

------------------------------------------------------------------------

# 10. Industry Use Cases

  Problem                   Recommended Algorithm
  ------------------------- -----------------------
  Customer Segmentation     K-Means
  Fraud Detection           DBSCAN
  Gene Analysis             Hierarchical
  Image Compression         PCA
  Embedding Visualization   UMAP / t-SNE
  Market Basket Analysis    Apriori

------------------------------------------------------------------------

# 11. Interview Decision Tree

``` text
Need labels?
    │
    No
    │
Need groups?
 │         │
Yes       No
 │         │
Noise?   Reduce Features?
 │         │
DBSCAN   PCA
 │
No
 │
Need hierarchy?
 │
Yes → Hierarchical
No  → K-Means

Visualization?
 │
t-SNE / UMAP

Association Rules?
 │
Apriori
```

------------------------------------------------------------------------

# 12. Cheat Sheet

``` text
Compact clusters      → K-Means
Unknown cluster shape → DBSCAN
Hierarchy             → Hierarchical
Feature reduction     → PCA
Beautiful plots       → t-SNE
Fast embeddings       → UMAP
Shopping patterns     → Apriori
```

------------------------------------------------------------------------

# 13. Interview Questions

-   K-Means vs DBSCAN?
-   PCA vs t-SNE?
-   UMAP vs t-SNE?
-   Why use PCA before t-SNE?
-   When is Hierarchical Clustering preferred?
-   What is the Apriori Principle?

------------------------------------------------------------------------

# 14. Chapter Summary

You now understand not only **how** each unsupervised learning algorithm
works, but also **where each one fits**.

-   **K-Means**: Fast clustering for compact groups.
-   **Hierarchical**: Relationship discovery and dendrograms.
-   **DBSCAN**: Arbitrary shapes and outlier detection.
-   **PCA**: Linear dimensionality reduction.
-   **t-SNE**: High-quality visualization.
-   **UMAP**: Fast scalable visualization and embeddings.
-   **Apriori**: Association rule discovery.

This completes **Chapter 7 -- Unsupervised Learning** and provides a
practical revision guide for interviews and real-world model selection.
