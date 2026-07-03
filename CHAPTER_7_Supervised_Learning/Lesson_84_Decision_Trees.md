
# Chapter 6 – Supervised Learning

# Lesson 84 – Decision Trees

> **Decision Trees are one of the most intuitive Machine Learning algorithms. They make predictions by asking a sequence of questions, just like how humans make decisions. They are easy to visualize, easy to interpret, and powerful enough to solve both classification and regression problems.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Decision Trees are.
- Learn why Decision Trees were developed.
- Understand tree structure and terminology.
- Learn Entropy, Gini Impurity, and Information Gain.
- Understand how Decision Trees are built.
- Learn pruning techniques.
- Build a Decision Tree using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is a Decision Tree?
2. Why Decision Trees were Invented
3. History
4. Tree Terminology
5. How a Decision Tree Works
6. Splitting Criteria
7. Entropy
8. Gini Impurity
9. Information Gain
10. Building a Decision Tree
11. Pruning
12. Feature Importance
13. Python Implementation
14. Advantages
15. Limitations
16. Real-World Applications
17. Mini Project
18. Interview Questions
19. Summary
20. What's Next?

---

# 1. What is a Decision Tree?

A Decision Tree is a supervised learning algorithm that predicts an outcome by repeatedly asking questions about the input data.

It works like a flowchart.

Example:

```
            Age > 30?
             /     \
          Yes       No
          /          \
 Income > 50K?     Reject
      /    \
   Yes      No
Approve    Reject
```

Each decision narrows the possibilities until a prediction is made.

---

# 2. Why Decision Trees were Invented

Many real-world decisions can be broken into a sequence of simple questions.

Examples:

- Should a loan be approved?
- Is an email spam?
- Does a patient have a disease?
- Should a customer receive a discount?

Decision Trees automate this process by learning the best sequence of questions from historical data.

---

# 3. History

Decision Trees originated in statistics and pattern recognition.

Popular algorithms include:

- ID3 (Iterative Dichotomiser 3)
- C4.5
- C5.0
- CART (Classification and Regression Trees)

Today, CART is the foundation of Scikit-Learn's Decision Tree implementation.

Timeline:

```
ID3
 │
 ▼
C4.5
 │
 ▼
C5.0
 │
 ▼
CART
 │
 ▼
Modern ML Libraries
```

---

# 4. Tree Terminology

### Root Node

The first decision.

```
      Root
```

### Internal Node

A decision point.

```
Age > 30?
```

### Leaf Node

Final prediction.

```
Approve
```

### Branch

Connection between nodes.

Complete structure:

```
        Root
       /    \
   Node     Node
   /  \      |
Leaf Leaf   Leaf
```

---

# 5. How a Decision Tree Works

Workflow:

```
Training Data
      │
Find Best Question
      │
Split Dataset
      │
Repeat
      │
Leaf Nodes
```

Example:

```
Customer

Income?

↓

High

↓

Credit Score?

↓

Approve
```

The tree continues splitting until a stopping condition is reached.

---

# 6. Splitting Criteria

The algorithm chooses the feature that best separates the data.

Common criteria:

- Entropy
- Information Gain
- Gini Impurity

The best split reduces uncertainty the most.

---

# 7. Entropy

Entropy measures disorder or uncertainty.

Formula:

```
Entropy = -Σ p log₂(p)
```

Interpretation:

```
All Same Class

Entropy = 0

Mixed Classes

Entropy = High
```

Example:

```
100% Cats

Entropy = 0

50% Cats
50% Dogs

Entropy = Maximum
```

Goal:

Choose splits that reduce entropy.

---

# 8. Gini Impurity

Gini measures how often a randomly selected sample would be incorrectly classified.

Formula:

```
Gini = 1 − Σ(p²)
```

Interpretation:

```
Pure Node

Gini = 0

Mixed Node

Higher Gini
```

Compared with Entropy:

| Entropy | Gini |
|----------|------|
| Slightly slower | Faster |
| Uses logarithms | Simpler calculation |
| Used by ID3/C4.5 | Used by CART |

---

# 9. Information Gain

Information Gain measures how much uncertainty decreases after a split.

Formula:

```
Information Gain

=

Parent Entropy

−

Weighted Child Entropy
```

Goal:

```
Highest Information Gain

↓

Best Split
```

ASCII:

```
Mixed Data

↓

Split

↓

Pure Groups
```

---

# 10. Building a Decision Tree

Algorithm:

```
Start

↓

Find Best Feature

↓

Split Data

↓

Repeat for Each Child

↓

Stop

↓

Leaf Node
```

Stopping conditions:

- Maximum depth reached
- Minimum samples reached
- Node becomes pure

---

# 11. Pruning

Large trees often overfit.

Pruning removes unnecessary branches.

### Pre-Pruning

Stop tree growth early.

Examples:

- max_depth
- min_samples_split

### Post-Pruning

Grow full tree first.

Remove branches that do not improve validation performance.

ASCII:

Before

```
Root
 │
Many Branches
 │
Leaves
```

After

```
Root
 │
Few Useful Branches
```

---

# 12. Feature Importance

Decision Trees estimate how useful each feature is.

Example:

```
Income

0.48

Age

0.32

Credit Score

0.20
```

Higher importance means the feature contributes more to predictions.

---

# 13. Python Implementation

```python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(
    criterion="gini",
    max_depth=5,
    random_state=42
)

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Visualize:

```python
from sklearn.tree import plot_tree
import matplotlib.pyplot as plt

plot_tree(model)
plt.show()
```

---

# 14. Advantages

- Easy to understand.
- Easy to visualize.
- Handles numerical and categorical data.
- Requires little preprocessing.
- Naturally performs feature selection.
- Works for classification and regression.

---

# 15. Limitations

- Can overfit easily.
- Sensitive to small changes in data.
- Individual trees may have lower accuracy than ensemble methods.
- Greedy splitting does not always produce the globally optimal tree.

---

# 16. Real-World Applications

Loan Approval

```
Income?

↓

Credit Score?

↓

Approve
```

Medical Diagnosis

```
Symptoms

↓

Disease?
```

Fraud Detection

```
Transaction

↓

Fraud?
```

Customer Churn

```
Customer Data

↓

Will Leave?
```

---

# 17. Mini Project

Predict loan approval.

Tasks:

1. Load a loan dataset.
2. Train a Decision Tree.
3. Visualize the tree.
4. Change `max_depth`.
5. Compare train and test accuracy.
6. Display feature importances.

---

# 18. Interview Questions

### What is a Decision Tree?

A supervised learning algorithm that predicts outcomes using a sequence of decision rules.

### What is Entropy?

A measure of uncertainty or impurity in a dataset.

### What is Gini Impurity?

A measure of how often a randomly selected sample would be incorrectly classified.

### What is Information Gain?

The reduction in entropy after splitting the data.

### Why is pruning necessary?

To reduce overfitting and improve generalization.

### Which algorithm does Scikit-Learn use?

CART (Classification and Regression Trees).

---

# 19. Summary

You learned:

- What Decision Trees are.
- Tree terminology.
- Entropy.
- Gini Impurity.
- Information Gain.
- Tree construction.
- Pruning.
- Feature importance.
- Python implementation.

---

# 20. What's Next?

**Lesson 85 – Random Forest**

You'll learn how combining hundreds of Decision Trees creates one of the most powerful supervised learning algorithms, including bagging, bootstrap sampling, random feature selection, out-of-bag error, feature importance, and why Random Forest often outperforms a single Decision Tree.
