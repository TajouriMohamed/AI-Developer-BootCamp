# Skill 8 — Code Editors

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--setting-up-your-environment-for-html-css-and-javascript)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

To write code, you need **a developer environment**. For this course, that means **three tools every web developer uses**:

| #     | Tool                                         | Purpose                        |
| ----- | -------------------------------------------- | ------------------------------ |
| **1** | **A text editor**                            | To write code                  |
| **2** | **A web browser**                            | To preview what we're building |
| **3** | **A version control and Repository Manager** | **Git & GitHub**               |

**The recommended tools for this course:**

- **Google Chrome** — a web browser. Download: [google.com/chrome](https://www.google.com/chrome/)
- **Visual Studio Code** — a code editor. Download: [code.visualstudio.com](https://code.visualstudio.com/)
- **Git & GitHub** — covered later in the bootcamp (Superskill #3).

> **Like any good craftsperson, it's important that you become familiar with your tools.**

This skill focuses on **the code editor** — what it is, why it matters, and why **VSCode** is the standard choice.

---

## 2. Why It Matters (for you, as a developer)

- **You'll spend most of your career in a text editor.** It's where the craft happens. Getting comfortable with your editor is a direct productivity multiplier.
- **The editor is where you'll write HTML, CSS, and JavaScript** — the three pillars from Skill 6. The editor must make them easy to work with.
- **Plugins change everything.** As the course says: _"The plugins that you're using have a huge impact on your productivity and the way you work."_
- **A familiar environment removes friction.** When the tool gets out of the way, you can focus on the problem — which is exactly what a professional setup is for.

---

## 3. Prerequisites

- Skill 6 (web development — the three pillars: HTML, CSS, JavaScript).

---

## 4. Key Concepts

1. **Three tools of the trade:** a **text editor**, a **web browser**, and **Git & GitHub**.
2. **Recommended for this course:** **Google Chrome** (browser) and **VSCode** (editor).
3. **A web browser** lets us **view web pages** — and **preview the results** of our code.
4. **A code editor** is software that helps us **edit text** — like a basic text editor, but with **additional features** (code highlighting, debugging support, and more).
5. **VSCode** is the **most used text editor**.
6. **VSCode provides a ton of plugins** — and **plugins have a huge impact on productivity**.
7. **The right plugins make VSCode fit your preferences** — you configure it to fit how you work.

---

## 5. Concepts Explained

### 5.1 Setting up your developer environment

> **For this course, we'll need three tools that every web developer uses:**
> **1. A text editor to write code.**
> **2. A web browser to preview what we're building.**
> **3. A version control and Repository Manager (Git & GitHub).**

**Why these three?**

- **The editor** is where code is written.
- **The browser** is where the code is _seen_ — the output, the result of running it.
- **Version control** is where the code is _tracked_ — the history of how it changed, and the collaboration surface for teams.

Together, they form a **feedback loop**:

> **Write (editor) → view (browser) → save and track (Git/GitHub) → repeat.**

**The recommended tools:**

| Tool                   | Category        | Download                                                |
| ---------------------- | --------------- | ------------------------------------------------------- |
| **Google Chrome**      | Web browser     | [google.com/chrome](https://www.google.com/chrome/)     |
| **Visual Studio Code** | Code editor     | [code.visualstudio.com](https://code.visualstudio.com/) |
| **Git & GitHub**       | Version control | Covered in Superskill #3                                |

You can use **any** browser or editor — these are _recommendations_, not requirements. The course picks them because they're widely used, well-supported, and familiar to most developers.

**Beginner framing:** these three tools are the _minimum_ to write, see, and save code. Everything else (frameworks, plugins, additional editors) layers on top.

**Intermediate framing:** the feedback loop is what makes development _iterative_. A tight loop — write, view, adjust — is what lets you learn fast. Anything that slows the loop (slow browser, broken editor, no version control) has an outsized cost.

**Junior-dev framing:** professional setups have all three. If you find yourself without one of them (e.g., writing code in a file with no version control, or previewing in a browser you can't inspect), you're making your life harder than it needs to be.

---

### 5.2 The web browser — your preview window

> **Google Chrome is a web browser. You may or may not already be using Google Chrome for browsing the web. A web browser allows us to view web pages.**

**What it does for us:**

> **We'll use Google Chrome to view the results after writing and making changes to our code.**

**The two roles of a browser:**

1. **As a user** — to browse the Web (Skill 1).
2. **As a developer** — to preview your work, inspect what's happening, and debug.

**In development, the browser is more than a viewer:**

- It **renders** your HTML, CSS, and JavaScript.
- It offers **DevTools** — inspect elements, view console logs, analyze network requests, run performance audits.
- It's where **you see whether your code works** — the moment of truth after every change.

**Beginner framing:** the browser is where you see what you've built. Without it, code is invisible.

**Intermediate framing:** Chrome DevTools is one of the most powerful debugging tools in web development. It's not an optional extra — it's part of the browser. Once you start using it daily, it becomes indispensable.

**Junior-dev framing:** you'll spend as much time in DevTools as in the editor. Both are first-class tools — not "the editor plus an afterthought."

---

### 5.3 The code editor — where the craft happens

> **Visual Studio Code is a popular code editor. A code editor is a very aptly named software; it helps us edit text.**

**How it compares to a default text editor:**

> **It is similar to the default text editor that comes preinstalled on Mac or Windows, but has additional features like code highlighting to enhance our coding and debugging experience.**

**What makes a code editor more than a text editor:**

| Feature                      | What it does                                                          |
| ---------------------------- | --------------------------------------------------------------------- |
| **Syntax highlighting**      | Colors keywords, strings, variables — makes code readable at a glance |
| **Auto-indentation**         | Keeps code formatted as you type                                      |
| **Bracket matching**         | Shows which `{` closes which `}`                                      |
| **Error underlining**        | Flags syntax errors as you write                                      |
| **File tree / project view** | Navigate a whole project, not just a file                             |
| **Integrated terminal**      | Run commands without leaving the editor                               |
| **Extensions**               | Add languages, linters, debuggers, and more                           |
| **Search across files**      | Find things across the whole project                                  |
| **Git integration**          | Stage and commit without leaving the editor                           |

**The difference is the point:**

> **A basic text editor writes text. A code editor writes _code_ — with awareness of the language.**

**Beginner framing:** a code editor is like a text editor that _understands_ what you're writing. It colors the code, catches obvious mistakes, and helps you navigate.

**Intermediate framing:** the editor's "understanding" comes from **language servers** and **parsers**. That's why code highlighting is accurate (not just regex), and why features like "go to definition" work. VSCode is an _extensible_ editor built around this idea.

**Junior-dev framing:** the choice of editor matters less than _how well you know it_. A developer fluent in VSCode is more productive than one constantly switching tools. Depth beats novelty.

---

### 5.4 VSCode — the standard choice

> **Visual Studio Code (or VSCode) is the most used text editor.**

**Why it's the standard:**

- **It's the most widely used** — so tutorials, documentation, and community help are mostly written with VSCode in mind.
- **It provides a ton of plugins** that make a developer's life easier.
- **It's flexible:** _"When you're using it, you have the ability to make it fit your preferences by installing the right plugins."_
- **It's free and cross-platform** — Windows, macOS, Linux.

**The plugin philosophy:**

> **The plugins that you're using have a huge impact on your productivity and the way you work.**

This is the key idea:

- **VSCode out of the box is good.** But **VSCode with the right plugins is _yours_.** The editor adapts to your workflow, not the other way around.
- **Plugins can be transformative** — a good formatter, a good linter, a good theme, a good Git integration — each one changes how you work.
- **Plugins can also slow you down** — too many, or the wrong ones, add noise. The skill is _choosing well_.

**The trade-off:**

|                 | **Few plugins**         | **Many plugins**                       |
| --------------- | ----------------------- | -------------------------------------- |
| **Speed**       | Fast, minimal friction  | Can get slow to start, harder to debug |
| **Flexibility** | Limited                 | Extensive                              |
| **Complexity**  | Low                     | Can be high                            |
| **Best for**    | Beginners, focused work | Advanced workflows, specific languages |

**Beginner framing:** VSCode is the editor most developers use. Install a few plugins and it becomes a powerful tool.

**Intermediate framing:** the right plugin set depends on your _stack_. A front-end developer wants different plugins from a Python developer. Your editor should reflect your actual work.

**Junior-dev framing:** start with a **minimal** plugin set — HTML/CSS/JS essentials, a theme you like, a formatter, a linter. Add plugins _when you find a problem they solve_. Resist the urge to install everything you see in a YouTube video.

---

## 6. Worked Example — setting up your environment for HTML, CSS, and JavaScript

> **Scenario:** you've just finished Skill 6 (Web Development) and want to start writing your first HTML, CSS, and JavaScript files.

**Step 1 — install Google Chrome.**
Visit [google.com/chrome](https://www.google.com/chrome/) and install it. This is your **preview window** — where your code will run.

**Step 2 — install VSCode.**
Visit [code.visualstudio.com](https://code.visualstudio.com/) and install it. This is your **editor** — where your code will live.

**Step 3 — open VSCode and create a project folder.**
Create a folder called `my-first-website` somewhere on your computer. Open it in VSCode (**File → Open Folder**).

**Step 4 — create three files:**

- `index.html` — the HTML (structure)
- `style.css` — the CSS (styling)
- `script.js` — the JavaScript (interactivity)

**Step 5 — install a few essential extensions.**
Open the Extensions panel (Ctrl+Shift+X / Cmd+Shift+X) and install:

- **Live Server** — serves your HTML locally and refreshes on save.
- **Prettier** — formats your code consistently.
- **ESLint** (optional) — catches JavaScript errors as you write.

**Step 6 — write a small page:**

`index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="style.css" />
    <title>My First Site</title>
  </head>
  <body>
    <h1>Hello, Web!</h1>
    <button id="greet">Click me</button>
    <script src="script.js"></script>
  </body>
</html>
```

`style.css`:

```css
body {
  font-family: sans-serif;
  background: #f0f4f8;
  text-align: center;
  padding: 2rem;
}
```

`script.js`:

```javascript
document.getElementById("greet").addEventListener("click", () => {
  alert("You clicked the button!");
});
```

**Step 7 — preview in Chrome.**
Right-click `index.html` → "Open with Live Server" (or open the file directly in Chrome). **You see the page.** Click the button — the alert fires.

**Step 8 — inspect what's happening.**
Right-click in Chrome → **Inspect**. Open the **Console** tab. See your logs, errors, and any output.

**What this example teaches:**

- **The three tools are used together** — editor writes, browser previews, Git (later) tracks.
- **The editor is where the writing happens**, but the browser is where the _verification_ happens.
- **Extensions make the editor fit _this_ project** — Live Server and Prettier are front-end specific; you might install different ones for a Python project.
- **The feedback loop is immediate** — change a file, save, see the result. That tight loop is what makes learning fast.

---

## 7. Common Pitfalls

- ❌ **Skipping the version control step.** It's easy to think "I'll learn Git later" — but _no version control_ means no undo, no history, no collaboration. Install it early.
- ❌ **Treating the editor and the browser as the same thing.** They're not. The editor writes; the browser verifies. You need both.
- ❌ **Installing every plugin you see.** More plugins ≠ more productivity. Start minimal, add when a problem arises.
- ❌ **Ignoring DevTools.** The browser is a _debugging_ tool as much as a viewing tool. Learn to open DevTools early.
- ❌ **Using a plain text editor for code.** Technically possible; practically painful. The highlighting, indentation, and error flagging a code editor provides are not optional for real work.
- ❌ **Switching editors every few months.** Depth of familiarity beats novelty. Pick one, learn it deeply.
- ❌ **Assuming VSCode is the only option.** It's the _most used_, but other editors (Sublime, Atom, JetBrains, Vim) are valid. The choice matters less than fluency.

---

## 8. Hands-On Exercises

1. **Install the three tools (15 min).** Install Google Chrome and VSCode if you haven't already. (Git comes later.) Confirm both launch.
2. **Create a project (10 min).** Create a folder called `my-first-site` and open it in VSCode. Create three files: `index.html`, `style.css`, `script.js`.
3. **Essential plugins (10 min).** Install **Live Server** and **Prettier** in VSCode. Note how they change your workflow — what's easier now?
4. **Write a small page (15 min).** Write a page with:
   - an `<h1>` heading,
   - a paragraph,
   - a button that shows an alert when clicked.
     Preview in Chrome. Then open DevTools → Console and check for errors.
5. **Plugin audit (10 min).** List 3–5 plugins you'd install for _your_ workflow. For each, note what problem it solves — not just "it's popular."
6. **Reflect on the loop (10 min).** Write a one-paragraph reflection on the **write → preview → debug** feedback loop. Which part feels slowest right now? What could you do to speed it up?

---

## 9. Checkpoint Questions

1. What are the **three tools** every web developer uses, and what does each do?
2. Why is **version control** part of the developer environment, not an optional extra?
3. What is the difference between a **plain text editor** and a **code editor**? Name at least three features a code editor adds.
4. What browser does the course recommend, and why might that choice matter for _this_ course?
5. What is **VSCode**, and why is it the most-used editor?
6. What role do **plugins** play in an editor like VSCode?
7. Why is **starting with minimal plugins** usually better than installing many at once?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
