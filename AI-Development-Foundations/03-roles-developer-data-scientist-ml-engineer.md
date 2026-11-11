# Skill 3 — AI Developer vs. Data Scientist vs. ML Engineer

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 What each role is really chasing](#51-what-each-role-is-really-chasing)
   - [5.2 Side-by-side comparison](#52-side-by-side-comparison)
   - [5.3 The lines blur](#53-the-lines-blur--and-thats-fine)
6. [Worked Example](#6-worked-example--the-study-assistant-question)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Job titles in AI are a bit of a mess — a lot of online arguments are just people using the same words to mean different things. But **three roles** turn up on most AI teams, and knowing roughly where the lines fall tells you **what to focus on** and **what you can safely leave to someone else for now**.

Keep the restaurant metaphor from Skill 2 running:

| Role                     | Roughly what they do                                                                 | In the kitchen                                       |
| ------------------------ | ------------------------------------------------------------------------------------ | ---------------------------------------------------- |
| **AI Developer** _(you)_ | Builds applications on top of existing models. Owns the product and the experience.  | The chef cooking real dishes from ready ingredients. |
| **Data Scientist**       | Explores data to find answers; builds and tests models to explain or predict things. | The food scientist studying the ingredients.         |
| **ML Engineer**          | Trains, optimises, and ships models; keeps them fast and reliable at scale.          | The engineer who builds and runs the kitchen itself. |

---

## 2. Why It Matters (for you, as a developer)

- **Focus.** Knowing the boundaries means you spend your time on skills that are actually yours — not on maths you'll never need.
- **Collaboration.** On real teams these three roles hand work to each other constantly. You need to know who to ask for what.
- **Reassurance.** Being an excellent AI developer leans **far more on good software habits and clear judgement than on heavy mathematics**. Both are learnable — and that's what the next few months are for.

---

## 3. Prerequisites

- Skill 1 (what AI is) and Skill 2 (what AI development is).
- No maths required for this skill.

---

## 4. Key Concepts

1. **Three distinct roles**: AI Developer, Data Scientist, ML Engineer.
2. **Each chases something different**: a working product / understanding / reliable machinery.
3. **Lines blur** on small teams, but the _direction_ of each role stays the same.
4. **AI Developer = product ownership**, not model training.
5. **You need judgement and software habits more than maths.**

---

## 5. Concepts Explained

### 5.1 What each role is really chasing

**Data Scientist — chasing _understanding_.**
Give them a pile of sales data and they'll tell you _why_ sales dropped in March, _which_ customers are about to leave, and _what's_ worth testing next. They live in statistics, experiments, and charts. Their output is often **an insight or a trained model handed to others**.

**ML Engineer — chasing _reliable machinery_.**
When a model needs to be trained on millions of records, or served to millions of users without falling over, that's their world: pipelines, performance, deployment, monitoring. They make sure the model **runs — fast and cheaply, forever**.

**AI Developer (you) — chasing _a working product_.**
You take capable models that already exist and turn them into something a real person can open and use, with all the surrounding software that implies. You care less about _how_ the model was trained and much more about **how to use it well inside an app people trust**.

**Beginner framing:** the data scientist asks "what does the data say?", the ML engineer asks "will it stay up?", and you ask "can a real person actually use this today?"

**Intermediate framing:**

- Data scientist → **insight / experiment / model selection**
- ML engineer → **training pipelines, serving infrastructure, performance, monitoring**
- AI developer → **integration, prompts, product features, UX, guardrails, cost, reliability of the app**

**Junior-dev framing:** think of it as the boundary between _research_, _platform_, and _application_. You live in the **application** layer — the same place you already live as a web developer. The new ingredient is that one of the APIs you call happens to be an LLM.

---

### 5.2 Side-by-side comparison

|                          | **AI Developer**                        | **Data Scientist**                                 | **ML Engineer**                       |
| ------------------------ | --------------------------------------- | -------------------------------------------------- | ------------------------------------- |
| **Chasing**              | A working product                       | Understanding                                      | Reliable machinery                    |
| **Core tools**           | APIs, backend, frontend, prompts, tests | Statistics, experiments, notebooks                 | Pipelines, deployment, monitoring     |
| **Typical output**       | A shipped feature or app                | An insight, a report, or a candidate model         | A trained model running in production |
| **Cares most about**     | User trust, UX, cost, safety            | Why the numbers look the way they do               | Uptime, latency, scale, cost          |
| **Maths intensity**      | Low                                     | High                                               | Medium–high                           |
| **Hands the next role…** | …a product to users                     | …a model or insight to the ML engineer / developer | …an endpoint the developer calls      |

---

### 5.3 The lines blur — and that's fine

- **On a small team**, one person might wear all three hats in a week.
- **On a big team**, they're separate jobs with separate desks.

Either way they **collaborate constantly**: the data scientist might recommend which model to use, the ML engineer might host it, and **you** build the app around it.

The reassuring part — especially if maths isn't your favourite thing — is that **being an excellent AI developer leans far more on good software habits and clear judgement than on heavy mathematics.** Both are learnable, and building them is precisely what the next few months are for.

---

## 6. Worked Example — the Study Assistant question

> **Question:** For the Study Assistant we'll build, which of these three roles is most responsible for turning it into something a student can actually open and chat with, and why is it that one?

**Reasoning walk-through:**

1. **What's being asked?** Who turns the _model_ into a _usable product_?
2. **Data Scientist?** They might advise which model fits the task and analyse how students use it. Useful, but not the ones who make it _openable and chat-able_.
3. **ML Engineer?** They might host the model and keep it fast and up. Critical, but their deliverable is an endpoint, not an app a student opens.
4. **AI Developer?** Builds the login, the chat interface, the memory of past questions, the prompt rules ("don't do the homework outright"), the storage so a teacher can review progress, and the guardrails that keep it safe.

**Conclusion:** the **AI Developer** — because making it _something a student can actually open and chat with_ means building the product around the model: interface, accounts, memory, rules, storage, and safety. The other roles supply the ingredient and keep it running; the AI developer turns it into a meal a real person can eat.

---

## 7. Common Pitfalls

- ❌ **Assuming the titles are precise.** They aren't — teams define them differently. Focus on _what the role chases_, not the label.
- ❌ **Thinking you need to be a data scientist to be a good AI developer.** You don't. Different craft.
- ❌ **Handing product work to the ML engineer.** Their job is a reliable endpoint, not a usable app.
- ❌ **Underestimating the collaboration.** The best AI developers _know who to ask_ and _when_.
- ❌ **Getting intimidated by maths.** The developer role is software and judgement first.

---

## 8. Hands-On Exercises

1. **Role sort (10 min).** Classify each task as **AI Developer / Data Scientist / ML Engineer**:
   (a) analysing why users churn, (b) building a login flow for an AI app, (c) keeping a model's endpoint under 300ms at 10k requests/sec, (d) writing the prompt that shapes a tutor's tone, (e) recommending which model to use for a task.
2. **Kitchen mapping (10 min).** Redraw the kitchen metaphor with one extra sentence per role explaining _what they'd hand to the next role_.
3. **Study Assistant roles (15 min).** List three tasks each role would own for the Study Assistant, and one sentence on how they'd hand work to the others.
4. **Self-audit (10 min).** Which of the three roles do you _currently_ resemble most, and which one are you trying to become? Write two sentences.

---

## 9. Checkpoint Questions

1. What is each role _chasing_ — in one word each?
2. Which role owns the product and the experience? Why?
3. Which role is responsible for keeping a model fast and reliable at scale?
4. Why is it OK that the lines blur on a small team?
5. What does being an excellent AI developer lean on _more_ than maths?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
