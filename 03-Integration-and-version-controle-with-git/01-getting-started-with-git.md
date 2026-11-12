# Skill 1 — Getting Started with Git

> **Superskill:** Integration and Version Control with Git
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--rolling-back-after-a-broken-change)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

> **We can imagine that web design is like a building and Git is one of the many important pillars that web design is built on.**

This skill is the **entry point** to version control — the practice of tracking every change to your code, so you can see what changed, when, and why — and undo it if needed.

**The four objectives of this superskill, stated upfront:**

1. **Understand what Git is.**
2. **Learn how to use the basic Git commands.**
3. **Discover how to configure Git.**
4. **Understand what GitHub is and how to work with remote repositories.**

This skill covers the _first_ — the mental model. The rest of the superskill builds the practice on top of it.

**The two core concepts of this skill:**

- **VCS** — Version Control System: the _category_ of software that tracks changes.
- **Git** — the specific _tool_ that implements version control, free and open source.

---

## 2. Why It Matters (for you, as a developer)

- **Without version control, you're one mistake away from losing months of work.** A corrupted file, an accidental deletion, a broken refactor — all become permanent. Git makes them reversible.
- **Git is the industry standard.** Every professional team uses version control. It's not optional — it's part of what "developer" means.
- **It's the foundation for collaboration.** Multiple developers working on the same codebase depend on Git to keep changes organized and non-conflicting.
- **It's also a safety net for solo work.** Even alone, the ability to _"roll back to a previous version"_ is one of the most valuable things you'll ever learn.

---

## 3. Prerequisites

- Skill 8 of Superskill #2 (Code Editors — the three-tool environment includes Git).
- Skill 9 of Superskill #2 (Set Your Dev Environment — VSCode installed).
- Skill 10 of Superskill #2 (GitHub Account — you have a GitHub account).

---

## 4. Key Concepts

1. **A VCS** (Version Control System) is **software that helps developer teams track and manage source code changes over time**.
2. **A snapshot** is a saved checkpoint of your files at a point in time — the core unit of version control.
3. **Without a VCS**, you keep multiple copies of code — which is **dangerous** (corruption, deletion, lost work).
4. **A VCS shows you all versions of your code** with a **clear history of changes** — so you can **go back to older versions** and try a different approach.
5. **Git** is a **free and open-source VCS** designed for everything from small to very large projects — with **speed and efficiency**.
6. **Git creates snapshots** of the codebase whenever you tell it to.
7. **Git is essential for collaboration** — it prevents code conflicts and allows revisiting previous snapshots.
8. **The rollback advantage:** if you break the app, you can **roll back to a previous version** instead of starting from scratch.

---

## 5. Concepts Explained

### 5.1 What a VCS is

> **A version control system is a software tool that helps developer teams track and manage source code changes over time.**

**What "track and manage" means in practice:**

> **As you edit and add to your code, you tell the version control system to take a snapshot of your files or save a checkpoint of your progress.**
> **The version control system saves that snapshot permanently so you can recall it later on if you need it.**

**The two operations:**

1. **Take a snapshot** — whenever _you_ decide the current state is worth saving.
2. **Recall a snapshot** — when you need to go back to that state.

**Beginner framing:** a VCS is a **time machine for your code**. Every snapshot is a point you can return to.

**Intermediate framing:** a VCS stores **the history of changes**, not just the latest version. You can diff any two snapshots, see who changed what and when, and merge parallel lines of work. This history is the foundation for every collaboration workflow.

**Junior-dev framing:** think of it as **undo for your entire project, across all files, forever**. Not "undo one keystroke" — undo to _any_ saved point, for _any_ subset of files.

---

### 5.2 Why a VCS matters — the danger of copies

> **Without a VCS, you're tempted to keep multiple copies of code on your computer.**
> **This is dangerous because it's easy for a file to get corrupted or deleted — meaning you're susceptible to losing months or even years' worth of work.**

**The "multiple copies" pattern** — which every developer has done at least once:

```
project/
project-final/
project-final-v2/
project-final-v2-ACTUAL/
project-final-v2-ACTUAL-USE-THIS-ONE/
project-working-backup-2024-03-15/
```

**Why this fails:**

- **No clear order.** Which copy is newest? Which is correct?
- **No history.** You can't see _what_ changed between copies.
- **No safety.** If the folder gets corrupted, _all_ copies are gone.
- **No collaboration.** Sharing copies by email or USB stick is fragile.
- **No confidence.** Restoring an old version means guessing which copy to use.

**How a VCS solves it:**

> **Version control systems solve that problem by presenting you with all versions of your code with a clear history of the changes made.**
> **This allows you to go back to older versions of the code and try a different approach.**

**Beginner framing:** instead of folders full of "final" and "final-v2," you have **one folder** with **a full history** you can browse at any time.

**Intermediate framing:** VCS replaces the **"copy as backup"** habit with a **linear, labeled history**. Instead of guessing which copy is newer, you have explicit commits with messages like _"fix login bug"_ or _"add signup form."_

**Junior-dev framing:** this pattern is _why_ Git feels magical the first time. You stop thinking in "versions of files" and start thinking in "history of changes."

---

### 5.3 Git — what it is

> **Git is a free and open-source VCS designed to handle everything from small to very large projects with speed and efficiency.**

**In plain English:**

> **Git is a tool that allows developers to track versions of their code over time.**
> **It does this by creating "snapshots" of the current state of the codebase whenever you tell it to.**

**The key phrase:** _"whenever you tell it to."_ Git does **not** auto-save continuously. You decide when a state is worth saving — those are **commits**, and each one is a **snapshot**.

**Why Git specifically?**

| Property                                 | What it means for you                                  |
| ---------------------------------------- | ------------------------------------------------------ |
| **Free and open source**                 | No cost, no license, full transparency                 |
| **Handles small to very large projects** | Same tool for a personal script and a massive codebase |
| **Speed and efficiency**                 | Fast operations even on large histories                |
| **Industry standard**                    | The skill transfers to every job, every team           |

**Beginner framing:** Git is the _tool_; version control is the _concept_. Git is one of several VCS tools, but it's the most widely used.

**Intermediate framing:** Git is a **distributed** VCS — every clone contains the _entire_ history, not just the latest version. This is why it's fast (operations are local) and resilient (no single server failure can lose history).

**Junior-dev framing:** when you `git init` in a project, you're turning a folder into a **Git repository** — a folder whose changes are tracked from that moment on. The folder is the same; the _behavior_ is different.

---

### 5.4 Git for collaboration

> **Git is essential when collaborating with other developers to ensure that there are no code conflicts between them, and that previous "snapshots" of the code can be revisited if necessary.**

**Two collaboration benefits:**

1. **No code conflicts** — Git's branching and merging tools help multiple developers work on the same codebase without stepping on each other.
2. **Revisiting previous snapshots** — if a change broke something, the team can identify exactly which change and revert it.

**Why this matters for teams:**

- **Parallel work.** Two developers can edit the same codebase at the same time — on different branches — and merge later.
- **Accountability.** Every commit has an author and a message. You know _who_ changed _what_ and _why_.
- **Safety net.** If a merge goes wrong, you can undo it. If a feature doesn't work out, you can abandon the branch.

**Beginner framing:** collaboration with Git means _shared history_ — everyone works from the same record of changes.

**Intermediate framing:** Git's **branching model** is what makes collaboration scale. A branch is a _separate line of history_ you can develop on, then merge back when ready. This is how professional teams ship features without destabilizing the main codebase.

**Junior-dev framing:** in your first job, "make a branch, make the change, open a PR" will be the daily rhythm. Everything starts from the basic Git commands in the skills that follow.

---

### 5.5 Git as a safety net — the rollback advantage

> **For example, if you are coding and you accidentally break or crash the app, you've just lost all your progress and you're forced to start from scratch.**
> **However, it's easier and safer if you're using Git and you can simply roll back to a previous version of the code.**

**The scenario, without Git:**

1. You've been coding for hours.
2. You make a change.
3. The app crashes.
4. You don't know what broke.
5. You have to figure out what to undo — and if you can't, you start over.

**The scenario, with Git:**

1. You've been coding for hours — and committing regularly.
2. You make a change.
3. The app crashes.
4. You run `git diff` — see exactly what changed since your last commit.
5. If needed, `git checkout -- .` (or `git restore`) to discard the change.
6. **You're back to the working version in seconds.**

**The general principle:**

> **Git turns "I broke it and I can't undo it" into "I broke it — let me go back one step and try again."**

**Beginner framing:** Git gives you the freedom to experiment, because you can always come back.

**Intermediate framing:** the safety net isn't just for mistakes — it's for _exploration_. **Try a radical refactor?** Commit first. **Attempt a tricky fix?** Commit first. **Play with an unfamiliar library?** Commit first. The ability to roll back makes _bold_ engineering possible.

**Junior-dev framing:** the single most common beginner-use of Git is **reverting a broken change**. Even before you learn branches or collaboration, learning to undo is what makes Git immediately valuable.

---

## 6. Worked Example — rolling back after a broken change

> **Scenario:** you're building a small JavaScript app. You make a change to a function, save the file, and the app breaks.

**Step 1 — what happened?**
You edited `app.js`, saved, and the browser now shows errors in the console. You can't tell what's wrong, and you don't remember the previous working state.

**Without Git:**

- You try to undo the edit by memory.
- You guess which lines to revert.
- You might make it worse.
- You might lose unrelated changes you actually wanted.
- Worst case: you start over from scratch.

**With Git:**

1. **`git status`** — shows which files have changed since the last commit.
   ```
   modified:   app.js
   ```
2. **`git diff app.js`** — shows exactly what changed, line by line.
   ```
   - function greet(name) {
   -   return "Hello, " + name;
   - }
   + function greet(name) {
   +   return "Hello, " + name
   + }
   ```
   **The missing semicolon isn't the bug** — but this shows you _what you changed_.
3. **`git diff`** reveals the actual problem — perhaps a variable renamed in a nearby function.
4. **`git restore app.js`** — discards your local changes, restoring the file to the last committed version.
5. **The app works again.** You take a breath, re-read the change, and try again.

**What this example teaches:**

- **`git status`** tells you _which_ files changed.
- **`git diff`** tells you _what_ changed.
- **`git restore`** (or `git checkout -- <file>`) takes you back to the last good state.
- **The safety net is real** — you recover in seconds, not hours.
- **The discipline matters:** you only get this safety if you **commit regularly**. If your last commit was three hours ago, "rollback" loses three hours of work.

---

## 7. Common Pitfalls

- ❌ **Thinking Git = GitHub.** Git is the _tool_; GitHub is a _hosting platform_ for Git repositories. You can use Git without GitHub; you can't use GitHub without Git.
- ❌ **Skipping commits because "it's just a small change."** Frequent commits are what make the safety net work. Small commits are easier to reason about than large ones.
- ❌ **Waiting until you break things to learn Git.** Learn it on a project that _isn't_ broken — so you're confident when you need it.
- ❌ **Believing "my code is safe on my laptop."** Laptops fail, drives corrupt, files get deleted. A remote repository (GitHub) is a _backup_ — not just a collaboration tool.
- ❌ **Treating version control as optional for solo work.** It's not. Solo developers benefit from rollback, history, and safety just as much as teams.
- ❌ **Copying folders as backup.** "project-final-v2" is the anti-pattern. Git replaces it entirely.
- ❌ **Assuming Git auto-saves continuously.** It doesn't. _You_ decide when to commit — and you should, regularly.

---

## 8. Hands-On Exercises

1. **Reflect on the copy problem (10 min).** Have you ever lost work because of a corrupted or deleted file? Have you ever kept multiple "final" versions of a project? Write down one story, and what would have been different with version control.
2. **VCS in your own words (10 min).** Write a two-sentence definition of a VCS and a two-sentence definition of Git. How are they related? How are they different?
3. **The snapshot analogy (10 min).** The course calls each save a "snapshot" or "checkpoint." In your own words, why is that a useful metaphor? What does it capture — and what does it miss?
4. **The collaboration question (10 min).** Imagine two developers editing the same file at the same time. How does Git help them avoid overwriting each other's work? (You don't need to know the exact commands — describe the _idea_.)
5. **The rollback scenario (15 min).** Write a short scenario (5–6 sentences) in which a developer breaks their app and uses Git to recover. What did they do before the break? What did they do after?
6. **Predict the commands (10 min).** Without looking at a tutorial, guess which Git commands do the following:
   - (a) see what files have changed,
   - (b) see exactly what changed in a file,
   - (c) discard local changes to a file,
   - (d) save a snapshot of the current state.
     Then, when you reach the next skill, check your guesses.

---

## 9. Checkpoint Questions

1. In one sentence, what is a **version control system**?
2. What is a **snapshot**, and when is one taken?
3. Why is keeping multiple copies of code **dangerous**?
4. What does a VCS provide that copies of folders do not?
5. In one sentence, what is **Git**?
6. What does it mean that Git is **free and open source** — and why does that matter?
7. Why is Git **essential for collaboration**? Name two reasons.
8. Describe the **rollback advantage** in your own words — using a concrete scenario.
9. Why is "commit regularly" important for the safety net to actually work?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
