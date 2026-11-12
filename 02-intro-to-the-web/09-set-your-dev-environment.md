# Skill 9 — Set Your Dev Environment

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--your-first-html-page)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Skill 8 introduced the **three tools** of a developer environment. This skill is the **hands-on guide**: **install VSCode on Windows, macOS, or Linux**, add a few essential extensions, and **create your first web page**.

By the end of this skill, you will have:

- **VSCode installed** on your operating system.
- **A minimal extension set** (Prettier + a theme) to make the editor yours.
- **A working `.html` file** you can open in your browser — your first web page.

The steps differ by OS, but the outcome is the same: **a working editor, a working browser, and a first file**.

---

## 2. Why It Matters (for you, as a developer)

- **A working environment is the prerequisite for everything.** You can't write HTML, CSS, or JavaScript without an editor and a browser that show you the results.
- **Installation is a one-time investment.** Do it once, carefully, and you don't think about it again for years.
- **Extensions shape your productivity.** As Skill 8 said: _"The plugins that you're using have a huge impact on your productivity."_ This skill starts you with two that matter early: **Prettier** (formatting) and **a theme** (visibility).
- **Your first page is a milestone.** It's the moment the three pillars (Skill 6) stop being abstract — HTML becomes a real file you can see in a browser.

---

## 3. Prerequisites

- Skill 8 (Code Editors — what VSCode is and why it matters).

---

## 4. Key Concepts

1. **VSCode installs on all three major operating systems** — Windows, macOS, Linux — with a _different_ process for each.
2. **Windows:** download `VSCodeSetup.exe`, run the installer, follow the wizard.
3. **macOS:** download the `.dmg`, drag the app into the Applications folder.
4. **Linux:** download the package for your distro (`.deb`, `.rpm`, Snap, or AUR), install via package manager.
5. **Extensions** — **Prettier** (code formatter) and **themes** (visual customization) are the first two worth installing.
6. **A `.html` file** is the fundamental unit of a web page — open it in a browser to see it.
7. **HTML is a markup language** — you'll learn it in depth in the next superskill.

---

## 5. Concepts Explained

### 5.1 Installing VSCode on Windows

**Step-by-step:**

1. **Download.** Open your browser and visit [code.visualstudio.com](https://code.visualstudio.com/). Click **"Download for Windows"** — the latest version downloads automatically.
2. **Run the installer.** Locate the downloaded file (usually `VSCodeSetup.exe`) and **double-click it**.
3. **UAC prompt (optional).** Windows may ask for permission to make changes. Click **"Yes"**.
4. **Destination folder (optional).** The default (`Program Files`) is usually recommended. Click **"Next"**.
5. **Additional tasks (optional).** Choose desktop shortcuts, context menu entries, etc., based on your preference. Click **"Next"**.
6. **Install.** Click **"Install"** to begin.
7. **Finish.** When complete, check **"Run Visual Studio Code"** and click **"Finish"**.
8. **Optional — Add to Start Menu.** After install, find VSCode in the Start Menu; drag it to the taskbar for quick access.

**Beginner framing:** it's a standard Windows installer — download, run, click through, done.

**Intermediate framing:** the optional steps (destination, additional tasks) rarely matter. The defaults are fine for most users. The one worth _considering_ is "Add to PATH" — it lets you launch VSCode from the terminal with `code .`, which is genuinely useful.

---

### 5.2 Installing VSCode on macOS

**Step-by-step:**

1. **Download.** Visit [code.visualstudio.com](https://code.visualstudio.com/). The site detects your OS and offers the **universal installer**. Click **"Download for macOS"**.
   - If auto-detection fails, choose **Intel** or **Apple Silicon** manually.
2. **Open the installer.** Locate the `.dmg` file and **double-click it**. A window opens showing VSCode alongside an **Applications** shortcut.
3. **Install.** **Drag** the VSCode icon onto the **Applications** shortcut. This copies the app to your Applications folder.
4. **Launch.** Open **Applications** and double-click **Visual Studio Code**.
5. **Optional — Add to Dock.** On first launch, macOS may ask if you want to add VSCode to the Dock. Choose based on preference.

**Beginner framing:** macOS installation is _drag-and-drop_ — no installer wizard, just move the app to Applications.

**Intermediate framing:** the "Add to Dock" prompt appears once. If you dismissed it, you can re-add from the Applications folder later. The _actual_ installation is the drag into Applications; the rest is convenience.

---

### 5.3 Installing VSCode on Linux

> **Installing Visual Studio Code on Linux is a breeze, and you can do it using various methods depending on your Linux distribution.**

**Four methods, each for a different distro:**

| Method             | For which distro          | How                                                   |
| ------------------ | ------------------------- | ----------------------------------------------------- |
| **`.deb` package** | Debian / Ubuntu-based     | Download `.deb` and install with your package manager |
| **`.rpm` package** | Red Hat / Fedora-based    | Download `.rpm` and install with your package manager |
| **Snap**           | Most modern Linux distros | `snap install code --classic` (from the Snap Store)   |
| **AUR**            | Arch Linux / Arch-based   | Install via an AUR helper like `yay`                  |

**The recommended order:**

> **Install using a package manager** — it's the most standard, most maintainable method. Snap and AUR are alternatives for specific distros.

**After install:**

> **Start Visual Studio Code** from the application menu, or by typing `code` in the terminal.

**Beginner framing:** Linux has multiple ways to install, depending on which distro you use. Pick the one that matches your system.

**Intermediate framing:** **package-manager installation is _always_ preferred** over downloading a raw archive. It lets you update VSCode through your normal system update flow — one less thing to maintain manually.

**Junior-dev framing:** if you're on Linux, you probably already know your distro's package manager. Use it. If not, **Snap** is the most portable option across modern distros.

---

### 5.4 VSCode extensions — your first two

> **Here are some examples of what you can achieve with an Extension API.**

The course highlights two categories worth installing early:

#### Prettier — the code formatter

> **Prettier is one of the best plugins for developers who need to follow a well-laid set of rules when developing.**
> **It's a robust opinionated code formatter that allows developers to format their codes in a structured way.**
> **Prettier works together with JavaScript, HTML, CSS, Markdown, and other modern tools and allows you to properly format your code.**

**Why it matters:**

- **Consistency.** Every file gets the same style — indentation, spacing, quotes — regardless of who wrote it.
- **Less friction.** You stop worrying about formatting and focus on the code.
- **Works across languages** — HTML, CSS, JS, Markdown, and more.

**The word "opinionated" is important:** Prettier has _one_ style by default. You don't configure every rule — you accept its format. That's a feature, not a bug: it ends the formatting debates.

#### Themes — making the editor yours

> **Since you'll be looking at your editor every day, why not make it as pretty as possible?**
> **There are tons of customization plugins that change the color scheme and the icons in the sidebar.**

**Popular free themes:**

- **One Monokai** — dark, classic Monokai color scheme.
- **One Dark Pro** — the Atom "One Dark" theme, very popular for VSCode.
- **Material Icon Theme** — replaces default file icons with language-specific icons.

**Why themes matter:**

- **You look at the editor for hours per day.** A theme you enjoy makes the work more pleasant.
- **Some themes improve readability.** Higher contrast, clearer syntax highlighting.
- **Icons help navigation.** Material Icon Theme, for example, shows file _types_ at a glance.

**Beginner framing:** Prettier makes code neat; a theme makes the editor pleasant. Install both, use both.

**Intermediate framing:** Prettier is _more than cosmetic_ — it's part of a workflow. Once installed, format-on-save becomes the default, and every file you touch is automatically consistent. This is one of the first "professional habit" setups a developer installs.

**Junior-dev framing:** the _correct_ extensions to install is a common beginner question, and the answer is often **"the ones that solve a problem you actually have."** Prettier and a theme are near-universal — install them early. Others (linters, language servers, debuggers) come later, as your work demands them.

---

### 5.5 Creating your first web page

> **Follow the next steps to create your first web page in this track:**
> **Create a file and name it whatever you want with the extension `.html` — which is a markup language of a web page.**

**Steps:**

1. **Create a file** named something like `index.html` (`.html` is the extension).
2. **Open it in VSCode.** Copy and paste the sample below.
3. **Save the file.**
4. **Open it in your browser.** Double-click, drag into the browser, or right-click → "Open with."

**The sample code:**

```html
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Woooohooow this is my first page :)</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

**What each part does (brief preview — full depth comes in Superskill #4):**

| Tag       | What it does                                   |
| --------- | ---------------------------------------------- |
| `<html>`  | The root of the page — everything goes inside  |
| `<head>`  | Metadata — the tab title, links to CSS, etc.   |
| `<title>` | The text shown in the browser **tab**          |
| `<body>`  | The visible content — everything the user sees |
| `<h1>`    | A top-level heading — big and bold             |
| `<p>`     | A paragraph                                    |

> **We will learn more about HTML in the next super skill.**

**What comes next (per the course):**

> **Our next steps would be to make it look better and style it using CSS.**
> **Afterward, we will make it interactive and user-friendly using JavaScript.**

**Beginner framing:** you've just created a real web page. It's simple, but it's real — it has structure (HTML), and it renders in a browser.

**Intermediate framing:** this sample is _deliberately minimal_. It has no CSS, no JavaScript, no external resources. It's the smallest possible thing that is still a web page. That minimalism is intentional: **start from zero, add layers.** CSS and JS come next, but only after HTML makes sense.

**Junior-dev framing:** the file is saved as `.html`. The browser reads the file _from disk_ — no server involved yet. This is the simplest possible version of the loop: edit → save → refresh. Every web developer starts here.

---

## 6. Worked Example — your first HTML page

> **Scenario:** you've finished installing VSCode and want to confirm your environment works.

**Step 1 — install VSCode** using the instructions for your OS (§5.1, §5.2, or §5.3).

**Step 2 — install two extensions.**

- **Prettier:** open the Extensions panel (Ctrl+Shift+X / Cmd+Shift+X), search "Prettier," install it.
- **A theme:** search "One Dark Pro" (or your preferred theme), install it, then select it via **File → Preferences → Color Theme**.

**Step 3 — create your first file.**
In VSCode: **File → New File**, save it as `index.html` in a folder called `my-first-page`.

**Step 4 — paste the sample:**

```html
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Woooohooow this is my first page :)</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

**Step 5 — format with Prettier.**
Press **Shift+Alt+F** (Windows/Linux) or **Shift+Option+F** (macOS). Prettier tidies the indentation. Notice how it's now consistently formatted.

**Step 6 — open in the browser.**
Right-click the file in your OS → **Open with → Google Chrome** (or drag the file into Chrome).

**Step 7 — observe what you see:**

- **The tab title** says _"Page Title"_ — that's `<title>`.
- **The page body** shows the heading _"Woooohooow this is my first page :)"_ and the paragraph _"This is a paragraph."_ — those are `<h1>` and `<p>`.

**Step 8 — inspect.**
In Chrome, right-click the page → **Inspect**. In the Elements panel, you can see the HTML _as the browser parsed it_. This is how you'll debug layout and content issues going forward.

**What this example teaches:**

- **The editor wrote the file; the browser rendered it.** The two are distinct steps in the loop.
- **Prettier is instant and invisible** — a single keystroke, and the file is consistently formatted.
- **The minimal HTML page works** — no CSS, no JS, just structure. This is the foundation everything else builds on.
- **DevTools shows the source** — the bridge between the file and the rendered page.

---

## 7. Common Pitfalls

- ❌ **Installing VSCode but not using it.** The point is to _write files_, not just install an app. Create a file and open it.
- ❌ **Skipping Prettier.** It's one of the two extensions worth installing _immediately_. Formatting gets harder as the file grows.
- ❌ **Skipping themes for too long.** You'll look at the editor daily. An hour spent choosing a theme is well invested.
- ❌ **Wrong install method on Linux.** Downloading a `.deb` and manually installing it _works_, but using your package manager is the _maintainable_ path — and the one the course recommends.
- ❌ **Saving the HTML file with the wrong extension.** If your file ends in `.txt` or has no extension, the browser won't render it as HTML. It must be `.html`.
- ❌ **Forgetting to save before refreshing the browser.** Many beginner "why isn't it updating?" moments are simply _unsaved file_. Save first; refresh second.
- ❌ **Editing in one program and viewing in another, without saving in between.** The browser reads the file from _disk_, not from your editor's memory. Save, then refresh.
- ❌ **Treating the sample page as the goal.** It's the _starting point_. The goal is to understand the workflow: write → save → refresh → inspect.

---

## 8. Hands-On Exercises

1. **Install VSCode (15 min).** Follow the instructions for _your_ operating system. Confirm it launches.
2. **Install Prettier and a theme (10 min).** Install both extensions. Set your theme via File → Preferences → Color Theme.
3. **Create `index.html` (10 min).** In a folder called `my-first-page`, create a file named `index.html` and paste the sample HTML.
4. **Format (5 min).** Press Shift+Alt+F (Windows/Linux) or Shift+Option+F (macOS). Confirm the file is now consistently indented.
5. **Open in Chrome (5 min).** Open the file. Confirm you see the heading and paragraph.
6. **Inspect (10 min).** Right-click → Inspect. In the Elements panel, find:
   - the `<title>` element,
   - the `<h1>`,
   - the `<p>`.
     Then modify the `<h1>` text in DevTools (changes are temporary — refresh to reset).
7. **Extend the page (15 min).** Add two more elements to your HTML:
   - an `<h2>` heading,
   - a `<ul>` list with two `<li>` items.
     Save, format, refresh. What changed?
8. **Reflect on the loop (5 min).** Write down the workflow you just followed:
   edit → save → refresh → inspect → edit again.
   What could you do to make this loop faster?

---

## 9. Checkpoint Questions

1. What are the **three main steps** to install VSCode on Windows?
2. What is the **macOS install method** — in one sentence?
3. Name **three ways** to install VSCode on Linux, and note when each applies.
4. What does **Prettier** do, and why is it worth installing first?
5. Why do **themes** matter, and what do popular ones (One Monokai, One Dark Pro, Material Icon) change?
6. What **file extension** must your first page have, and why does it matter?
7. What is the difference between the **editor** and the **browser** in the workflow you just followed?
8. Why does the course mention that **HTML is "a markup language"** — and what comes after HTML in this track?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
