# Lesson 158 --- Why Transformers Replaced RNNs (Part 3)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# Learning Objectives

In this part, you will learn:

-   Why Attention changed Deep Learning forever
-   How the Transformer thinks differently from an RNN
-   Why every modern Large Language Model (LLM) uses Transformers
-   How Attention naturally leads to Self-Attention (Lesson 159)

------------------------------------------------------------------------

# A Different Way of Thinking

Imagine you are reading the sentence:

> **The cat sat on the mat because it was tired.**

To understand the word **"it"**, your brain immediately asks:

> **Who is "it"?**

Your brain doesn't reread every previous word one by one.

Instead, it instantly focuses on the most relevant words.

    The   cat   sat   on   the   mat   because   it   was   tired
            ↑                                │
            └────────────────────────────────┘

This ability to focus is exactly what inspired **Attention**.

------------------------------------------------------------------------

# RNN Memory vs Transformer Attention

## RNN

    Word1
      │
    Word2
      │
    Word3
      │
    Word4
      │
    Word5

Information must travel through every hidden state.

If something is forgotten halfway, it is lost forever.

------------------------------------------------------------------------

## Transformer

    Word1 ─────────────┐
     │                 │
     │                 ▼
    Word5 ◄──────── Word3
     ▲                 ▲
     │                 │
     └────── Word2 ────┘

Every word can directly communicate with any other word.

No long memory chain is required.

------------------------------------------------------------------------

# Why This is Powerful

Suppose a document contains **10,000 words**.

An RNN tries to remember information through one evolving memory.

    Input

    ↓

    Hidden State

    ↓

    Hidden State

    ↓

    Hidden State

    ↓

    Output

A Transformer keeps every token available and lets Attention decide what
matters.

    Token1
    Token2
    Token3
    Token4
    ...

    ↓

    Attention

    ↓

    Relevant Information

Instead of remembering everything,

it simply **looks where it needs to look.**

------------------------------------------------------------------------

# Human Brain Analogy

Imagine studying for an exam.

### RNN Method

You try to memorize the entire textbook.

    Page1

    ↓

    Page2

    ↓

    Page3

    ↓

    ...

    ↓

    Exam

Very difficult.

------------------------------------------------------------------------

### Transformer Method

Instead of memorizing everything,

you use bookmarks.

    Question

    ↓

    Relevant Chapter

    ↓

    Relevant Page

    ↓

    Relevant Paragraph

You immediately access the important information.

Attention works similarly.

------------------------------------------------------------------------

# The Birth of Attention

Researchers realized something surprising.

Instead of asking

> "Can the network remember everything?"

they asked

> "Can the network learn what to focus on?"

That small change completely transformed Deep Learning.

Instead of storing more memory,

they improved **information retrieval**.

------------------------------------------------------------------------

# Why This Matters for Modern AI

Nearly every modern AI system is built on Transformers.

Examples include:

    Transformer

    ├── GPT
    ├── BERT
    ├── LLaMA
    ├── Gemini
    ├── Claude
    ├── Mistral
    ├── T5
    ├── ViT
    └── Stable Diffusion (uses Transformer components)

Understanding Transformers means understanding the foundation of today's
AI revolution.

------------------------------------------------------------------------

# Computational Perspective

Suppose we have 6 words.

### RNN

    Time

    Word1

    ↓

    Word2

    ↓

    Word3

    ↓

    Word4

    ↓

    Word5

    ↓

    Word6

Total execution depends on previous computations.

------------------------------------------------------------------------

### Transformer

    Word1 ─┐

    Word2 ─┤

    Word3 ─┤

    Word4 ─┤

    Word5 ─┤

    Word6 ─┘

    ↓

    Parallel Processing

This is why training that once took weeks became dramatically faster.

------------------------------------------------------------------------

# Intuition Before Self-Attention

Imagine every word asking:

    Who should I pay attention to?

    How important are they?

    Should I ignore some words?

    Should I focus strongly on others?

Those three simple questions are the foundation of Self-Attention.

In the next lesson, we'll discover how Transformers answer them
mathematically.

------------------------------------------------------------------------

# Interview Questions

### Q1. Why is Attention better than memory?

**Answer:** It retrieves relevant information directly instead of
forcing the model to remember everything.

------------------------------------------------------------------------

### Q2. Why are Transformers considered scalable?

**Answer:** They process tokens in parallel and make efficient use of
GPUs.

------------------------------------------------------------------------

### Q3. What is the biggest conceptual change introduced by Transformers?

**Answer:** Replacing recurrence with Attention.

------------------------------------------------------------------------

# Summary

In this part, we learned:

-   Attention replaces long-term memory.
-   Every token can communicate directly with every other token.
-   Parallel computation makes Transformers much faster.
-   Modern LLMs are all based on this architecture.
-   The next step is understanding **Self-Attention**, the core
    mechanism inside every Transformer.

------------------------------------------------------------------------

# What's Next

The final part of Lesson 158 will summarize everything, compare RNNs and
Transformers comprehensively, discuss limitations of Transformers,
provide revision notes, a cheat sheet, and prepare you for Lesson 159:
**Self-Attention**.
