# Integration and Version Control with Git

> **Superskill 3 of 44** — AI Developer Bootcamp
> A beginner-to-junior training track for web developers stepping into AI development.

---

## Table of Contents

- [About This Repository](#about-this-repository)
- [Who This Is For](#who-this-is-for)
- [What You'll Learn](#what-youll-learn)
- [Repository Structure](#repository-structure)
- [Skill Index](#skill-index)
- [How to Use This Repository](#how-to-use-this-repository)
- [Prerequisites](#prerequisites)
- [Learning Path](#learning-path)
- [Cheatsheet](#cheatsheet)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## About This Repository

This repository contains the **complete training documentation** for **Superskill #3 — Integration and Version Control with Git**, the third of **44 superskills** in the AI Developer Bootcamp.

The superskill covers **6 core skills plus a conclusion**, taking you from _"what is version control?"_ to _"I've opened my first pull request on GitHub."_ It's the foundation for every project you'll ever work on — solo or in a team — because version control is the tool that makes collaborative development possible.

Each skill is delivered as a **standalone Markdown training document**, structured for progressive learning from **beginner → intermediate → junior developer**.

---

## Who This Is For

- **Web developers** with solid software fundamentals who want to move into AI development.
- **Self-taught developers** who want a structured, professional-quality curriculum.
- **Junior developers** preparing for their first AI-focused role.
- **Anyone** who has never used Git or GitHub — or who uses it but doesn't fully understand it.

> **No AI background required.** Familiarity with basic web development concepts is helpful but not mandatory.

---

## What You'll Learn

By the end of this superskill, you will be able to:

- ✅ Explain **what version control is** and why it matters for every developer.
- ✅ Describe **what Git is** — a free, open-source, distributed Version Control System.
- ✅ Use the **core Git commands** — `init`, `status`, `add`, `commit`, `rm --cached`.
- ✅ **Configure Git** — set your name and email, create aliases, use `.gitignore`.
- ✅ Understand **GitHub** — a web-based Git repository hosting service, **not** Git itself.
- ✅ **Connect local repos to GitHub** — `git remote add`, `git push`.
- ✅ Use the **contribution workflow** — fork, clone, pull request.
- ✅ Navigate the **fork → clone → change → push → pull request** cycle confidently.

---

## Repository Structure

```
integration-and-version-control-with-git/
│
├── README.md
│
├── 01-getting-started-with-git.md
├── 02-basic-git-commands.md
├── 03-configuring-git.md
├── 04-github-introduction.md
├── 05-working-with-remotes.md
├── 06-github-workflow.md
└── 07-conclusion.md
```

---

## Skill Index

| #   | Skill                        | Focus                                                         | Document                                                             |
| --- | ---------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------- |
| 1   | **Getting Started with Git** | What a VCS is, what Git is, the snapshot model                | [`01-getting-started-with-git.md`](./01-getting-started-with-git.md) |
| 2   | **Basic Git Commands**       | `init`, `status`, `add`, `commit`, `rm --cached`              | [`02-basic-git-commands.md`](./02-basic-git-commands.md)             |
| 3   | **Configuring Git**          | File states, `.gitignore`, `user.name`, `user.email`, aliases | [`03-configuring-git.md`](./03-configuring-git.md)                   |
| 4   | **GitHub Introduction**      | What GitHub is, Git vs. GitHub, the email alignment rule      | [`04-github-introduction.md`](./04-github-introduction.md)           |
| 5   | **Working with Remotes**     | `git remote add`, `git push`, connecting to GitHub            | [`05-working-with-remotes.md`](./05-working-with-remotes.md)         |
| 6   | **GitHub Workflow**          | Fork, clone, pull request — the contribution flow             | [`06-github-workflow.md`](./06-github-workflow.md)                   |
| 7   | **Conclusion**               | Wrap-up, cheatsheet, and what comes next                      | [`07-conclusion.md`](./07-conclusion.md)                             |

---

## How to Use This Repository

### As a learner

1. **Read the skills in order.** Each one builds on the previous.
2. **Do the exercises.** Every doc ends with hands-on work and checkpoint questions.
3. **Don't skip the worked examples.** They're the bridge from concept to practice.
4. **Keep the cheatsheet open.** The conclusion contains a full cheatsheet covering all commands — it's a reference you'll use daily.
5. **Practice on real repos.** Fork something, clone it, make a change, open a PR — the exercises walk you through it.

### As a reference

- Each document is **self-contained** — you can jump to any skill if you need a refresher.
- **Tables and comparison matrices** are designed for quick scanning.
- **Pitfalls sections** are short, concrete checklists you can return to while working.
- **The cheatsheet in the conclusion** covers every command from Skills 1–6.

### As an instructor

- Each skill doc includes **checkpoint questions** you can use for assessment.
- The **hands-on exercises** are sequenced — they build on each other across skills.
- The **worked examples** are self-contained and can be assigned as reading.
- **Git Immersion** (linked in Skill 6) is a recommended external practice resource.

---

## Prerequisites

| Level            | Requirement                                                                                  |
| ---------------- | -------------------------------------------------------------------------------------------- |
| **Required**     | None for this superskill — it's the entry point to version control.                          |
| **Helpful**      | A GitHub account and VSCode installed (created in [Superskill #2](../02-intro-to-the-web/)). |
| **Not required** | Any prior Git experience.                                                                    |

---

## Learning Path

| Skills | Theme               | Goal                                                  |
| ------ | ------------------- | ----------------------------------------------------- |
| **1**  | Introduction git    | Understand what version control is and why it matters |
| **2**  | Common Git commands | Use the core Git commands (init, add, commit, status) |
| **3**  | Configuring Git     | Configure Git for your identity and workflow          |
| **4**  | Start GutHub        | Understand GitHub — what it is, what it isn't         |
| **5**  | Connecting          | Connect local repos to GitHub (remote add, push)      |
| **6**  | Contribution        | Contribute to repos you don't own (fork, clone, PR)   |
| **7**  | Conclusion          | Review, cheatsheet, and what comes next               |

**Estimated time:** ~4–6 hours of reading + ~3–4 hours of exercises = **~8–10 hours total**, spread across a week or two.

---

## Cheatsheet

A full cheatsheet covering every command from Skills 1–6 is included in the **[Conclusion](./07-conclusion.md#3-cheatsheet)**.

**Quick reference — the most-used commands:**

```bash
# Setup
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Core loop
git init
git status
git add .
git commit -m "message"

# Remotes
git remote add origin <URL>
git push origin main

# Contribution workflow
# 1. Fork on GitHub
git clone https://github.com/YOUR-USERNAME/repo.git
# 2. Edit files
git add .
git commit -m "message"
git push origin main
# 3. Open a pull request on GitHub
```

> **The course's original cheatsheet** is available on [Google Drive](https://drive.google.com/file/d/1bCAgl2Baeoo1a8OhEPkf_y5d6xR8_crO/view).

---

## License

This material is provided for **educational use** as part of the AI Developer Bootcamp.

---

## Acknowledgements

- **Bootcamp:** AI Developer Bootcamp
- **Superskill:** 3 of 44 — _Integration and Version Control with Git_
- **Format:** Standalone Markdown training documents, beginner → junior developer level

---

**Version control is not optional — it's part of what "developer" means.**
