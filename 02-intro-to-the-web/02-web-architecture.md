# Skill 2 — Web Architecture

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--a-request-end-to-end)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

The Web can be summarized as **a series of interactions between two types of systems: clients and servers.**

- **Clients** — the user's devices that **request and render** web content.
- **Servers** — the programs or systems that **deliver** data, resources, or services.

Everything on the Web — every page you load, every image you see, every API your code calls — is the result of one of these two roles talking to the other. Understanding them is the foundation for everything that follows: HTML, CSS, JavaScript, HTTP, backends, APIs.

---

## 2. Why It Matters (for you, as a developer)

- **Every web app you build is a client-server system.** Frontend code runs on the client; backend code runs on the server. Knowing the roles tells you _where_ each piece of code belongs.
- **It shapes every architectural decision.** What runs in the browser vs. what runs on the server, what's public vs. what's private, what scales where — all of it follows from the client-server split.
- **It explains security boundaries.** Some code and data live on the client (visible to the user); some live on the server (hidden). Confusing the two is a classic source of bugs and vulnerabilities.
- **It's the mental model for the rest of the bootcamp.** HTTP, APIs, FastAPI, deployment — all of it assumes you know what a client and a server are.

---

## 3. Prerequisites

- Skill 1 (the Internet vs. the Web — you need the "infrastructure vs. content" distinction).

---

## 4. Key Concepts

1. **The Web is a series of interactions between clients and servers.**
2. **Clients request and render; servers deliver.**
3. **Clients are not connected directly to the Internet** — they connect through their **ISP** (Internet Service Provider).
4. **Clients are diverse:** browsers, mobile apps, TVs, and more — and their number is growing rapidly.
5. **Servers run on special hardware** with network equipment and dedicated network access.
6. **Servers are connected directly to the Internet**, and the **web pages (content) are stored on that server's hard drive**.
7. **There are different types of servers** — web servers, mail servers, virtual servers — each specialized for specific types of data or processing.

---

## 5. Concepts Explained

### 5.1 Clients — the request-and-render side

> **Clients are the user's devices that request and render web content.**

**Examples of clients:**

- **Browsers** — Chrome, Firefox, Safari, Edge.
- **Mobile applications** — apps on iOS and Android that talk to web services.
- **TVs** — smart TVs and streaming devices.
- **Anything else that can make HTTP requests** — watches, cars, IoT devices, game consoles.

**Two key facts:**

> **1. Clients are not connected directly to the Internet.**
> **2. Clients are connected to the Internet through their ISP (Internet Service Provider).**

**Why this matters:**

- Your client's connection quality depends on your ISP.
- Your ISP sits between you and the server — relevant for privacy, censorship, and speed.
- When a web app "doesn't work," it's worth asking: is it the client, the ISP, or the server?

**Beginner framing:** a client is whatever _you_ are using to view the Web. It asks for content and shows it to you.

**Intermediate framing:** a client is any software that speaks **HTTP** (and, for dynamic apps, **WebSocket** or other protocols). The _type_ of client determines what rendering capabilities are available — a browser renders HTML/CSS/JS; a mobile app renders native views and may just consume JSON.

**Junior-dev framing:** your **frontend code runs on the client**. That means the user can see it, modify it, and — in security terms — _you should assume they will_. Never put secrets or trust-critical logic in client code.

---

### 5.2 Servers — the delivery side

> **Servers are programs or systems that run on a special computer** — with special hardware like network equipment and dedicated network access.

**Their job:**

> **Deliver data, resources, or services to other computers — clients — over a network.**

**Key facts:**

- **Servers are connected directly to the Internet.** Unlike clients, they don't go through a consumer ISP in the same way — they typically have dedicated network infrastructure in data centers.
- **The web pages (content) are stored on the server's hard drive.**

**Types of servers (examples):**

| Type                | What it does                                                                   |
| ------------------- | ------------------------------------------------------------------------------ |
| **Web servers**     | Serve web pages and HTTP APIs (e.g., Nginx, Apache, Node.js processes)         |
| **Mail servers**    | Handle sending, receiving, and storing email (SMTP/IMAP/POP3)                  |
| **Virtual servers** | Software-defined servers running on shared physical hardware (e.g., cloud VMs) |

**The common thread:**

> **These specialize in specific types of data or specific processing capabilities. They're all involved in providing the content that you request or the services that you need to perform.**

**Beginner framing:** a server is a computer that's _always on_, _always connected_, and _waiting_ for requests. When a request arrives, it sends back the right content.

**Intermediate framing:** a "server" is a **role**, not a specific piece of hardware. Any computer running a listening process can act as a server. In practice, production servers live in **data centers**, with redundancy, load balancing, and monitoring around them.

**Junior-dev framing:** your **backend code runs on the server**. That's where secrets live, where authentication happens, where the database is queried — and where you can trust things the client can't see.

---

### 5.3 Clients vs. servers — side by side

|                         | **Client**                                            | **Server**                                  |
| ----------------------- | ----------------------------------------------------- | ------------------------------------------- |
| **Role**                | Requests and renders content                          | Delivers content and services               |
| **Examples**            | Browser, mobile app, TV, IoT device                   | Web server, mail server, virtual server     |
| **Connection**          | Through an **ISP**                                    | **Directly** to the Internet                |
| **Where content lives** | Nowhere — it's fetched and rendered                   | On the **server's hard drive**              |
| **Hardware**            | Ordinary user devices                                 | Specialized hardware in data centers        |
| **Trust boundary**      | **Untrusted** — assume the user can see and modify it | **Trusted** — you control what's exposed    |
| **What runs here**      | Frontend code (HTML/CSS/JS, mobile apps)              | Backend code (APIs, databases, auth, logic) |

**The trust distinction is the one to internalize.** A client is _by definition_ under someone else's control. A server is under yours. This split governs how you design security, where secrets live, and which logic can be trusted.

---

### 5.4 What this implies for architecture

Once you see the client-server split, several things follow naturally:

1. **Content has to be stored somewhere** — on the server — and fetched by the client.
2. **Some logic runs on the client, some on the server** — the boundary is a _design decision_, not an accident.
3. **The client can't be trusted** — anything security-sensitive (API keys, password checks, business rules that matter) must live on the server.
4. **The server can be trusted _because you control it_** — but only the parts you actually control (your code, your database, your config).
5. **The ISP sits between them** — a real-world third party that affects speed, privacy, and reliability.

These five facts are the bedrock of every web app you'll build for the rest of your career.

---

## 6. Worked Example — a request, end to end

> **Scenario:** a user opens `https://example.com` in a mobile browser on a phone connected to Wi-Fi.

**Step-by-step, with the client-server split clear at every stage:**

1. **The phone (client)** is connected to Wi-Fi → router → **ISP** → the Internet.
2. **The browser** (a client program on the phone) parses the URL and prepares an HTTP request.
3. **The request leaves the phone**, travels through the ISP, and reaches the **server** at `example.com`.
4. **The server program** — running on dedicated hardware in a data center — receives the request.
5. **The server retrieves the HTML** from its hard drive (or generates it dynamically).
6. **The server sends the response back** — HTML, then CSS, JS, images, each fetched the same way.
7. **The browser on the phone renders the page** — the client's job is now _rendering_.
8. **Any JavaScript** in the page runs **on the client** — and is now visible to the user.
9. **Any API calls** the page makes go _back_ to the server for data.

**What this example teaches:**

- **The client does two things:** _requests_ content, then _renders_ it.
- **The server does one thing:** _delivers_ content and services.
- **The ISP is in the middle** — never forget it's there.
- **Some things (JS, HTML) are visible on the client** — assume the user can read them.
- **Other things (database, secrets, business rules) live only on the server** — and are safe _because_ the client can't see them.

---

## 7. Common Pitfalls

- ❌ **Thinking clients connect directly to the Internet.** They connect **through their ISP** — that's a meaningful middle layer.
- ❌ **Assuming "client" means "browser."** Mobile apps, TVs, watches, and APIs are clients too.
- ❌ **Treating the client as trustworthy.** The user can see and modify everything the client does. **Never put secrets in client code.**
- ❌ **Assuming "server" means "one physical computer."** A server is a _role_ — and modern apps typically use many servers behind a load balancer.
- ❌ **Forgetting that content lives on the server's hard drive.** If it's not stored there (or reachable from there), the client can't fetch it.
- ❌ **Ignoring the ISP layer.** Slow or blocked connections are often an ISP problem, not a client or server problem.
- ❌ **Confusing server _types_.** A web server, a mail server, and a virtual server are all servers, but they do different things.

---

## 8. Hands-On Exercises

1. **Identify the clients (10 min).** List every device in your home that can access web content. For each, say whether it's a browser, an app, or something else.
2. **ISP check (10 min).** Find out who your ISP is. Can you name one thing your ISP affects (speed, privacy, content availability)?
3. **Where does the code run? (15 min).** For each piece of logic, say whether it runs on the **client**, the **server**, or **both**:
   - (a) rendering a button's hover effect,
   - (b) checking a user's password,
   - (c) storing user preferences in a database,
   - (d) validating a form field before submission,
   - (e) enforcing "only admins can delete users."
4. **Trace one request (15 min).** Open DevTools → Network, load any website, and pick **one** request. Note:
   - which side made the request (client),
   - which side responded (server),
   - how long it took.
5. **Server types (10 min).** For each type, give one example service you use that relies on it: **web server**, **mail server**, **virtual server** (hint: cloud VMs).

---

## 9. Checkpoint Questions

1. In one sentence, what are the two types of systems the Web is built from?
2. What does a **client** do? Name three examples.
3. What does a **server** do? What is stored on a server's hard drive?
4. How are clients connected to the Internet — directly, or through something? Name it.
5. How are servers connected to the Internet — directly, or through something?
6. Why is the **trust boundary** between client and server important for security?
7. Name three types of servers and what each specializes in.

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
