# Skill 3 — Configuring Git

> **Superskill:** Integration and Version Control with Git
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--configuring-git-and-setting-up-aliases)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Skill 2 taught you the **core commands**. This skill covers three things that make Git _usable_ day-to-day:

1. **File status** — the three states Git sees every file in.
2. **Configuration** — how to tell Git who you are.
3. **Aliases** — how to make Git faster to type.

None of these are "advanced" features, but skipping them makes everything else harder. Configuring your identity is a **one-time setup**; `.gitignore` is the **first file you should create** in any project; aliases save **keystrokes for the rest of your career**.

---

## 2. Why It Matters (for you, as a developer)

- **File status is the mental model for everything else.** Understanding _tracked / untracked / ignored_ is what makes `git status` readable and `git add` precise.
- **`.gitignore` prevents real damage.** Committing secrets (API keys, `.env` files) or build artifacts (`node_modules/`, `dist/`) is one of the most common beginner mistakes — and the hardest to fully undo.
- **Git identity is permanent-ish.** Every commit carries your name and email. Configure it once, correctly, before your first commit.
- **Aliases pay off forever.** A 2-second alias saves hours over a career. `git st` instead of `git status` is not laziness — it's workflow design.

---

## 3. Prerequisites

- Skill 1 (Getting Started with Git).
- Skill 2 (Basic Git Commands — `init`, `status`, `add`, `commit`).

---

## 4. Key Concepts

1. **Three file states:** **Tracked**, **Untracked**, **Ignored**.
2. **Tracked** = previously staged or committed.
3. **Untracked** = not staged or committed.
4. **Ignored** = **explicitly told** to be ignored — usually build artifacts and machine-generated files.
5. **`.gitignore`** is the file where ignored patterns live.
6. **`.gitconfig`** contains configurations affecting Git's behavior.
7. **`git config`** is how you read and write those configurations.
8. **`git config --global user.name` / `user.email`** sets your identity.
9. **Aliases** = shortcuts for Git commands — temporary (terminal session) or global (`--global`).

---

## 5. Concepts Explained

### 5.1 File status — three states

> **Git sees every file in your working copy as one of three things:**

| State         | What it means                                             |
| ------------- | --------------------------------------------------------- |
| **Tracked**   | A file which has been previously **staged or committed**. |
| **Untracked** | A file which has **not been staged or committed**.        |
| **Ignored**   | A file which Git has been **explicitly told to ignore**.  |

**What "ignored" means in practice:**

> **Ignored files are usually built artifacts and machine-generated files that can be derived from your repository source, or should otherwise not be committed.**

**Examples of things worth ignoring:**

| Category              | Examples                                       |
| --------------------- | ---------------------------------------------- |
| **Build artifacts**   | `dist/`, `build/`, `*.o`, `*.pyc`              |
| **Dependencies**      | `node_modules/`, `venv/`, `vendor/`            |
| **Environment files** | `.env`, `.env.local`                           |
| **Secrets**           | `secrets.json`, `credentials.*`                |
| **OS / editor files** | `.DS_Store`, `.idea/`, `.vscode/`, `Thumbs.db` |
| **Logs**              | `*.log`, `logs/`                               |

**The `.gitignore` rule:**

> **If we have a file that we do not want to track, we just put it inside the `.gitignore` file.**

**Beginner framing:** three buckets — _Git knows about it and saves it_ (tracked), _Git sees it but doesn't save it_ (untracked), _Git pretends it doesn't exist_ (ignored).

**Intermediate framing:** the three states aren't static — they transition. `untracked → tracked` (via `git add`), `tracked → untracked` (via `git rm --cached`), and any file can become `ignored` by adding its pattern to `.gitignore`. Understanding the transitions is understanding Git's file model.

**Junior-dev framing:** before you commit _anything_ in a new project, create `.gitignore`. It's the cheapest way to avoid the "oops, I committed my API key" moment that every developer has had exactly once.

---

### 5.2 `.gitignore` — the ignore file

**The file:** `.gitignore` sits at the **root of the repository** (or in subfolders, for scoped ignores).

**The rules inside it:**

- One pattern per line.
- Comments start with `#`.
- `*.log` — ignore all `.log` files.
- `node_modules/` — ignore the whole folder.
- `!important.log` — _un-ignore_ a specific file (use sparingly).

**Example `.gitignore` for a JavaScript project:**

```
# Dependencies
node_modules/

# Build output
dist/
build/

# Environment variables (secrets!)
.env
.env.local

# Logs
*.log

# OS files
.DS_Store
Thumbs.db
```

**What this prevents:**

- Your `node_modules/` folder (often hundreds of MB) from being committed and pushed.
- Your `.env` file (containing API keys) from leaking to GitHub.
- Random `.DS_Store` files from polluting every commit.

**Beginner framing:** `.gitignore` is a _list of files Git should pretend not to see_. Add patterns before you first commit.

**Intermediate framing:** `.gitignore` is **not retroactive**. If a file was already committed, adding it to `.gitignore` doesn't untrack it — you have to `git rm --cached` first. This is why the file should exist **before the first commit**.

**Junior-dev framing:** every repository should have a `.gitignore`. For common stacks, GitHub provides templates when you create a repo — grab the one that matches your project.

---

### 5.3 Configuration — telling Git who you are

> **The `.gitconfig` file contains a list of configurations that affects the behavior of git commands.**
> **To manipulate it, we use the command `git config <configuration>`.**

**The most important configuration — your identity:**

> **To change the name and email used by Git to identify the user, we run the following command:**

```bash
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR EMAIL"
```

> **(PS. change `YOUR.NAME` and `YOUR.EMAIL` with your own values.)**

**What these settings do:**

- **`user.name`** — the name that appears in every commit's metadata.
- **`user.email`** — the email attached to every commit.

**Why it's important:**

- **Every commit carries your name and email.** If you commit without configuring these, Git may use defaults (or refuse to commit — depending on the version).
- **Your GitHub profile links commits to your account by email.** Use the **same email** on your local Git config and your GitHub account, or commits won't be attributed to you.
- **These are permanent-ish.** Once a commit is made, its author metadata is recorded forever — changing it later requires rewriting history (which is painful).

**The `--global` flag:**

- **`--global`** — applies to _all_ repositories on your machine.
- **No flag** — applies only to the _current_ repository.

**For most developers, `--global` is right** — you want the same identity across all projects.

**Beginner framing:** before you commit, tell Git your name and email. Otherwise, your commits have no attribution.

**Intermediate framing:** `git config` writes to `.gitconfig` (a file in your home directory). You can edit it directly, but `git config` is safer — it validates the keys and maintains the file structure.

**Junior-dev framing:** use the same email as your GitHub account. If you use a _different_ email locally, your commits will be attributed to "Unknown" (or nothing) on GitHub — an easy mistake to make and hard to notice.

**Other useful config settings (not covered in the source, but worth knowing):**

```bash
# Set default branch name for new repos
git config --global init.defaultBranch main

# Set default editor (for commit messages without -m)
git config --global core.editor "code --wait"

# Show helpful output colors
git config --global color.ui auto
```

These aren't required, but they make Git friendlier on first use.

---

### 5.4 Aliases — shortcuts for Git commands

> **Oftentimes, you'll be finding yourself typing git commands over and over again.**
> **For example, `git add`, `git init`, and `git status` are commands you will be repeatedly using.**
> **The smart thing to do in this case is use a shortcut, or an alias. Aliases help make your Git experience simpler, easier, and more familiar.**

**The general syntax:**

```bash
git config alias.KEYBOARD_SHORTCUT COMMAND
```

**Example — a temporary alias:**

```bash
git config alias.st status
```

Now `git st` does the same thing as `git status`.

> **To create a temporary alias, which will last as long as your terminal session is open, you can type `git config alias.KEYBOARD_SHORTCUT COMMAND`.**

**Example — a global alias:**

> **If you would like your alias to be a part of your global configuration, add `--global` after `git config`.**
> **For example, to alias `git i` to `git init` globally, you would type:**

```bash
git config --global alias.i init
```

**Common aliases worth setting up:**

| Alias         | Command                 | What it does     |
| ------------- | ----------------------- | ---------------- |
| `git st`      | `status`                | Shorter status   |
| `git ci`      | `commit`                | Shorter commit   |
| `git co`      | `checkout`              | Shorter checkout |
| `git br`      | `branch`                | Shorter branch   |
| `git lg`      | `log --oneline --graph` | Prettier history |
| `git unstage` | `reset HEAD --`         | Unstage files    |

**Beginner framing:** aliases are _nicknames_ for Git commands. `git st` = `git status`.

**Intermediate framing:** aliases are **per-session or per-machine**. Temporary aliases die with the terminal; global aliases live in `.gitconfig` and persist forever. For daily commands, always use `--global`.

**Junior-dev framing:** aliases are a **workflow optimization**, not a luxury. After a few weeks of typing `git status` ten times a day, `git st` starts to feel like a gift. Set up 3–5 of the ones you use most, and forget about it.

**A caution:** aliases are personal. Don't expect `git st` to work on a colleague's machine — they haven't configured it. Only use aliases for _your_ convenience, not for sharing commands.

---

## 6. Worked Example — configuring Git and setting up aliases

> **Scenario:** you've just installed Git and want to configure it properly before your first commit.

**Step 1 — verify installation.**

```bash
git --version
```

Expected output: something like `git version 2.40.0`.

**Step 2 — set your identity.**

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```

Use the **same email as your GitHub account** — this is how commits get attributed to you on GitHub.

**Step 3 — verify the configuration.**

```bash
git config --global --list
```

Expected output includes:

```
user.name=Your Full Name
user.email=your.email@example.com
```

**Step 4 — set a few useful defaults (optional but recommended).**

```bash
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
```

This makes new repositories start on `main` (matching GitHub's default) and uses VSCode for commit messages.

**Step 5 — add aliases for common commands.**

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.lg "log --oneline --graph --all"
```

**Step 6 — verify aliases work.**

```bash
git st
git lg
```

You should see the same output as `git status` and `git log --oneline --graph --all`.

**Step 7 — create a `.gitignore` in a new project.**

In a fresh project folder:

```bash
git init
echo "node_modules/" > .gitignore
echo ".env" >> .gitignore
echo "*.log" >> .gitignore
git status
```

You should see `.gitignore` **and** the ignored patterns are not listed — even if matching files exist.

**Step 8 — check file status explicitly.**

```bash
git status
```

You'll see:

```
On branch main
No commits yet
Untracked files:
  .gitignore
nothing added to commit but untracked files present
```

The `.gitignore` itself is untracked (Git needs to know about it), but any `node_modules/`, `.env`, or `*.log` files that exist are **hidden** from the status.

**What this example teaches:**

- **Configuration is a one-time setup** — but it should be done _before the first commit_.
- **Aliases are fast to set up** — 30 seconds, and you get shorter commands for the rest of your career.
- **`.gitignore` is created _early_, not retroactively** — before the first `git add .`.
- **`git status` reflects the three states** — untracked (`.gitignore`), tracked (none yet), ignored (hidden).

---

## 7. Common Pitfalls

- ❌ **Committing before setting `user.name` and `user.email`.** Your commits will have no author or generic defaults, and won't appear on GitHub.
- ❌ **Using different emails for Git and GitHub.** Your commits will appear as "Unknown" on GitHub — invisible on your profile and contributions graph.
- ❌ **Adding `.gitignore` _after_ committing files that should be ignored.** The file won't help retroactively — you need `git rm --cached` first.
- ❌ **Committing secrets by mistake.** API keys, `.env` files, and credentials committed to a public repo are a serious problem — and once in history, they're hard to remove.
- ❌ **Confusing `git config` (no `--global`) with `--global`.** Without `--global`, the setting only applies to the current repository.
- ❌ **Using aliases that collide with real Git commands.** `git alias.add status` (aliasing `add` to `status`) will confuse you and break scripts. Use unique aliases.
- ❌ **Ignoring `node_modules/` but not committing `package.json`.** `node_modules/` is regenerable from `package.json` — ignore the former, commit the latter.
- ❌ **Forgetting that `.gitignore` is itself tracked.** The file must be committed for collaborators to benefit — otherwise, they'll commit what you ignored.

---

## 8. Hands-On Exercises

1. **Configure your identity (5 min).** If not done already, set `user.name` and `user.email` globally. Use the same email as your GitHub account. Verify with `git config --global --list`.
2. **Add useful aliases (10 min).** Set up global aliases for `status`, `commit`, `checkout`, and `log --oneline --graph --all`. Test each one.
3. **Create a `.gitignore` (10 min).** In a new folder:
   - Run `git init`.
   - Create `.gitignore` with patterns for `node_modules/`, `.env`, and `*.log`.
   - Create dummy files matching each pattern.
   - Run `git status` and confirm the ignored files don't appear.
4. **The three states (10 min).**
   - Create a file `a.txt` and run `git status` → what state is it? **Untracked**.
   - Run `git add a.txt` and `git status` → what state? **Tracked (staged)**.
   - Run `git commit -m 'add a.txt'` and `git status` → what state? **Tracked (committed)**.
   - Add `a.txt` to `.gitignore` and `git status` → what state? **Still tracked** — `.gitignore` doesn't untrack already-tracked files. Confirm this.
5. **Retroactive untracking (10 min).**
   - Create `secret.txt`, `git add`, `git commit`.
   - Add `secret.txt` to `.gitignore`.
   - Run `git status` — the file is still tracked.
   - Run `git rm --cached secret.txt` — now Git stops tracking it, but the file stays on disk.
   - `git status` — the file is now ignored.
6. **Debug your config (10 min).** Run `git config --global --list`. What's in there? Do you see anything you didn't set intentionally? Try `git config user.name` (without `--global`) inside a repo — does it return the same value?
7. **Reflect (5 min).** Which of these three areas — file status, config, aliases — do you think you'll use most often? Why?

---

## 9. Checkpoint Questions

1. What are the **three states** Git sees every file in? Briefly define each.
2. What kind of files are typically **ignored**, and why?
3. What file do you put ignore patterns in?
4. Why does `.gitignore` not work retroactively — and what do you do if you've already committed a file that should be ignored?
5. What does `.gitconfig` contain?
6. What is the difference between `git config` and `git config --global`?
7. What do `user.name` and `user.email` affect — and why does the email matter for GitHub attribution?
8. What is a **Git alias**, and how do you create a **global** one?
9. What's the difference between a **temporary** alias and a **global** alias?
10. Why is it recommended to create `.gitignore` **before** your first commit?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
