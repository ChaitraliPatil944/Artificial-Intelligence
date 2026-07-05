# Chapter 7 -- Unsupervised Learning

# Lesson 101 -- Apriori Algorithm

> **The Apriori Algorithm is one of the most influential algorithms in
> data mining. It efficiently discovers frequent itemsets and
> association rules by eliminating impossible candidates early using the
> Apriori Principle.**

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will:

-   Understand the Apriori Algorithm.
-   Learn the Apriori Principle.
-   Understand candidate generation and pruning.
-   Generate frequent itemsets.
-   Build association rules.
-   Implement Apriori in Python.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is Apriori?
2.  Why Apriori was Invented
3.  History
4.  The Apriori Principle
5.  Key Terminology
6.  How Apriori Works
7.  Candidate Generation
8.  Pruning
9.  Example Walkthrough
10. Time Complexity
11. Apriori vs FP-Growth
12. Python Implementation
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

------------------------------------------------------------------------

# 1. What is Apriori?

Apriori is an **unsupervised learning algorithm** used to discover
**frequent itemsets** from transaction data.

``` text
Transactions
      │
Find Frequent Itemsets
      │
Generate Rules
```

It forms the foundation of many recommendation systems.

------------------------------------------------------------------------

# 2. Why Apriori was Invented

A supermarket may have millions of transactions.

Checking every possible item combination would be computationally
impossible.

Apriori dramatically reduces the search space.

------------------------------------------------------------------------

# 3. History

Apriori was introduced in 1994 by **Rakesh Agrawal** and **Ramakrishnan
Srikant**.

``` text
Market Basket Analysis
        │
Association Rules
        │
Apriori
        │
Modern Data Mining
```

------------------------------------------------------------------------

# 4. The Apriori Principle

The key idea:

> **If an itemset is infrequent, every larger itemset containing it must
> also be infrequent.**

Example:

``` text
{Bread, Eggs}

↓

Not Frequent

↓

{Bread, Eggs, Milk}

Cannot be Frequent
```

This simple rule eliminates enormous numbers of candidates.

------------------------------------------------------------------------

# 5. Key Terminology

-   **Transaction**: One purchase record.
-   **Itemset**: A group of items.
-   **Frequent Itemset**: Appears above the minimum support threshold.
-   **Candidate Itemset**: A possible frequent itemset awaiting
    evaluation.

------------------------------------------------------------------------

# 6. How Apriori Works

``` text
Transactions
      │
Generate 1-itemsets
      │
Remove Infrequent Ones
      │
Generate 2-itemsets
      │
Prune
      │
Generate 3-itemsets
      │
Repeat
      │
Association Rules
```

------------------------------------------------------------------------

# 7. Candidate Generation

Example:

Frequent 1-itemsets:

``` text
Bread
Milk
Butter
```

Generate candidates:

``` text
{Bread, Milk}
{Bread, Butter}
{Milk, Butter}
```

------------------------------------------------------------------------

# 8. Pruning

Before counting support, Apriori removes impossible candidates.

``` text
Candidate

{Bread, Eggs, Milk}

↓

Subset

{Bread, Eggs}

↓

Infrequent

↓

Discard Candidate
```

------------------------------------------------------------------------

# 9. Example Walkthrough

Transactions:

``` text
T1 = Bread Milk
T2 = Bread Butter
T3 = Bread Milk Butter
T4 = Milk Butter
```

Minimum Support = 50%

Frequent 1-itemsets:

``` text
Bread
Milk
Butter
```

Frequent 2-itemsets:

``` text
Bread Milk
Bread Butter
Milk Butter
```

Rules:

``` text
Bread → Milk

Milk → Butter
```

------------------------------------------------------------------------

# 10. Time Complexity

Worst case:

``` text
O(2ⁿ)
```

because every possible itemset may need evaluation.

Pruning greatly reduces practical computation.

------------------------------------------------------------------------

# 11. Apriori vs FP-Growth

  Feature                   Apriori   FP-Growth
  ------------------------- --------- -----------
  Candidate Generation      Yes       No
  Multiple Database Scans   Yes       Fewer
  Speed                     Slower    Faster
  Memory Usage              Higher    Lower

------------------------------------------------------------------------

# 12. Python Implementation

``` python
from mlxtend.frequent_patterns import apriori
from mlxtend.frequent_patterns import association_rules

frequent = apriori(
    df,
    min_support=0.3,
    use_colnames=True
)

rules = association_rules(
    frequent,
    metric="lift",
    min_threshold=1.2
)

print(rules)
```

------------------------------------------------------------------------

# 13. Advantages

-   Easy to understand.
-   Generates interpretable rules.
-   Powerful for market basket analysis.
-   Widely used in education and industry.

------------------------------------------------------------------------

# 14. Limitations

-   Multiple database scans.
-   Slow on very large datasets.
-   Candidate generation can explode with many items.

------------------------------------------------------------------------

# 15. Real-World Applications

-   Product recommendations
-   Retail shelf arrangement
-   Medical symptom associations
-   Fraud pattern discovery
-   Website click analysis

------------------------------------------------------------------------

# 16. Mini Project

1.  Load a grocery transaction dataset.
2.  One-hot encode transactions.
3.  Run Apriori.
4.  Generate association rules.
5.  Rank rules by Lift.

------------------------------------------------------------------------

# 17. Interview Questions

### What is Apriori?

An algorithm for discovering frequent itemsets and association rules.

### What is the Apriori Principle?

If an itemset is infrequent, every superset is also infrequent.

### Why is pruning important?

It removes impossible candidates early, reducing computation.

### Why is FP-Growth often faster?

Because it avoids explicit candidate generation.

------------------------------------------------------------------------

# 18. Summary

You learned:

-   Apriori Principle
-   Candidate generation
-   Pruning
-   Frequent itemsets
-   Association rules
-   Python implementation

------------------------------------------------------------------------

# 19. What's Next?

**Lesson 101A -- Comparative Study of Unsupervised Learning**

You'll compare K-Means, Hierarchical Clustering, DBSCAN, PCA, t-SNE,
UMAP, and Apriori, learning exactly when each technique should be used
in interviews and real-world projects.
