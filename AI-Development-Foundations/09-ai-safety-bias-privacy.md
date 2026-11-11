# Skill 9 — AI Safety, Bias and Privacy

> **Superskill:** AI Development Foundations, Ethics & Setup
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
   - [5.1 Hallucination](#51-hallucination--confidently-wrong)
   - [5.2 Bias — inherited from us](#52-bias--inherited-from-us)
   - [5.3 Privacy](#53-privacy--its-their-data-not-yours)
   - [5.4 The habits that follow](#54-the-habits-that-follow)
6. [Worked Example](#6-worked-example--softening-a-confident-wrong-answer)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Plenty of tutorials sprint past this to get to the fun code. **Please don't.** The developers who build a real career in this field — rather than a demo that embarrasses them later — are the ones who **take these three problems seriously from the very first line**.

None of this is about being fearful. **It's about being professional.**

The three problems:

1. **Hallucination** — the model states something false in flawless, confident prose.
2. **Bias** — the model inherits human prejudice from its training data.
3. **Privacy** — real people's data flows through your app, and you owe them care.

Each has a **concrete habit** that follows from it. Build those in from the start and they cost you almost nothing; **bolt them on later and they cost you a great deal.**

---

## 2. Why It Matters (for you, as a developer)

- **These are the failure modes that actually cause real-world harm.** Not exotic jailbreaks — confident wrong answers, quiet unfairness, careless data handling.
- **Reputation is asymmetric.** One embarrassing incident (a leaked prompt containing PII, a biased hiring filter, a hallucinated medical claim) can undo months of good work.
- **The habits are cheap at the start, expensive later.** A disclaimer added on day one is trivial; a disclaimer retrofitted across an entire product is a project.
- **You are responsible for what you build.** Not for solving society's problems, but for asking the honest questions and taking concrete first steps.

---

## 3. Prerequisites

- Skill 5 (what an LLM is; hallucinations).
- Skill 7 (why answers vary; why low temperature doesn't equal truth).
- Skill 8 (value shapes — helps you judge "high-stakes" vs. "low-stakes").

---

## 4. Key Concepts

1. **Hallucination** = confidently wrong. Never wire a model **straight into a decision that matters** without a check in between.
2. **Bias** is **inherited from human writing** — models can quietly disadvantage some users.
3. **Privacy:** real people's data is in your hands. **Safe default: send less.**
4. **Four non-negotiable habits** follow:
   - Tell people **they're talking to an AI** and **it can be wrong**.
   - **Don't hand sensitive data to a model** without a real reason.
   - **Keep a human in the loop** for anything that carries weight.
   - **Think about fairness before you ship**, not after someone complains.
5. **Build these in from the start.** Cheap early, expensive late.

---

## 5. Concepts Explained

### 5.1 Hallucination — confidently wrong

We met this in Skill 5, and it's worth repeating because **it's the one that causes the most real-world harm**.

> **An LLM can state something false in flawless, confident prose.**

Imagine:

- your **study assistant** inventing a historical date,
- your **coding assistant** suggesting a function that doesn't exist.

**The lesson for a builder is firm:**

> **Never wire a model straight into a decision that matters without a check in between.**

That check can take three forms:

| Check                       | What it looks like                                                                     |
| --------------------------- | -------------------------------------------------------------------------------------- |
| **Human review**            | A person approves the output before it takes effect                                    |
| **Second system verifying** | Another process (a rule engine, a retrieval step, a validator) cross-checks the output |
| **Design constraint**       | The AI simply doesn't get the final say on anything high-stakes                        |

**Beginner framing:** treat the model's output as a _draft_, never a _verdict_, whenever being wrong has consequences.

**Intermediate framing:** "high-stakes" is context-dependent. A poem generator has no stakes; a legal summariser has high stakes; a study assistant has _medium_ stakes that vary by question. Design your checks proportional to the stakes.

**Junior-dev framing:** this is the AI equivalent of _never trust client input_. Client input goes through validation; model output goes through the same discipline.

---

### 5.2 Bias — inherited from us

> **A model learns from human writing, and human writing is soaked in human prejudice.**

Without care, that bias can:

- **seep into a model's answers**, and
- **quietly disadvantage some of your users** —

in hiring tools, in lending, in **who gets a helpful answer and who doesn't**.

**What you are NOT responsible for as a junior developer:** solving societal bias. That's a research and policy problem, not a solo project.

**What you ARE responsible for:** asking **the honest question**:

> **Does this product work as well for everyone who'll use it, or only for people like me?**

**A concrete first step:** **test with a variety of users and inputs.** Different names, different dialects, different backgrounds, different use cases. If your model answers well for one group and poorly for another, you've found bias — and you can start addressing it.

**Beginner framing:** bias isn't a bug the model "has"; it's a **pattern reflected from data**. Your job is to notice when that reflection is skewed.

**Intermediate framing:** bias shows up as _differential quality_ — the model's helpfulness varies systematically across groups. Measuring that difference (even informally) is the first concrete bias check.

---

### 5.3 Privacy — it's their data, not yours

> **The instant real people use your app, you're handling their information**, and you owe them **genuine care** about what you send to a model and how you store it.

**The safe default is to send less:**

- **Don't forward personal details** to a third-party model **unless you truly need to** and **are allowed to**.
- **Strip identifiers** (names, emails, account IDs) wherever the task doesn't require them.
- **Know your retention.** What you send is logged by the provider; what you store is your responsibility.

We'll go deeper on the specifics in the next skill (Prompt Injection and PII). For now, internalise the default: **less is safer.**

**Beginner framing:** treat every piece of user data as if it were your own medical record. Would you want it pasted into a stranger's chat window? Then don't paste a user's.

**Intermediate framing:** privacy has two surfaces — **what leaves your app** (sent to the model) and **what stays** (your storage). You control both. Default to minimising both.

---

### 5.4 The habits that follow

These principles turn into **a few simple, non-negotiable habits**:

| Habit                                                                           | Why it matters                                                 |
| ------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| **Tell people plainly that they're talking to an AI and that it can be wrong.** | Honesty; sets expectations; reduces harm from confident errors |
| **Don't hand sensitive data to a model without a real reason.**                 | Privacy; you control the flow                                  |
| **Keep a human in the loop for anything that carries weight.**                  | Safety; proportional review                                    |
| **Think about fairness before you ship, not after someone complains.**          | Bias; cheaper and more effective to build in than to retrofit  |

**The economics of these habits:**

> **Build these in from the start and they cost you almost nothing.**
> **Bolt them on later and they cost you a great deal.**

This isn't a moral lecture — it's a **practical engineering trade-off**. The teams that bolt safety on late spend more, ship slower, and often ship worse products. The teams that build it in from day one barely notice the cost.

---

## 6. Worked Example — softening a confident wrong answer

> **Question:** Your assistant gives a student a wrong answer, delivered with total confidence. Name one concrete thing you could build into the product to soften the damage.

**Reasoning walk-through:**

The question isn't "how do we stop all wrong answers?" (you can't — see Skill 5). The question is: **what do you build so that when a wrong answer happens, the damage is smaller?**

**Options, with trade-offs:**

| Approach                                                       | How it softens damage                                     | Trade-off                                                  |
| -------------------------------------------------------------- | --------------------------------------------------------- | ---------------------------------------------------------- |
| **AI disclaimer + uncertainty language**                       | Sets expectations; users learn to verify                  | Feels clunky if overdone                                   |
| **"Verify with a source" link next to factual claims**         | Gives users a fast path to check                          | Requires source retrieval in the pipeline                  |
| **Confidence signalling** (e.g., "I'm not certain about this") | Distinguishes high-confidence from low-confidence answers | Models are often confidently wrong — signals are imperfect |
| **Human review for high-stakes topics** (e.g., medical, legal) | Prevents harm from slipping through silently              | Slower; more expensive                                     |
| **"Was this helpful?" feedback button**                        | Detects and flags wrong answers so you can improve        | Only helps _after_ the first user sees the error           |
| **Second-model verification**                                  | A separate model reviews the answer for contradictions    | Adds latency and cost                                      |
| **Retrieval grounding** (RAG — later skill)                    | The answer cites an actual retrieved source               | Requires building a retrieval pipeline                     |

**The single most concrete, cheapest thing to build:**

> **A visible "AI-generated — may be wrong, please verify" notice, paired with a per-answer thumbs-up/down feedback button.**

Why this combination:

- **The notice** addresses the trust problem directly.
- **The feedback button** turns every wrong answer into a data point you can act on.
- **Neither requires a retrieval pipeline** or human staff. **Both are cheap from day one.**

**Then, as the product matures**, layer in **retrieval grounding** and **human review for high-stakes topics** — because the disclaimer softens damage but doesn't prevent it.

**The general principle:**

> **You can't eliminate wrong answers. You can make them visible, correctable, and expensive to ignore.**

---

## 7. Common Pitfalls

- ❌ **"We'll add safety later."** Safety retrofitted is expensive, slow, and often incomplete. Build it in from the start.
- ❌ **Trusting low temperature to prevent hallucinations.** It makes answers _repeatable_, not _true_ (see Skill 7).
- ❌ **Assuming bias is someone else's problem.** Junior developers aren't responsible for society's bias — but they _are_ responsible for asking whether their product works for everyone who'll use it.
- ❌ **Sending the whole user profile to the model because it's convenient.** Send less. Strip identifiers unless the task genuinely requires them.
- ❌ **Letting the model have the final say on anything high-stakes.** Add a human, a validator, or a design constraint.
- ❌ **Skipping the AI disclaimer.** Users assume a fluent answer comes from an informed source — tell them otherwise, visibly.
- ❌ **Treating fairness testing as a one-off.** Test with varied users and inputs _before_ launch and _after_, because behaviour drifts.

---

## 8. Hands-On Exercises

1. **Stakes audit (10 min).** List five AI features you've used (or built). For each, classify as **low**, **medium**, or **high** stakes, and name the check you'd want in between the model and the decision.
2. **Bias probe (15 min).** Take a task an LLM can perform (e.g., "draft a professional bio"). Ask it to draft bios for two different names — one common in one culture, one in another. Note any differences in tone, content, or quality. What would you change in your product to catch this?
3. **Data minimisation (10 min).** For an AI note-taking app, list everything that _might_ be sent to the model. Then mark each item: _needed_ or _not needed_. How much could you cut?
4. **Disclaimer design (10 min).** Write the exact wording of the AI disclaimer you'd put on the Study Assistant. Aim for plain, honest, not alarmist.
5. **Softening strategy (15 min).** Using the table in §6, pick _two_ mechanisms you'd build into the Study Assistant to soften a confidently wrong answer. Justify each in one sentence.
6. **Habits checklist (5 min).** For the four habits in §5.4, write one concrete implementation choice you'll make for the Study Assistant's first version.

---

## 9. Checkpoint Questions

1. In one sentence, what is a **hallucination**, and why can't it be fully prevented?
2. What does it mean to "never wire a model straight into a decision that matters without a check in between"? Name three forms that check can take.
3. Where does **bias** in an LLM come from, and what's the honest question you should ask about your own product?
4. What is the **safe default for privacy**, and why?
5. Name the **four non-negotiable habits** this skill recommends.
6. Why is "build these in from the start" a _practical_ recommendation, not just an ethical one?
7. What's one concrete thing you can build to soften the damage of a confidently wrong answer?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
