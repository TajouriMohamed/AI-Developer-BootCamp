# Skill 1 — What Is AI?

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 Describing the answer vs. learning it](#51-the-core-idea-describing-the-answer-vs-learning-it)
   - [5.2 AI vs. ML vs. Deep Learning](#52-ai-vs-machine-learning-vs-deep-learning--three-nested-boxes)
   - [5.3 Neural networks](#53-a-quick-honest-word-on-neural-networks)
   - [5.4 What this does NOT mean](#54-what-this-does-not-mean)
6. [Worked Example](#6-worked-example--the-spam-filter-question)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Artificial Intelligence (AI) is **software that performs tasks we'd normally call "intelligent" — understanding language, recognising images, making judgements — by learning from data instead of following step-by-step rules a human wrote in advance.**

That's the whole idea in one sentence. The rest of this document unpacks it.

If you remember only one contrast from this skill, remember this one:

| Traditional software                      | AI software                                                         |
| ----------------------------------------- | ------------------------------------------------------------------- |
| Does exactly what it's told, line by line | Is shown many examples and works out its own way to handle new ones |
| Behaviour comes from **rules you write**  | Behaviour comes from **patterns learned from data**                 |

You already use AI several times a day without noticing: your phone's word suggestions, spam filtering, "you might also like" recommendations. None of those were given a rule for your exact situation. They looked at huge piles of past behaviour, found patterns, and made a reasonable guess about you.

---

## 2. Why It Matters (for you, as a developer)

- Almost every modern product you'll build or maintain now has an AI component, or will soon.
- The mental model in this skill ("learning from data vs. following rules") is the foundation for _everything_ else in this bootcamp — LLMs, RAG, agents, all of it.
- When someone says "we used AI," knowing the layers (AI → ML → Deep Learning) lets you ask the right follow-up question: **"which kind?"**

---

## 3. Prerequisites

- None technically. Basic programming intuition helps (you have it).
- No math required for this skill.

---

## 4. Key Concepts

| #   | Concept                              | In one line                                                                                                       |
| --- | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| 1   | **AI = learning from data**          | Not following hand-written rules.                                                                                 |
| 2   | **"Learning from data"**             | The system adjusts itself using many labelled examples until it performs well, then generalises to unseen inputs. |
| 3   | **AI > ML > Deep Learning**          | They are _nested_, not synonyms.                                                                                  |
| 4   | **Neural networks**                  | Webs of simple math connections ("weights") that training adjusts automatically.                                  |
| 5   | **AI does not "understand" like us** | It produces outputs that _look_ intelligent because the patterns are good. (This returns later in the bootcamp.)  |

---

## 5. Concepts Explained

### 5.1 The core idea: describing the answer vs. learning it

Suppose you want a program that tells **cat photos from dog photos**.

| Approach                 | How it works                                                                                                                         | Outcome                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| **Rule-based (old way)** | Try to describe a cat in code — pointy ears, whiskers, a certain face shape.                                                         | Hopeless: for every rule, some cat breaks it and some dog obeys it. |
| **Machine learning**     | Gather thousands of photos labelled "cat" or "dog" and let the system adjust itself, over and over, until it's good at the examples. | Works on photos it has never seen.                                  |

The critical insight:

> **The system never receives a definition of "cat."**
> It builds its own internal sense of what cats tend to look like — from the examples — and then applies that sense to photos it has never seen.

That shift — from _describing the answer_ to _learning it from examples_ — is the seed of everything in this course.

#### Three ways to think about it

- **Beginner framing:** teaching by example rather than by instruction. You don't tell a child "a cat has ears at 45°, whiskers of length X…"; you point at cats and say "cat."

- **Intermediate framing:**
  - the "labelled examples" are called **training data**.
  - The repeated self-adjustment is **training**.
  - The ability to handle photos it never saw is **generalisation** — and it's the whole point. A model that only works on its training data is useless.

- **Junior-dev framing:** in web terms, a rule-based system is like a giant `if/else` tree you hand-write and maintain forever. An ML model is like a function whose _body_ is generated from data — you tune the data and the training process, not the individual branches.

---

### 5.2 AI vs. Machine Learning vs. Deep Learning — three nested boxes

People use these as if they're synonyms. They aren't. Picture **three boxes, each sitting inside the last**:

```text
┌─────────────────────────────────────────────────────┐
│  ARTIFICIAL INTELLIGENCE (AI)                       │
│  Any technique that makes a machine behave in a     │
│  way we'd call "smart" — including old-fashioned    │
│  hand-written rules.                                │
│                                                     │
│  ┌───────────────────────────────────────────────┐  │
│  │  MACHINE LEARNING (ML)                        │  │
│  │  Approaches where the system learns patterns  │  │
│  │  from data instead of being told the rules.   │  │
│  │                                               │  │
│  │  ┌─────────────────────────────────────────┐  │  │
│  │  │  DEEP LEARNING (DL)                     │  │  │
│  │  │  A family of ML methods built on neural │  │  │
│  │  │  networks. The engine behind modern AI  │  │  │
│  │  │  — including every model in this        │  │  │
│  │  │  bootcamp.                              │  │  │
│  │  └─────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
```

- **Artificial Intelligence** — the outermost box: _any_ technique that makes a machine behave smartly. Includes hand-written rules _and_ learning systems.
- **Machine Learning** — a box inside AI: specifically, approaches where the system **learns patterns from data** instead of being told the rules. The cat/dog example is ML.
- **Deep Learning** — a smaller box inside ML: a particular family of methods built on **neural networks**. It's the engine behind the AI that feels almost magical today — **including every model you'll use in this bootcamp**.

> **Rule of thumb:** when someone says "we used AI," a fair follow-up is: **"which kind?"** A spam filter from 2005 and a chatbot from 2025 are both AI, but they're worlds apart in how they work.

---

### 5.3 A quick, honest word on neural networks

You'll hear "neural network" constantly. Here's the plain version — and you genuinely don't need more than this for now:

> A neural network is a **big web of simple math connections, each with a number (a "weight") attached.** During training, the system is shown examples and nudges all those weights — millions or billions of tiny adjustments — until its output tends to match the right answers. **"Deep" just means the web has many layers stacked up**, which lets it learn very complicated patterns.

Key points:

- **Nobody sits down and sets those numbers by hand** — the training process finds them.
- You will use the finished result without ever touching the weights yourself.
- The "neural" in the name is a loose inspiration from how brains connect; it is **not** a claim that the machine thinks like a brain. We'll come back to that debate later.

---

### 5.4 What this does NOT mean

None of the above means the machine "understands" in the human sense. It produces outputs that _look_ intelligent because the learned patterns are good. That distinction matters for trust, safety, and expectations — and it's a thread we'll pull on throughout the bootcamp.

> **The useful takeaway for now:** AI systems get their abilities **from data and training, not from a rulebook** — and that's exactly why they can handle messy, real-world inputs that no rulebook could ever cover.

---

## 6. Worked Example — the spam filter question

> **Question:** A spam filter can be built as a set of hand-written rules _or_ trained on thousands of real emails. Which one copes better with a brand-new scam it has never seen, and why?

### Reasoning walk-through

1. **Hand-written rules filter**
   You write things like `if subject contains "FREE MONEY" → spam`. It works for the scams you anticipated. A brand-new scam that phrases things differently slips through — because _you never wrote a rule for it_.
2. **Trained filter**
   It has seen thousands of past spam and ham (legitimate) emails. It learned _patterns_ — tone, structure, sender behaviour, word combinations — not specific phrases. A new scam that _feels_ like spam statistically gets caught, even though no rule mentions it.
3. **The trade-off**

   | Filter type | Strength                 | Weakness                                                          |
   | ----------- | ------------------------ | ----------------------------------------------------------------- |
   | Rule-based  | Explainable              | Brittle — misses anything not anticipated                         |
   | Trained     | Generalises to new scams | Hard to trace ("why was this flagged?") — no human-readable rules |

### Conclusion

The **trained** filter generally copes better with novel scams, because it generalises from patterns rather than relying on rules someone thought of in advance. That is exactly the "learning from data" advantage this whole skill is about.

---

## 7. Common Pitfalls

- ❌ **Treating AI, ML, and Deep Learning as synonyms.** They're nested. Get the boxes right.
- ❌ **Thinking "learning" means the machine understands.** It means the weights were adjusted to fit examples well.
- ❌ **Assuming AI always beats rules.** For simple, well-defined, explainable tasks, hand-written rules can be _better_ (cheaper, traceable, reliable). AI shines on messy, high-variety inputs.
- ❌ **Imagining someone hand-codes the "knowledge."** Training finds the weights; no human writes them.
- ❌ **Confusing "works on training data" with "works."** Generalisation to unseen inputs is the real test.

---

## 8. Hands-On Exercises

1. **Spot the AI (10 min).** List 5 things you used today that involve AI. For each, write one line on _what data_ it probably learned from (e.g., "autocomplete → learned from what people type").
2. **Nested boxes (5 min).** Without looking, redraw the AI → ML → Deep Learning boxes and label one real example in each.
3. **Rule vs. learning (15 min).** Pick a simple classification task you understand (e.g., "is this email a newsletter?"). Write 3 hand-written rules for it. Then list 3 cases where your rules fail but a trained model might succeed.
4. **Web-dev bridge (10 min).** In one paragraph, explain to a fellow web developer — using only web analogies — the difference between rule-based software and ML.

---

## 9. Checkpoint Questions

1. In one sentence, what is AI?
2. What's the fundamental difference between traditional software and AI software?
3. Put these in order from outermost to innermost: _Deep Learning, AI, Machine Learning_.
4. What is a "weight" in a neural network, and who sets it?
5. Why can a trained spam filter catch a scam it has never seen, while a rule-based one often can't?
6. Does "learning from data" mean the machine understands like a human? Explain briefly.

_(Answers are implied throughout Sections 5 and 6 — try to answer before re-reading.)_
