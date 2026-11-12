# Skill 7 — Inference and Model Responses

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 Inference vs. training](#51-inference-vs-training)
   - [5.2 Why the same question gives different answers](#52-why-the-same-question-gives-different-answers)
   - [5.3 Temperature](#53-temperature--the-creativity-dial)
   - [5.4 The other knobs](#54-the-other-knobs-brief)
6. [Worked Example](#6-worked-example--the-creativity-dial-in-action)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

**"Inference"** is one of those words that sounds impressive and means something ordinary:

> **It's simply the model doing its job — taking an input and producing an output.**

Every single time you send a prompt and get an answer back, **that's one inference.**

- **Training** is when the model learns — once, expensively, up front.
- **Inference** is _every use after that._

When people talk about "the cost of running" an AI feature, they usually mean the cost of **all those inferences adding up.**

There's a second idea in this skill, and it's the one that unsettles beginners: **the same question often gives different answers.** This skill explains why, and how to control it.

---

## 2. Why It Matters (for you, as a developer)

- **Inference is what you're paying for at runtime.** Each call to the model is a billable event. Scaling an AI feature is scaling inference.
- **Non-determinism is a design constraint, not a bug.** Normal software is predictable; LLM output isn't, unless you push it there. Understanding _why_ is essential before you build anything real.
- **You control the personality with one number.** Choosing temperature (and other sampling parameters) is a **design decision**, not a technicality — the same model can be a careful tutor or a wild brainstormer.
- **You'll be asked "why did the answer change?"** — by a user, a teammate, or an angry support ticket. This skill is your answer.

---

## 3. Prerequisites

- Skill 5 (what an LLM is; next-token prediction).
- Skill 6 (tokens and the context window — inference costs are measured in tokens).

---

## 4. Key Concepts

1. **Inference = using the model** (input → output). Training happens once; inference happens every time.
2. **Runtime cost = many inferences adding up.**
3. **Same prompt ≠ same answer**, because the model **samples** from likely next tokens rather than always picking the single most likely one.
4. **Temperature** is the main control: a dial between "careful" and "creative" (roughly 0 → 1+).
5. **Low temperature** = focused, consistent, repeatable — good for facts and study help.
6. **High temperature** = inventive, surprising — good for brainstorming, risky for correctness.
7. **Other knobs exist** (max output tokens, an alternative randomness control), but **temperature is the one you'll reach for most.**

---

## 5. Concepts Explained

### 5.1 Inference vs. training

|                  | **Training**                     | **Inference**                            |
| ---------------- | -------------------------------- | ---------------------------------------- |
| **When**         | Once, up front                   | Every time you call the model            |
| **What happens** | Weights are adjusted to fit data | Weights are _used_ to produce output     |
| **Cost shape**   | Very expensive, one-off          | Cheap per call, but **adds up at scale** |
| **Who does it**  | The model provider (usually)     | You, via the API                         |
| **Frequency**    | Once per model version           | Every request                            |

**The key phrase:** _"the cost of running an AI feature"_ = the sum of all inference calls.

**Beginner framing:** training is like studying for an exam once. Inference is answering a question during the exam — every question, every time.

**Intermediate framing:** inference is a **forward pass** through the network. The weights are frozen. Every call re-runs that pass, and every call costs compute and money.

**Junior-dev framing:** think of training as building a function, and inference as _calling_ it. Your app is a caller. The function's behaviour depends on the arguments you pass — including sampling parameters.

---

### 5.2 Why the same question gives different answers

If you ask an LLM the same thing twice, you'll often get **two slightly different replies**. Beginners find this unsettling, because normal software is predictable.

**The reason:**

> When a model picks the next token, it isn't forced to choose the single most likely option every time. **It _samples_ from the likely options, with a bit of controlled randomness.**

That randomness:

- is what **lets it feel natural and varied rather than robotic**, and
- **you can turn it up or down.**

**Beginner framing:** it's like rolling a loaded die. The most likely outcome still wins most often — but not _every_ time. That tiny variation is what makes the text feel human.

**Intermediate framing:** the model outputs a **probability distribution** over the next token. Decoding strategy decides how to pick from it. "Always pick the most likely" = _greedy decoding_ (deterministic-ish). "Sample from the distribution" = _randomised decoding_ (varied). Temperature reshapes that distribution before sampling.

**Junior-dev framing:** imagine a function that doesn't return a single value but a weighted list of candidates. The sampler picks one. Change the sampler, change the output. Same input, different output — on purpose.

---

### 5.3 Temperature — the creativity dial

> The main control is a setting called **temperature**, usually running from about **0 to 1** (sometimes higher). Think of it as a dial between **"careful"** and **"creative."**

| Range                   | Behaviour                                                                                | Good for                         | Risky for                                             |
| ----------------------- | ---------------------------------------------------------------------------------------- | -------------------------------- | ----------------------------------------------------- |
| **Low** (~0 – 0.3)      | Plays it safe; picks the most likely continuations. **Focused, consistent, repeatable.** | Facts, definitions, study help   | Originality, brainstorming                            |
| **Medium** (~0.4 – 0.7) | A balance. A little variety without going off the rails.                                 | General conversation             | Tasks needing strict correctness _or_ wild creativity |
| **High** (~0.8 and up)  | Takes more chances; **more inventive and surprising.**                                   | Brainstorming names, story ideas | Anything that has to be correct                       |

**How to think about the dial:**

- **Low temperature ≈ asking a careful expert.** Reliable, predictable, sometimes a bit dry.
- **High temperature ≈ asking a creative friend.** Lively, original, occasionally nonsense.

**The key mindset:**

> **Choosing temperature is a design decision, not a technicality.**

- A **study assistant** that must be accurate lives **down at the low end.**
- A tool for generating **wild marketing taglines** might live **up high.**

**Same model, a very different personality — one number apart.**

---

### 5.4 The other knobs (brief)

You'll meet a couple of other controls:

- **Max output tokens** — a limit on how many tokens the answer can use. Useful for cost control and for keeping replies short.
- **An alternative randomness control** (e.g., _top-p_ / _nucleus sampling_) — another way to shape how the sampler picks. Temperature is still the one you'll reach for most.

You don't need deep detail on these yet. Just know they exist, and that **temperature is the primary personality dial.**

---

## 6. Worked Example — the creativity dial in action

> **Question:** Would you set a **low** or a **high** temperature for (a) answering a maths question and (b) helping a student brainstorm essay topics, and why for each?

**Reasoning walk-through:**

**(a) Maths question → LOW temperature (~0 – 0.3).**

- Maths has **one correct answer**. "Plausible but different" is _wrong_, not creative.
- Low temperature makes the model **pick the most likely continuations**, producing **focused, consistent, repeatable** answers.
- If a student asks the same maths question twice, they should get the **same** answer — not a different one because the sampler rolled differently.

**(b) Brainstorming essay topics → HIGH temperature (~0.8+).**

- The goal is **variety and surprise**, not correctness. There is no single "right" list of topics.
- High temperature makes the model **more inventive**, breaking out of the obvious first answer.
- If it produces a few duds alongside two gems, that's an acceptable trade — the user filters.

**The general rule:**

> **Ask: does this task have one right answer, or many good ones?**
> One right answer → low temperature. Many good answers → high temperature.

**And the mindset to keep:** the choice is a **design decision you make on purpose**, not a setting you leave at default.

---

## 7. Common Pitfalls

- ❌ **Treating inference as free.** Every call costs money; at scale, inference cost dominates.
- ❌ **Expecting deterministic output by default.** Sampling means variation unless you push temperature low (or use a deterministic mode where offered).
- ❌ **Confusing "same prompt → same answer" with correctness.** It's about _consistency_, not _accuracy_. A confidently wrong answer at low temperature is still wrong — just repeatably wrong.
- ❌ **Leaving temperature at default.** Your product's personality is being decided by a number you didn't choose.
- ❌ **Using high temperature for anything factual.** Study help, definitions, calculations — all should live at the low end.
- ❌ **Assuming low temperature fixes hallucinations.** It makes answers _more repeatable_, not more _true_.
- ❌ **Ignoring max-token limits.** A runaway reply is both slow and expensive.

---

## 8. Hands-On Exercises

1. **Same prompt, twice (10 min).** Ask an LLM the same factual question twice at default settings. Note the differences. Then ask at temperature 0 (or lowest available) and compare.
2. **Temperature sweep (15 min).** Ask for "five names for a coffee shop" at low, medium, and high temperature. Compare how surprising vs. safe the lists feel.
3. **Design decisions (10 min).** For each product, pick a temperature and justify in one sentence:
   (a) a maths tutor, (b) a marketing tagline generator, (c) a customer-support bot, (d) a poetry-writing assistant, (e) a legal-contract summariser.
4. **Inference cost reasoning (10 min).** A feature is used by 1,000 users per day, each making 5 requests. If each request costs $0.002, what's the monthly inference bill (roughly)? What would halving the calls per user save?
5. **Documenting the choice (10 min).** For the Study Assistant, write one short paragraph explaining the temperature you'd choose for _explanations_, and a different one for _brainstorming_, and why.

---

## 9. Checkpoint Questions

1. In one sentence, what is **inference**?
2. What's the difference between training and inference in terms of _when_ and _how often_ they happen?
3. Why does the same prompt sometimes produce different answers?
4. What does **temperature** control, and what's the range you'll typically use?
5. What temperature would you choose for a maths tutor? For a brainstorming tool? Why?
6. Why is "same answer every time" not the same thing as "correct answer every time"?
7. Name one other sampling knob besides temperature, and what it does.

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
