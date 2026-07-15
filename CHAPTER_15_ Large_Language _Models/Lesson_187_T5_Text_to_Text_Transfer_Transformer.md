# Chapter 15 -- Large Language Models

# Lesson 187 -- T5 (Text-to-Text Transfer Transformer)

> **T5 (Text-to-Text Transfer Transformer) is an encoder-decoder
> Transformer model introduced by Google Research in 2019. T5
> reformulates every Natural Language Processing (NLP) task as a
> text-to-text problem, allowing the same architecture to perform
> translation, summarization, question answering, classification, and
> many other tasks by simply changing the input prompt.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what T5 is.
-   Learn why T5 was developed.
-   Study the encoder-decoder Transformer architecture.
-   Understand the text-to-text paradigm.
-   Learn span corruption pretraining.
-   Explore real-world applications.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is T5?
2.  Why T5 Was Invented
3.  Evolution to T5
4.  T5 Architecture
5.  Text-to-Text Paradigm
6.  Span Corruption Pretraining
7.  Fine-Tuning T5
8.  Applications
9.  Hugging Face Example
10. Advantages & Limitations
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is T5?

T5 is an **encoder-decoder Transformer**.

``` text
Input Text
     │
Encoder
     │
Context
     │
Decoder
     │
Output Text
```

Everything is treated as text in and text out.

------------------------------------------------------------------------

# 2. Why T5 Was Invented

Earlier models often required different output heads for different NLP
tasks.

T5 simplified this by converting every task into text generation.

Examples:

``` text
translate English to French:
Hello

↓

Bonjour
```

``` text
summarize:
<long article>

↓

Short summary
```

``` text
sentiment:
I love this movie.

↓

positive
```

------------------------------------------------------------------------

# 3. Evolution to T5

``` text
Seq2Seq
    │
Attention
    │
Transformer
    │
BERT / GPT
    │
T5
```

T5 unified many NLP tasks under one framework.

------------------------------------------------------------------------

# 4. T5 Architecture

``` text
Input
  │
Token + Position Embeddings
  │
Transformer Encoder
  │
Context Representation
  │
Transformer Decoder
  │
Generated Text
```

Popular variants:

  Model        Parameters
  ---------- ------------
  T5-Small            60M
  T5-Base            220M
  T5-Large           770M
  T5-3B                3B
  T5-11B              11B

------------------------------------------------------------------------

# 5. Text-to-Text Paradigm

Every task becomes a prompt.

``` text
question:
What is AI?

↓

Artificial Intelligence
```

``` text
translate English to German:
Good morning

↓

Guten Morgen
```

One architecture handles many tasks.

------------------------------------------------------------------------

# 6. Span Corruption Pretraining

Instead of masking individual words, T5 masks spans.

Example:

``` text
The cat sat on the mat.

↓

The <extra_id_0> on the mat.
```

Target:

``` text
<extra_id_0> cat sat
```

This encourages the model to reconstruct meaningful text spans.

------------------------------------------------------------------------

# 7. Fine-Tuning T5

Workflow:

``` text
Pretrained T5
      │
Task Prompt
      │
Fine-Tune
      │
Task-Specific Model
```

Minimal architectural changes are required.

------------------------------------------------------------------------

# 8. Applications

-   Translation
-   Summarization
-   Question Answering
-   Text Classification
-   Dialogue Systems
-   Grammar Correction
-   Data-to-Text Generation

------------------------------------------------------------------------

# 9. Hugging Face Example

``` python
from transformers import pipeline

summarizer = pipeline(
    "summarization",
    model="t5-small"
)

text = "Artificial Intelligence is transforming many industries..."

print(summarizer(text))
```

------------------------------------------------------------------------

# 10. Advantages & Limitations

  Advantages                 Limitations
  -------------------------- -------------------------------------------
  One model for many tasks   Larger models require significant compute
  Flexible prompting         Slower than specialized small models
  Strong transfer learning   Prompt wording can affect performance

------------------------------------------------------------------------

# 11. Mini Project

1.  Load T5-Small.
2.  Summarize an article.
3.  Translate English to French.
4.  Perform sentiment classification using prompts.
5.  Compare outputs for different prompt styles.

------------------------------------------------------------------------

# 12. Interview Questions

### What does T5 stand for?

Text-to-Text Transfer Transformer.

### What makes T5 unique?

It treats every NLP task as text input to text output.

### What architecture does T5 use?

Encoder-decoder Transformer.

### What pretraining objective does T5 use?

Span corruption (text infilling).

------------------------------------------------------------------------

# 13. Summary

You learned:

-   T5 fundamentals.
-   Encoder-decoder architecture.
-   Text-to-text learning.
-   Span corruption.
-   Fine-tuning workflow.
-   Real-world applications.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 188 -- Llama**

You'll learn how Meta's Llama family of open-weight Large Language
Models was developed, its architecture, training philosophy, model
variants, ecosystem, and why it became one of the most influential
open-source LLM families.
