# Skill 8 — AI Use Cases in Business

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 The only question a business really asks](#51-the-only-question-a-business-really-asks)
   - [5.2 The common buckets](#52-the-common-buckets)
   - [5.3 The three shapes of value](#53-the-three-shapes-of-value)
   - [5.4 The habit to build](#54-the-habit-to-build)
6. [Worked Example](#6-worked-example--wheres-the-concrete-value)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

It's easy to be dazzled by a slick demo and lose sight of the **only question a business ever really asks**:

> **Does this solve a real problem for real people, better than what they do today?**

A demo wins applause for an afternoon. A product earns its place on an ordinary Tuesday when nobody's watching.

Most genuinely useful AI products fall into **a handful of familiar shapes**, and knowing them helps you **recognise a good opportunity when you see one** — and avoid building a neat demo nobody needs.

This skill gives you two frameworks:

- **The common buckets** — _where_ AI shows up in business.
- **The three shapes of value** — _why_ it's worth building at all.

---

## 2. Why It Matters (for you, as a developer)

- **It keeps you honest.** The most valuable habit in this course is asking _"where's the concrete value?"_ **before** writing any code.
- **It separates products from demos.** A demo impresses; a product earns its place.
- **It shapes your project.** The idea you generate here is the one you'll use for the Final Project at the end of this Super Skill.
- **It protects you from building the wrong thing well.** The most common failure in AI isn't bad code — it's solving a problem nobody actually has.

---

## 3. Prerequisites

- Skill 2 (what AI development is — building products, not demos).
- Skill 5 (what LLMs are and aren't good at).

---

## 4. Key Concepts

1. **The only question a business asks:** does this solve a real problem _better than today_?
2. **The six common buckets:** content work, customer support, sense-making, education, automation, coding help.
3. **The three shapes of value:** **saves time**, **saves money**, **improves quality**.
4. **A strong product idea points to at least one of these — without squirming.**
5. **If it can't, be suspicious.** You may have a neat demo rather than a real product.
6. **The habit to build:** ask _"where's the concrete value?"_ before writing any code.

---

## 5. Concepts Explained

### 5.1 The only question a business really asks

> **Does this solve a real problem for real people, better than what they do today?**

Everything else — the model choice, the architecture, the interface — is downstream of that. A slick demo can win an audience for an afternoon, but **a product earns its place on an ordinary Tuesday when nobody's watching.**

This is the framing you should carry into every AI project:

- **Not "can we use AI here?"** (yes, almost always — that's not a useful question)
- **But "does using AI here make something measurably better?"** (that's the useful question)

---

### 5.2 The common buckets

Most useful AI products fall into a small number of familiar shapes:

| Bucket               | What it does                                                          | Examples                                                                     |
| -------------------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **Content work**     | Drafts text that is necessary but tedious                             | Emails, product descriptions, job posts, social captions                     |
| **Customer support** | Answers common questions instantly, at any hour                       | An assistant answering FAQs at 3 a.m. without a tired human on the other end |
| **Sense-making**     | Turns something long into a short, honest, actionable summary         | Contracts, research papers, a thousand product reviews                       |
| **Education**        | Tutors and study aids                                                 | _— this is the bucket our own project sits in_                               |
| **Automation**       | Wires AI into a workflow so a dull repetitive step happens on its own | Document triage, ticket routing, data entry                                  |
| **Coding help**      | Explains, drafts, and reviews code                                    | Assistants that explain unfamiliar code, draft new code, review changes      |

**Why this list matters:** it gives you a **vocabulary for spotting opportunities**. When you see a task in one of these buckets — especially one someone does _over and over by hand_ — that's a candidate.

**Beginner framing:** these are the "neighbourhoods" where AI products live. You don't need to invent a new neighbourhood; you can build a better house in an existing one.

**Intermediate framing:** each bucket has a **natural value shape** (see §5.3). Content work → time. Customer support → money (volume). Sense-making → quality. Mapping bucket → value shape is a fast way to sanity-check an idea.

---

### 5.3 The three shapes of value

Underneath every bucket, the value shows up as **one of just three things**:

| Value shape          | How it works                                                                       | Example                                                                             |
| -------------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Saves time**       | Does something **faster** than a person could                                      | Drafting a first-pass email in seconds instead of ten minutes                       |
| **Saves money**      | Handles **volume** that would otherwise need more staff                            | A support bot answering 80% of tickets that would have needed a hire                |
| **Improves quality** | Makes **fewer mistakes**, is **more consistent**, or **personalises** to each user | A summariser that never omits a critical clause; a tutor that adapts to the learner |

**The test:**

> **A strong product idea can point, _without squirming_, to at least one of these.**
> **If it can't, be suspicious: you may have a neat demo rather than a real product.**

**Beginner framing:** "saves time, saves money, improves quality" — that's the whole business case. If your pitch can't name one, it's a hobby.

**Intermediate framing:** these three are also **different sales stories**:

- Time saved → pitched as **productivity**.
- Money saved → pitched as **cost reduction** (usually the easiest sell to a CFO).
- Quality improved → pitched as **risk reduction** or **customer experience**.

The shape of value tells you _who_ will champion the product inside a company.

**Junior-dev framing:** this is the acceptance criterion for the _idea itself_, before any technical acceptance criteria exist. If your idea can't pass this check, no amount of good engineering will save it.

---

### 5.4 The habit to build

> **Asking "where's the concrete value?" before writing any code is one of the most valuable habits you can build in this whole course.**

It's not that demos are bad. It's that **demos are cheap and products are expensive** — in time, effort, and the trust of whoever you're building for. The habit protects you from spending weeks on something impressive and useless.

---

## 6. Worked Example — where's the concrete value?

**Scenario:** someone proposes "an AI app that generates motivational quotes on demand."

**Step 1 — which bucket?**
It's _content work_ (drafting text). Fine — that's a real bucket.

**Step 2 — which value shape?**
Let's test each:

- **Saves time?** Marginally — but people can find quotes instantly already. The baseline is _very_ fast.
- **Saves money?** Not obviously — nobody is paying staff to generate motivational quotes.
- **Improves quality?** Questionable — quotes aren't a quality-critical output, and the "best" quotes are already curated.

**Step 3 — the verdict.**
This idea **squirms** when asked which value shape it hits. That's a strong signal it's **a neat demo rather than a real product.**

**Step 4 — the pivot.**
Ask: _who does something over and over by hand, where this capability would clearly help?_

- A **sales team** writing the same type of cold email hundreds of times a week → **saves time** (and likely **saves money** vs. a hire).
- A **support team** rephrasing the same answer for different customer tones → **improves quality** (consistency and personalisation).
- A **teacher** writing fresh practice questions every week → **saves time**, and in a _volume-sensitive_ way, **saves money**.

**The pattern to internalise:**

> **Bucket + value shape + a real person doing it over and over = candidate product.**
> **Demo + applause + no clear value shape = hobby.**

This is the same instinct you'll apply to your own Final Project idea.

---

## 7. Common Pitfalls

- ❌ **Falling in love with the demo.** Slick ≠ useful. Ask "ordinary Tuesday" test: would anyone use this when nobody's watching?
- ❌ **Skipping the value-shape test.** If you can't name time/money/quality, you may be building a demo.
- ❌ **Confusing "uses AI" with "solves a problem."** AI is the ingredient; the value is the meal.
- ❌ **Overestimating time savings.** If the baseline task is already fast, "saves time" is a weak pitch.
- ❌ **Ignoring who the value accrues to.** _Who_ saves the time or money matters as much as _how much_.
- ❌ **Building for an imagined user.** Real users do tasks _over and over by hand_ — start there.
- ❌ **Treating the buckets as exhaustive.** They're a vocabulary for spotting opportunities, not a cage.

---

## 8. Hands-On Exercises

1. **Bucket-spotting (10 min).** Classify each as one of the six buckets, and say which value shape it mainly hits:
   (a) a tool that summarises user feedback, (b) a bot that answers returns-policy questions, (c) a system that drafts LinkedIn posts, (d) a tutor that adapts to a learner's level, (e) a tool that flags risky clauses in contracts.
2. **The squirm test (15 min).** Take three app ideas you've seen recently (or invented). For each, write the value shape it points to — or write _"squirms"_ if it can't.
3. **Your own task (15 min).** Think of a task **you, or someone close to you, does over and over by hand**. Could an AI-powered app save time, save money, or improve quality there? Write down:
   - the task,
   - the bucket,
   - the value shape,
   - one sentence on _who_ benefits.
     _You'll want this for the project at the end of this Super Skill._
4. **Pivot practice (10 min).** Take one "squirming" idea from exercise 2 and pivot it so it hits a clear value shape. Write the pivot in one sentence.
5. **The pitch (10 min).** In three sentences, pitch your exercise-3 idea: _what it does, which bucket, which value shape._

---

## 9. Checkpoint Questions

1. What's the **only question a business really asks** about an AI product?
2. Name the **six common buckets** AI products fall into.
3. Name the **three shapes of value**, with a one-line example of each.
4. What does it mean for an idea to **"squirm"** when asked which value shape it hits?
5. Why is "uses AI" not a sufficient justification for building something?
6. What is the habit you're building in this skill, and why is it valuable _before_ writing any code?
7. In your own words: what makes something a **product** rather than a **demo**?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
