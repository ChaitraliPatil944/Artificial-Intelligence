# Lesson 158 --- Why Transformers Replaced RNNs (Part 2)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# From RNN Thinking to Transformer Thinking

In Part 1, we saw **why RNNs struggle**:

-   Long-term dependencies
-   Vanishing gradients
-   Sequential processing
-   Poor GPU utilization

Now we'll understand **how Transformers solve these problems**.

------------------------------------------------------------------------

# The Fundamental Shift

An RNN thinks like this:

    Word1
      │
    Word2
      │
    Word3
      │
    Word4

Each word waits for the previous one.

A Transformer thinks differently:

               Word1
              ↗ ↑ ↖
    Word2 ←→ Word3 ←→ Word4
              ↘ ↓ ↙
               Word5

Every word can directly interact with every other word.

------------------------------------------------------------------------

# Why Sequential Processing is Slow

Imagine a sentence with 1,000 words.

An RNN performs something like:

    Step 1
    ↓

    Step 2
    ↓

    Step 3
    ↓

    ...

    ↓

    Step 1000

You cannot compute Step 1000 until Step 999 finishes.

Training takes longer because computations cannot happen simultaneously.

------------------------------------------------------------------------

# GPU Parallelism

Modern GPUs contain thousands of small processing cores.

Example:

    GPU

    □□□□□□□□□□□□□□□□□□□□

    Thousands of cores

GPUs are designed to execute many operations at once.

Transformers take advantage of this by processing all tokens together.

    Token1 ─┐
    Token2 ─┤
    Token3 ─┤
    Token4 ─┤
    Token5 ─┘

    ↓

    Processed Together

------------------------------------------------------------------------

# Long-Term Dependency Problem

Consider:

> "The girl who won the robotics competition after months of preparation
> proudly accepted her medal."

The word **her** refers to **girl**.

RNN:

    Girl ---------------------------> her

    Memory

    █████████
    ██████
    ████
    ██
    █

Transformer:

    Girl <=========================> her

    Direct Connection

Distance no longer matters.

------------------------------------------------------------------------

# The Revolutionary Idea

Instead of remembering everything through one hidden state, let every
word decide:

> "Which other words are important for me?"

This idea became **Attention**.

    Dog
     │
     ├────► chased
     │
     ├────► the
     │
     └────► cat

Each token assigns importance to other tokens.

------------------------------------------------------------------------

# Why This Was a Breakthrough

Instead of compressing an entire sentence into one memory vector:

    Sentence

    ↓

    One Hidden State

Transformers keep information distributed across all tokens.

    Word1

    Word2

    Word3

    Word4

    ↓

    All communicate through Attention

Information is not forced through a narrow bottleneck.

------------------------------------------------------------------------

# Complexity Comparison

  Model         Sequential   Parallel   Long Context
  ------------- ------------ ---------- --------------
  RNN           Yes          No         Poor
  LSTM          Yes          No         Better
  GRU           Yes          No         Better
  Transformer   No           Yes        Excellent

------------------------------------------------------------------------

# Real-World Analogy

Imagine building a bridge.

### RNN

One worker.

    Worker

    ↓

    Brick 1

    ↓

    Brick 2

    ↓

    Brick 3

### Transformer

Hundreds of workers.

    Worker Worker Worker Worker

    ↓

    Many bricks laid simultaneously

Same bridge.

Much faster.

------------------------------------------------------------------------

# Why Google Built Transformers

Google Translate had become increasingly difficult to improve using
RNNs.

Researchers needed:

-   Faster training
-   Better translations
-   Better long-range understanding
-   Better GPU utilization

The answer was the Transformer architecture published in 2017.

------------------------------------------------------------------------

# Interview Questions

### Why are Transformers faster than RNNs?

**Answer:** They process all tokens simultaneously instead of
sequentially.

### Why do Transformers perform better on long documents?

**Answer:** Attention allows direct interaction between distant words
without relying on a fading hidden state.

### What is the biggest conceptual difference?

**Answer:** RNNs carry information forward through recurrence, while
Transformers connect tokens directly using attention.

------------------------------------------------------------------------

# Key Takeaways

-   Transformers remove recurrence.
-   All tokens are processed in parallel.
-   Long-distance relationships become easy to learn.
-   GPUs are used much more efficiently.
-   Attention becomes the core building block.

------------------------------------------------------------------------

# Next Part

In **Part 3**, we'll study **Attention** itself, understand why it
works, and build intuition for **Self-Attention**, the heart of every
Transformer.
