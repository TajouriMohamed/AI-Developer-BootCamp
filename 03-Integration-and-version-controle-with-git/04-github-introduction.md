# Skill 4 — GitHub Introduction

> **Superskill:** Integration and Version Control with Git
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--getting-your-github-account-aligned-with-git)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

> **GitHub is a web-based Git repository hosting service.**
> **Simply put, it is a tool that enables collaboration by hosting shared Git repositories that teams of developers can all contribute to.**

The single most important distinction in this skill:

> **While GitHub uses Git, the functionality it provides is entirely different from Git.**
> **Git and GitHub are not the same thing.**

|                   | **Git**                      | **GitHub**                                     |
| ----------------- | ---------------------------- | ---------------------------------------------- |
| **What it is**    | A **Version Control System** | An **online platform** for hosting and sharing |
| **Where it runs** | On your machine              | On the web                                     |
| **What it does**  | Tracks changes to your files | Stores and shares Git repositories             |

**This skill covers:**

- What GitHub is (and what it isn't).
- Why developers use it.
- How to set up an account — including **matching your `.gitconfig` email** to avoid friction later.

The next chapters will cover `push`, `pull`, **forking**, and **pull requests** — but first, the account.

---

## 2. Why It Matters (for you, as a developer)

- **GitHub is where your code lives _online_.** It's the remote copy — your backup, your portfolio, your collaboration surface.
- **It's how the world shares code.** The largest open-source projects — Angular, React, Node.js — live on GitHub. Knowing the platform is table stakes.
- **The email mismatch problem is real and avoidable.** A tiny setup detail now saves an hour of confusion later.
- **Everything in the rest of this superskill depends on it.** `push`, `pull`, `fork`, `pull request` — all of these assume a GitHub account, correctly connected.

---

## 3. Prerequisites

- Skill 1 (what Git is).
- Skill 2 (basic commands — `init`, `add`, `commit`).
- Skill 3 (configuring Git — **`user.name` and `user.email` set**).

---

## 4. Key Concepts

1. **GitHub is a web-based Git repository hosting service** — a platform for **hosting shared Git repositories**.
2. **GitHub uses Git, but is not Git.** Git is the VCS; GitHub is the hosting and collaboration platform.
3. **Why use GitHub:**
   - **Safe remote storage** — your code survives a lost laptop.
   - **Collaboration** — private and public.
   - **Open-source ecosystem** — most major projects live there.
4. **The remote workflow** (coming next): **`push`** to send code up, **`pull`** to bring code down.
5. **GitHub-specific concepts:** **forking** and **pull requests** (covered later).
6. **The email rule:** the email in your `.gitconfig` should **match** the email on your GitHub account.
7. **Famous projects on GitHub:** Angular, React, Ruby on Rails, Bootstrap, Node.js, jQuery, Homebrew.

---

## 5. Concepts Explained

### 5.1 What GitHub is

> **GitHub is a web-based Git repository hosting service.**
> **Simply put, it is a tool that enables collaboration by hosting shared Git repositories that teams of developers can all contribute to.**

**The three layers:**

| Layer               | What it means                                                                       |
| ------------------- | ----------------------------------------------------------------------------------- |
| **Web-based**       | It lives on the internet, accessible from any browser                               |
| **Git repository**  | It stores Git repositories — the same `.git` histories you've been building locally |
| **Hosting service** | It _hosts_ those repositories so multiple people can access them                    |

**What that enables:**

- **Remote storage** — your code lives somewhere other than your laptop.
- **Shared access** — teammates can clone, contribute, and review.
- **Public and private** — repositories can be visible to the world or restricted to your team.

**Beginner framing:** GitHub is where Git repositories go to be shared. It's a website that stores your code so others can see it and work with it.

**Intermediate framing:** GitHub is a **Git server with a web front-end**. Underneath, it's just Git repositories. The web layer adds collaboration features (issues, pull requests, reviews, actions) — but the _core_ is still Git.

**Junior-dev framing:** your local repo (`.git`) is one copy; the GitHub repo is another copy. They're connected through _remotes_ — the topic of the next skills.

---

### 5.2 Git vs. GitHub — the crucial distinction

> **While GitHub uses Git, the functionality it provides is entirely different from Git.**
> **So try to make it stick in your mind that Git and GitHub are not the same thing.**

> **In short: Git is a Version Control System, while GitHub is an online platform for hosting and sharing code, text files, and more complex file formats.**

**The side-by-side:**

|                         | **Git**                            | **GitHub**                         |
| ----------------------- | ---------------------------------- | ---------------------------------- |
| **Category**            | Version Control System             | Hosting and collaboration platform |
| **Runs**                | On your computer                   | On the web                         |
| **Created**             | By Linus Torvalds (2005)           | By GitHub Inc. (2008)              |
| **Language**            | Command-line tool                  | Web application + API              |
| **Requires the other?** | No — Git works fine without GitHub | Yes — GitHub _needs_ Git           |
| **Alternatives**        | Mercurial, SVN, Perforce           | GitLab, Bitbucket                  |

**The one-line summary:**

> **Git is the tool. GitHub is the service that hosts the tool's repositories.**

**Beginner framing:** Git is the _engine_; GitHub is the _garage_ where cars go to be shared. You can have a car without a garage; you can't have a garage without a car.

**Intermediate framing:** Git is **distributed** — every clone is a full copy. GitHub is one of many **remote hosts** for Git. You can use Git without any remote; you can host a Git remote on your own server (self-hosted GitLab, Gitea, etc.).

**Junior-dev framing:** when someone says _"put it on GitHub,"_ they mean _"push your local Git repo to a GitHub remote."_ The two are different steps: Git commits locally; GitHub hosts remotely.

---

### 5.3 Why use GitHub

> **GitHub provides a great way for you to store your code in a safe and remote location** (in case something happens to your local machine).
> **It's a fantastic way to collaborate with other developers both privately and publicly.**

**Two core reasons:**

1. **Remote storage — backup and safety.**
   If your laptop dies, your code survives. This alone justifies using a remote repository.

2. **Collaboration — public and private.**
   Teammates can clone, contribute, and review. Open-source projects can be forked and improved.

**The open-source dimension:**

> **Many large open-source projects are hosted on GitHub, which makes it very easy to examine shared code both on GitHub and on local machines.**

**Famous projects on GitHub:**

- **Angular** — Google's front-end framework.
- **React** — Meta's UI library.
- **Ruby on Rails** — the classic web framework.
- **Twitter Bootstrap** — the CSS framework you met in Superskill #2.
- **Node.js** — JavaScript runtime.
- **jQuery** — the classic JS library.
- **Homebrew** — macOS package manager.

**Beginner framing:** GitHub is a backup + a community + a portfolio, in one place.

**Intermediate framing:** GitHub's value isn't just storage — it's the **social layer**: stars, forks, issues, and PRs make code _discoverable_ and _discussable_. That's what turned GitHub from "Git hosting" into "the home of open source."

**Junior-dev framing:** your GitHub profile is **visible to employers**. The projects you've starred, the repos you've built, the PRs you've opened — they're all part of your professional identity.

---

### 5.4 What's coming next — the remote workflow

> **In the next couple of chapters we will learn how to move code from our local repository to a remote repository on GitHub using the `push` command, as well as retrieve code from a remote repository on GitHub using the `pull` command.**

**The two directions:**

| Command    | Direction      | What it does                                    |
| ---------- | -------------- | ----------------------------------------------- |
| **`push`** | Local → Remote | Sends your commits to GitHub                    |
| **`pull`** | Remote → Local | Brings commits from GitHub down to your machine |

**The GitHub-specific concepts:**

> **We'll also learn about GitHub-specific concepts like forking and pull requests.**

| Concept          | What it means (preview)                                               |
| ---------------- | --------------------------------------------------------------------- |
| **Fork**         | Your own copy of someone else's repository — you can modify it freely |
| **Pull request** | A proposal to merge your changes back into the original repository    |

**Beginner framing:** `push` sends your work up; `pull` brings work down. Forking and pull requests are how you collaborate with people you don't share write-access with.

**Intermediate framing:** `push` and `pull` are **remote-tracking operations**. Your local branch has a "remote-tracking" counterpart on GitHub; `push` and `pull` keep them in sync. The next skills will cover this in detail.

---

### 5.5 Getting started — the account and the email rule

> **If you don't have an account on GitHub yet, head to github.com and create an account. Signing up is easy!**

**The critical setup detail:**

> **Be sure to use whatever email address is in your `.gitconfig` when you sign up on GitHub.**

**Why it matters:**

> **If you'd rather sign up with a different email address, change your `.gitconfig` accordingly.**
> **You'll run into some minor annoyances if there's a mismatch between the email address in your GitHub profile and the email address in your `.gitconfig`.**

**What happens on a mismatch:**

- Your commits **do** get pushed to GitHub — but they show up as **unlinked** to your GitHub profile.
- Your avatar and username don't appear next to the commits.
- Contribution graphs (the green squares on your profile) **don't count** those commits.

**Two ways to fix it:**

1. **Change the email on your GitHub account** to match `.gitconfig`.
2. **Change `.gitconfig`** to match your GitHub email (more common):
   ```
   git config --global user.email "you@example.com"
   ```

**Beginner framing:** your local Git and your GitHub account must agree on who you are. Same email = commits linked to your account. Different email = commits attributed but _unlinked_.

**Intermediate framing:** GitHub identifies commits by **email address**. It matches the commit's email to a known email on some GitHub account. If there's no match, the commit still exists — it's just not claimed by anyone. Add the email to your GitHub account (Settings → Emails) to retroactively link past commits.

**Junior-dev framing:** if you see commits on GitHub with a default avatar and no name next to them, it's almost always an email mismatch. Fix `.gitconfig`, and — if you want past commits to link — add the old email to your GitHub account.

---

## 6. Worked Example — getting your GitHub account aligned with Git

> **Scenario:** you have Git configured locally, and you're about to sign up for GitHub. You want to make sure the two will work together from day one.

**Step 1 — check your current Git email.**

```bash
git config --global user.email
```

Note the output. This is what your commits will say.

**Step 2 — decide on your GitHub email.**

You have two options:

- **Option A:** use the email from step 1 when signing up.
- **Option B:** use a different email, and change `.gitconfig` to match.

Either works. The point is they should be **the same**.

**Step 3 — sign up (if not already).**

Visit [github.com](https://github.com), click **Sign up**, and complete the flow (Skill 10 of Superskill #2 covered the signup steps).

**Step 4 — verify alignment.**

After signup, on GitHub: **Settings → Emails**. Confirm your signup email is listed.

Then locally:

```bash
git config --global user.email
```

**If they match** → you're ready. Every commit you push will be linked to your account.

**If they don't match** → fix one of them:

- Change `.gitconfig`:
  ```bash
  git config --global user.email "you@example.com"
  ```
- Or add the other email to your GitHub account (Settings → Emails → Add email).

**Step 5 — test with a real push (preview).**

The next skills will show you the actual `push`. For now, just confirm that the email on your `.gitconfig` matches the email on GitHub.

**What this example teaches:**

- **The email is the identity link.** Every commit carries it; GitHub matches on it.
- **Fixing a mismatch takes 10 seconds — before you push.** After you push, you'd have to either fix `.gitconfig` (only helps future commits) or add the old email to GitHub (helps retroactively).
- **Better to set it right the first time.** Small setup detail; large downstream impact.

---

## 7. Common Pitfalls

- ❌ **Thinking Git and GitHub are the same.** They're related but distinct. You can use Git without GitHub; you can't use GitHub without Git.
- ❌ **Using an email on GitHub that doesn't match `.gitconfig`.** Commits show up unlinked to your profile — no avatar, no green squares, no attribution.
- ❌ **Signing up with a throwaway email.** GitHub accounts live for years; use an email you'll keep.
- ❌ **Assuming GitHub is the only Git host.** GitLab, Bitbucket, self-hosted options exist. GitHub is the most popular, not the only.
- ❌ **Treating GitHub as optional for solo work.** Even as a solo developer, remote backup is _the_ reason to use it — a dead laptop shouldn't mean a dead project.
- ❌ **Confusing "push" with "commit".** Commit is local; push is remote. You can commit ten times before pushing once.
- ❌ **Believing "forking" = "cloning."** Forking creates _your own_ copy on GitHub; cloning creates a _local_ copy on your machine. Related, not identical.

---

## 8. Hands-On Exercises

1. **Git vs. GitHub in your own words (10 min).** Write two sentences each — one defining Git, one defining GitHub — and one sentence explaining how they relate.
2. **Check your email alignment (5 min).** Run `git config --global user.email`. Compare it to the email on your GitHub account. If they don't match, fix it now.
3. **Explore a famous GitHub repo (10 min).** Visit one of: `github.com/angular/angular`, `github.com/facebook/react`, `github.com/nodejs/node`, or `github.com/jquery/jquery`. Note:
   - the number of stars,
   - the number of forks,
   - the structure of the code (files and folders on the main branch).
4. **Why fork? (10 min).** Describe, in plain language, why someone would fork a repository instead of cloning it.
5. **Read the setup instructions (10 min).** Look up _one_ of the famous repos above. Find its README. Does it tell you to `clone` or `fork` first? Why do you think it recommends that?
6. **Email mismatch test (optional, 15 min).** If you have a practice repo, deliberately change `user.email` to a different address, commit, push to GitHub (if you've learned push — if not, skip). Observe whether the commit is linked to your profile. Then fix it.

---

## 9. Checkpoint Questions

1. In one sentence, what is **GitHub**?
2. What's the difference between **Git and GitHub** — in one sentence each?
3. Why does the course say _"Git and GitHub are not the same thing"_?
4. Name **three reasons** to use GitHub as a developer.
5. What are the two directions of remote work — what does each command (`push` / `pull`) do?
6. What is a **fork**? A **pull request**? (You don't need the full workflow yet — just the concept.)
7. Why does it matter that your `.gitconfig` email matches your GitHub account email?
8. What happens to commits when the emails don't match?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
