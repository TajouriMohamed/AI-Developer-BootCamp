# Skill 5 — What Is an LLM?

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 How next-word prediction becomes intelligence](#51-how-next-word-prediction-becomes-intelligence)
   - [5.2 When you use an LLM, what's actually happening](#52-when-you-use-an-llm-whats-actually-happening)
   - [5.3 What they're brilliant at](#53-what-theyre-brilliant-at)
   - [5.4 Where they let you down, and why](#54-where-they-let-you-down-and-why)
6. [Worked Example](#6-worked-example--next-word-prediction-building-an-answer)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

**LLM** stands for **Large Language Model** — and each word earns its place:

- **"Large"** — these models are enormous, trained on a huge slice of the internet, books, and code, with **billions of internal weights**.
- **"Language"** — their specialty is text.
- **"Model"** — at the end of the day, it's a mathematical system that makes predictions.

Put the hype aside and an LLM is a system that got extraordinarily good at **one deceptively simple task**:

> **Given some text, predict what comes next.**

That's it. Everything else — the fluency, the facts, the coding help — emerges from getting _really, really good_ at that one task.

---

## 2. Why It Matters (for you, as a developer)

- **The whole bootcamp runs on this mental model.** Tokens, context windows, inference, prompt engineering, RAG, agents — every later skill builds on "next-word prediction."
- **It tells you exactly what to trust and what not to.** An LLM predicts _plausible_ text; it does **not** look facts up. That single fact shapes how you design every product you build on top of one.
- **It explains the failure modes you'll engineer around**: hallucinations, knowledge cut-offs, overconfidence. You can't fix what you don't understand.

---

## 3. Prerequisites

- Skill 1 (AI → ML → Deep Learning; what "learning from data" means).
- Skill 4 (the four waves; why generative AI matters).

---

## 4. Key Concepts

1. **LLM = a system that predicts the next chunk of text, extraordinarily well.**
2. **Capabilities emerge as a side effect of prediction** — grammar, facts, style, a rough model of the world.
3. **Generation is iterative:** predict a chunk, append it, predict the next, repeat.
4. **LLMs do not look facts up.** They produce _plausible_ continuations — which can be confidently wrong (**hallucination**).
5. **Knowledge cut-off:** they only know what was in their training data.
6. **Treat an LLM as a pattern-matcher, not a mind** — "a fast, astonishingly well-read, slightly overconfident intern."
7. **Named models you'll meet:** GPT (OpenAI), Mistral, Llama (Meta), Claude (Anthropic).

---

## 5. Concepts Explained

### 5.1 How next-word prediction becomes intelligence

It really is that simple at its core — and it's worth seeing **why** something so simple can feel so smart.

During training, the model is shown endless text **with the last piece hidden**, and it practises guessing that piece, **billions of times**, adjusting its weights whenever it's wrong.

To get good at guessing the next word across all of human writing, it's **forced** to pick up:

- grammar,
- facts,
- styles,
- a sense of how arguments flow,
- even a rough model of the world —

because **all of that helps it predict better**.

> **Nobody programmed those abilities in. They _emerged_ as a side effect of getting really, really good at prediction.**

**Beginner framing:** it's like autocomplete on your phone — but trained on so much text, at such scale, that it can hold a topic across a page and follow instructions in plain English.

**Intermediate framing:** the training objective is _next-token prediction_; the emergent abilities (reasoning-like behaviour, instruction-following, style control) are **downstream consequences** of optimising that objective at scale. You don't get them by adding features — you get them by making prediction better.

**Junior-dev framing:** think of it as a function `predict_next(text_so_far) -> next_chunk`. Generation is a loop that calls this function over and over. That's the entire mechanism.

---

### 5.2 When you use an LLM, what's actually happening

When you use an LLM, it's doing exactly this:

> Taking **everything so far** — your question, plus any instructions and history you've supplied — and **generating a continuation, one small chunk at a time**, each chunk chosen because it's the **most plausible next thing**.

Your phone's autocomplete is a **toy version** of the same idea. An LLM does it well enough to hold a topic across a page and follow instructions you give it in plain English.

**Implication for you as a developer:** the "input" to the model is _everything so far_ — your system prompt, the chat history, the user's message, any retrieved documents. All of it matters. (This is why context windows and prompt design become real engineering concerns in later skills.)

---

### 5.3 What they're brilliant at

Because they've effectively **read so much**, LLMs are wonderful at:

- **explaining a concept** at whatever level you ask,
- **summarising** something long into something short,
- **drafting a first version** of almost any text,
- **translating**,
- **reformatting messy notes**,
- **helping you think through code**.

For a study assistant, that covers most of what you'd ever want.

---

### 5.4 Where they let you down, and why

Now the part you **must internalise**, because it shapes how you build:

> **An LLM predicts plausible text; it does not look facts up in a database.**

So it can produce something that **sounds completely authoritative and is simply wrong**. We call that a **hallucination** — and it **isn't a bug you can fully switch off**. It's a direct consequence of how the thing works.

It will **invent a citation, a date, or a function that doesn't exist**, all with total confidence — because a confident-sounding sentence is often the most "plausible" continuation.

**Two related limits follow:**

1. **Knowledge cut-off.** An LLM only knows what was in its training data. It won't know last week's news unless you give it that information.
2. **"Understanding" is an open debate.** Whether it truly understands anything is a genuine philosophical question — but for practical purposes, **treat it as a pattern-matcher, not a mind.**

**The healthiest mental model:**

> **An LLM is like a fast, astonishingly well-read, slightly overconfident intern.**
> Fantastic help — and never to be trusted blindly on anything that matters.

---

### 5.5 Models you'll run into

| Model family | Maker      | Notes                                         |
| ------------ | ---------- | --------------------------------------------- |
| **GPT**      | OpenAI     | The family behind ChatGPT.                    |
| **Mistral**  | Mistral AI | French, and a serious player in Europe.       |
| **Llama**    | Meta       | Widely used open model family.                |
| **Claude**   | Anthropic  | Known for careful, safety-oriented behaviour. |

You'll call several of them from code later, and **much of what you learn on one carries straight over to the others**. The core concepts — tokens, context, prompts, inference — are shared; only the API surface differs.

---

## 6. Worked Example — next-word prediction building an answer

**Step 1 — the prompt:**

```text
The capital of France is
```

To continue it well, the model must have absorbed, from training, that this sentence is almost always finished with **"Paris."** So it predicts:

```text
Paris
```

**Step 2 — feed it back in.** Now the input is:

```text
The capital of France is Paris
```

and it predicts the next piece — maybe a full stop:

```text
.
```

**Step 3 — repeat.** One tiny prediction at a time, it builds a whole answer.

**Scale that up and the same trick writes essays and code.**

**What this example teaches:**

- The model doesn't "look up" _Paris_ — it predicts it because that's the most plausible continuation given training.
- The model has **no separate memory** beyond what you feed back in each step.
- **Confidence ≠ correctness.** It predicted "Paris" confidently — and it will predict a nonexistent API function just as confidently, because that's _plausible_ too.

---

## 7. Common Pitfalls

- ❌ **Thinking an LLM "knows" facts.** It predicts plausible text; it doesn't query a database.
- ❌ **Assuming hallucinations are a fixable bug.** They're a property of the mechanism. You _mitigate_ them (grounding, retrieval, guardrails) — you don't switch them off.
- ❌ **Forgetting the knowledge cut-off.** The model doesn't know anything after its training data unless you supply it.
- ❌ **Treating the model as a mind.** It's a pattern-matcher. Design accordingly.
- ❌ **Assuming behaviour is "programmed in."** Abilities emerged from prediction; that's why they're broad — and why they're uneven.
- ❌ **Believing model lock-in is severe.** Core concepts carry across GPT, Mistral, Llama, Claude. Learn the concepts once.

---

## 8. Hands-On Exercises

1. **Predict the next chunk (10 min).** For each prompt, write the _most plausible_ next few words — then note a **plausible but wrong** continuation:
   (a) "The first president of the United States was…"
   (b) "To reverse a list in Python, use…"
   (c) "The 2027 Nobel Prize in Physics went to…"
   Which of these exposes the knowledge cut-off? Which exposes hallucination risk?
2. **Autocomplete vs. LLM (10 min).** In two sentences, explain the difference between your phone's autocomplete and an LLM. Which one holds a topic across a page, and why does that matter?
3. **Hallucination hunt (15 min).** Ask an LLM (or imagine asking) for a citation, a date, and a function name you're unsure about. Note which ones you'd need to verify before shipping.
4. **Intern metaphor (10 min).** Write down three rules you'd follow when giving work to a "fast, well-read, overconfident intern" — and map each rule to a technique you might build into an AI product.

---

## 9. Checkpoint Questions

1. What does each letter of **LLM** stand for, and what does each word mean?
2. In one sentence, what is an LLM's core task?
3. How do abilities like grammar and facts get into the model — are they programmed, or something else?
4. What is a **hallucination**, and why can't it be fully switched off?
5. What is a **knowledge cut-off**?
6. Why is "overconfident intern" a useful mental model for building products?
7. Name two model families you'll likely call from code.

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
