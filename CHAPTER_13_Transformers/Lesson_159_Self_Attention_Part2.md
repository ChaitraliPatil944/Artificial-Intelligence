# Lesson 159 --- Self Attention (Part 2)

> **Chapter 13 --- Transformers**

------------------------------------------------------------------------

# Learning Objectives

In this part, you will learn:

-   Why every word creates Query, Key, and Value vectors
-   The intuition behind Q, K, and V before studying the mathematics
-   How Self-Attention decides which words are important
-   How humans naturally perform attention in daily life

------------------------------------------------------------------------

# Recap

In Part 1, we learned that every word can communicate with every other
word.

Now the question is:

> **How does a Transformer know which words are important?**

The answer lies in three vectors:

    Query (Q)

    Key (K)

    Value (V)

These three vectors are generated for every token.

------------------------------------------------------------------------

# A Library Analogy

Imagine you walk into a library.

You want a book about **Artificial Intelligence**.

What happens?

    You ask:

    "I need an AI book."

    ↓

    Librarian checks every book.

    ↓

    Books matching your request receive more attention.

    ↓

    The best matching books are handed to you.

This is almost exactly how Self-Attention works.

------------------------------------------------------------------------

# Understanding Query

A **Query** represents:

> "What am I looking for?"

Example sentence:

    The cat drank milk.

Suppose we are processing the word:

    drank

Its Query might ask:

    Who performed the action?

    What object is related to me?

    Which words help me understand my meaning?

Think of Query as a **question**.

------------------------------------------------------------------------

# Understanding Key

Every word also creates a Key.

A Key answers:

> "What information do I contain?"

Example:

    cat

    Key:

    Animal
    Subject
    Living Thing

Another example:

    milk

    Key:

    Object
    Drink
    Food

Each word advertises its identity through its Key.

------------------------------------------------------------------------

# Understanding Value

Finally, every word creates a Value.

The Value stores the actual information that will be passed forward.

    Word

    ↓

    Value

    ↓

    Useful Information

If a word receives high attention, its Value contributes more to the
final representation.

------------------------------------------------------------------------

# Putting Everything Together

Imagine you're in a classroom.

Teacher asks:

> "Who knows Python?"

Teacher's question is the **Query**.

    Query

Each student raises a hand if they know Python.

Those raised hands represent the **Keys**.

    Key

The student who is selected explains Python.

That explanation is the **Value**.

    Value

So the process becomes:

    Question

    ↓

    Compare

    ↓

    Choose

    ↓

    Receive Information

------------------------------------------------------------------------

# Token Perspective

Suppose the sentence is:

    The dog chased the ball

When processing:

    chased

The model asks:

    Which word is the subject?

    dog?

    ball?

    the?

It compares its Query against every Key.

Words with higher similarity receive greater attention.

------------------------------------------------------------------------

# Visual Representation

                   Query

                     │

                     ▼

    Key1   Key2   Key3   Key4

      │       │      │      │

      └──── Compare Similarity ────┐

                                   ▼

                      Attention Scores

                                   ▼

                        Values Combined

                                   ▼

                        New Representation

------------------------------------------------------------------------

# Human Brain Analogy

Imagine entering a crowded room looking for your friend.

Your brain doesn't memorize everyone.

Instead, it asks:

    Who looks like my friend?

That is your Query.

Every person's appearance acts like a Key.

When you find the correct person, the conversation you have is the
Value.

Your brain naturally performs attention all the time.

------------------------------------------------------------------------

# Why Three Different Vectors?

One vector cannot perform all three jobs efficiently.

Separating them allows the model to:

-   Search (Query)
-   Describe (Key)
-   Transfer information (Value)

This separation is one of the reasons Transformers work so well.

------------------------------------------------------------------------

# Interview Questions

### What is a Query?

A vector representing what information a token is searching for.

------------------------------------------------------------------------

### What is a Key?

A vector describing the characteristics of a token.

------------------------------------------------------------------------

### What is a Value?

The information contributed by a token after attention scores are
computed.

------------------------------------------------------------------------

### Why are Query, Key, and Value different?

Because searching, matching, and information transfer are different
tasks.

------------------------------------------------------------------------

# Key Takeaways

-   Every token generates Query, Key, and Value vectors.
-   Queries ask questions.
-   Keys advertise information.
-   Values carry information.
-   Attention compares Queries against Keys.
-   High-scoring Values contribute more to the final output.

------------------------------------------------------------------------

# Next Part

In Part 3, we'll study the complete mathematics behind Self-Attention,
including dot products, attention scores, softmax, and a fully worked
numerical example.
