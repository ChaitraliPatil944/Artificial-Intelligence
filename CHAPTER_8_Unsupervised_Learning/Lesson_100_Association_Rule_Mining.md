# Chapter 7 -- Unsupervised Learning

# Lesson 100 -- Association Rule Mining

> **Association Rule Mining is an unsupervised learning technique used
> to discover interesting relationships between items in large datasets.
> It is best known for Market Basket Analysis, where businesses identify
> products that are frequently purchased together.**

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will:

-   Understand Association Rule Mining.
-   Learn why it was invented.
-   Understand transactions, itemsets, and association rules.
-   Learn Support, Confidence, Lift, and Conviction.
-   Understand the rule generation process.
-   Prepare for the Apriori algorithm.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is Association Rule Mining?
2.  Why was it Invented?
3.  History
4.  Transactions & Itemsets
5.  Frequent Itemsets
6.  Association Rules
7.  Support
8.  Confidence
9.  Lift
10. Conviction
11. Rule Generation Workflow
12. Python Example
13. Advantages
14. Limitations
15. Real-World Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

------------------------------------------------------------------------

# 1. What is Association Rule Mining?

Association Rule Mining discovers relationships between items that
appear together.

``` text
Transaction Database
        │
Discover Patterns
        │
Association Rules
```

Example:

``` text
Bread → Butter
Milk  → Cereal
```

------------------------------------------------------------------------

# 2. Why was it Invented?

Retailers wanted answers like:

-   Which products are purchased together?
-   Which items should be placed nearby?
-   Which products should be recommended?

Association Rule Mining automates this discovery.

------------------------------------------------------------------------

# 3. History

``` text
Data Mining
     │
Market Basket Analysis
     │
Association Rule Mining
     │
Apriori Algorithm
```

It became popular in retail and later expanded into healthcare,
cybersecurity, and recommender systems.

------------------------------------------------------------------------

# 4. Transactions & Itemsets

### Transaction

``` text
T1 = {Bread, Butter, Milk}
```

### Itemset

A collection of one or more items.

``` text
{Bread, Butter}
```

------------------------------------------------------------------------

# 5. Frequent Itemsets

An itemset is **frequent** if it appears often enough in the dataset.

Example:

``` text
{Bread, Milk}

Appears in 80% of transactions

↓

Frequent Itemset
```

------------------------------------------------------------------------

# 6. Association Rules

General form:

``` text
A → B
```

Meaning:

> If A is purchased, B is likely to be purchased as well.

Example:

``` text
Bread → Butter
```

------------------------------------------------------------------------

# 7. Support

Support measures how often an itemset appears.

Formula:

``` text
Support(A)

=

Transactions containing A
-------------------------
Total Transactions
```

Example:

100 transactions

Bread appears in 40.

``` text
Support = 40 / 100 = 0.40
```

------------------------------------------------------------------------

# 8. Confidence

Confidence measures how often B occurs when A occurs.

Formula:

``` text
Confidence(A→B)

=

Support(A∪B)
------------
Support(A)
```

High confidence means the rule is reliable.

------------------------------------------------------------------------

# 9. Lift

Lift measures whether A and B occur together more often than expected by
chance.

Formula:

``` text
Lift

=

Confidence(A→B)
---------------
Support(B)
```

Interpretation:

-   Lift \> 1 → Positive relationship
-   Lift = 1 → Independent
-   Lift \< 1 → Negative relationship

------------------------------------------------------------------------

# 10. Conviction

Conviction measures the strength of an implication.

Higher conviction indicates a stronger rule.

It complements confidence and lift.

------------------------------------------------------------------------

# 11. Rule Generation Workflow

``` text
Transaction Data
        │
Find Frequent Itemsets
        │
Generate Rules
        │
Evaluate
Support
Confidence
Lift
        │
Strong Rules
```

------------------------------------------------------------------------

# 12. Python Example

``` python
from mlxtend.frequent_patterns import apriori
from mlxtend.frequent_patterns import association_rules

frequent = apriori(df,
                   min_support=0.2,
                   use_colnames=True)

rules = association_rules(
    frequent,
    metric="confidence",
    min_threshold=0.7
)

print(rules.head())
```

------------------------------------------------------------------------

# 13. Advantages

-   Discovers hidden relationships.
-   Useful for recommendation systems.
-   Easy to interpret.
-   Works without labels.

------------------------------------------------------------------------

# 14. Limitations

-   Computationally expensive on huge datasets.
-   Generates many insignificant rules.
-   Requires threshold tuning.

------------------------------------------------------------------------

# 15. Real-World Applications

-   Market Basket Analysis
-   Product Recommendation
-   Website Click Analysis
-   Medical Diagnosis Patterns
-   Cybersecurity Event Correlation

------------------------------------------------------------------------

# 16. Mini Project

1.  Load a grocery transactions dataset.
2.  Convert transactions into one-hot encoding.
3.  Generate frequent itemsets.
4.  Produce association rules.
5.  Rank rules using Lift.

------------------------------------------------------------------------

# 17. Interview Questions

### What is Association Rule Mining?

An unsupervised technique for discovering relationships among items.

### What is a transaction?

A single record containing purchased items.

### What is Support?

The frequency of an itemset in the dataset.

### What is Confidence?

The probability that B occurs when A occurs.

### What is Lift?

A measure of how much stronger a rule is than random chance.

------------------------------------------------------------------------

# 18. Summary

You learned:

-   Transactions
-   Itemsets
-   Association Rules
-   Support
-   Confidence
-   Lift
-   Conviction
-   Rule generation workflow

------------------------------------------------------------------------

# 19. What's Next?

**Lesson 101 -- Apriori Algorithm**

You'll learn how the Apriori algorithm efficiently discovers frequent
itemsets using the Apriori Principle, candidate generation, pruning, and
iterative search.
