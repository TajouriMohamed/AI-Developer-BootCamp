# Skill 2 — What Is AI Development?

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 The restaurant metaphor](#51-the-restaurant-metaphor)
   - [5.2 Using AI vs. building with it](#52-Using-AI-vs-building-with-it--made-concrete)
   - [5.3 What an AI developer actually does](#53-What-an-AI-developer-actually-does-day-to-day)
   - [5.4 AI Development vs. AI Engineering](#54-AI-Development-vs-AI-Engineering-the-ASIDE)
6. [Worked Example](#6-worked-example--the-before-you-move-on-question)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

There are two ways to be "involved with food": sitting at the table eating, or running the kitchen. Most people meet AI as the **diner** — they open a chatbot and type questions. This course is about becoming the person who **runs the kitchen**.

**AI development means building software products on top of AI models — connecting your own program to a model so it becomes one ingredient inside an application you build, wrapped in an interface, memory, firm rules, and the features real users actually need.**

The model stops being "a website you visit" and becomes **a component inside a product you own**.

---

## 2. Why It Matters (for you, as a developer)

- The gap between _a clever reply_ and _a dependable product_ is where the entire career lives.
- Most of the job is **software engineering you already know**, applied to a new kind of component. That's the reassuring truth of this field.
- Knowing the difference between "using AI" and "building with AI" tells you exactly what skills to invest in — and what to ignore.

---

## 3. Prerequisites

- Skill 1 (what AI is, and the AI → ML → Deep Learning picture).
- Basic web development experience: APIs, HTTP request/response, environment variables, backend + frontend separation. (You have all of this.)

---

## 4. Key Concepts

1. **Using AI ≠ building with AI.** A user consumes a chatbot; a developer embeds a model inside a product.
2. **An AI developer is a software engineer with one strange new ingredient.**
3. **"AI Development" ≠ "AI Engineering."** The latter trains/operates the models; the former builds products on top of models already trained by others.
4. **Most of the work happens _around_ the model** — backend, storage, auth, interface, guardrails, cost/speed handling.
5. **A model is one ingredient**, not the whole meal. The product is what makes its output useful, safe, and repeatable.

---

## 5. Concepts Explained

### 5.1 The restaurant metaphor

Picture two people in a restaurant:

- One sits at a table, eating. → **the AI _user_**
- One is in the back running the kitchen: deciding the menu, cooking, plating, making sure nobody gets food poisoning. → **the AI _developer_**

Both are "involved with food." Only one is doing the work that makes the meal happen.

**Beginner framing:** you're not here to eat. You're here to run the kitchen.

**Intermediate framing:** the model is the raw ingredient (the fish, the flour). Your job is menu design (product design), cooking (integration and prompting), plating (UX), and food safety (guardrails, auth, privacy).

**Junior-dev framing:** think of the model as a third-party API you don't control. Your job is the same as with any third-party API — wrap it, secure it, handle failures, expose it to users through a product.

---

### 5.2 Using AI vs. building with it — made concrete

|                    | **User**                                           | **AI Developer**                                            |
| ------------------ | -------------------------------------------------- | ----------------------------------------------------------- |
| **Action**         | Opens ChatGPT in a browser, types, reads, moves on | Connects their own program directly to a model via an API   |
| **Persistence**    | Nothing is saved into a product                    | The product remembers, stores, and acts on outputs          |
| **Control**        | Cannot change the model's behaviour                | Shapes behaviour with prompts, guardrails, memory, features |
| **Responsibility** | None beyond their own use                          | Correctness, safety, cost, availability, UX                 |
| **Outcome**        | A clever reply                                     | A dependable product                                        |

**Worked contrast — the study app:**

A student using ChatGPT to study is a **user**: they type, they read, they move on, nothing is saved into a product.

Now imagine **you** build a study app where:

- a learner logs in,
- their past questions are remembered,
- the assistant is **forbidden** from doing their homework outright,
- quizzes are generated on demand,
- and everything is stored so a teacher can review progress.

**Same underlying model. Completely different thing.** The model answered the questions; **you built the product that made those answers useful, safe, and repeatable.**

That gap — between _a clever reply_ and _a dependable product_ — is the space you'll live in for the rest of your career.

---

### 5.3 What an AI developer actually does, day to day

Stripped of buzzwords, the job is **software engineering with one strange new ingredient**. A normal day might include:

- **Choosing the right model for the task**, balancing quality, speed, and cost. A cheap fast model for simple replies; a stronger one for hard reasoning.
- **Connecting to it from code through an API**, while keeping your secret keys out of the codebase so they never leak.
- **Writing and refining the instructions (the prompts)** that shape how the model behaves, then testing them until the behaviour is reliable.
- **Handling reality:** the model's mistakes, the occasional timeout, the token limits, the bill at the end of the month.
- **Building everything around the model:** the backend, the storage, the login, the interface, and the guardrails that keep it safe.

Notice how little of that is about the model itself, and how much is ordinary, solid software work.

---

### 5.4 AI Development vs. AI Engineering (the "ASIDE")

This is exactly why the course is called **"AI Development"** and not **"AI Engineering."**

|                   | **AI Engineering**                             | **AI Development** (this course)                       |
| ----------------- | ---------------------------------------------- | ------------------------------------------------------ |
| **Focus**         | Training and operating the models themselves   | Building products on top of models others have trained |
| **Work lives in** | Data, training pipelines, model infrastructure | Backend, prompts, product features, guardrails, UX     |
| **Typical role**  | ML engineer / research engineer                | AI developer / full-stack engineer with AI             |
| **Day-to-day**    | Datasets, GPUs, model evaluation, ops          | APIs, storage, auth, prompts, cost, tests, deployment  |

Related worlds, very different days. You don't need to train a model to build a great AI product — and this bootcamp is deliberately the _product_ side.

---

## 6. Worked Example — the "before you move on" question

> **Question:** Pick one app you use that clearly has AI inside it. What do you think its developers had to build _around_ the model, beyond the model itself, to make it genuinely useful and safe?

**Reasoning walk-through** (using a generic AI note-taking app as the example):

1. **Authentication & accounts** — the model has no idea who the user is; the product does.
2. **Storage & memory** — past notes, past questions, and past answers must be persisted and retrieved so the model has context.
3. **Prompt layer** — instructions that shape the model's tone, format, and boundaries (e.g., "cite sources", "never invent facts", "refuse to do homework outright").
4. **Guardrails** — checks on inputs (block prompt injection, strip PII) and outputs (block unsafe or malformed responses).
5. **Interface & UX** — loading states, streaming text, retry buttons, error messages when the model times out.
6. **Failure handling** — timeouts, rate limits, token overruns, partial failures.
7. **Cost controls** — caching, model routing (cheap model first), usage limits per user.
8. **Observability** — logs, traces, and metrics so you can see _why_ the model produced a bad answer and fix it.
9. **Evaluation & testing** — a way to check that prompt changes didn't break behaviour.

**Conclusion:** the model produced the text — but almost everything that made the app _useful and safe_ was ordinary software engineering around it. That is the AI developer's craft.

---

## 7. Common Pitfalls

- ❌ **Thinking the model _is_ the product.** The model is one ingredient; the product is the meal.
- ❌ **Confusing "AI Development" with "AI Engineering."** You're not training models here; you're building on top of them.
- ❌ **Underestimating the "around the model" work.** Auth, storage, guardrails, cost, errors — that's most of the job.
- ❌ **Leaving secret keys in the codebase.** A classic, career-limiting mistake (more in later skills).
- ❌ **Treating prompt writing as a one-off.** Prompts are code: they need testing and iteration like any other logic.
- ❌ **Ignoring the bill.** Token costs are a real engineering constraint, not an afterthought.

---

## 8. Hands-On Exercises

1. **Diner vs. kitchen (10 min).** List three AI products you use. For each, write one sentence: _what would a user version look like, and what does the developer version add?_
2. **Around-the-model audit (15 min).** Pick one AI app you use daily. List at least five things its developers must have built _around_ the model.
3. **Role mapping (10 min).** For each of these tasks, say whether it's **AI Engineering** or **AI Development**: (a) fine-tuning a base model on a company's documents, (b) writing a prompt that enforces a JSON output format, (c) building a login flow for an AI app, (d) training a new model from scratch.
4. **Study-app spec (20 min).** Write a one-paragraph spec for the study app described in §5.2, listing the components _around_ the model you'd need to build.

---

## 9. Checkpoint Questions

1. In one sentence, what is AI development?
2. What's the difference between _using_ AI and _building with_ AI?
3. Why is the course called "AI Development" and not "AI Engineering"?
4. Name at least five things an AI developer builds _around_ the model on a normal day.
5. What makes the "study app" example different from a student using ChatGPT?

_(Answers are implied throughout Sections 5 and 6 — try to answer before re-reading.)_
