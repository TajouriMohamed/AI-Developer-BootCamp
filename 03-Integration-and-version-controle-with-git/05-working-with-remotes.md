# Skill 5 — Working with Remotes

> **Superskill:** Integration and Version Control with Git
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--from-local-repo-to-github)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

So far, everything has happened **locally** — on your machine. This skill is where your code goes **remote** — up to GitHub.

Two operations make this happen:

1. **Create a remote repository on GitHub** — an empty repo on github.com.
2. **Push your local code to it** — with two commands:
   - `git remote add origin <URL>` — connects your local repo to the GitHub repo.
   - `git push origin master` — sends your commits to GitHub.

That's it. Two commands, and your code is online.

**What "remote" means:**

- A **remote** is a Git repository **hosted somewhere other than your machine**.
- `origin` is the default **name** for that remote.
- **`master`** (or `main`) is the **branch** being pushed.

---

## 2. Why It Matters (for you, as a developer)

- **This is the moment your code becomes shareable.** Until you push, it's on your machine and nowhere else. Push makes it backup-able, reviewable, and collaborative.
- **Every professional project uses remotes.** Solo or team, local-only development is fragile — one disk failure and it's gone.
- **The two commands here are the foundation of the entire remote workflow.** Later skills — pull, fetch, branches, pull requests — all build on `git remote add` and `git push`.
- **This is the moment you can share a URL with someone.** Your GitHub repo becomes a public artifact — a link you can send.

---

## 3. Prerequisites

- Skill 1 (what Git is).
- Skill 2 (basic commands — `init`, `add`, `commit`).
- Skill 3 (configuring Git — **email set** to match GitHub).
- Skill 4 (GitHub account — created and email aligned).

---

## 4. Key Concepts

1. **Create a remote repository** on GitHub at [github.com/new](https://github.com/new).
2. **No need to initialize with a README** — you'll push existing local code instead.
3. **GitHub provides setup instructions** after creating the repo — including the URL.
4. **`git remote add origin <URL>`** attaches the GitHub repo address to your local project.
   - `origin` = the default name for the remote.
   - `<URL>` = the address GitHub provides.
5. **`git push origin master`** sends your local commits to the remote branch `master`.
   - `origin` = the remote name.
   - `master` = the local branch being pushed.
6. **"And voila!"** — your files are now on GitHub.
7. **Modern default:** since 2020, GitHub uses **`main`** as the default branch name, not `master`. Both work; the course uses `master` (older convention).

---

## 5. Concepts Explained

### 5.1 Creating a remote repository

> **Once you have a GitHub account, head over to [github.com/new](https://github.com/new) and create a repository.**

**The steps:**

1. **Go to [github.com/new](https://github.com/new).**
2. **Enter a repository name** — e.g., `first-repo`.
3. **Don't worry about:**
   - **The description.** Can be added later.
   - **Initializing with a README.** Skip it — you have local code.
4. **Click "Create repository."**

**What you get:**

> **After you've created the repository, GitHub will give you a few instructions to get started.**
> **The instructions should look something like this (the URL towards the end will depend on your GitHub username).**

**What those instructions contain:**

- The **URL** of your new remote — something like `https://github.com/YOUR-USERNAME/first-repo.git`.
- Commands to **push an existing repo** (the path you'll take) or **initialize a new one**.

**The URL matters:**

- It's the **address** of your remote.
- It ends with `.git` — a Git convention.
- It's unique to your GitHub account and repo.

**Beginner framing:** this step creates an **empty container** on GitHub — a place where your code will eventually live.

**Intermediate framing:** the new repo is _empty_ (no commits). Your local repo has commits. The next step is to **connect** the two so the empty remote can receive your history.

**Junior-dev framing:** skipping the "Initialize with README" checkbox is **crucial** when pushing existing code — because if the remote has a README commit, your local repo and the remote will have **divergent histories**, and you'll need to reconcile them. Starting empty avoids that entirely.

---

### 5.2 Attaching the remote — `git remote add`

> **First, we need to attach the address of the GitHub repo to our local project, simply by running:**
> **`git remote add origin YOUR_REPO_URL`**

**What this command does:**

- **`git remote add`** — adds a new remote to your local repo.
- **`origin`** — the name you're giving it (a convention, not a requirement).
- **`YOUR_REPO_URL`** — the URL GitHub gave you.

**The name `origin`:**

- **Convention** — nearly every repo names its primary remote `origin`.
- **Not required** — you can name it `github`, `upstream`, `fork`, anything.
- **Why `origin`:** because "where this came from" is a useful default name.

**The URL:**

- **HTTPS** form: `https://github.com/YOUR-USERNAME/first-repo.git`
- **SSH** form: `git@github.com:YOUR-USERNAME/first-repo.git`

Both work; HTTPS is easier for beginners; SSH is preferred once set up.

**Beginner framing:** `git remote add origin <URL>` tells Git _"remember this URL under the name `origin`."_

**Intermediate framing:** a repo can have **multiple remotes** — `origin` for your fork, `upstream` for the original, `backup` for a personal mirror. `git remote add` is how each one is registered. `git remote -v` lists them all.

**Junior-dev framing:** the URL is your connection to GitHub. `origin` is the default name. You only add a remote **once** per repo — after that, `push` and `pull` use the stored URL.

---

### 5.3 Pushing — `git push origin master`

> **After providing the remote URL to the local repository to take the local files to the remote host, we have to run this command:**
> **`git push origin master`**

**What this command does:**

- **`git push`** — sends commits from local to remote.
- **`origin`** — the remote to push to.
- **`master`** — the branch to push.

**The two-part form (`origin master`) has three meanings:**

| Part         | Meaning                                                |
| ------------ | ------------------------------------------------------ |
| **`push`**   | The action — send commits up                           |
| **`origin`** | Where — to the remote named `origin`                   |
| **`master`** | What — the branch called `master` (in your local repo) |

**What gets pushed:**

- **All commits** on the `master` branch (that aren't already on the remote).
- **Not** your working tree, not untracked files, not `.git` internal files — just the **committed history**.

**The result:**

> **And voila! Our files are now in GitHub.**

**The modern note on `master` vs. `main`:**

> Since 2020, GitHub's default branch name is **`main`**, not `master`.
> Both are valid branch names; the convention is shifting. If your local branch is `main`, use `git push origin main` instead.
> You can check with `git branch` — the asterisk marks your current branch.

**Beginner framing:** `git push origin master` sends your commits to GitHub. After it runs, the remote has the same history as your local repo.

**Intermediate framing:** `git push` is a **fast-forward-only** operation by default. It succeeds only if the remote's history is a strict prefix of yours — i.e., you have everything the remote has, plus new commits. If the remote has commits you don't have, `push` is rejected.

**Junior-dev framing:** push is **not a backup in the sense of syncing files.** It sends **commits**. If you have uncommitted changes, they're not pushed. If you have untracked files, they're not pushed. Only committed history goes up.

---

### 5.4 What the remote now contains

After a successful push, the remote repo on GitHub contains:

- **The same commit history** as your local repo's `master` branch.
- **The same files** at their committed state.
- **The `.git` metadata** — but as a _hosted_ copy, not a clone of your local machine.

**What the remote does NOT contain:**

- **Your uncommitted changes** — only committed history is pushed.
- **Untracked files** — files Git doesn't know about don't go up.
- **Your local config** — `.gitconfig` is local; GitHub has its own settings.
- **Your `.git` folder as-is** — the remote is its own repo, not a mirror of your disk.

**Beginner framing:** the remote is a _copy of your committed history_, not a copy of your folder.

**Intermediate framing:** `push` updates the **remote branch** to match your local branch. The remote's `HEAD` now points to your latest commit. GitHub's UI renders the file tree from that commit.

**Junior-dev framing:** if you forget to commit before pushing, nothing changes on GitHub — because nothing was sent. **Commit first, then push.** The two-step flow (commit → push) is a common source of confusion.

---

## 6. Worked Example — from local repo to GitHub

> **Scenario:** you have a local repo called `first-repo` with a few commits. You want it on GitHub.

**Step 1 — check your local state.**

```bash
cd first-repo
git log --oneline
```

You should see at least one commit. If not, create one:

```bash
echo "Hello" > README.md
git add .
git commit -m "initial commit"
```

**Step 2 — create the remote on GitHub.**

- Go to [github.com/new](https://github.com/new).
- Name it `first-repo`.
- **Do NOT** initialize with a README.
- Click **Create repository**.

**Step 3 — copy the remote URL.**

GitHub shows a URL like:

```
https://github.com/YOUR-USERNAME/first-repo.git
```

Copy it.

**Step 4 — add the remote.**

```bash
git remote add origin https://github.com/YOUR-USERNAME/first-repo.git
```

**Step 5 — verify the remote was added.**

```bash
git remote -v
```

Output:

```
origin  https://github.com/YOUR-USERNAME/first-repo.git (fetch)
origin  https://github.com/YOUR-USERNAME/first-repo.git (push)
```

**Step 6 — push.**

```bash
git push origin master
```

Output:

```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (5/5), 380 bytes | 380.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/YOUR-USERNAME/first-repo.git
 * [new branch]      master -> master
```

**Step 7 — verify on GitHub.**

Refresh your repo page on github.com. Your files are there. Your commit history is visible.

**Step 8 — make another change and push again.**

```bash
echo "Second line" >> README.md
git add .
git commit -m "add second line"
git push origin master
```

The remote now has two commits.

**What this example teaches:**

- **Setup happens once.** `git remote add origin ...` is run _only_ the first time. Future pushes just use `git push origin master`.
- **The two commands have distinct jobs.** `remote add` **connects**; `push` **sends**.
- **The remote branch's name matters.** Pushing `master` to `master` works because both branches exist. Pushing `main` to `master` (or vice versa) does something different — covered in later skills.
- **The loop is now local + remote.** `commit` (local) → `push` (remote). That's the full cycle.

---

## 7. Common Pitfalls

- ❌ **Initializing the GitHub repo with a README when you're pushing existing code.** The remote will have a commit your local repo doesn't — and `push` will be rejected. Better: start empty.
- ❌ **Confusing `git remote add origin <URL>` with `git clone <URL>`.** `remote add` **connects** an existing local repo; `clone` **copies** a remote repo to a new local folder.
- ❌ **Forgetting the `.git` suffix on the URL.** `https://github.com/user/repo.git` is the URL; `https://github.com/user/repo` (no `.git`) usually works for clone but not always for `remote add`. Copy exactly what GitHub gives you.
- ❌ **Pushing without committing first.** Only **committed** changes go up. If `git status` shows nothing to commit, `push` sends nothing new.
- ❌ **Using `master` when your branch is `main`.** Use `git branch` to check. If your branch is `main`, run `git push origin main`.
- ❌ **Thinking the push is "backup of your folder."** Push sends _commits_, not files. Untracked files and uncommitted edits stay local.
- ❌ **Not verifying with `git remote -v`.** The most common first-time error is a typo in the URL. Verify before pushing.
- ❌ **Pushing to the wrong remote.** If you have multiple remotes (`origin`, `upstream`), pushing to the wrong one sends your code to the wrong place. Check with `git remote -v` before pushing.

---

## 8. Hands-On Exercises

1. **Create a practice repo (10 min).** Create an empty repo on GitHub called `git-practice-remote`. **Do NOT** initialize with a README.
2. **Add the remote locally (10 min).** In a local practice repo (or create one), run `git remote add origin <URL>`. Verify with `git remote -v`.
3. **Push (10 min).** Make sure you have at least one commit. Run `git push origin master` (or `git push origin main` if your branch is `main`). Confirm on GitHub.
4. **Push again (10 min).** Make a small change, commit, push. Confirm the second commit appears on GitHub.
5. **`master` vs. `main` (10 min).** Run `git branch`. Note the branch name. Try pushing `master` if your branch is `main` (or vice versa) — what happens? Why?
6. **`git remote -v` inspection (5 min).** Run `git remote -v`. What does the `(fetch)` and `(push)` notation mean? (Hint: look at what each row is for.)
7. **What doesn't get pushed (10 min).** Create an untracked file `local-only.txt`. Push (with no changes committed). Confirm on GitHub that the file **is not** there. Then commit it, push, and confirm it **is**.

---

## 9. Checkpoint Questions

1. What is a **remote repository**, and why do we need one?
2. What does `git remote add origin <URL>` do?
3. Why is the remote named **`origin`** — is that required?
4. What does `git push origin master` do? Name each part.
5. What's the difference between **committing** and **pushing**?
6. Why should you **not** initialize a GitHub repo with a README when pushing existing code?
7. What's the difference between `master` and `main` — and how do you know which your repo uses?
8. How can you verify that your remote was added correctly?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
