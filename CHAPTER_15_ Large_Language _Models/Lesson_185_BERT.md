# Chapter 15 -- Large Language Models

# Lesson 185 -- BERT (Bidirectional Encoder Representations from Transformers)

> **BERT (Bidirectional Encoder Representations from Transformers) is a
> Transformer-based language model introduced by Google in 2018. Unlike
> earlier language models that processed text in only one direction,
> BERT reads text bidirectionally, allowing it to understand the context
> of a word using both the words before and after it. This breakthrough
> dramatically improved Natural Language Processing (NLP) tasks such as
> question answering, text classification, and named entity
> recognition.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what BERT is.
-   Learn why BERT was developed.
-   Study the BERT architecture.
-   Understand bidirectional learning.
-   Learn Masked Language Modeling (MLM) and Next Sentence Prediction
    (NSP).
-   Explore real-world applications.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is BERT?
2.  Why BERT Was Invented
3.  Evolution Before BERT
4.  BERT Architecture
5.  Bidirectional Context
6.  Pre-training Tasks
7.  Fine-Tuning BERT
8.  Applications
9.  TensorFlow & Hugging Face Example
10. Advantages & Limitations
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is BERT?

BERT is an **encoder-only Transformer** model.

``` text
Input Text
     │
Transformer Encoder Stack
     │
Contextual Embeddings
     │
Task-Specific Output
```

It learns rich contextual representations for every token.

------------------------------------------------------------------------

# 2. Why BERT Was Invented

Earlier models like Word2Vec, GloVe, and standard RNNs had limitations:

-   Static word embeddings
-   Limited context
-   Unidirectional language modeling

Example:

``` text
The fisherman sat by the bank.
```

The word **bank** means something different in:

``` text
The bank approved my loan.
```

BERT distinguishes these meanings using context from **both
directions**.

------------------------------------------------------------------------

# 3. Evolution Before BERT

``` text
Bag of Words
      │
TF-IDF
      │
Word2Vec
      │
LSTM / GRU
      │
Attention
      │
Transformer
      │
BERT
```

------------------------------------------------------------------------

# 4. BERT Architecture

``` text
Input Tokens
      │
Token Embeddings
      │
Position Embeddings
      │
Segment Embeddings
      │
Transformer Encoder × N
      │
Contextual Representations
```

Common variants:

  Model          Layers   Hidden Size
  ------------ -------- -------------
  BERT Base          12           768
  BERT Large         24          1024

------------------------------------------------------------------------

# 5. Bidirectional Context

Traditional models:

``` text
Left → Right
```

or

``` text
Right ← Left
```

BERT:

``` text
Left ⇄ Word ⇄ Right
```

Every token attends to both past and future tokens during pre-training.

------------------------------------------------------------------------

# 6. Pre-training Tasks

## Masked Language Modeling (MLM)

Random words are masked.

``` text
The cat sat on the [MASK].

↓

mat
```

The model predicts the missing word.

### Why MLM?

It forces BERT to use surrounding context instead of simply predicting
the next word.

------------------------------------------------------------------------

## Next Sentence Prediction (NSP)

Example:

Sentence A:

``` text
The sky is blue.
```

Sentence B:

``` text
Clouds are visible today.
```

BERT predicts whether Sentence B naturally follows Sentence A.

*(Many later BERT variants removed NSP, but it is important
historically.)*

------------------------------------------------------------------------

# 7. Fine-Tuning BERT

General workflow:

``` text
Pretrained BERT
      │
Add Small Output Layer
      │
Fine-Tune on Your Dataset
      │
Task-Specific Model
```

Applications require only a small task-specific head.

------------------------------------------------------------------------

# 8. Applications

-   Sentiment Analysis
-   Question Answering
-   Named Entity Recognition (NER)
-   Text Classification
-   Semantic Search
-   Document Ranking
-   Information Extraction

------------------------------------------------------------------------

# 9. TensorFlow & Hugging Face Example

``` python
from transformers import pipeline

classifier = pipeline(
    "sentiment-analysis",
    model="bert-base-uncased"
)

result = classifier("I love learning AI!")
print(result)
```

------------------------------------------------------------------------

# 10. Advantages & Limitations

  -----------------------------------------------------------------------
  Advantages                         Limitations
  ---------------------------------- ------------------------------------
  Deep contextual understanding      Encoder-only architecture

  Excellent transfer learning        Slower inference than smaller models

  Strong benchmark performance       Not designed for long-form text
                                     generation
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 11. Mini Project

1.  Load the IMDb dataset.
2.  Fine-tune BERT for sentiment analysis.
3.  Evaluate accuracy and F1-score.
4.  Test custom reviews.
5.  Compare with an LSTM classifier.

------------------------------------------------------------------------

# 12. Interview Questions

### What does BERT stand for?

Bidirectional Encoder Representations from Transformers.

### Why is BERT called bidirectional?

Because it learns from both left and right context simultaneously.

### What are BERT's two original pre-training tasks?

-   Masked Language Modeling (MLM)
-   Next Sentence Prediction (NSP)

### Is BERT better for text generation or text understanding?

Text understanding.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Why BERT was created.
-   Encoder-only architecture.
-   Bidirectional learning.
-   MLM and NSP.
-   Fine-tuning workflow.
-   Real-world applications.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 186 -- GPT (Generative Pre-trained Transformer)**

You'll learn how GPT differs from BERT, why decoder-only Transformers
excel at text generation, the evolution from GPT-1 to modern GPT models,
autoregressive language modeling, instruction tuning, and the foundation
of conversational AI systems.
