# Skill 11 — AI Product Thinking

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 Think like a product person](#51-think-like-a-product-person)
   - [5.2 The six questions a real idea can answer](#52-the-six-questions-a-real-idea-can-answer)
   - [5.3 The MVP](#53-the-mvp--the-discipline-that-gets-things-finished)
   - [5.4 Scoping down](#54-scoping-down-is-not-giving-up-on-the-vision)
6. [Worked Example](#6-worked-example--scoping-the-study-assistant-mvp)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Before you build a single feature, it pays to **slow down and think like the person who has to justify why the thing should exist at all.**

- **Engineers love to start coding.** The best ones **resist just long enough** to make sure they're coding the _right_ thing.
- **A clever demo impresses your friends for an evening.**
- **A product quietly solves someone's problem, day after day** — and that's a much higher bar.

This skill gives you two disciplines:

1. **Six plain questions** a solid idea can answer without flinching.
2. **The MVP habit** — the smallest version that still genuinely helps someone, which is how projects actually get finished.

---

## 2. Why It Matters (for you, as a developer)

- **It's the cheapest possible design work.** Answering six questions takes an hour. Rebuilding a wrong product takes months.
- **It separates shipping from dreaming.** The MVP habit is what makes the difference between "I have an idea" and "I have a product."
- **It connects every earlier skill.** The value shape comes from Skill 8, the risks from Skill 9 and 10, the AI's role from Skill 5 — this skill asks you to _assemble_ them into a plan.
- **It's what the Final Project will demand.** The idea brief and quiz at the end of this Super Skill will ask exactly these questions.

---

## 3. Prerequisites

- Skill 8 (AI use cases; the three shapes of value).
- Skill 9 and Skill 10 (safety, bias, privacy, prompt injection, PII).

---

## 4. Key Concepts

1. **Slow down before coding.** Resist just long enough to make sure you're coding the _right_ thing.
2. **Six questions** a solid idea can answer without flinching: **problem, audience, AI's role, value, risks, success signal.**
3. **"Everyone" is not an audience.** Picture one real person.
4. **MVP = the smallest version of your idea that still genuinely helps someone**, built quickly to put in front of real people and learn from them.
5. **The temptation to plan everything at once is exactly how projects die** under their own weight.
6. **Scoping down isn't giving up on the vision — it's the fastest honest route towards it.**

---

## 5. Concepts Explained

### 5.1 Think like a product person

> **Engineers love to start coding. The best ones resist just long enough to make sure they're coding the right thing.**

This is a **deliberate pause**, not a fear of building. It's the same idea as writing acceptance criteria before code: cheap now, expensive later.

**Beginner framing:** before you spend a weekend building something, spend an hour making sure it's the _right_ something.

**Intermediate framing:** the pause is where you **catch the wrong problem** — the thing nobody actually needs, or the thing whose value shape doesn't hold up under questioning. Catching it before code is the cheapest possible bug fix.

**Junior-dev framing:** this is the same design review you'd do on any feature — except the "feature" is the _entire product_, so the stakes on the review are higher.

---

### 5.2 The six questions a real idea can answer

> **A solid idea can face a few plain questions without flinching, and each one exists for a reason.**

| Question                                                    | Why it exists                                                                    | If the answer is weak...                                                       |
| ----------------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **What problem does this solve?**                           | Forces you to name the pain in one sentence                                      | If you can't, _there probably isn't one_                                       |
| **Who exactly is it for?**                                  | "Everyone" is not an audience                                                    | Picture **one real person** — if you can't, you don't have a user yet          |
| **What does the AI actually do in it?**                     | Forces you to be specific about the model's _job_                                | If the answer is vague, you're **sprinkling "AI" on for show**                 |
| **Where's the value?**                                      | Ties the idea to _time, money, or quality_ (Skill 8)                             | Which one, **concretely**? If it can't say, it's a demo                        |
| **What could go wrong, and how will you guard against it?** | Forces you to confront **hallucination, bias, privacy, injection** (Skills 9–10) | Name the **real risks** and your **defences** — vague confidence is a red flag |
| **How will you know it's working?**                         | Forces a **number or a signal** you could check in a month                       | If you can't check it, you can't learn — you're guessing                       |

**Why each question exists:**

- **Problem** — without a named pain, there's nothing to solve.
- **Audience** — designing for "everyone" designs for no one; designing for _one person_ is concrete.
- **AI's role** — keeps you from adding "AI" as decoration; forces you to justify why the model is _the_ tool for the job.
- **Value** — the "squirm test" from Skill 8, now embedded in the idea check.
- **Risks** — bakes safety into the plan from the start (Skill 9's lesson: cheap early, expensive late).
- **Success signal** — without a number or signal, you can't tell whether you're building something useful or something impressive.

**Beginner framing:** imagine a skeptical friend asking these six questions. If you can answer all six without flinching, you have a real idea. If any one makes you sweat, that's where to work.

**Intermediate framing:** these six are a **pre-flight checklist**, not a post-mortem. They're cheap to answer and catch expensive mistakes. Answering them in writing is itself valuable — writing forces clarity that conversation lets you dodge.

---

### 5.3 The MVP — the discipline that gets things finished

> **MVP** stands for **minimum viable product**: **the smallest version of your idea that still genuinely helps someone**, built quickly so you can put it in front of real people and learn from them **instead of guessing.**

**Why this matters:**

> **The temptation is always to plan everything at once, and that's exactly how projects die under their own weight.**

**The core discipline:**

- **Pick one thing.**
- **Do it well.**
- **Ship it.**
- **Learn from real users.**
- **Add the next thing on top of something that already earns its keep.**

**Beginner framing:** if you try to build ten features at once, you finish none of them. If you build one feature well, you've shipped a product — and _then_ you can add the rest.

**Intermediate framing:** every feature you add before validating the core is a bet you're making _without evidence_. The MVP is **the cheapest possible way to get evidence** — one real user's reaction is worth more than a month of planning.

**Junior-dev framing:** in web terms, it's the difference between a full-stack app with a dozen integrations and a single page that does one useful thing for one real person. Ship the single page first.

---

### 5.4 Scoping down is not giving up on the vision

> **Scoping down like this isn't giving up on the vision; it's the fastest honest route towards it.**

The vision can stay large. The **first version** should stay small. This is not a compromise — it's how the vision _actually gets built_.

**The sequence:**

1. **Vision** — the full product you imagine.
2. **MVP** — the smallest version that already helps someone.
3. **Iterate** — add each subsequent feature **on top of something that already earns its keep.**

**The mistake to avoid:** thinking "if I just add _one more feature_ before launching, it'll be more impressive." That's how launches slip by months, and how projects die under their own weight.

---

## 6. Worked Example — scoping the Study Assistant MVP

> **The temptation** for the Study Assistant: **quizzes, flashcards, progress charts, and a dozen clever features.**

**The MVP is not that.** The MVP is **one thing done well:**

> **Answer a student's study question clearly and helpfully.**

**Walk through the six questions for this MVP:**

| Question                            | Answer                                                                                                                                                                                          |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **What problem does this solve?**   | A student has a question about something they're studying and doesn't have quick, clear help available.                                                                                         |
| **Who exactly is it for?**          | One student — say, someone revising for a specific exam, with a specific subject.                                                                                                               |
| **What does the AI actually do?**   | Takes a study question and produces a clear, level-appropriate explanation.                                                                                                                     |
| **Where's the value?**              | **Time saved** (immediate help vs. waiting for a tutor) and **quality improved** (explanations adapted to the student's level).                                                                 |
| **What could go wrong?**            | Hallucination (wrong facts — needs disclaimer + verify path); PII (student pastes personal details — needs masking); prompt injection (student tries to override rules — needs firm structure). |
| **How will you know it's working?** | **Signal:** users ask follow-up questions in the same session. **Number:** 60%+ of first-session users return within a week.                                                                    |

**What's _not_ in the MVP:**

- Quizzes
- Flashcards
- Progress charts
- Teacher dashboards
- Multi-subject support

**These are season two.** They go _on top of_ a first version that already works.

**The insight:**

> **If that single thing works and people find it useful, everything else is season two** — added later **on top of something that already earns its keep.**

**The pivot this makes possible:** once the MVP ships, real users will tell you _which_ of the season-two features they actually want. You stop guessing and start building to evidence.

---

## 7. Common Pitfalls

- ❌ **Starting to code before answering the six questions.** The pause is cheap; the rebuild isn't.
- ❌ **Designing for "everyone."** "Everyone" is not an audience. Pick one real person.
- ❌ **Sprinkling "AI" on for show.** If the model's role isn't specific, AI probably isn't the point of the product.
- ❌ **Skipping the risk question.** Naming risks _before_ building is how you guard against them (Skill 9's lesson).
- ❌ **Having no success signal.** If you can't name a number or signal, you can't tell whether the product works.
- ❌ **Building the vision first.** Ten features at once = zero features finished. Ship one.
- ❌ **Believing scoping down is defeat.** It's the fastest honest route to the vision, not a detour from it.
- ❌ **Adding features before validating the core.** Every unvalidated feature is a bet without evidence.

---

## 8. Hands-On Exercises

1. **Six-question audit (15 min).** Take the idea you noted in Skill 8, exercise 3. Answer all six questions in writing. **Highlight any question you can't answer confidently** — that's where to work next.
2. **Audience of one (10 min).** Answer _"Who exactly is it for?"_ for your idea. Write a one-paragraph description of **one real person** (a specific role, context, and pain). Would this person actually use your product? Why?
3. **Squirm test (10 min).** For your idea, answer _"Where's the value?"_ with one of: **time, money, or quality**. Write the concrete version ("saves X minutes per task") not the abstract one ("saves time").
4. **Risk inventory (10 min).** For your idea, list:
   - the **top hallucination risk** and how you'd soften it,
   - the **top PII risk** and how you'd mask or avoid it,
   - the **top prompt-injection risk** and how you'd structure the prompt.
5. **Success signal (10 min).** Write down one **number** and one **signal** you could check in a month to tell whether your product is working. Aim for something measurable, not aspirational.
6. **MVP scoping (20 min).** Take your idea and write down:
   - the **full vision** (5+ features you imagine),
   - the **single smallest feature** that would already make it useful to someone.
     _That one feature is your MVP._

---

## 9. Checkpoint Questions

1. Why does the skill recommend **slowing down before coding**?
2. Name the **six questions** a solid idea can answer without flinching.
3. Why is "everyone" not an audience? What should replace it?
4. Why does the skill insist on naming **which value shape** (time, money, or quality) — not just "value"?
5. What is an **MVP**, in one sentence?
6. Why is **the temptation to plan everything at once** dangerous?
7. Why is **scoping down** the fastest route _towards_ the vision, not a detour from it?
8. For the Study Assistant, what is the MVP — and what specifically is _not_ in it?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
