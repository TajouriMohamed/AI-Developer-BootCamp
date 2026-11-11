# Skill 6 — Tokens and Context Window

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 Tokens](#51-tokens--how-a-model-reads)
   - [5.2 Why tokens matters](#52-why-tokens-matter-to-you--the-billing-unit)
   - [5.3 The context window](#53-the-context-window--the-models-working-memory)
   - [5.4 Putting them together](#54-putting-them-together--the-mental-model)
6. [Worked Example](#6-worked-example--tokenising-real-text)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

These two ideas **sound technical** and turn out to be **intensely practical**. You'll bump into both within your **first hour of writing AI code**, and understanding them now will save you real confusion later.

- **Tokens** = how a model _reads_ text. They're the unit everything is measured and billed in.
- **The context window** = the model's _working memory_. It's the total amount of text, measured in tokens, that the model can consider at one time — and it has hard edges.

Together, they explain why prompts cost money, why long chats "forget" their beginning, and why managing memory becomes _your_ job as the developer.

---

## 2. Why It Matters (for you, as a developer)

- **Tokens are the billing unit.** How much you can send, how long the reply can be, and what each request costs are all counted in tokens — not words.
- **Asymmetric pricing.** Providers usually charge **more for the tokens the model _writes_ than the ones you _send_.** Thinking in tokens is part of doing this job _well_ rather than _expensively_.
- **The context window is a hard limit.** When it fills up, something has to give — and deciding _what_ gives becomes your job, not the model's.
- **There is no memory between calls.** Each API call is independent unless _you_ supply the history. This shapes every AI app you'll build.

---

## 3. Prerequisites

- Skill 5 (what an LLM is; next-chunk prediction).

---

## 4. Key Concepts

1. **A model reads _tokens_, not letters or whole words** — chunks between a letter and a word.
2. **Rough sizing:** ~3–4 characters, or ~¾ of an English word, per token. Common words = 1 token; rare/long words = several.
3. **Everything is billed in tokens** — input _and_ output — and **output usually costs more.**
4. **The context window is a fixed-size "whiteboard"** holding _everything you send + everything it writes back_ at once.
5. **No memory between calls.** You resend the relevant conversation each time.
6. **When the window overflows, the oldest content falls off** — so _you_ manage what stays, what's summarised, and what's dropped.

---

## 5. Concepts Explained

### 5.1 Tokens — how a model reads

A model doesn't read letters, and it doesn't quite read words either. It reads **tokens**: chunks of text sitting **somewhere between a letter and a word**.

**Rules of thumb:**

- One token ≈ **3–4 characters**, or roughly **¾ of an English word**.
- **Common words** are usually a **single token**.
- **Rare or long words** get **split into several**.
- **Spaces, punctuation, and even parts of code** all become tokens too.

**Beginner framing:** imagine chopping text into bite-sized pieces before the model can "chew" it. Familiar pieces stay whole; unfamiliar ones get chopped smaller.

**Intermediate framing:** tokenisation is a _fixed vocabulary_ learned during training. The model never sees raw characters — it sees token IDs. That's why the exact character count and token count diverge, especially for code, non-English text, and unusual words.

**Junior-dev framing:** think of a token as the model's "atom" of text. Every count, limit, and price you'll ever see is expressed in these atoms.

---

### 5.2 Why tokens matter to you — the billing unit

> **Tokens are the unit that _everything_ is measured and billed in.**

That means:

- **How much text you can send** — measured in tokens.
- **How long the answer can be** — measured in tokens.
- **What each request costs** — measured in tokens.

Providers **charge per million tokens**, and they usually **charge more for the tokens the model writes than the ones you send.**

**The practical lesson:** learning to think in tokens — noticing that a giant prompt or a chatty reply costs real money — is a genuine part of doing this job **well rather than expensively.**

---

### 5.3 The context window — the model's working memory

> **The context window is the total amount of text, measured in tokens, that a model can consider at one time.**

**The whiteboard picture:** a whiteboard of **fixed size**. _Everything you send it, plus everything it writes back, has to fit on that board at once._ It is the model's **short-term memory**, and it has **hard edges**.

**The surprising consequence for beginners:**

> **The model has no memory between separate calls unless you provide it.**

Each time you call the API, **you typically resend the relevant conversation so far**, so it all sits on the whiteboard together.

**What happens when the window fills:**

- A conversation grows longer than the window.
- Something has to give.
- **The oldest lines get pushed off the board**, and the model effectively **forgets how the chat began.**

**And that's the key shift:** managing what stays on that whiteboard — and deciding what to drop or summarise when it fills up — becomes **your job as the developer, not the model's.**

---

### 5.4 Putting them together — the mental model

| Concept            | What it is                             | Why it matters                                  | Who manages it                                                  |
| ------------------ | -------------------------------------- | ----------------------------------------------- | --------------------------------------------------------------- |
| **Token**          | Small chunk of text the model reads    | It's the unit of _cost_ and _limits_            | You (by writing efficient prompts and replies)                  |
| **Context window** | Total tokens the model can see at once | Hard limit on conversation length and knowledge | You (by deciding what stays, what's summarised, what's dropped) |

**The everyday workflow this implies:**

1. You build a **prompt** (system instructions + history + user message + any documents) — measured in tokens.
2. You send it. The model **generates a continuation** — also measured in tokens.
3. The **whole thing** counts against the context window _and_ the bill.
4. Next turn, you resend the relevant history — and decide what to keep or trim.

---

## 6. Worked Example — tokenising real text

**Example A — short phrase:**

```text
"Hello there" → about 3 tokens
```

**Example B — one long word splitting into several:**

```text
"unbelievable" → "un" + "bel" + "iev" + "able" → 4 tokens for one word
```

**Example C — the sizing rules applied:**

| Content                      | Rough token count                                                        |
| ---------------------------- | ------------------------------------------------------------------------ |
| A short paragraph            | ~60–100 tokens                                                           |
| A whole lesson like this one | ~2,000 tokens                                                            |
| A 1,000-word article         | ~750 tokens (¾ of word count)                                            |
| A page of code               | Often _more_ than expected — symbols, indentation, and identifiers split |

**What this teaches:**

- **Word count ≠ token count.** They're correlated but never identical — and the gap widens for code, rare words, and non-English text.
- **Long inputs cost more than they look.** A "short paragraph" is already 60–100 tokens.
- **Output costs more than input.** A verbose reply is a real, recurring bill.
- **You can _see_ this.** A tokenizer in the browser makes it click in two minutes (see Exercise 1).

---

## 7. Common Pitfalls

- ❌ **Counting words instead of tokens.** They're different units. Always think in tokens for cost and limits.
- ❌ **Assuming the model remembers the previous call.** It doesn't — _you_ resend the context each time.
- ❌ **Ignoring output cost.** Replies cost more than inputs; chatty responses are expensive.
- ❌ **Letting the conversation grow unbounded.** When the window fills, the oldest content falls off silently.
- ❌ **Assuming token limits are a tokenizer quirk.** They're a fundamental constraint of the model architecture.
- ❌ **Underestimating token cost of code.** Symbols, whitespace, and identifiers split aggressively — code is often more expensive per line than prose.

---

## 8. Hands-On Exercises

1. **Try the tokenizer (5–10 min).** Open a tokenizer in your browser (search "OpenAI tokenizer" or "Mistral tokenizer"). Paste:
   - a sentence of your own,
   - a rare or made-up word,
   - a short code snippet.
     Watch them shatter into tokens. **Two minutes here makes the whole idea click** — and it'll stop token limits from ever confusing you.
2. **Word vs. token (10 min).** Take a 100-word paragraph. Count words, then count tokens with a tokenizer. Compute the ratio. Try the same with a code snippet and compare.
3. **Whiteboard modelling (15 min).** Sketch a 10-turn conversation on a whiteboard. Assign each turn an approximate token count. Show which turns fall off when the total exceeds a hypothetical 4,000-token window.
4. **Cost reasoning (10 min).** If a provider charges $X per million input tokens and $3X per million output tokens, estimate the monthly cost of an assistant that handles 1,000 conversations of ~2,000 tokens each, with ~500-token replies.
5. **Memory strategy (15 min).** For the Study Assistant, write a one-paragraph strategy for keeping the earliest student context from being forgotten as the conversation grows.

---

## 9. Checkpoint Questions

1. What is a **token**, and roughly how many characters is one?
2. Why does "unbelievable" split into several tokens?
3. In what unit is AI usage **billed**, and why does _output_ usually cost more than _input_?
4. What is the **context window**? Use the whiteboard picture in your answer.
5. Why does the model seem to "forget" early parts of a long conversation?
6. Does the model remember anything **between** separate API calls? What do you have to do about it?
7. When the window fills up, who decides what stays and what's dropped — the model or you? What techniques could you use?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
