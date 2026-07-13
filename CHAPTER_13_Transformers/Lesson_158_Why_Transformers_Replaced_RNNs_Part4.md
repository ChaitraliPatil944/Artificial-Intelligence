# Lesson 158 --- Why Transformers Replaced RNNs (Part 4)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# Complete Comparison

  Feature                 RNN      LSTM      GRU        Transformer
  ----------------------- -------- --------- ---------- -------------
  Sequential Processing   Yes      Yes       Yes        No
  Parallel Processing     No       No        No         Yes
  Long-Term Memory        Poor     Good      Good       Excellent
  Vanishing Gradient      Severe   Reduced   Reduced    Minimal
  Training Speed          Slow     Slow      Moderate   Fast
  GPU Utilization         Poor     Poor      Moderate   Excellent
  Scalability             Low      Medium    Medium     Very High
  Basis of Modern LLMs    No       No        No         Yes

------------------------------------------------------------------------

# Advantages of Transformers

## 1. Parallel Processing

All tokens are processed simultaneously.

    Token1 ─┐
    Token2 ─┤
    Token3 ─┤
    Token4 ─┘
         ↓
     Parallel

------------------------------------------------------------------------

## 2. Better Long-Range Understanding

    Word ----------------------------------------------> Related Word

    Direct Attention

Distance is no longer a major obstacle.

------------------------------------------------------------------------

## 3. Excellent GPU Performance

Thousands of GPU cores work together.

    □□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□
    GPU Cores

    ↓

    Process many tokens simultaneously

------------------------------------------------------------------------

## 4. Highly Scalable

Increasing model size generally improves capability when enough data and
compute are available.

Examples:

-   BERT
-   GPT
-   LLaMA
-   Gemini
-   Claude

------------------------------------------------------------------------

# Limitations of Transformers

Transformers are powerful but not perfect.

### High Memory Usage

Every token attends to every other token.

    100 words

    ↓

    100 × 100 Attention Matrix

As sequence length grows, memory requirements increase rapidly.

------------------------------------------------------------------------

### Expensive Training

Large Transformer models require:

-   Powerful GPUs
-   Large datasets
-   Significant electricity
-   Long training times

Training frontier models can take weeks or months.

------------------------------------------------------------------------

### Data Hungry

Transformers generally perform best with enormous amounts of training
data.

Small datasets often benefit from transfer learning or fine-tuning.

------------------------------------------------------------------------

# Where Transformers Are Used

    Transformer

    ├── ChatGPT
    ├── Google Translate
    ├── GitHub Copilot
    ├── Gemini
    ├── Claude
    ├── Image Captioning
    ├── Speech Recognition
    ├── Vision Transformers
    ├── Protein Folding
    └── Recommendation Systems

------------------------------------------------------------------------

# Interview Cheat Sheet

### Why did Transformers replace RNNs?

-   Parallel computation
-   Better long-term dependencies
-   Faster training
-   Better GPU utilization
-   Higher accuracy

------------------------------------------------------------------------

### What is the biggest conceptual difference?

**RNN**

    Memory

**Transformer**

    Attention

------------------------------------------------------------------------

### Why is Attention superior?

Instead of remembering everything,

the model learns **what information is important**.

------------------------------------------------------------------------

# Common Interview Questions

### 1. What problem do Transformers solve?

Long-term dependency and sequential computation.

------------------------------------------------------------------------

### 2. Which paper introduced Transformers?

**Attention Is All You Need (2017).**

------------------------------------------------------------------------

### 3. Why are Transformers faster?

Because they process all tokens simultaneously.

------------------------------------------------------------------------

### 4. Are RNNs obsolete?

No.

RNNs are still useful for:

-   Tiny embedded devices
-   Small time-series problems
-   Low-resource environments

However, Transformers dominate modern NLP and many vision tasks.

------------------------------------------------------------------------

# Revision Notes

Remember these keywords:

-   Sequential
-   Parallel
-   Hidden State
-   Attention
-   Long-Term Dependency
-   GPU Utilization
-   Self-Attention
-   Encoder
-   Decoder

------------------------------------------------------------------------

# Mini Exercise

Think about the sentence:

> "The dog that chased the cat because it was hungry ran away."

Questions:

1.  What does **it** refer to?
2.  Why might an RNN struggle?
3.  Why would a Transformer solve it more effectively?

Try answering before moving to the next lesson.

------------------------------------------------------------------------

# Key Takeaways

-   RNNs introduced sequence learning.
-   LSTMs and GRUs improved memory.
-   Sequential computation remained a bottleneck.
-   Transformers removed recurrence.
-   Attention became the new foundation.
-   Modern AI systems are built upon this architecture.

------------------------------------------------------------------------

# Preparing for Lesson 159

Now that you know **why Transformers exist**, the next question is:

> **How does a Transformer decide which words are important?**

The answer is **Self-Attention**.

That mechanism is the heart of every Transformer and will be explored in
the next lesson.

------------------------------------------------------------------------

# End of Lesson 158

Congratulations!

You now understand the motivation behind the Transformer architecture.
This historical perspective makes the mathematics of Self-Attention much
easier to grasp because you know exactly which problems it was designed
to solve.
