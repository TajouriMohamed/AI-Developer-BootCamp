# Skill 10 — GitHub Account

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--from-sign-up-to-first-repository)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

> **GitHub is an online software development platform used for storing, tracking, and collaborating on software projects.**

It's more than a place to keep files. GitHub is:

- **A storage and collaboration platform** — developers from all over the world work on shared projects.
- **An ecosystem** — with a **social networking aspect**, letting individual developers contribute to multiple teams and projects.
- **A version control surface** — built on **two connected principles: version control and Git**.
- **A website host** — via **GitHub Pages**, which publishes static HTML, JS, and CSS files directly from a repository.

This skill covers what GitHub is, how to **create an account**, and how to **sign in** — step by step.

---

## 2. Why It Matters (for you, as a developer)

- **GitHub is where your work lives.** It's the de facto home for code — public, private, individual, and team projects.
- **It's the collaboration layer.** Reviewing code, filing issues, proposing changes, tracking history — all of it happens on GitHub.
- **It's a portfolio.** Employers and collaborators look at GitHub profiles. A well-maintained account is a professional asset.
- **It's a website host.** For a web developer, **GitHub Pages** means you can publish a static site for free, straight from a repository.
- **It's the foundation for the rest of the bootcamp.** Git and version control get a dedicated superskill later — this is the entry point.

---

## 3. Prerequisites

- Skill 8 (Code Editors — the three-tool environment includes Git & GitHub).
- Skill 9 (Set Your Dev Environment — VSCode installed and working).

---

## 4. Key Concepts

1. **GitHub is an online software development platform** for **storing, tracking, and collaborating** on software projects.
2. **It's more than storage** — it has a **social networking aspect** and an ecosystem of tools.
3. **Two connected principles** underlie it: **version control** and **Git**.
4. **GitHub Pages** hosts **static websites** — just publish static HTML, JS, and CSS from a repository.
5. **One email = one GitHub account.** An email can't be reused for a second account.
6. **A GitHub account requires:** email, password, and a **unique username**.
7. **Verification includes a puzzle** — solving a set of human-verification challenges.
8. **A profile can include:** full name, bio, company, location, website, and social links.

---

## 5. Concepts Explained

### 5.1 What GitHub is

> **GitHub is an online software development platform used for storing, tracking, and collaborating on software projects.**

**Three roles in one:**

| Role              | What it does                                                                                     |
| ----------------- | ------------------------------------------------------------------------------------------------ |
| **Storage**       | Hosts your code — public or private repositories                                                 |
| **Tracking**      | Records the history of every change                                                              |
| **Collaboration** | Lets multiple developers work on the same project, review each other's work, and discuss changes |

**The open-source dimension:**

> **It allows collaboration with developers from all over the world, and this open-source solution, like also the others, enables potential developers to contribute and share their knowledge to benefit the global community.**

**The ecosystem dimension:**

> **GitHub has many unique features that make it extremely popular these days, since it is an entire ecosystem complete with an elaborate social networking aspect, besides simple storage — allowing individual developers to contribute to multiple teams and projects.**

**Beginner framing:** GitHub is where your code lives and where other developers can see it, review it, and contribute to it.

**Intermediate framing:** GitHub is a **hosted platform for Git repositories**. It adds a web interface, collaboration features (issues, pull requests, reviews), and integrations — but the _core_ is Git under the hood. Knowing Git is knowing GitHub.

**Junior-dev framing:** your GitHub profile is your public developer identity. Your repositories, commit history, and contributions form a track record that others can inspect. Treat it as a portfolio — because that's how it will be read.

---

### 5.2 Version control and Git — the two connected principles

> **It should be understood by knowing two connected principles, which are version control and Git.**

**Version control:**

- The practice of **tracking changes** to files over time.
- Lets you see _what_ changed, _when_, _by whom_, and _why_.
- Lets you **roll back** to earlier versions, branch off to try ideas, and merge changes.

**Git:**

- The **tool** that implements version control on your machine.
- A **distributed version control system** — every clone contains the full history.
- GitHub is a **hosting platform for Git repositories** — the remote copy.

**The relationship:**

> **Git is the tool. Version control is the concept. GitHub is the platform.**
> You use Git locally to track changes; GitHub stores and shares the result.

**Beginner framing:** Git tracks the history; GitHub stores that history online and makes it shareable.

**Intermediate framing:** Git is **distributed** — every clone has the full history, not just the latest version. That's what makes offline work, branching, and merging possible. GitHub is one of many remote Git hosts (others include GitLab and Bitbucket).

**Junior-dev framing:** you'll learn Git commands in a later superskill. For now: GitHub ≠ Git. GitHub is _built on_ Git, but it adds a UI, collaboration tools, and hosting on top.

---

### 5.3 GitHub Pages — hosting a static website

> **GitHub is also a great place for conveniently hosting static websites using its feature GitHub Pages, by simply publishing static HTML, JS, and CSS files from a GitHub repository.**
> **It has emerged as a popular choice for hosting websites due to its simplicity, versatility, and seamless integration with version control systems.**

**What GitHub Pages does:**

- **Publishes a static site** from a repository.
- **Free for public repositories** — a common portfolio and documentation tool.
- **No server required** — the site is served by GitHub from your files.
- **Integrated with version control** — update the files in the repo, and the site updates.

**What "static" means here:**

- HTML, CSS, and JS files are served as-is.
- **No server-side code** — no databases, no backend logic, no authentication.
- Perfect for: **portfolios, documentation, project landing pages, blogs (with static site generators)**.

**Beginner framing:** if your site is just HTML/CSS/JS files, GitHub Pages can host it — for free, straight from your repo.

**Intermediate framing:** GitHub Pages is a **static site host**. It reads files from a branch in your repo and serves them via a CDN. The "static" limitation is real — it's not for full-stack apps. But for docs and portfolios, it's one of the simplest deployment paths available.

**Junior-dev framing:** you'll use this later in the bootcamp — deploy a portfolio or documentation site directly from your bootcamp projects. It's a fast, free way to put your work online.

---

### 5.4 Creating a GitHub account — the rules

> **One email for one GitHub account.**
> **A GitHub account requires one email, and that email cannot be used to create another GitHub account.**

**The rules:**

- **One email = one account.** Not negotiable at sign-up.
- **A unique username** is also required — usernames are visible and permanent-ish.
- **Multiple email addresses can map to a single account** (for notifications, recovery, etc.) — but the sign-up email is the primary one.

**What a GitHub account needs:**

| Requirement      | Notes                                       |
| ---------------- | ------------------------------------------- |
| **Email**        | Must not be used for another GitHub account |
| **Password**     | The system requires a **strong** password   |
| **Username**     | Must be **unique** across GitHub            |
| **Verification** | A **puzzle** confirms you're human          |

**Beginner framing:** pick a good username — you'll live with it. Use your primary email; it can't be reused.

**Intermediate framing:** your username is your **public identity** on GitHub — it appears in every URL, commit, and collaboration. Choose thoughtfully: professional is safer than playful for a career asset.

**Junior-dev framing:** you can change your username later, but it breaks old URLs and can confuse collaborators. Choose once, choose well.

---

### 5.5 Signing up — the full flow

> **Visit [github.com](https://github.com), click Sign up, and follow the flow.**

**The 26-step flow, distilled into phases:**

**Phase 1 — Start the signup:**

1. Visit [github.com](https://github.com).
2. Click **Sign up**.
3. Use an **email that has not been used** for another GitHub account.
4. Type the email, click **Continue**.
5. Set a password until it says **"Password is strong"**, click **Continue**.
6. Enter a **unique username**, click **Continue**.
7. Choose whether to receive product updates and announcements via email, click **Continue**.

**Phase 2 — Verification:** 8. Click **Start puzzle** to verify as a human. 9. Solve **first puzzle**. 10. Solve **second puzzle**. 11. Solve **third puzzle**. 12. Solve **fourth puzzle**. 13. Receive confirmation that the account is verified, click **Create account**.

**Phase 3 — Email verification:** 14. Check your email for a code from GitHub. 15. Enter the emailed code.

**Phase 4 — Profile setup:** 16. You're on the **GitHub Dashboard**. Access the menu via the icon at the **top-right corner**. 17. Choose **Your profile** from the menu. 18. Click **Edit profile** if necessary. 19. Add **full name, short bio, company, location, website, and links to social accounts**. Click **Save**.

**Phase 5 — Welcome & sign-in test:** 20. Check your email — there's a **welcome message** from GitHub. 21. Access the menu again, click **Sign out**. 22. Confirm, click **Sign out**. 23. Choose **Sign in**. 24. Provide **username and password**, click **Sign in**. 25. Wait for the sign-in process.

**Phase 6 — You're in:** 26. **Create a repository**, or do various activities on GitHub. Read **GitHub Docs** for help.

**Beginner framing:** the flow is longer than most sign-ups because GitHub takes account verification seriously — puzzles, emailed code, profile setup. Take it one step at a time.

**Intermediate framing:** the puzzle phase can be annoying, but it's a **bot-prevention measure**. Multiple puzzles in sequence are used when verification is uncertain. Don't refresh the page mid-puzzle — you'll lose progress.

**Junior-dev framing:** the welcome email is worth reading — it links to onboarding guides and explains the layout. Your **profile page** is your public face: fill it out properly, including a professional bio and a link to your website or portfolio.

---

### 5.6 Your GitHub profile

> **Full name, short bio, company, location, website, and some links to social accounts can be added to your GitHub profile.**

**What a strong profile includes:**

| Field            | Why it matters                              |
| ---------------- | ------------------------------------------- |
| **Full name**    | Makes your profile human, searchable        |
| **Short bio**    | One-line summary of what you do             |
| **Company**      | Workplace (or "Student" / "Freelance")      |
| **Location**     | Useful for networking, collaboration        |
| **Website**      | Portfolio, blog, or personal site           |
| **Social links** | Twitter, LinkedIn, etc. — proof of presence |

**Beginner framing:** your profile is the first thing people see when they visit your GitHub. Fill it out — an empty profile looks like an inactive account.

**Intermediate framing:** GitHub profiles are **searchable and linked from your repos**. Recruiters and collaborators often click through. A complete profile with a clear bio communicates professionalism and makes you findable.

**Junior-dev framing:** fill in **at minimum**: name, bio, and website. Even a one-sentence bio ("Web developer learning AI") is better than nothing. Add social links so people can reach you.

---

## 6. Worked Example — from sign-up to first repository

> **Scenario:** you've just signed up for GitHub and want to test that everything works.

**Step 1 — sign in.**
Visit [github.com](https://github.com). Click **Sign in**. Enter your username and password.

**Step 2 — look at the dashboard.**
You land on your **homepage** — a feed of activity from people and projects you follow. This is your command center.

**Step 3 — view your profile.**
Click the **profile icon** (top-right) → **Your profile**. This is your public page. Fill in:

- Your **full name**.
- A **short bio** (e.g., "Web developer | Learning AI development").
- Your **website** (or a placeholder).
- Your **LinkedIn** (or another social link).

Click **Save**.

**Step 4 — create a repository.**

- From the top-right **+** menu, choose **New repository**.
- **Repository name:** `my-first-page` (or similar).
- **Description:** _"My first HTML page"_.
- **Visibility:** **Public** (so it can be viewed).
- **Initialize with a README:** check the box.
- Click **Create repository**.

**Step 5 — observe what got created.**
You'll see:

- Your **README.md** rendered on the page.
- The **file listing** (currently just `README.md`).
- Tabs for **Code**, **Issues**, **Pull requests**, **Actions**, **Projects**, **Wiki**, **Security**, **Insights**, **Settings**.

**Step 6 — edit the README.**
Click the pencil icon on `README.md`. Add a sentence: _"This is my first GitHub repository."_ Scroll down, click **Commit changes**.

**Step 7 — see the history.**
Click **Commits** (top of the file list). You now have **two commits**: the initial one and your edit. This is version control in action — the same feature that Git provides.

**Step 8 — try GitHub Pages (optional).**

- Go to **Settings** → **Pages**.
- Under **Source**, pick `main` branch, `/ (root)`.
- Save. GitHub will tell you your site will be available at `https://<your-username>.github.io/my-first-page/` after a minute.

**What this example teaches:**

- **The account flow ends in a working dashboard** — not just a registered email.
- **Repositories are the units of GitHub.** One repo = one project.
- **Commits are the unit of history.** Each save is a commit.
- **GitHub Pages is one setting away** from publishing a static site.
- **The dashboard, profile, and repository pages** are the three surfaces you'll use most.

---

## 7. Common Pitfalls

- ❌ **Reusing an email for a second GitHub account.** Not allowed. One email = one account.
- ❌ **Picking a careless username.** Your username appears in every URL and commit. Choose something professional.
- ❌ **Skipping profile setup.** An empty profile looks like an inactive account — fill in name, bio, and website at minimum.
- ❌ **Confusing GitHub and Git.** GitHub is a _platform_; Git is the _tool_ underneath it. The two are related, not identical.
- ❌ **Assuming GitHub Pages hosts anything.** It hosts **static** sites only — HTML, CSS, JS files. No server-side code.
- ❌ **Refreshing mid-puzzle during sign-up.** You'll lose progress. Complete the puzzle in one sitting.
- ❌ **Not reading the welcome email.** It contains onboarding guidance and a link to documentation — useful the first time.
- ❌ **Skipping the sign-in test.** After signing up, sign out and sign in again to _confirm_ everything works.

---

## 8. Hands-On Exercises

1. **Create your account (15 min).** Visit [github.com](https://github.com), click Sign up, and complete the flow:
   - unique email,
   - strong password,
   - unique username,
   - human puzzle(s),
   - emailed verification code.
2. **Fill in your profile (10 min).** Add full name, short bio, website (or placeholder), and one social link.
3. **Create a first repository (10 min).** Name it `my-first-page`, set it public, and check **"Initialize with a README."**
4. **Edit the README (5 min).** Click the pencil icon, add one sentence, commit the change.
5. **View the commit history (5 min).** Click "Commits" — how many are there? What are their messages?
6. **Try GitHub Pages (10 min).** Go to **Settings → Pages**, set the source to your `main` branch. After a minute, visit the URL GitHub provides.
7. **Reflect (10 min).** Write down three questions you have about GitHub after finishing this skill. (You'll likely answer some of them in Superskill #3 — Git integration.)

---

## 9. Checkpoint Questions

1. In one sentence, what is **GitHub**, and what is it used for?
2. Name the **three roles** of GitHub (storage, tracking, collaboration) and what each means.
3. What are the **two connected principles** GitHub is built on?
4. What is **GitHub Pages**, and what kinds of sites can it host?
5. What are the **rules** for a GitHub account — email, password, username, verification?
6. What information can you add to your **GitHub profile**?
7. Why is it useful to **sign out and sign back in** after creating your account?
8. What does it mean to say GitHub is **"built on Git"** — and how are the two different?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
