# Chapter 15 -- Large Language Models

# Lesson 192 -- DeepSeek

> **DeepSeek is a family of open-weight Large Language Models developed
> by DeepSeek AI. The DeepSeek ecosystem includes general-purpose
> language models, coding models, multimodal models, and
> reasoning-focused models. It emphasizes strong reasoning, efficient
> architectures, and broad accessibility for researchers and
> developers.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what DeepSeek is.
-   Learn why DeepSeek was developed.
-   Explore the DeepSeek model family.
-   Understand reasoning-focused models.
-   Study Mixture of Experts (MoE).
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is DeepSeek?
2.  Why DeepSeek Was Developed
3.  Evolution of DeepSeek Models
4.  Architecture
5.  DeepSeek-R1 & Reasoning
6.  Mixture of Experts
7.  Open-Weight Ecosystem
8.  Applications
9.  Hugging Face Example
10. Advantages & Limitations
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is DeepSeek?

DeepSeek is a family of Transformer-based LLMs.

``` text
Prompt
   │
Transformer
   │
Reasoning
   │
Generated Response
```

It includes language, coding, and multimodal models.

------------------------------------------------------------------------

# 2. Why DeepSeek Was Developed

Goals include:

-   High-quality reasoning
-   Strong coding performance
-   Efficient open-weight models
-   Accessible AI research

------------------------------------------------------------------------

# 3. Evolution of DeepSeek Models

``` text
DeepSeek LLM
      │
DeepSeek Coder
      │
DeepSeek VL
      │
DeepSeek R1
```

The family expanded from general language models into coding,
vision-language, and advanced reasoning.

------------------------------------------------------------------------

# 4. Architecture

High-level pipeline:

``` text
Input Tokens
      │
Embeddings
      │
Decoder Transformer
      │
Attention
      │
Next Token Prediction
```

Many DeepSeek models use efficient Transformer optimizations and some
variants employ Mixture of Experts.

------------------------------------------------------------------------

# 5. DeepSeek-R1 & Reasoning

Reasoning-focused models emphasize solving complex tasks step by step
during training and inference.

Applications:

-   Mathematics
-   Programming
-   Scientific reasoning
-   Logical problem solving

------------------------------------------------------------------------

# 6. Mixture of Experts (MoE)

``` text
Input
  │
Router
 ├──► Expert A
 ├──► Expert B
 ├──► Expert C
 └──► ...
      │
Combine Outputs
```

Benefits:

-   Higher capacity
-   Lower computation per token
-   Better scalability

------------------------------------------------------------------------

# 7. Open-Weight Ecosystem

Advantages:

-   Local deployment
-   Fine-tuning
-   Research
-   Community contributions

Popular techniques:

-   LoRA
-   QLoRA
-   Quantization

------------------------------------------------------------------------

# 8. Applications

-   Coding assistants
-   Research assistants
-   Enterprise AI
-   Chatbots
-   RAG systems
-   Education
-   Scientific analysis

------------------------------------------------------------------------

# 9. Hugging Face Example

``` python
from transformers import pipeline

generator = pipeline(
    "text-generation",
    model="deepseek-ai/deepseek-llm"
)

print(generator(
    "Explain gradient descent.",
    max_length=80
))
```

------------------------------------------------------------------------

# 10. Advantages & Limitations

  Advantages                  Limitations
  --------------------------- ------------------------------------
  Strong reasoning            Large models need capable hardware
  Open-weight ecosystem       Deployment can be complex
  Excellent coding ability    Quality varies across checkpoints
  Active research community   Fine-tuning requires expertise

------------------------------------------------------------------------

# 11. Mini Project

1.  Run a DeepSeek model locally.
2.  Compare reasoning and coding prompts.
3.  Quantize the model.
4.  Measure inference speed.
5.  Compare with another open-weight LLM.

------------------------------------------------------------------------

# 12. Interview Questions

### What is DeepSeek?

A family of open-weight Large Language Models focused on reasoning,
coding, and efficient deployment.

### What is DeepSeek-R1 known for?

Strong reasoning capabilities on complex problems.

### Why are MoE models useful?

They increase model capacity while activating only a subset of experts,
improving efficiency.

### Is DeepSeek suitable for local deployment?

Yes, many models are available as open weights and support local
inference.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   DeepSeek fundamentals.
-   Model family.
-   Reasoning-focused models.
-   Mixture of Experts.
-   Open-weight ecosystem.
-   Applications.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 193 -- Phi**

You'll learn how Microsoft's Phi family demonstrates that carefully
curated training data and efficient architectures can produce compact
language models with impressive reasoning abilities, making them ideal
for edge devices and resource-constrained environments.
