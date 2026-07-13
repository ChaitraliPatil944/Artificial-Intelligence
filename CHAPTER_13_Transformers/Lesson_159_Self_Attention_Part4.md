# Lesson 159 --- Self Attention (Part 4)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# Learning Objectives

In this final part, you will:

-   Implement a simple version of Self-Attention.
-   Understand its computational complexity.
-   Learn its strengths and limitations.
-   Prepare for technical interviews.
-   Build intuition for Multi-Head Attention.

------------------------------------------------------------------------

# Self-Attention Algorithm

    Input Tokens
          │
          ▼
    Create Q, K, V
          │
          ▼
    Compute Q × Kᵀ
          │
          ▼
    Scale (later in Lesson 162)
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
    Context-Aware Output

------------------------------------------------------------------------

# NumPy Implementation

``` python
import numpy as np

Q = np.random.rand(3, 4)
K = np.random.rand(3, 4)
V = np.random.rand(3, 4)

scores = Q @ K.T
weights = np.exp(scores) / np.sum(np.exp(scores), axis=1, keepdims=True)
output = weights @ V

print(output)
```

------------------------------------------------------------------------

# PyTorch Implementation

``` python
import torch

Q = torch.rand(3, 4)
K = torch.rand(3, 4)
V = torch.rand(3, 4)

scores = Q @ K.T
weights = torch.softmax(scores, dim=-1)
output = weights @ V

print(output)
```

------------------------------------------------------------------------

# Time Complexity

Suppose a sequence contains **n** tokens.

Each token compares itself with every other token.

    Token1 → n comparisons
    Token2 → n comparisons
    ...
    Tokenn → n comparisons

Overall complexity:

    O(n²)

This quadratic growth is one limitation of standard Transformers.

------------------------------------------------------------------------

# Advantages

-   Learns long-range dependencies.
-   Fully parallelizable.
-   Excellent GPU utilization.
-   Produces context-aware representations.
-   Foundation of modern LLMs.

------------------------------------------------------------------------

# Limitations

-   High memory consumption.
-   O(n²) computation for long sequences.
-   Large models require significant compute.
-   Training from scratch demands huge datasets.

------------------------------------------------------------------------

# Why Multi-Head Attention?

Imagine reading a sentence.

You might focus on:

-   Grammar
-   Meaning
-   Subject
-   Object
-   Emotion

One attention mechanism cannot capture every relationship equally well.

Transformers solve this using **Multiple Attention Heads**.

    Sentence

          │

     ┌────┼────┐
     │    │    │
     ▼    ▼    ▼

    Head1 Head2 Head3

          │
          ▼

    Combined Output

This will be explored in Lesson 164.

------------------------------------------------------------------------

# Real-World Applications

Self-Attention powers:

-   ChatGPT
-   Machine Translation
-   Text Summarization
-   Question Answering
-   Code Generation
-   Vision Transformers
-   Speech Recognition
-   Image Captioning

------------------------------------------------------------------------

# Interview Cheat Sheet

**What is Self-Attention?**

A mechanism that lets each token determine which other tokens are most
relevant.

**Why is it better than an RNN?**

It models long-distance relationships directly and enables parallel
computation.

**Why use Softmax?**

To convert similarity scores into normalized attention weights.

**What is the output?**

A context-aware embedding for every token.

------------------------------------------------------------------------

# Revision Notes

Remember this sequence:

    Input

    ↓

    Embedding

    ↓

    Q, K, V

    ↓

    QKᵀ

    ↓

    Softmax

    ↓

    Weighted Values

    ↓

    Context Vector

Memorize the formula:

    Attention(Q, K, V)

    =

    Softmax(QKᵀ)

    ×

    V

The scaling factor will be added in the next lessons.

------------------------------------------------------------------------

# Mini Exercise

Sentence:

    The student solved the problem because she practiced.

Think about:

1.  Which word should **she** attend to?
2.  Which Query is being evaluated?
3.  Which Keys receive the highest score?
4.  Which Values contribute most to the final representation?

------------------------------------------------------------------------

# Key Takeaways

-   Self-Attention is the core operation inside every Transformer.
-   Every token generates Query, Key, and Value vectors.
-   Similarity is measured with dot products.
-   Softmax produces attention weights.
-   Values are combined into new context-aware embeddings.
-   Multi-Head Attention extends this idea further.

------------------------------------------------------------------------

# End of Lesson 159

Congratulations! 🎉

You now understand the intuition, workflow, mathematics, implementation,
and practical importance of Self-Attention.

In **Lesson 160**, we'll dive deeper into **Query, Key, and Value**,
exploring how they are learned, why separate projection matrices are
required, and how they evolve during training.
