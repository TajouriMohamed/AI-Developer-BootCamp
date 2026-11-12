# Skill 6 — Web Development

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--a-contact-form-across-all-three-layers)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

> **Web development is the process of building websites and applications for the Internet or for a private network known as an Intranet.**

It's not only about **design** — it's also about the **coding and programming that powers the website's functionality**.

From the simplest static pages to social platforms, e-commerce sites, and content management systems (CMS), **all the tools we use daily via the Internet have been built by web developers.**

Web development breaks down into **three layers**:

| Layer                   | Also called | Runs on                      |
| ----------------------- | ----------- | ---------------------------- |
| **Client-side coding**  | Front-end   | The user's browser           |
| **Server-side coding**  | Back-end    | The server                   |
| **Database technology** | —           | The DBMS (behind the server) |

This skill maps the territory: **what a web developer is**, **the types of web developers**, and **the core skills** you'll be building over the next few weeks.

---

## 2. Why It Matters (for you, as a developer)

- **It names the three layers you'll work in for the rest of your career.** Front-end, back-end, database — every project touches all three, even if you specialize in one.
- **It gives you a role model.** Front-end, back-end, and full stack are real job titles with real boundaries. Knowing the boundaries helps you choose a direction — and collaborate with people in the other roles.
- **It names the three pillars** — HTML, CSS, JavaScript — so you know what's coming. Everything later in this superskill and the bootcamp builds on them.
- **It's the mental map for the whole superskill.** Once you see the three layers, every subsequent skill (HTML, CSS, JS, DOM) slots into place.

---

## 3. Prerequisites

- Skill 1 (Internet vs. Web).
- Skill 2 (Web architecture — clients and servers).
- Skill 5 (databases — the third layer).

---

## 4. Key Concepts

1. **Web development** = the process of building websites and applications — **design + coding + functionality**.
2. **Three layers:** **client-side** (front-end), **server-side** (back-end), **database technology**.
3. **A web developer** is an **interactive and creative artist**; their **canvas is the user's browser**.
4. **Three types of web developers:** **front-end**, **back-end**, **full stack**.
5. **The three pillars of web development:** **HTML, CSS, JavaScript**.
   - **HTML** defines the _content_.
   - **CSS** defines _how it's displayed_.
   - **JavaScript** makes it _interactive_.
6. **A web developer's daily work:** fixing bugs, building features, reading others' code, collaborating.

---

## 5. Concepts Explained

### 5.1 What web development is

> **Web development is the process of building websites and applications for the Internet or for a private network known as an Intranet.**

**Two clarifications:**

- **It's not only design.** Design is _one_ part — the coding and programming that powers the site's functionality is the other.
- **It covers a huge range.** From the simplest static pages to social media and CMS — all built by web developers.

**The three layers, in detail:**

| Layer                       | What it covers                                             | Examples                                 |
| --------------------------- | ---------------------------------------------------------- | ---------------------------------------- |
| **Client-side (front-end)** | Everything the user sees and interacts with in the browser | Layout, fonts, colors, menus, forms      |
| **Server-side (back-end)**  | Everything behind the scenes — logic, data flow, security  | APIs, authentication, business rules     |
| **Database technology**     | Where data is stored and retrieved                         | SQL / NoSQL databases behind the backend |

**Beginner framing:** web development is the craft of building for the browser. It has a visible side (what you see) and a hidden side (what makes it work).

**Intermediate framing:** the three layers are a **layered architecture**. Each has its own tools and concerns. A strong web developer is fluent at least at the boundaries — knowing _what_ belongs where, even if they specialize in one layer.

**Junior-dev framing:** every project you touch has all three layers. Even a "simple" front-end app needs a server somewhere (at minimum, the one serving the files) and some form of data storage (even if it's just static files).

---

### 5.2 What defines a web developer

> **A web developer is by nature an interactive and creative artist.** She/he is **driven by a deep desire to create things**. A web developer's **canvas is a user's web browser**.

**The LEGO analogy:**

> **A web developer's job is to use the basic building blocks of the Web (like HTML, CSS, and JavaScript) to create something complex like a web page** — the way a curious child takes pleasure in joining LEGO blocks, then taking them apart to see how they're made.

**What this conveys:**

- **Creation is the drive.** You build things — and you enjoy the building.
- **The blocks are simple; the combinations are endless.** HTML, CSS, and JS are individually simple; combined, they produce everything on the Web.
- **Curiosity matters.** Reading others' code, taking things apart, understanding how they work — that's part of the craft.

**Beginner framing:** you're a builder. The browser is where your work lives.

**Intermediate framing:** the LEGO analogy is more than motivational — it's architecturally accurate. Web pages _are_ composed of small reusable pieces (elements, components, modules). Learning to think in composable pieces is one of the biggest level-ups in web development.

---

### 5.3 Types of web developers

> **Front-end, back-end, and full stack** — three roles with different scopes.

#### Front-end Developer

> **Client-side scripting, or front-end development, refers to everything that the end user experiences directly.**

- **Runs on the browser.**
- **Directly relates to what people see** when they visit a website.
- **Layout, fonts, colors, menus, contact forms** — all designed by the front-end.

**The tools:** HTML, CSS, JavaScript, and modern frameworks (React, Vue, Angular).

#### Back-end Developer

> **Server-side scripting, or back-end development, is all about what goes on behind the scenes.**

- **The part of a website the user doesn't see.**
- **Stores and organizes data.**
- **Ensures everything on the client-side runs smoothly** — by communicating with the front-end.

**The request/response flow:**

> **Whenever something happens on the client-side** (like a user fills out a form), **the browser sends a request to the server-side.**
> **The server-side "responds" with relevant information** in the form of front-end code that the browser can then interpret and display.

This is the **request/response cycle** (Skill 2 and Skill 4 revisit it — here it's framed from the developer's perspective).

**The tools:** server-side languages (PHP, Python, Node.js, Ruby, Java), frameworks (Django, FastAPI, Express, Rails), databases.

#### Full Stack Developer

> **A full stack web developer is a person who can develop both client and server software.**

**Beyond HTML and CSS, they know how to:**

- **Program a web page** — JavaScript, jQuery, React, Angular, or Vue.
- **Program a server** — PHP, ASP, Python, or Node.
- **Program a database** — SQL, SQLite, or MongoDB.

**The side-by-side comparison:**

|                    | **Front-end**        | **Back-end**                  | **Full stack**    |
| ------------------ | -------------------- | ----------------------------- | ----------------- |
| **Focus**          | User experience      | Logic and data                | Both              |
| **Runs on**        | The browser          | The server                    | Both              |
| **Languages**      | HTML, CSS, JS        | PHP, Python, Node, Ruby, Java | Both              |
| **Data**           | Fetches and displays | Stores, validates, protects   | Both              |
| **Typical output** | What users see       | What users _don't_ see        | The whole product |

**Beginner framing:** front-end is _what you see_; back-end is _what makes it work_; full stack is _both_.

**Intermediate framing:** the boundaries blur in practice. A "front-end" developer today often writes server-side code (SSR frameworks, API routes, serverless functions). A "back-end" developer often needs to understand client-side behavior. Full stack is the _combination_, not a separate discipline.

**Junior-dev framing:** many entry-level jobs are **front-end** or **back-end**; full stack roles tend to want a year or two of experience. Choose a starting direction, but expect to touch all three layers over time.

---

### 5.4 The skills of a web developer

> **Mainly, it requires the mastery of these three languages: HTML, CSS and JavaScript.**

**They are the three pillars of web development**, and collectively **they make a website function**:

| Language       | Role                                                  | What it defines                                     |
| -------------- | ----------------------------------------------------- | --------------------------------------------------- |
| **HTML**       | Defines the **content** to be displayed               | Structure — headings, paragraphs, images, links     |
| **CSS**        | Instructs the browser **how to display that content** | Styling — layout, colors, fonts, spacing            |
| **JavaScript** | Makes the content **interactive**                     | Behavior — clicks, form validation, dynamic updates |

**The full sentence from the course, worth memorizing:**

> **Defining the content to be displayed (HTML), instructing a browser how to display that content (CSS), and making the content interactive (JavaScript).**

**What else a web developer does:**

- **Reads other people's code** and makes changes to it.
- **Finds and debugs errors** — called **"bugs"** (shortcomings in existing code).
- **Works on new projects from scratch** — or improves **existing websites**.
- **Works with other developers** to discuss ways to solve problems.

**A typical day:**

> **Fixing bugs, developing new features (enhancements) and web pages, and working with other developers to discuss ways to solve problems.**

**Beginner framing:** HTML is the skeleton, CSS is the skin, JavaScript is the muscles. Together they make a working page.

**Intermediate framing:** the three pillars are the **front-end stack**. Everything in modern front-end development — frameworks, build tools, state management — is built on top of them. The pillars don't become obsolete; they become _assumed_.

**Junior-dev framing:** the pillars are non-negotiable. Frameworks change; HTML, CSS, and JS stay. Fluency in them is what makes frameworks easy to learn.

**A reassuring note from the course:**

> **Don't be overwhelmed by all of these details. You'll soon see that they're all very connected, and learning one of these languages automatically makes you better at a few others!**

This is true — and it's worth internalizing early. HTML, CSS, and JavaScript share concepts (structure, selection, events, state) that transfer across all three.

---

## 6. Worked Example — a contact form across all three layers

> **Scenario:** a user fills out a contact form on a website and clicks Submit.

**The front-end (client-side):**

1. **HTML** defines the form: `<input>`, `<textarea>`, `<button>`.
2. **CSS** styles it: layout, colors, spacing, focus states.
3. **JavaScript** handles the click: reads the inputs, validates them (e.g., email format), and sends a request.

**The request:**

4. **The browser sends an HTTP request** to the server (Skill 3, Skill 4) — typically a `POST` with the form data.

**The back-end (server-side):**

5. **The server receives the request** and validates the data again (never trust the client).
6. **The server writes to the database** — storing the contact message, the sender's email, timestamp, etc. (Skill 5).
7. **The server builds a response** — either a JSON payload (`{"status": "ok"}`) or a redirect, or new HTML to render.

**The database:**

8. **The database stores the record** — so the message can be retrieved later, searched, and reviewed.

**The response back to the client:**

9. **The browser receives the response** and updates the UI — a success message, an error notice, or a redirect.

**What this example teaches:**

- **All three layers participate in one action.** No single layer alone can handle a form submission.
- **Each layer has its own job.** Front-end handles presentation and interaction; back-end handles logic and trust; database handles persistence.
- **The request/response cycle is the connective tissue.** It's the moment where the layers talk to each other.

---

## 7. Common Pitfalls

- ❌ **Thinking web development is "just design."** It's design _plus_ coding _plus_ functionality — and the coding is the bulk of the work.
- ❌ **Assuming one role does everything.** Front-end, back-end, and full stack are real distinctions. Even full stack developers often lean one direction.
- ❌ **Skipping HTML/CSS/JS because "frameworks are better."** Frameworks sit on top of the pillars. Skipping them means the frameworks never fully make sense.
- ❌ **Believing "front-end" means "no logic."** Modern front-end is deeply logic-heavy — validation, state, routing, data fetching.
- ❌ **Assuming back-end is "just database queries."** It's also authentication, authorization, business rules, error handling, and security.
- ❌ **Treating full stack as a "one-person team."** It's a _breadth_ of skills, not a promise to replace three people.
- ❌ **Getting overwhelmed by the breadth.** As the course says: it's _connected_. Learning one language makes you better at others. Depth comes gradually.

---

## 8. Hands-On Exercises

1. **Identify the layers (10 min).** For each feature of a website, say which layer(s) it involves:
   - (a) a hover effect on a button,
   - (b) validating an email address in a signup form,
   - (c) storing a user's profile picture,
   - (d) displaying a list of products,
   - (e) checking whether a user is logged in.
2. **Role matching (10 min).** For each task, say whether it's primarily **front-end**, **back-end**, or **full stack**:
   - (a) making a page responsive,
   - (b) designing a database schema,
   - (c) building a React component that fetches data from an API,
   - (d) writing an API endpoint that creates a user,
   - (e) debugging a broken form submission that touches all three layers.
3. **The LEGO analogy (10 min).** In your own words, explain how a web page is like a LEGO build. Give one concrete example of a "block" and one example of a "build."
4. **Pillars in action (15 min).** For a simple to-do list page, list:
   - one piece of HTML that defines the structure,
   - one piece of CSS that styles it,
   - one piece of JavaScript that makes it interactive.
5. **A typical day (10 min).** The course says a typical day involves **fixing bugs, building features, and collaborating**. Write a one-paragraph "day in the life" of a web developer working on a small app.
6. **Self-assessment (10 min).** Which of the three roles (front-end, back-end, full stack) appeals to you most right now? Why? Write two sentences.

---

## 9. Checkpoint Questions

1. In one sentence, what is **web development**?
2. What are the **three layers** of web development, and what does each do?
3. What is the difference between **front-end** and **back-end** development?
4. What does a **full stack** developer do beyond front-end and back-end?
5. Name the **three pillars** of web development and what each is responsible for.
6. What is a **bug**, and what role does debugging play in a developer's day?
7. Why does the course say the three languages are **"very connected"**? What does that mean practically?
8. What does it mean that "a web developer's canvas is the user's browser"?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
