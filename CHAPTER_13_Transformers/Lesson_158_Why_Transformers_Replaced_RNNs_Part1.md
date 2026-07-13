# Lesson 158 --- Why Transformers Replaced RNNs (Part 1)

> **Chapter 13 --- Transformers**

## Learning Objectives

-   Understand why RNNs were revolutionary.
-   Learn their limitations.
-   Understand why Transformers were invented.
-   Prepare for interview questions.

------------------------------------------------------------------------

## Introduction

Imagine reading a 500-page novel. Humans can remember characters
introduced at the beginning while reading the ending. Traditional RNNs
struggle with this because information gradually fades as sequences
become longer.

Researchers improved RNNs using LSTMs and GRUs, but another issue
remained: they processed information **one token at a time**, preventing
efficient parallel computation.

This motivated the invention of the Transformer architecture in 2017.

------------------------------------------------------------------------

## Evolution

    Feed Forward NN
          │
          ▼
         RNN
          │
          ▼
        LSTM
          │
          ▼
         GRU
          │
          ▼
     Transformer

## Why RNNs Were Invented

Language is sequential. The meaning of a word depends on previous words.

Example:

    I → love → AI

RNNs introduced a hidden state to carry information forward.

## The Biggest Problems

### 1. Forgetting Long Context

    Boy -------------------------------> his

    Memory
    ██████████
    ███████
    ████
    ██
    █

The farther information travels, the weaker it becomes.

### 2. Vanishing Gradient

Repeated multiplication of values smaller than one causes gradients to
shrink toward zero.

    0.8 × 0.8 × 0.8 × ... → 0

### 3. Sequential Processing

    Word1
      │
    Word2
      │
    Word3
      │
    Word4

Each computation waits for the previous one, making GPUs inefficient.

## Child-Friendly Analogy

Imagine 100 students solving homework.

**RNN:** One pencil for everyone.

**Transformer:** One pencil for every student.

The second approach finishes much faster.

## Interview Questions

**Q:** Why were Transformers invented?

**A:** To overcome the long-term memory limitations and sequential
computation bottleneck of RNNs.

## Key Takeaways

-   RNNs introduced sequence learning.
-   Long sequences caused memory problems.
-   LSTM and GRU improved but did not eliminate them.
-   Sequential computation prevented full GPU utilization.
-   Transformers solved these issues using attention.

## Next Part

Part 2 explains how attention removes recurrence and enables parallel
processing.
