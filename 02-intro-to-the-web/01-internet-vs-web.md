# Skill 1 — The Internet vs. The Web

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--following-a-request-from-click-to-page)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Many people use the terms **Internet** and **World Wide Web** (a.k.a. **the Web**) interchangeably, but the two terms are **not synonymous**.

They are two **separate but related** things:

- **The Internet** is the **infrastructure** — a global network of billions of computers and other electronic devices.
- **The Web** is a **collection of websites** you access _through_ the Internet.

The simplest framing:

> **The Internet is the road. The Web is the traffic on it.**

You can use the Internet without the Web (email, chat, file transfer), but you can't use the Web without the Internet.

---

## 2. Why It Matters (for you, as a developer)

- **Precision matters.** When you debug a "network issue," you need to know whether it's the _connection_ (Internet) or the _page_ (Web). They fail differently and are fixed differently.
- **It explains what a browser actually does.** A browser is a _Web_ client — it's not the Internet. Confusing the two leads to broken mental models of what your code is talking to.
- **It's the foundation for everything next.** HTTP, DNS, servers, APIs — all of it builds on the distinction between _infrastructure_ and _content_.
- **It comes up in interviews.** "What's the difference between the Internet and the Web?" is a classic warm-up question, and the confident answer signals how clearly you think about systems.

---

## 3. Prerequisites

- None. This is the entry point to the Web.

---

## 4. Key Concepts

1. **The Internet** = a global **network of physical cables** and devices.
2. **The Web** = a **collection of websites** accessed through the Internet.
3. **A web browser** is an application that _displays_ websites — it is **not** the Internet.
4. **Servers** store websites and respond to requests over the Internet.
5. **A request round trip** happens in seconds: your computer → server → your computer.
6. **The Internet does much more than the Web** — email, chat, media, banking, and more.

---

## 5. Concepts Explained

### 5.1 The Internet — the infrastructure

> **The Internet is a global network of billions of computers and other electronic devices.**

With the Internet, it's possible to:

- access almost any information,
- communicate with anyone else in the world,
- do much more.

**How you connect:**

- You connect a computer to the Internet — this is called **going online**.
- When someone says a computer is **online**, it's just another way of saying it's **connected to the Internet**.

**The physical reality:**

> **The Internet is a global network of _physical cables_** — copper telephone wires, TV cables, and fiber optic cables.

Even **wireless** connections like **Wi-Fi** and **3G/4G** rely on these physical cables to access the Internet. The "wireless" part is only the last hop from the device to the router; the backbone is physical.

**Beginner framing:** the Internet is the _plumbing_. It carries everything, regardless of what's flowing through it.

**Intermediate framing:** the Internet is a **packet-switched network**. Data is broken into packets, routed independently across many possible paths, and reassembled at the destination. The physical cables are the _medium_; the routing is the _system_.

**Junior-dev framing:** think of it as the **transport layer of the world** — analogous to the network layer in a stack diagram. It moves bytes; it doesn't care what those bytes represent.

---

### 5.2 The Web — the content layer

> **The World Wide Web — usually called the Web for short — is a collection of different websites you can access through the Internet.**

- A **website** is made up of **related text, images, and other resources**.
- Websites can **resemble other forms of media** — like newspaper articles or television programs — or they can be **interactive** in a way that's unique to computers.

**Purpose can be almost anything:**

- a news platform,
- an advertisement,
- an online library,
- a forum for sharing images,
- an educational site.

**The relationship to the Internet:**

> **The Web runs _on top of_ the Internet.**
> The Internet provides the connection; the Web provides the content and the protocols to access it.

**Beginner framing:** the Web is _what you see and interact with_ when you open a browser. The Internet is what _delivers_ it to you.

**Intermediate framing:** the Web is one **application** of the Internet — specifically, one built on **HTTP/HTTPS**, **URLs**, and **HTML**. Other applications (email via SMTP, file transfer via FTP, video calls via WebRTC) are also built on the Internet but are _not_ the Web.

**Junior-dev framing:** the Web is the layer of protocols and content formats (`http://`, `https://`, HTML, CSS, JS) that your browser speaks. When you build a web app, you're building _for_ the Web, _on top of_ the Internet.

---

### 5.3 The web browser — not the Internet

> **Once you are connected to the Internet, you can access and view websites using a type of application called a _web browser_.**

**Crucial distinction:**

> **The web browser itself is not the Internet. It only _displays_ websites that are stored on the Internet.**

**Think of it this way:**

|                              | **The Internet**                         | **The Web browser**                             |
| ---------------------------- | ---------------------------------------- | ----------------------------------------------- |
| **What it is**               | Infrastructure (network)                 | Software (an application)                       |
| **Role**                     | Carries data between computers           | Requests, receives, and renders web pages       |
| **Examples**                 | ISP network, cables, routers             | Chrome, Firefox, Safari, Edge                   |
| **Fails without the other?** | No — the Internet works without browsers | Yes — a browser is useless without a connection |

**The rule:** a browser without the Internet is like a car without roads. A connection without a browser still lets you use other Internet services (email, chat).

---

### 5.4 How the Internet works — the request cycle

> **When you visit a website, your computer sends a request over these wires to a server.**

**The two participants:**

- **Your computer** (the _client_) — asks for something.
- **The server** — where websites are stored. It works a lot like your computer's hard drive.

**The cycle:**

1. **You type a URL** or click a link.
2. **Your computer sends a request** over the physical cables.
3. **The request arrives at a server.**
4. **The server retrieves the website** (files, data, resources).
5. **The server sends the correct data back** to your computer.
6. **Your browser renders it** on screen.

> **What's amazing is that this all happens in just a few seconds.**

**Beginner framing:** you ask for a page; a server on the other side of the world fetches it and sends it back.

**Intermediate framing:** in reality this is a whole stack: **DNS** resolves the domain to an IP address, **TCP** establishes a connection, **HTTP** carries the request and response, and **TLS** encrypts it if it's HTTPS. You'll go deeper on each in later skills.

**Junior-dev framing:** the "server" is just a computer running a program that listens for requests and responds. When you build a backend later, _you_ are writing that program.

---

### 5.5 What you can do on the Internet (beyond the Web)

The Internet is much bigger than the Web. Common uses:

| Use                     | What it is                                                  | Example                    |
| ----------------------- | ----------------------------------------------------------- | -------------------------- |
| **Finding information** | Search engines look up relevant websites by keyword         | Google, Bing, Yahoo!       |
| **Email**               | Electronic mail — send/receive messages across the Internet | Gmail, Outlook             |
| **Social networking**   | Connect and share with many people at once                  | Facebook, Instagram        |
| **Chat / IM**           | Real-time short messages                                    | WhatsApp, Slack            |
| **Online media**        | Streaming video and audio                                   | YouTube, Netflix, Spotify  |
| **Everyday tasks**      | Banking, bills, shopping — convenience from home            | Online banking, e-commerce |

**Key insight:** most of these _use_ the Internet, but **not all use the Web**. Email and chat are Internet services that aren't _web pages_ — though modern email and chat often _have_ web interfaces. The underlying protocols differ.

**What a web developer should take away:**

> **The Web is the largest and most visible part of the Internet, but not the only part.**
> When you build a web app, you're writing software that speaks web protocols; when you interact with other Internet services (SMTP, WebSocket, etc.), you're reaching beyond the Web layer.

---

## 6. Worked Example — following a request from click to page

> **Scenario:** you type `https://example.com` into your browser and press Enter.

**Step-by-step:**

1. **You're online** — your device is connected to the Internet (Wi-Fi → router → physical cable → ISP).
2. **Your browser parses the URL** — protocol `https`, host `example.com`, path `/`.
3. **DNS resolves `example.com`** to an IP address (e.g., `93.184.216.34`).
4. **Your computer opens a TCP connection** to that IP, and **TLS encrypts it** (because of `https`).
5. **Your browser sends an HTTP GET request** over that connection.
6. **The request travels across physical cables**, through routers, to the server at that IP.
7. **The server** (a computer running a web server program) **retrieves the HTML** for the homepage.
8. **The server sends the response back** — HTML, then more requests for CSS, JS, and images.
9. **Your browser renders the page** — parsing HTML, applying CSS, running JS.

**Total elapsed time:** typically **under a second** for a well-optimized site, a few seconds at worst.

**What this example teaches:**

- **The Internet moved the bytes; the Web defined what they meant.**
- **Multiple layers cooperate** — DNS, TCP, TLS, HTTP, HTML — each doing its part.
- **The "server" is just a computer** listening for requests. Nothing magic about it.
- **The browser is doing a lot of work** — but it's still not "the Internet."

---

## 7. Common Pitfalls

- ❌ **Using "Internet" and "Web" interchangeably.** They're related but distinct. Precision matters in debugging and design.
- ❌ **Thinking the browser _is_ the Internet.** It's an application that uses the Internet.
- ❌ **Forgetting the physical layer.** "The cloud" is still cables, routers, and data centers. Wi-Fi is the last hop, not the whole path.
- ❌ **Assuming all Internet use is Web use.** Email, chat, file transfer, video calls — all Internet, not all Web.
- ❌ **Believing the Web is the only thing on the Internet.** It's the biggest visible surface, but far from the only service.
- ❌ **Skipping the request cycle.** Understanding it now makes HTTP, DNS, and backend work make sense later.

---

## 8. Hands-On Exercises

1. **Internet vs. Web, in your own words (10 min).** Write a two-sentence explanation of each, then one sentence on how they relate. Share it with someone non-technical — did they understand it?
2. **Spot the layers (10 min).** For each activity, say whether it uses **the Internet only**, **the Web only**, or **both**:
   (a) sending an email, (b) browsing a news site, (c) a WhatsApp message, (d) watching Netflix, (e) a video call in Zoom, (f) a Google search.
   _Hint: some are trickier than they look._
3. **Trace a request (15 min).** Open your browser's **DevTools → Network tab**, load any website, and observe:
   - how many requests fire,
   - which are HTML, CSS, JS, images,
   - how long the whole page took.
     Write down what you see.
4. **Physical layer hunt (10 min).** Find one physical cable connected to your device or router. What type is it? Trace (as best you can) how your connection leaves your home.
5. **The "browser is not the Internet" test (10 min).** Close your browser. Can you still use the Internet? List three things you can do without a browser.

---

## 9. Checkpoint Questions

1. In one sentence, what is the **Internet**?
2. In one sentence, what is the **Web**?
3. How are they related — which one runs on top of which?
4. What is a **server**, and where are websites stored?
5. Why is the **web browser not the Internet**? Give one example of something you can do on the Internet without a browser.
6. What physical medium carries most of the Internet's traffic?
7. Name three things you can do on the Internet that are **not** the Web.

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
