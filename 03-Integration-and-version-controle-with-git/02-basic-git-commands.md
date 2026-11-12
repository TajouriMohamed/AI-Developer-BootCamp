# Skill 2 — Basic Git Commands

> **Superskill:** Integration and Version Control with Git
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--a-complete-first-repository)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Skill 1 gave you the **mental model** of version control. This skill gives you the **tool in your hands**: installing Git, initializing a repository, and using the basic commands that make everything else work.

**What you'll learn:**

- **Install Git** on Windows, Linux, or macOS.
- **Initialize a repository** with `git init`.
- **Check status** with `git status`.
- **Stage files** with `git add`.
- **Unstage / stop tracking** with `git rm --cached`.
- **Commit changes** with `git commit`.

These six things are the **core loop** of Git. Everything later — branches, remotes, merges — builds on top of them.

---

## 2. Why It Matters (for you, as a developer)

- **The basic commands are used _daily_.** Every working developer types `git status`, `git add`, and `git commit` dozens of times per week.
- **The core loop is where mistakes happen.** Staging the wrong file, forgetting to commit, undoing the wrong change — almost all beginner Git pain comes from these six commands.
- **Understanding the staging area is the key unlock.** It's the concept that confuses beginners most, and the one that makes the rest of Git make sense.
- **These commands are the foundation for everything else.** Branches, remotes, merging, conflict resolution — none of it makes sense without `init`, `status`, `add`, and `commit`.

---

## 3. Prerequisites

- Skill 1 (Getting Started with Git — what Git is, what a VCS is).
- A terminal (Command Prompt / PowerShell on Windows, Terminal on Mac/Linux).
- A folder you want to turn into a repository.

---

## 4. Key Concepts

1. **Install Git before using it.** Recommended methods:
   - **Windows:** Git for Windows installer.
   - **Linux:** `sudo apt install git-all`.
   - **Mac:** `brew install git` (after installing Homebrew).
2. **Initialize a repository** with `git init` — creates a hidden `.git` folder where Git stores everything.
3. **Check status** with `git status` — shows what's changed.
4. **Stage files** with `git add .` (all) or `git add <file>` (specific). Staging puts files in an **intermediate area** for the next commit.
5. **Stop tracking a file** with `git rm --cached <file>` — removes from Git but **keeps** the file on disk.
6. **Commit changes** with `git commit -m 'message'` — a **snapshot** of the staged state, with a message.

---

## 5. Concepts Explained

### 5.1 Installing Git

> **Git isn't usually set up by default on your computer, so you need to install and configure it before you can start using it to manage your code.**
> **It's important to keep Git up to date, just like all the other software on your machine. Updates protect you from security vulnerabilities, fix bugs, and give you access to new features.**

**Recommended installation by platform:**

| Platform    | Method                                                                                                            |
| ----------- | ----------------------------------------------------------------------------------------------------------------- |
| **Windows** | Download and install **Git for Windows**. Once installed, Git is available from the command prompt or PowerShell. |
| **Linux**   | Run `sudo apt install git-all` in the terminal.                                                                   |
| **macOS**   | Install **Homebrew**, then run `brew install git` from the terminal.                                              |

**On Windows specifically:**

> **We recommend that you stick with the defaults selected during the installation unless you have a good reason to change them.**

**Beginner framing:** Git doesn't come pre-installed. Install it once, and it's available for every project on your machine.

**Intermediate framing:** the installation method matters for **updates**. Package managers (apt, brew, Windows installers) keep Git updatable through the same channel as the rest of your software — the _maintainable_ path.

**Junior-dev framing:** verify installation by running `git --version` in a terminal. If it prints a version number, you're ready. If it says "command not found," the install didn't complete or wasn't added to PATH.

---

### 5.2 Initializing a repository

> **Once we have Git installed we need to "initialize" a repository before we can start using it.**

**The steps:**

1. **Navigate** to the folder you want to track (using the terminal).
2. **Run `git init`.**

**What happens:**

```
Desktop/learn_git$ git init
Reinitialized existing Git repository in /home/<username>/Desktop/learn_git/.git/
```

**The key insight:**

> **This command just created a hidden folder called `.git`, where all the magic happens.**

**What `.git` contains:**

- The full history of commits.
- Branches and tags.
- Configuration for this repository.
- Everything Git needs to track changes.

**Beginner framing:** `git init` turns a normal folder into a **Git repository** — the folder is the same, but Git starts tracking it.

**Intermediate framing:** the `.git` folder is the **repository**; the rest of the folder is the **working tree**. Git compares the working tree to the last committed state and reports differences.

**Junior-dev framing:** you only run `git init` **once per project**. Running it again on the same folder is harmless — Git says "Reinitialized" and continues.

---

### 5.3 Checking status

> **To check the current status of your repository we use the `git status` command.**

**What `git status` shows:**

- Which files have changed since the last commit.
- Which files are **staged** (ready to commit).
- Which files are **untracked** (Git doesn't know about them yet).
- Which branch you're on.

**Typical output (simplified):**

```
On branch main
Changes not staged for commit:
  modified:   index.html

Untracked files:
  style.css
  script.js
```

**Beginner framing:** `git status` is your **starting point** — always run it before `git add` and `git commit` to see what's actually happening.

**Intermediate framing:** `git status` shows the **three states** a file can be in:

- **Modified** — changed but not staged.
- **Staged** — marked for the next commit.
- **Untracked** — new; Git hasn't been told to track it.

**Junior-dev framing:** get in the habit of running `git status` **before every commit**. It's the cheapest way to avoid committing the wrong thing.

---

### 5.4 Staging files with `git add`

> **At this point, we do not have any files for Git to track. We need to add files specifically to Git to tell it to track them.**
> **We add files using the "add" command.**

**Two forms:**

| Command              | What it does                                                                    |
| -------------------- | ------------------------------------------------------------------------------- |
| `git add .`          | **Add all files** in the current directory (and subfolders) to the staging area |
| `git add <filename>` | **Add a specific file**                                                         |

**What staging actually means:**

> **After running `git add .`, Git will add all the repository files to an intermediate area called the staging area.**

**The staging area** is one of Git's most distinctive features. It's a **middle layer** between your working files and your commits:

```
Working Directory  →  Staging Area  →  Commit
   (files)              (add)           (commit)
```

**Beginner framing:** staging is "I want this in my next snapshot." You stage, then commit.

**Intermediate framing:** the staging area lets you **select** what goes into a commit — not just commit everything at once. This is what makes atomic commits possible: commit the bug fix separately from the new feature, even if you edited both files.

**Junior-dev framing:** if you've only edited one file, `git add .` and `git add <file>` are equivalent. As you get more precise about commits, `git add <file>` becomes the go-to for selective staging.

---

### 5.5 Removing files with `git rm`

> **Let's say you have added files to Git and you do not want it to track any of them.**
> **Running a simple `git rm` command will not only remove it from Git, but will also remove it from your local file system as well!**

**The dangerous command:**

```
git rm <file>
```

**What it does:**

- Removes the file from Git's tracking.
- **Also deletes the file from disk.**
- **The file is gone.**

**The safe command:**

```
git rm --cached <file>
```

**What it does:**

- Removes the file from Git's tracking (unstages it).
- **Keeps the file on your local system.**

**The `--cached` flag is the difference.**

**Beginner framing:** `git rm` deletes the file. `git rm --cached` just stops Git from caring about it — the file stays.

**Intermediate framing:** `git rm --cached` is used when you accidentally added a file that shouldn't be tracked — like a log file, a build artifact, or a secrets file. You want Git to forget about it without losing it.

**Junior-dev framing:** when you stage a file _by mistake_, use `git rm --cached` (not `git rm`) to undo the staging. If you then add it to `.gitignore`, Git won't try to track it again.

---

### 5.6 Committing changes

> **Once you have staged your files, you can commit them into Git.**
> **Imagine a commit command as a snapshot at a certain point in time where you can return back to access your repository at that stage.**
> **You assign a commit message to every commit, which you can pass with the `-m` prefix.**

**The command:**

```
git commit -m 'first commit'
```

**What it does:**

- Takes everything in the **staging area**.
- Saves it as a **snapshot** with the given message.
- Adds it to the repository's history.

**The message matters:**

- **It's what future-you will read** when scrolling through history.
- **It should describe _why_ the change was made** — not just what.
- **Good:** `"add login form validation"`
- **Bad:** `"update"`, `"changes"`, `"fix"`, `"asdf"`

**Beginner framing:** a commit is a **saved checkpoint** with a label. The label is your message.

**Intermediate framing:** commits are **atomic units of history**. Each one should represent a single logical change — a bug fix, a feature, a refactor. This makes history readable and reverts surgical.

**Junior-dev framing:** you commit **often** — after every meaningful change. Small, frequent commits are easier to understand, easier to revert, and easier to review than large ones.

---

## 6. Worked Example — a complete first repository

> **Scenario:** you have a folder called `learn_git` with a file in it, and you want to track it with Git.

**Step 1 — install Git** (if not already installed).
Run `git --version` in a terminal. If it errors, follow the install method for your OS (§5.1).

**Step 2 — navigate to the folder.**

```bash
cd ~/Desktop/learn_git
```

**Step 3 — initialize the repository.**

```bash
git init
```

Output:

```
Initialized empty Git repository in /home/<username>/Desktop/learn_git/.git/
```

**Step 4 — create a file.** (If you don't have one already.)

```bash
echo "Hello Git" > hello.txt
```

**Step 5 — check status.**

```bash
git status
```

Output shows:

```
Untracked files:
  hello.txt
```

Git sees the file, but doesn't track it yet.

**Step 6 — stage the file.**

```bash
git add .
```

Now run `git status` again:

```
Changes to be committed:
  new file:   hello.txt
```

The file is **staged** — in the middle area, ready to commit.

**Step 7 — commit.**

```bash
git commit -m 'first commit'
```

Output:

```
[main (root-commit) a1b2c3d] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 hello.txt
```

**Step 8 — verify.**
Run `git status`. Now it says:

```
nothing to commit, working tree clean
```

**Step 9 — change the file and see the loop.**
Edit `hello.txt` (add a second line). Run `git status` — the file is now **modified**. Stage with `git add .`, commit with `git commit -m 'add second line'`. Repeat.

**What this example teaches:**

- **`git init` once** — every subsequent command works on the initialized repo.
- **`git status`** at every step — it's your feedback loop.
- **Stage then commit** — the two-step flow is deliberate, not redundant.
- **The working tree goes clean** after each commit — nothing to commit means everything is saved.
- **The loop repeats** — edit → status → add → commit → repeat.

---

## 7. Common Pitfalls

- ❌ **Running `git rm <file>` when you meant `git rm --cached <file>`.** The first deletes the file from disk; the second stops tracking without deleting. Confusing them loses work.
- ❌ **Skipping `git status` before committing.** You may commit files you didn't intend to.
- ❌ **Running `git init` in the wrong folder.** Git tracks from that point down — if you initialize too high (e.g., in your home directory), everything below is tracked.
- ❌ **Committing with a bad message.** "update" and "fix" tell future-you nothing. Write _why_ the change was made.
- ❌ **Committing everything at once.** `git add .` is fine for small projects; for larger ones, stage selectively so each commit is a coherent change.
- ❌ **Forgetting to save the file before committing.** Git tracks the **saved** state — edits in the editor's buffer aren't committed.
- ❌ **Assuming `git add` commits.** It doesn't. `git add` stages; `git commit` commits. They're distinct steps.
- ❌ **Using Git without a `.gitignore`.** Log files, `node_modules/`, `.env` files — all get tracked by default. Ignore them before the first commit.

---

## 8. Hands-On Exercises

1. **Verify Git is installed (5 min).** Run `git --version` in a terminal. Note the version.
2. **Create and initialize (10 min).** Create a folder called `git-practice`. Navigate to it, run `git init`, and check for the hidden `.git` folder (Windows: enable hidden files; Mac/Linux: `ls -la`).
3. **The core loop (15 min).** Inside `git-practice`:
   - create a file `notes.txt`,
   - run `git status` (see it untracked),
   - run `git add .` (see it staged),
   - run `git commit -m 'add notes file'` (see the commit).
4. **The `git rm` distinction (10 min).**
   - Add a new file `temp.txt`.
   - Stage it with `git add temp.txt`.
   - Run `git rm --cached temp.txt` — confirm the file **still exists** on disk.
   - Then run `git rm temp.txt` — confirm the file **is deleted** from disk.
5. **Bad commits (10 min).** Make a change with a terrible commit message (`"asdf"`). Then look at `git log --oneline`. What could you have written instead?
6. **Add a `.gitignore` (10 min).** Create a file called `secret.env`. Add `secret.env` to a new `.gitignore` file. Run `git status` — confirm the file is no longer listed.
7. **Repeat the loop (10 min).** Make three changes, each time: edit → `git status` → `git add` → `git commit -m '...'`. Observe how each change adds a new entry to the history.

---

## 9. Checkpoint Questions

1. What does `git init` do — and what does it create?
2. Why is `git status` the first command you should run before staging?
3. What is the **staging area**, and why does it exist?
4. What does `git add .` do? How is it different from `git add <file>`?
5. What's the difference between `git rm <file>` and `git rm --cached <file>`? Which one deletes the file from disk?
6. What is a **commit**, and what does `-m` do?
7. Why does the course call a commit a **"snapshot"**?
8. Why should commit messages describe _why_ a change was made, not just _what_?
9. What does `nothing to commit, working tree clean` mean?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
