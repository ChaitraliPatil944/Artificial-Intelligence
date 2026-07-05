# Chapter 8 -- Model Evaluation & Optimization

# Lesson 116 -- Grid Search

> **Grid Search is an exhaustive hyperparameter optimization technique
> that systematically tries every possible combination of hyperparameter
> values from a predefined search space. It is one of the most widely
> used methods for selecting the best machine learning model
> configuration.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Grid Search.
-   Learn why it was developed.
-   Understand exhaustive search.
-   Learn how GridSearchCV works.
-   Understand computational cost.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Grid Search?
2.  Why Grid Search?
3.  Search Space
4.  How Grid Search Works
5.  GridSearchCV
6.  Computational Complexity
7.  Advantages
8.  Limitations
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Grid Search?

Grid Search evaluates **every possible combination** of selected
hyperparameter values.

``` text
Hyperparameters
      │
Generate All Combinations
      │
Train Model
      │
Evaluate
      │
Best Combination
```

------------------------------------------------------------------------

# 2. Why Grid Search?

Manual tuning becomes impractical when several hyperparameters are
involved.

Grid Search automates this process by systematically exploring the
search space.

------------------------------------------------------------------------

# 3. Search Space

Example:

``` text
max_depth

3
5
7

n_estimators

100
200
```

Possible combinations:

``` text
(3,100)
(3,200)
(5,100)
(5,200)
(7,100)
(7,200)
```

Every combination will be evaluated.

------------------------------------------------------------------------

# 4. How Grid Search Works

``` text
Choose Hyperparameter Grid
         │
Generate All Combinations
         │
Train Model
         │
Cross Validation
         │
Average Scores
         │
Select Best Model
```

------------------------------------------------------------------------

# 5. GridSearchCV

Grid Search is commonly combined with Cross Validation.

Benefits:

-   More reliable evaluation.
-   Less dependent on a single split.

------------------------------------------------------------------------

# 6. Computational Complexity

Suppose:

``` text
5 values for max_depth

4 values for learning_rate

3 values for n_estimators
```

Total models:

``` text
5 × 4 × 3 = 60
```

With 5-fold Cross Validation:

``` text
60 × 5 = 300 trainings
```

Grid Search becomes expensive as the search space grows.

------------------------------------------------------------------------

# 7. Advantages

-   Finds the best combination within the grid.
-   Simple to understand.
-   Reproducible.
-   Integrates naturally with Cross Validation.

------------------------------------------------------------------------

# 8. Limitations

-   Computationally expensive.
-   Slow for many hyperparameters.
-   May miss good values outside the predefined grid.

------------------------------------------------------------------------

# 9. Python Example

``` python
from sklearn.model_selection import GridSearchCV
from sklearn.ensemble import RandomForestClassifier

params = {
    "n_estimators": [100, 200],
    "max_depth": [5, 10]
}

grid = GridSearchCV(
    RandomForestClassifier(),
    param_grid=params,
    cv=5,
    scoring="accuracy"
)

grid.fit(X_train, y_train)

print(grid.best_params_)
print(grid.best_score_)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a Random Forest.
2.  Define a parameter grid.
3.  Run GridSearchCV.
4.  Compare default and tuned models.
5.  Explain the improvement.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Grid Search?

An exhaustive search over every hyperparameter combination.

### Why combine it with Cross Validation?

To obtain more reliable performance estimates.

### What is the biggest limitation?

Computational cost increases rapidly as the search space grows.

### Does Grid Search always find the globally best hyperparameters?

Only within the predefined grid.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   What Grid Search is.
-   How exhaustive search works.
-   GridSearchCV.
-   Search spaces.
-   Advantages and limitations.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 117 -- Random Search**

You'll learn why Random Search often outperforms Grid Search on large
search spaces, understand stochastic sampling, compare efficiency, and
see why many practitioners prefer it for real-world hyperparameter
optimization.
