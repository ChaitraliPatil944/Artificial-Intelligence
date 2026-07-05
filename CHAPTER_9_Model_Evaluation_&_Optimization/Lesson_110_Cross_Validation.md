# Chapter 8 -- Model Evaluation & Optimization

# Lesson 110 -- Cross Validation

> **Cross Validation is a model evaluation technique that estimates how
> well a machine learning model will perform on unseen data by
> repeatedly training and testing it on different subsets of the
> dataset. It provides a more reliable estimate than a single train-test
> split.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Cross Validation.
-   Learn why it was invented.
-   Understand K-Fold, Stratified K-Fold, LOOCV, Repeated K-Fold,
    Shuffle Split and Time Series CV.
-   Compare Cross Validation with Train/Test Split.
-   Prepare for interview questions.

------------------------------------------------------------------------

# Table of Contents

1.  What is Cross Validation?
2.  Why Cross Validation?
3.  Train/Test Split vs Cross Validation
4.  K-Fold Cross Validation
5.  Stratified K-Fold
6.  Leave-One-Out (LOOCV)
7.  Repeated K-Fold
8.  Shuffle Split
9.  Time Series Cross Validation
10. Choosing K
11. Advantages
12. Limitations
13. Python Implementation
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

------------------------------------------------------------------------

# 1. What is Cross Validation?

Instead of evaluating a model once, Cross Validation evaluates it
multiple times.

``` text
Dataset
   │
Split Multiple Ways
   │
Train + Test
   │
Average Score
```

------------------------------------------------------------------------

# 2. Why Cross Validation?

A single train/test split may be lucky or unlucky.

Cross Validation reduces this randomness.

------------------------------------------------------------------------

# 3. Train/Test Split vs Cross Validation

  Train/Test        Cross Validation
  ----------------- ------------------
  One split         Multiple splits
  Fast              Slower
  Less reliable     More reliable
  Higher variance   Lower variance

------------------------------------------------------------------------

# 4. K-Fold Cross Validation

Example with K = 5

``` text
Fold1 Test
Fold2 Train
Fold3 Train
Fold4 Train
Fold5 Train

↓

Repeat until every fold becomes the test set.
```

Final score:

``` text
Average of all folds
```

------------------------------------------------------------------------

# 5. Stratified K-Fold

Maintains the class distribution in every fold.

Useful for imbalanced datasets.

------------------------------------------------------------------------

# 6. Leave-One-Out Cross Validation (LOOCV)

``` text
100 Samples

Train = 99

Test = 1

Repeat 100 times
```

Very accurate but computationally expensive.

------------------------------------------------------------------------

# 7. Repeated K-Fold

Runs K-Fold multiple times using different random splits.

Produces a more stable estimate.

------------------------------------------------------------------------

# 8. Shuffle Split

Randomly creates train/test splits multiple times.

Useful when fixed folds are unnecessary.

------------------------------------------------------------------------

# 9. Time Series Cross Validation

Time-ordered data cannot be randomly shuffled.

``` text
Train → Test

Jan Feb Mar → Apr

Jan Feb Mar Apr → May
```

Always train on the past and test on the future.

------------------------------------------------------------------------

# 10. Choosing K

Typical values:

-   K = 5
-   K = 10

Smaller K:

-   Faster
-   Higher variance

Larger K:

-   Slower
-   Lower bias

------------------------------------------------------------------------

# 11. Advantages

-   Better estimate of model performance.
-   Reduces dependence on one split.
-   Better model selection.
-   Uses data efficiently.

------------------------------------------------------------------------

# 12. Limitations

-   Slower than a single split.
-   Expensive for large datasets.
-   Must choose the appropriate strategy.

------------------------------------------------------------------------

# 13. Python Implementation

``` python
from sklearn.model_selection import cross_val_score
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

scores = cross_val_score(model, X, y, cv=5)

print(scores)
print(scores.mean())
```

------------------------------------------------------------------------

# 14. Mini Project

1.  Train a Decision Tree.
2.  Evaluate using a train/test split.
3.  Evaluate using 5-Fold CV.
4.  Compare the results.
5.  Repeat with Random Forest.

------------------------------------------------------------------------

# 15. Interview Questions

### Why is Cross Validation better than a single train/test split?

It evaluates the model on multiple subsets, reducing dependence on one
random split.

### What is K-Fold?

A method where the dataset is divided into K parts and each part becomes
the test set once.

### When use Stratified K-Fold?

For imbalanced classification datasets.

### Why not shuffle time-series data?

It would leak future information into the training set.

------------------------------------------------------------------------

# 16. Summary

You learned:

-   Cross Validation fundamentals.
-   K-Fold.
-   Stratified K-Fold.
-   LOOCV.
-   Repeated K-Fold.
-   Shuffle Split.
-   Time Series Cross Validation.
-   Python implementation.

------------------------------------------------------------------------

# 17. What's Next?

**Lesson 111 -- Bias vs Variance**

You'll learn the fundamental trade-off behind every machine learning
model, understand underfitting and overfitting from first principles,
and discover why finding the right balance is the key to building models
that generalize well.
