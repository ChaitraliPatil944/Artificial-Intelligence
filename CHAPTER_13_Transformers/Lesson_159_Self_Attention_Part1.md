# Lesson 159 --- Self Attention (Part 1)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# Learning Objectives

By the end of this part you will:

-   Understand what Self-Attention is.
-   Learn why it is the heart of Transformers.
-   Build intuition before learning the mathematics.
-   Prepare for the Query-Key-Value lessons.

------------------------------------------------------------------------

# Introduction

Imagine you are reading:

> **The animal didn't cross the street because it was too tired.**

When you read **it**, your brain automatically asks:

> Who is **it**?

You don't treat every previous word equally.

Instead, you **focus** on the important ones.

This focusing mechanism is called **Attention**.

When a sentence pays attention to **itself**, it is called
**Self-Attention**.

------------------------------------------------------------------------

# Why Do We Need Self-Attention?

RNNs remember information using one hidden state.

    Word1
      │
    Word2
      │
    Word3
      │
    Word4

Transformers do something completely different.

Every word communicates with every other word.

    Dog ───────── Cat
     │  ╲      ╱  │
     │   ╲    ╱   │
     │    ╲  ╱    │
    Chased  The  Quickly

Each word asks:

-   Which words are important?
-   Which words can I ignore?
-   How much importance should I give each word?

------------------------------------------------------------------------

# Child-Friendly Analogy

Imagine a classroom.

Teacher asks:

> "Who helped solve the science project?"

Every student looks around the room before answering.

    Student A ---> Student C
    Student B ---> Student C
    Student D ---> Student A

Everyone gathers information from everyone else.

That is Self-Attention.

------------------------------------------------------------------------

# Why "Self"?

Because the words attend only to **other words in the same sentence**.

Sentence:

    The cat drank milk.

Relationships:

    The  <----> cat

    cat  <----> drank

    drank <----> milk

No outside sentence is required.

------------------------------------------------------------------------

# Visualizing Self-Attention

Sentence:

    I love Artificial Intelligence

                     Intelligence
                     ↑     ↑
                     │     │
    I  ←────────────┼─────┘
    │               │
    │               │
    love ───────── Artificial

Every token can directly interact with every other token.

------------------------------------------------------------------------

# Why Is This Better?

Suppose two related words are far apart.

    Alice ....................................... she

An RNN must remember "Alice" across the entire sequence.

A Transformer directly connects them.

    Alice <===========================> she

Distance becomes much less important.

------------------------------------------------------------------------

# Real-World Example

Search engines do something similar.

When you search:

    Best AI books

The engine doesn't treat every page equally.

It gives more weight to pages that are more relevant.

Self-Attention gives more weight to important words.

------------------------------------------------------------------------

# Interview Questions

**Q:** What is Self-Attention?

**Answer:** A mechanism where each token learns which other tokens in
the same sequence are most relevant.

**Q:** Why is it called Self-Attention?

**Answer:** Because the attention is computed within the same input
sequence.

------------------------------------------------------------------------

# Key Takeaways

-   Self-Attention is the core building block of Transformers.
-   Every token communicates with every other token.
-   Important words receive higher attention.
-   Long-distance relationships become easier to learn.

------------------------------------------------------------------------

# Next Part

In Part 2 we'll discover how every word creates **Query**, **Key**, and
**Value** vectors, which power the Self-Attention mechanism.
