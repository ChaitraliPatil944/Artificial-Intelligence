# Chapter 8 -- Model Evaluation & Optimization

# Lesson 117 -- Random Search

> **Random Search is a hyperparameter optimization technique that
> randomly samples combinations of hyperparameters instead of testing
> every possible combination. Despite its simplicity, it often finds
> excellent models with much less computation than Grid Search.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Random Search.
-   Learn why it was introduced.
-   Compare it with Grid Search.
-   Learn how `RandomizedSearchCV` works.
-   Understand computational efficiency.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Random Search?
2.  Why Random Search?
3.  Random Search Workflow
4.  Search Distributions
5.  RandomizedSearchCV
6.  Grid Search vs Random Search
7.  Advantages
8.  Limitations
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Random Search?

Instead of evaluating every hyperparameter combination, Random Search
evaluates only a **random subset**.

``` text
Search Space
      │
Random Samples
      │
Train & Evaluate
      │
Best Configuration
```

------------------------------------------------------------------------

# 2. Why Random Search?

Grid Search becomes expensive as the number of hyperparameters grows.

Many hyperparameters have only a small effect on performance.

Random Search spends computation exploring **more unique regions**
instead of exhaustively checking every combination.

------------------------------------------------------------------------

# 3. Random Search Workflow

``` text
Define Search Space
        │
Randomly Sample
        │
Train Model
        │
Cross Validation
        │
Keep Best Result
```

------------------------------------------------------------------------

# 4. Search Distributions

Unlike Grid Search, Random Search can sample from distributions.

Examples:

``` text
Learning Rate

0.0001 → 0.1
```

``` text
Tree Depth

2 → 20
```

Each iteration selects random values.

------------------------------------------------------------------------

# 5. RandomizedSearchCV

`RandomizedSearchCV` performs Random Search with Cross Validation.

You specify:

-   Parameter distributions
-   Number of iterations
-   Cross-validation folds
-   Evaluation metric

------------------------------------------------------------------------

# 6. Grid Search vs Random Search

  Feature                   Grid Search   Random Search
  ------------------------- ------------- -----------------
  Strategy                  Exhaustive    Random Sampling
  Speed                     Slower        Faster
  Large Search Space        Poor          Good
  Guarantees Best in Grid   Yes           No
  Explores More Regions     Limited       Better

------------------------------------------------------------------------

# 7. Advantages

-   Faster than Grid Search.
-   Scales to large search spaces.
-   Works well with continuous hyperparameters.
-   Often finds near-optimal solutions.

------------------------------------------------------------------------

# 8. Limitations

-   No guarantee of finding the absolute best combination.
-   Results depend on the number of iterations.
-   Randomness can produce slightly different outcomes.

------------------------------------------------------------------------

# 9. Python Example

``` python
from sklearn.model_selection import RandomizedSearchCV
from sklearn.ensemble import RandomForestClassifier
from scipy.stats import randint

params = {
    "n_estimators": randint(100, 500),
    "max_depth": randint(3, 20)
}

search = RandomizedSearchCV(
    RandomForestClassifier(),
    param_distributions=params,
    n_iter=20,
    cv=5,
    random_state=42
)

search.fit(X_train, y_train)

print(search.best_params_)
print(search.best_score_)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a Random Forest.
2.  Run Grid Search.
3.  Run Random Search with the same budget.
4.  Compare runtime.
5.  Compare validation scores.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Random Search?

A hyperparameter optimization method that evaluates randomly selected
parameter combinations.

### Why can Random Search outperform Grid Search?

Because it explores a wider variety of parameter values using the same
computational budget.

### When should you prefer Random Search?

When the search space is large or contains continuous-valued
hyperparameters.

### Does Random Search guarantee the best hyperparameters?

No. It trades exhaustive search for computational efficiency.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Random Search fundamentals.
-   Search distributions.
-   RandomizedSearchCV.
-   Comparison with Grid Search.
-   Advantages and limitations.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 118 -- Bayesian Optimization**

You'll learn how Bayesian Optimization uses previous evaluations to
intelligently choose the next hyperparameters to test, making it one of
the most efficient optimization techniques for expensive machine
learning models.
