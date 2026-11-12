# Skill 6 — GitHub Workflow

> **Superskill:** Integration and Version Control with Git
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--fork-clone-fix-pull-request)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Skill 5 showed you how to **push to your own repo**. But what happens when you want to contribute to **someone else's repo** — an open-source project, a client's codebase, a teammate's project?

You **cannot push directly** to a repo you don't own. GitHub's workflow solves this with three ideas:

| Concept          | What it is                                                       |
| ---------------- | ---------------------------------------------------------------- |
| **Fork**         | Your **own copy** of someone else's repo, under your username    |
| **Clone**        | A **local copy** of that forked repo, on your machine            |
| **Pull request** | A **proposal to merge** your changes back into the original repo |

This is the **standard contribution workflow** for open source — and for most team collaboration on GitHub.

> **Note:** The course also points to **Git Immersion** — a guided practice resource for the fundamentals of Git.

---

## 2. Why It Matters (for you, as a developer)

- **Most GitHub work is on repos you don't own.** Contributing to open source, working with a team, fixing a client's bug — all use **fork → clone → change → pull request**.
- **It's the daily workflow of professional developers.** Even inside a team, the same flow (branch → PR → review → merge) is how code changes move from idea to production.
- **Forking is _GitHub-specific_.** Learning it means learning the _platform_, not just the tool — a critical distinction for collaboration.
- **It lets you experiment safely.** Your fork is _yours_ — you can push freely without affecting the original.

---

## 3. Prerequisites

- Skill 2 (basic commands — `init`, `add`, `commit`).
- Skill 3 (configuring Git — **email set**).
- Skill 4 (GitHub account).
- Skill 5 (working with remotes — `git remote add`, `git push`).

---

## 4. Key Concepts

1. **You cannot push directly to a repo you don't own.** GitHub enforces permissions.
2. **Fork** = **a copy of someone else's repo, under your username**. You can push to your fork freely.
3. **Forking is a GitHub feature**, not a Git feature. It's about permissions on the platform.
4. **Clone** = **download a remote repo to your local machine**. Use `git clone <URL>`.
5. **`git clone`** does in one step what `git init` + `git remote add` + `git pull` do together.
6. **Pull request (PR)** = a **proposal to merge** your fork's changes into the original repo. The maintainer reviews it, then merges or rejects.
7. **The full flow:** **fork → clone → change → push → pull request → review → merge**.

---

## 5. Concepts Explained

### 5.1 Fork — your own copy on GitHub

> **When collaborating with others, you're unable to push directly to the original repository** (imagine if you could play with one of the world's largest open source projects and repositories… that would be insane).
> **So the logical thing to do is make a copy of someone else's remote repository and make sure it is under our username so that we can push code to it.**
> **This ensures that our experimenting with the repository doesn't affect the original version.**

**How to fork:**

> **To practice forking, head over to any repo on GitHub and on the top right you will see a button with the text Fork.**
> **Click on this button and you will have a copy of the repository under your name!**

**What you get:**

- A **complete copy** of the original repo — history, files, all branches (by default).
- The copy lives at `github.com/YOUR-USERNAME/repo-name`.
- **You have full push access** to your fork.
- **You do NOT have push access** to the original.

**The critical note:**

> **"Forking" is strictly a GitHub feature and it is not by any means related to Git.**
> **It is simply a way to make your own copy of a repository on your account where you have permission to push your code to GitHub.**

**Beginner framing:** forking creates a **personal copy** of someone else's repo. It's yours — you can edit freely.

**Intermediate framing:** forking happens **on GitHub** — the platform tracks the "fork relationship" so the original knows your fork exists. This matters for pull requests (see §5.3) — GitHub knows which repo to propose changes _to_.

**Junior-dev framing:** forking vs. cloning is a common point of confusion. **Fork** = copy on GitHub. **Clone** = copy on your machine. You usually fork first (to get your own remote), then clone (to work locally).

---

### 5.2 Clone — the local copy

> **Once you have applied "forking" on the repository, you need to select it (the remote one you just made) and download the code on your local computer** (i.e., make a local repository).
> **Instead of making a folder and going through the whole `git init` process and adding a remote, you can conveniently use the `git clone` command, which accepts a link to the repository and downloads it into a folder** (with everything already set up!).

**How to clone:**

> **Click on the button clone and that will provide us with a remote URL. Then just copy the URL.**
> **In the terminal, just run `git clone THE_COPIED_ADDRESS`.**

**The command:**

```bash
git clone https://github.com/facebook/react.git
```

**What `git clone` does in one step:**

| What it does              | Normally requires                    |
| ------------------------- | ------------------------------------ |
| Creates a local folder    | `mkdir <name>`                       |
| Initializes a Git repo    | `git init`                           |
| Adds the remote           | `git remote add origin <URL>`        |
| Downloads all commits     | `git pull origin master` (or `main`) |
| Checks out a working tree | (implicit)                           |

**What you get:**

- A folder named after the repo (`react/` in the example).
- Full Git history.
- The remote `origin` already configured to point at the URL.
- A working tree at the default branch.

**Beginner framing:** `git clone <URL>` is the fastest way to get a repo from GitHub onto your computer. One command; everything is ready.

**Intermediate framing:** clone **copies the full history**, not just the latest commit — because Git is distributed. That's why a cloned repo is functional offline immediately after cloning.

**Junior-dev framing:** when you clone, `origin` is set to the **URL you cloned from**. If you forked first and then cloned _your fork_, `origin` points to **your fork** — not the original. That's exactly what you want for pushing.

---

### 5.3 Pull request — proposing your changes

> **Now let's say you are collaborating with an organization on GitHub (where you forked the repository from) and you would like to merge your changes with the original repo that you forked** (remember you can't just push to it, because you do not have permission to do so).
> **You can issue a pull request and the person who can grant permission can either merge or reject it.**

**How to create a pull request:**

> **To do this, click on "New pull request" and then click on "Create pull request".**
> **You should then be able to go to the original repository and see your pull request or "PR".**

**What a pull request is:**

- **A formal proposal** — "here are my changes; please review and merge them into your repo."
- **A discussion thread** — the maintainer and you can comment, ask questions, suggest changes.
- **A record** — it's visible on the original repo, tied to the specific commits and branch you're proposing.
- **A decision point** — the maintainer either **merges** it (accepts the change) or **rejects** it (declines the change).

**The flow:**

```
Your fork (branch: feature-fix)
    │
    │ push commits
    ▼
GitHub (your fork's feature-fix branch)
    │
    │ "New pull request"
    ▼
Original repo (maintainer reviews)
    │
    ├── Merge ────→ changes appear in original repo
    └── Reject ──→ changes stay in your fork only
```

**Beginner framing:** a pull request is **a polite request**: _"Can you merge my changes into your project?"_ The owner decides.

**Intermediate framing:** a PR is **not a Git concept** — it's a **GitHub collaboration feature**. The _underlying_ Git operation is a `merge`; the _PR_ is the discussion and approval layer around it. On GitLab it's called a "merge request"; on Bitbucket, also a "pull request" — but the mechanism is the same.

**Junior-dev framing:** the PR is where code review happens. Expect comments asking for changes, questions about your approach, and requests to split large changes. Responding well to feedback is part of the craft.

---

### 5.4 The full workflow, end to end

Putting it all together — the standard contribution flow:

**Step 1 — find a repo on GitHub.**
Browse to a repo you want to contribute to. E.g., `github.com/facebook/react`.

**Step 2 — fork it.**
Click **Fork** (top right). You now own a copy: `github.com/YOUR-USERNAME/react`.

**Step 3 — clone your fork.**

```bash
git clone https://github.com/YOUR-USERNAME/react.git
cd react
```

**Step 4 — make your changes.**
Edit files, add features, fix bugs — whatever you want to contribute.

**Step 5 — commit and push to your fork.**

```bash
git add .
git commit -m "fix: correct typo in README"
git push origin main
```

**Step 6 — open a pull request.**
Go to your fork on GitHub, click **New pull request**, choose the branch you pushed, and click **Create pull request**.

**Step 7 — respond to review.**
The maintainer may comment, request changes, or merge. If they request changes, commit them and push again — the PR updates automatically.

**Step 8 — merged (or closed).**
If merged, your changes appear in the original repo — and you're credited as a contributor.

**The picture:**

```
Original repo (owner: facebook)
        │
        │ fork (GitHub copies the repo)
        ▼
Your fork (owner: your-username)
        │
        │ clone (download to your machine)
        ▼
Your local repo
        │
        │ commits + push (back to your fork)
        ▼
Your fork (with new commits)
        │
        │ pull request (propose to original)
        ▼
Original repo (maintainer reviews, merges)
```

**Beginner framing:** fork → clone → change → push → PR → review → merge. That's the whole workflow.

**Intermediate framing:** the flow exists because **you don't have write access** to the original. The fork gives you a workspace; the pull request is how you ask the owner to accept your work.

**Junior-dev framing:** you'll use this exact workflow on teams too — often with branches instead of forks (if you have write access). But the _fork + PR_ pattern is the one open-source projects use, and the one you'll use to contribute to your first real project.

---

### 5.5 Git Immersion — practicing the fundamentals

> **This is a guided tour that walks through the fundamentals of Git, inspired by the premise that to know a thing is to do it.**

**The practice exercise:**

> **• Start Git Immersion here**
> **• try to finish Labs as much as you can**
> **• Good Luck.**

**What Git Immersion is:**

- A **hands-on lab series** — each lab introduces a Git concept, then asks you to try it.
- **"To know a thing is to do it"** — the philosophy is _practice over theory_.
- Free and self-paced: [gitimmersion.com](http://gitimmersion.com).

**Why it's worth doing:**

- **Reading about Git ≠ knowing Git.** The commands only become intuitive after typing them dozens of times.
- **The labs build on each other** — like this bootcamp, each lab assumes the previous ones.
- **You can complete them at your own pace** — a weekend, a week, or longer.

**Beginner framing:** Git Immersion is practice. It's not required reading — it's _doing_.

**Intermediate framing:** the labs cover the same territory as this superskill — plus branches, merging, rebasing, and remotes — through exercises. If any concept still feels shaky, the relevant lab is worth doing.

**Junior-dev framing:** bookmark [gitimmersion.com](http://gitimmersion.com). When you hit a Git concept you don't fully understand, there's a lab for it.

---

## 6. Worked Example — fork, clone, fix, pull request

> **Scenario:** you want to fix a typo in the README of a public repo on GitHub.

**Step 1 — find the repo.**
Open `github.com/some-username/some-repo`.

**Step 2 — fork.**
Click **Fork** (top right). You now have `github.com/YOUR-USERNAME/some-repo`.

**Step 3 — clone your fork.**

```bash
git clone https://github.com/YOUR-USERNAME/some-repo.git
cd some-repo
```

**Step 4 — create a branch (good practice).**

```bash
git checkout -b fix-typo
```

**Step 5 — make the change.**
Edit the README file — e.g., fix a misspelling.

**Step 6 — commit and push.**

```bash
git add README.md
git commit -m "fix: correct typo in introduction"
git push origin fix-typo
```

**Step 7 — open a pull request.**
On GitHub, go to `github.com/YOUR-USERNAME/some-repo`. GitHub shows a banner: _"Compare & pull request"_ for the `fix-typo` branch. Click it.

- **Base repository:** `some-username/some-repo`
- **Base branch:** `main` (or `master`)
- **Head repository:** `YOUR-USERNAME/some-repo`
- **Compare branch:** `fix-typo`

Add a title (_"Fix typo in introduction"_) and a description (_"Corrects 'recieve' to 'receive' in line 4."_). Click **Create pull request**.

**Step 8 — wait for review.**
The maintainer sees the PR on their repo. They may merge immediately, ask for changes, or close it. Either way, you've made your contribution.

**What this example teaches:**

- **Forking is the first step** — you need your own copy before you can change anything.
- **Cloning is the second step** — GitHub has the copy; your machine needs it too.
- **Branches help** — even for a small change, a branch keeps `main` clean.
- **The pull request is the _ask_** — you don't merge yourself; the maintainer decides.
- **The workflow is entirely doable solo** — you can fork, clone, and PR your _own_ test repo to practice.

---

## 7. Common Pitfalls

- ❌ **Thinking "fork" and "clone" are the same.** Fork = copy on **GitHub**. Clone = copy on **your machine**. You usually do both.
- ❌ **Pushing to the original repo's main branch.** You can't — you don't have permission. Push to **your fork**.
- ❌ **Forgetting to fork before cloning the original.** If you clone the original directly, you can't push — you don't own it.
- ❌ **Opening a PR with a huge, unfocused change.** Maintainers prefer **small, focused PRs** — one fix or feature per PR.
- ❌ **Ignoring PR review feedback.** Maintainers may ask for changes. Respond, commit, push — the PR updates automatically.
- ❌ **Assuming "pull request" is a Git command.** It's a **GitHub feature**. There's no `git pull-request` — the underlying operation is a merge.
- ❌ **Skipping the branch step.** PRs _can_ come from your fork's `main` branch — but branches are safer and more conventional.
- ❌ **Not syncing with the original before contributing.** If the original has moved on, your fork may be out of date — merging your PR could conflict. (Syncing is covered in later skills.)

---

## 8. Hands-On Exercises

1. **Fork a public repo (5 min).** Go to `github.com/facebook/react` (or any public repo). Click **Fork**. Confirm the fork appears at `github.com/YOUR-USERNAME/react`.
2. **Clone your fork (5 min).** Copy the fork's URL. Run `git clone <URL>` in a folder. `cd` into the cloned folder.
3. **Check the remotes (5 min).** Run `git remote -v`. What does `origin` point to? Is it your fork, or the original?
4. **Make a small change (10 min).** Edit the README. Commit with `git add .` and `git commit -m 'update README'`. Push with `git push origin main` (or `master`).
5. **Open a pull request (10 min).** On GitHub, go to your fork. GitHub should show a **"Compare & pull request"** banner. Follow it — **but don't actually create the PR to the original repo unless it's your own test repo**.
6. **Practice on your own fork (10 min).** Fork your own `git-practice-remote` repo (from Skill 5's exercise). Clone the fork. Push a change. Open a PR **to yourself** — you'll see the flow without affecting anyone else's project.
7. **Explore a real PR (10 min).** Go to `github.com/facebook/react/pulls` (or any repo's **Pull requests** tab). Open any PR. Read the description, the conversation, and the merge status. Note: what is the maintainer _deciding_?
8. **Try Git Immersion (as long as you like).** Start at [gitimmersion.com](http://gitimmersion.com). Do the first two or three labs. Note what feels easy and what feels unfamiliar.

---

## 9. Checkpoint Questions

1. What is a **fork**, and why is it necessary to contribute to a repo you don't own?
2. Why does the course say forking is **"strictly a GitHub feature"**?
3. What is a **clone**, and how is it different from a fork?
4. What does `git clone <URL>` do that `git init` + `git remote add` + `git pull` would otherwise do separately?
5. What is a **pull request**, and who decides whether to merge it?
6. What is the standard contribution workflow on GitHub — in order?
7. Why is it good practice to create a branch before making changes, even for a small fix?
8. What does the maintainer _see_ when you open a PR against their repo?
9. What is **Git Immersion**, and what philosophy does it follow?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
