# Skill 7 — Website Creation with CMS

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--building-a-small-shop-site-step-by-step)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

There are **two ways to create a website**:

| Approach                            | Who it's for                        | What it means                                                                                                             |
| ----------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **CMS** (Content Management System) | People **without technical skills** | An **easy-to-use system** to control and manage content — add/delete images, links, and other content without coding      |
| **Hard coding**                     | **Web developers**                  | Requires **specific skills and programming languages** — the complex way, but with full freedom to build a custom website |

This skill focuses on the **CMS path**: what a CMS is, which platforms dominate, what you can build with them, and the **six steps** to launch a CMS site.

Hard coding is what the rest of this bootcamp teaches — but a professional web developer **knows both paths** and knows _when each one is the right tool_.

---

## 2. Why It Matters (for you, as a developer)

- **Clients will ask for CMS work.** A huge share of real-world web projects are WordPress, Shopify, or similar. Knowing how they work is a marketable skill.
- **CMS knowledge shapes your architecture decisions.** When you build a custom app, you'll often _borrow_ CMS ideas — content types, admin panels, plugins — and knowing the patterns helps.
- **Knowing when _not_ to hard-code is professional judgment.** Not every project needs a custom build. Recommending a CMS when it fits is a sign of maturity, not a shortcut.
- **WordPress alone powers over 61% of sites with a known CMS.** You will encounter it. Understanding its strengths and limits is unavoidable.

---

## 3. Prerequisites

- Skill 2 (Web architecture — clients and servers).
- Skill 6 (Web development — front-end, back-end, database layers).

---

## 4. Key Concepts

1. **Two ways to build a website:** CMS and hard coding.
2. **A CMS is software** that helps users create, manage, and modify content **without technical knowledge**.
3. **A CMS handles the basic infrastructure** (pages, images, storage) so you focus on content and design.
4. **Most-known CMS platforms:** WordPress, Wix, Squarespace, Joomla!, Shopify, Drupal, Blogger, Prestashop, Magento, Bitrix.
5. **WordPress** = the most popular CMS, with **over 61% market share** among sites with a known CMS.
6. **Prestashop** = an open-source **e-commerce** CMS, split into **front office** (visible to users) and **back office** (admin interface).
7. **You can build almost any site type** with a modern CMS: static sites, blogs, e-commerce, forums, social networks, courses, memberships, portfolios.
8. **Six steps to launch:** pick a platform → install → choose plugins → customize design → upload content → go online.

---

## 5. Concepts Explained

### 5.1 Two ways to create a website

**CMS — the accessible path:**

> **CMS (Content Management System) is an easy-to-use system that allows you to control and manage the content within your website without necessarily having technical skills.**
> **You can easily add and delete images, links, presentation links, and other content on your website.**

**Hard coding — the developer's path:**

> **Hard coding requires specific skills and knowledge of programming languages. That is the complex way to create a website — and that is what web developers do.**
> **In hard coding, you have the freedom to change what you want and build a custom website that completely satisfies the needs of the user, the employer, and the client.**

**The trade-off:**

|                     | **CMS**                   | **Hard coding**       |
| ------------------- | ------------------------- | --------------------- |
| **Skills needed**   | None (or minimal)         | Programming languages |
| **Speed to launch** | Fast                      | Slower                |
| **Flexibility**     | Constrained by the CMS    | Full freedom          |
| **Cost**            | Often cheaper upfront     | More upfront work     |
| **Customization**   | Extend via plugins/themes | Anything you can code |
| **Maintenance**     | Handled by the CMS        | You own it            |

**Beginner framing:** a CMS is a website _builder_; hard coding is _building from raw materials_. Both produce a website — with different trade-offs.

**Intermediate framing:** this isn't "easy vs. hard" — it's **"buy vs. build."** A CMS is a product you extend; hard coding is a product you create. Both are legitimate engineering decisions.

**Junior-dev framing:** as a web developer, you'll often be asked to **customize a CMS** (WordPress themes, Shopify templates) _and_ to **build custom apps**. Knowing both is a career advantage.

---

### 5.2 What a CMS is

> **A CMS is software that helps users create, manage, and modify content on a website without the need for technical knowledge.**
> **In simpler terms, a CMS is a tool that helps you build a website without needing to write all the code from scratch — or even know how to code at all.**

**The key insight:**

> **Instead of building your own system for creating web pages, storing images, and other functions, the CMS handles all the basic infrastructure tasks for you — so you can focus on more forward-facing parts of your website.**

**What a CMS handles for you:**

- Page creation and management
- Image and media storage
- User accounts and permissions
- Content editing (often with a rich text editor)
- Publishing workflows (draft, review, publish)
- Themes and layouts
- Plugins and extensions

**Beyond websites:**

> **Besides websites, you can also find CMSs for other functions like document management.**

**Beginner framing:** a CMS is a _tool_ that gives you the website infrastructure — you supply the content and design choices.

**Intermediate framing:** a CMS is a **content-first abstraction**. It separates _content_ (what you write, upload, edit) from _presentation_ (the theme, the layout) and from _infrastructure_ (the server, the database). This separation is what makes it powerful — the same content can appear in different layouts, and non-technical users can edit content safely.

**Junior-dev framing:** WordPress is technically a **PHP application with a MySQL database**. When you "customize a theme," you're writing PHP, HTML, CSS, and JS. The CMS handles the plumbing; you handle the surface.

---

### 5.3 The most known CMS platforms

> **The most known CMS platforms are WordPress, Wix, Squarespace, Joomla!, Shopify, Drupal, Blogger, Prestashop, Magento, and Bitrix.**

They fall into different categories:

| Platform        | Type                   | Notes                                    |
| --------------- | ---------------------- | ---------------------------------------- |
| **WordPress**   | General-purpose CMS    | Most popular; huge plugin ecosystem      |
| **Wix**         | Website builder (SaaS) | Drag-and-drop; hosted; less code control |
| **Squarespace** | Website builder (SaaS) | Design-focused; hosted                   |
| **Joomla!**     | General-purpose CMS    | Powerful; steeper learning curve         |
| **Shopify**     | E-commerce platform    | Hosted; focused on online stores         |
| **Drupal**      | General-purpose CMS    | Enterprise-grade; complex; very flexible |
| **Blogger**     | Blogging platform      | Google-owned; simple                     |
| **Prestashop**  | E-commerce CMS         | Open-source; self-hosted                 |
| **Magento**     | E-commerce platform    | Powerful; enterprise-scale e-commerce    |
| **Bitrix**      | CMS / intranet         | Popular in some regions                  |

**The two platforms the course focuses on:**

#### WordPress

> **WordPress is the best example of a popular CMS. While there are certainly other content management systems out there, WordPress maintains over 61% of the market share on websites with a known content management system.**

**Strengths:**

- **An incredibly clear administration console**, with an abundance of menus.
- **Versatility** — a blog can become a showcase site, a portfolio, or even an e-commerce site.
- **A large community of users and developers** — so you can find a multitude of resources (templates, modules, plugins) to optimize and personalize your website.

**Weaknesses:**

- **Configuration possibilities can put off some beginner users** — the depth of options can feel overwhelming.

#### Prestashop

> **Prestashop is an open-source CMS that allows you to create an online e-commerce store.**
> **The CMS can be modified by adding modules available on the Prestashop platform, or developed artistically.**

**Prestashop's two-part structure:**

| Part                                       | What it is                                                                                                |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| **Front office** (front interface)         | **The part that's visible to Internet users on the web**                                                  |
| **Back office** (administration interface) | **The part that's only visible to the site administrator** — allows you to manage the content of the site |

> **It is a preconceived and modular website.**

**Beginner framing:** WordPress is the generalist; Prestashop is the e-commerce specialist.

**Intermediate framing:** the **front office / back office** split is a _universal_ concept — not just Prestashop. Every serious web app has a public-facing surface and an admin surface. Learning the distinction here makes it easy to recognize everywhere else.

**Junior-dev framing:** the front/back office distinction is the CMS-version of the **client-server** split from Skill 2 — but from the _user's perspective_: what the visitor sees vs. what the admin manages. When you build custom apps later, you'll design the same split.

---

### 5.4 What kinds of websites you can build with a CMS

> **Nowadays, most content management systems are pretty flexible. While there are a few that focus on a specific use — like Magento and eCommerce — most of the popular content management systems can be used to create essentially any type of website.**

**WordPress, for example, can power:**

| Type                  | What it is                                        |
| --------------------- | ------------------------------------------------- |
| **Static websites**   | Pages that rarely change — home, about, contact   |
| **Blogs**             | Chronological posts, categories, comments         |
| **E-commerce stores** | Products, carts, checkout, orders                 |
| **Forums**            | Threaded discussions between users                |
| **Social networks**   | User profiles, feeds, connections                 |
| **Online courses**    | Lessons, progress tracking, quizzes               |
| **Membership sites**  | Gated content for paying or registered users      |
| **Portfolios**        | Showcase of work — images, projects, case studies |

**The key insight:**

> **Most popular CMSs can be used to create essentially any type of website** — _if_ you're willing to accept the CMS's way of doing it.

**Beginner framing:** a modern CMS isn't _just_ for blogs. It's a flexible platform that can power many kinds of sites.

**Intermediate framing:** the limit of a CMS is **how far the plugin ecosystem covers your use case**. If it does, you're fast. If it doesn't, you're fighting the CMS — which is exactly when hard coding becomes the right choice.

---

### 5.5 How a CMS website is made — the six steps

> **To build a website with a CMS, the proper steps are as follows:**

| Step                              | What to do                                                                                                                                                                                       |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1. Pick a platform**            | **Choose the CMS that best suits your web development needs and final expectations** — _before launching anything._                                                                              |
| **2. Install the CMS**            | **The installation process is easy, intuitive, and takes only a couple of minutes.**                                                                                                             |
| **3. Choose and install plugins** | **Almost all reputable CMSs require plugin installation** — plugins **add functionality** to your project. If you don't need a full-featured complicated project, you can continue without them. |
| **4. Customize the design**       | **Pick a suitable theme and customize your website design.** Almost all CMSs come with **integrated templates**, but you can also find **multiple variants on the web.**                         |
| **5. Upload content**             | **Replace the pre-designed content with your own** (images, text, media files) to get a unique, personalized project.                                                                            |
| **6. Go online**                  | **The final step is website publication.**                                                                                                                                                       |

**Beginner framing:** these are the six steps to launch — pick, install, extend, style, fill, publish.

**Intermediate framing:** the order matters:

- **Pick before installing** — choosing poorly costs a rebuild.
- **Plugins before design** — plugins affect layout and compatibility.
- **Design before content** — content is written _into_ the design, not around it.
- **Publish last** — because publishing is the decision that exposes everything.

**Junior-dev framing:** this six-step flow is the **CMS version of a build pipeline**. It's the same discipline as any project — decide, set up, extend, style, fill, ship. You'll recognize it in hard-coded projects too.

---

## 6. Worked Example — building a small shop site step by step

> **Scenario:** you've been asked to build a small online shop for a local business.

**Step 1 — Pick a platform.**
The site needs an online store with products, a cart, and a checkout. **Prestashop** or **Shopify** fit the e-commerce focus; **WordPress + WooCommerce** works if a blog or content is also needed. **Decision:** choose based on the _primary_ purpose.

**Step 2 — Install the CMS.**
For a self-hosted option (Prestashop), install on a hosting provider — usually a few clicks or a one-line command. For a hosted option (Shopify), sign up and you're in.

**Step 3 — Choose and install plugins.**

- **Prestashop modules** for payments, shipping, reviews, SEO.
- **WordPress plugins** (if chosen) for WooCommerce, payments, shipping.
- **Skip what you don't need** — plugins add complexity and maintenance.

**Step 4 — Customize the design.**
Pick a theme. For a shop, this means product grid layout, product page template, cart and checkout styling. Then customize — colors, typography, logo, layout.

**Step 5 — Upload content.**
Add products: names, images, descriptions, prices, stock, categories. Replace theme demo content with real content.

**Step 6 — Go online.**
Publish. Test the flow end-to-end: browse → add to cart → checkout → order confirmation.

**What this example teaches:**

- **The six steps work for real projects**, not just tutorials — they're the same order any CMS build follows.
- **The front office / back office split is visible from step 4 onward** — you're editing in the back office; customers see the front office.
- **The choice in step 1 determines the rest of the project.** Changing platforms at step 5 means starting over.
- **Not every project needs every step** — a simple blog might skip step 3 entirely.

---

## 7. Common Pitfalls

- ❌ **Thinking "CMS = easy, hard coding = professional."** Both are legitimate. The right choice depends on the project's needs, budget, and timeline.
- ❌ **Assuming a CMS is just for blogs.** Modern CMSs power e-commerce, memberships, forums, courses, and portfolios.
- ❌ **Skipping step 1 (platform choice).** Choosing poorly means rebuilding later — the most expensive kind of mistake.
- ❌ **Over-installing plugins.** Every plugin adds complexity, security surface, and maintenance. Install only what you need.
- ❌ **Ignoring the front office / back office split.** It's a useful mental model — the admin surface and user surface are different products with different needs.
- ❌ **Confusing CMS with no-code.** CMS themes still require HTML/CSS/PHP/JS work to customize deeply. "No-code" is really "less code."
- ❌ **Assuming CMS sites don't need developers.** Customization, plugin integration, and performance tuning are _developer work_ — just on a CMS instead of from scratch.
- ❌ **Recommending a CMS for every project.** A custom build is sometimes the right call. Judgment matters more than tooling.

---

## 8. Hands-On Exercises

1. **Two paths (10 min).** For each project, say whether a CMS or hard coding fits better, and why:
   - (a) a personal blog you want to launch this weekend,
   - (b) a social network for a niche community,
   - (c) a small business site with a few pages,
   - (d) a real-time collaboration tool,
   - (e) an online store with 50 products.
2. **Platform matching (10 min).** For each scenario, pick a CMS from the list (WordPress, Shopify, Prestashop, Magento, Squarespace, Wix) and justify in one sentence:
   - (a) a portfolio for a photographer,
   - (b) a small online shop for handmade goods,
   - (c) a large enterprise store with complex logistics,
   - (d) a blog with frequent posts and comments.
3. **Front office / back office (10 min).** List three things that appear in the **front office** of a shop site, and three that appear only in the **back office**.
4. **The six steps (15 min).** For a small blog site, write the six steps in your own words — and note one decision you'd have to make at each step.
5. **Plugin judgment (10 min).** Imagine you're building a small restaurant site. List:
   - two plugins you'd install,
   - two you'd avoid (and why).
6. **CMS vs. code (10 min).** Pick one scenario from Exercise 1 and write two paragraphs: one arguing for a CMS, one arguing for hard coding. Then decide.

---

## 9. Checkpoint Questions

1. What are the **two ways to create a website**? Briefly describe each.
2. In one sentence, what is a **CMS**?
3. Why does a CMS make websites accessible to people without technical skills?
4. Name **five CMS platforms** and one characteristic of each.
5. Why is **WordPress** so widely used — name at least two reasons.
6. What's the difference between the **front office** and the **back office** in a CMS like Prestashop?
7. Name the **six steps** to launch a CMS website.
8. Why does the course say a web developer should know **both** approaches (CMS and hard coding)?
9. What kinds of websites can you build with a modern CMS? Name at least four.

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
