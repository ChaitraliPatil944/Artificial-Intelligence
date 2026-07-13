# Lesson 159 --- Self Attention (Part 3)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# Learning Objectives

By the end of this part you will:

-   Understand the mathematics behind Self-Attention.
-   Learn dot products, attention scores, and Softmax intuitively.
-   Work through a simple numerical example.
-   See how the Self-Attention equation is built.

------------------------------------------------------------------------

# The Self-Attention Pipeline

    Input Tokens
         │
         ▼
    Create Query (Q), Key (K), Value (V)
         │
         ▼
    Q × Kᵀ
         │
         ▼
    Attention Scores
         │
         ▼
    Softmax
         │
         ▼
    Attention Weights
         │
         ▼
    Weights × Values
         │
         ▼
    New Token Representation

------------------------------------------------------------------------

# Step 1: Create Q, K and V

Suppose the sentence is:

    I love AI

Each word becomes three vectors.

    I      → Q₁ K₁ V₁
    love   → Q₂ K₂ V₂
    AI     → Q₃ K₃ V₃

These vectors are learned during training.

------------------------------------------------------------------------

# Step 2: Compare Query with Every Key

Imagine we are processing:

    love

Its Query is compared with every Key.

    Q(love)

    │

    ├── K(I)

    ├── K(love)

    └── K(AI)

The comparison uses the **dot product**.

------------------------------------------------------------------------

# What is a Dot Product?

A dot product measures similarity.

For two vectors:

    A = [2, 3]

    B = [4, 1]

    A · B

    = (2×4) + (3×1)

    = 8 + 3

    = 11

Larger values generally indicate greater similarity.

------------------------------------------------------------------------

# Example Attention Scores

Suppose:

    love

    compares with

    I

    love

    AI

Scores:

    I      → 1.2

    love   → 2.8

    AI     → 3.9

These are raw scores.

They are not probabilities yet.

------------------------------------------------------------------------

# Step 3: Softmax

Softmax converts scores into probabilities.

Before Softmax:

    1.2

    2.8

    3.9

After Softmax (illustrative):

    0.05

    0.27

    0.68

Notice:

    0.05 + 0.27 + 0.68 = 1

Now we know how much attention each word receives.

------------------------------------------------------------------------

# Step 4: Weight the Values

Every Value is multiplied by its attention weight.

    0.05 × V(I)

    +

    0.27 × V(love)

    +

    0.68 × V(AI)

These are added together to create the new representation of **love**.

------------------------------------------------------------------------

# Complete Equation

The Self-Attention equation is:

    Attention(Q,K,V)

    =

    Softmax(QKᵀ)

    ×

    V

The complete Transformer later adds a scaling factor:

                QKᵀ
    Softmax( -------- )

                √dₖ

    ×

    V

The scaling term will be studied in Lesson 162.

------------------------------------------------------------------------

# Intuition

Think of a group discussion.

    Question

    ↓

    Who has the best answer?

    ↓

    Listen mostly to them

    ↓

    Combine everyone's useful ideas

Self-Attention behaves the same way.

------------------------------------------------------------------------

# Worked Mini Example

Sentence:

    Cats chase mice

Processing:

    chase

Similarity scores:

    Cats  → 0.80

    chase → 0.10

    mice  → 0.95

After Softmax:

    Cats  → 0.41

    chase → 0.21

    mice  → 0.38

The updated representation for **chase** is mainly influenced by
**Cats** and **mice**, because they carry the most relevant information.

------------------------------------------------------------------------

# Interview Questions

### Why use Softmax?

It converts arbitrary similarity scores into probabilities that sum to
one.

### Why use the dot product?

It provides a simple and efficient measure of similarity between Query
and Key vectors.

### What does the output of Self-Attention represent?

A new context-aware representation of each token.

------------------------------------------------------------------------

# Key Takeaways

-   Queries search for information.
-   Keys describe available information.
-   Dot products measure similarity.
-   Softmax creates attention weights.
-   Values are combined using those weights.
-   The result is a context-aware embedding.

------------------------------------------------------------------------

# Next Part

Part 4 will cover:

-   Python implementation
-   Time complexity
-   Advantages and limitations
-   Multi-Head intuition
-   Interview cheat sheet
-   Revision notes
