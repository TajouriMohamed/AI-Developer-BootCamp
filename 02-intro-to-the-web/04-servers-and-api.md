# Skill 4 — Servers and API

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--a-rest-api-in-action)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

**API** is the acronym for **Application Programming Interface**.

> **It is a software intermediary that allows two applications to speak to each other.**
> **An API is a set of programming code that enables data transmission between one software product and another. It also contains the terms of this data exchange.**

Whenever you use an application like Facebook, send an instant message, or check the weather on your phone, **you're using an API.**

This skill covers three things:

1. **What APIs are** and why they matter.
2. **REST** — the most popular architecture for web APIs, and its rules.
3. **HTTP methods** — the verbs that make REST work.

---

## 2. Why It Matters (for you, as a developer)

- **APIs are the connective tissue of modern software.** Every frontend you build talks to a backend via an API. Every third-party service you integrate (payments, maps, AI models) is reached through an API.
- **REST is the default architecture for web APIs.** Knowing its constraints means you can design APIs that are predictable, scalable, and easy for others to use.
- **HTTP methods are your verbs — in full.** You saw the four common ones in Skill 3; here you'll see the complete set, plus the distinctions (`PUT` vs `PATCH`, `GET` vs `HEAD`) that matter in real APIs.
- **AI development is API-driven.** The LLM integrations later in the bootcamp are all API calls — knowing how APIs are designed and consumed is directly transferable.

---

## 3. Prerequisites

- Skill 2 (Web architecture — clients and servers).
- Skill 3 (Internet protocols — HTTP and the four common methods).

---

## 4. Key Concepts

1. **API = Application Programming Interface** — a **software intermediary** that lets two applications speak.
2. It's a **set of programming code** that enables **data transmission** between software, with **terms of exchange**.
3. **APIs simplify and speed up development** — they exist to be reused.
4. **Advantages:** automation, application access, more scope, unlimited data access, efficiency, integration, personalization, adaptation.
5. **REST** (Representational State Transfer) is a popular **web API architecture** with **architectural constraints**.
6. **Four REST constraints:** client-server, statelessness, cacheability, layered system.
7. **REST uses HTTP's original instructions** — with five rules (URL = resource, verbs = operations, responses = representations, links = relationships, parameters = auth).
8. **HTTP methods (verbs):** GET, HEAD, POST, PUT, DELETE, CONNECT, OPTIONS, TRACE, PATCH.

---

## 5. Concepts Explained

### 5.1 What an API is

> **API is the acronym for Application Programming Interface.**
> **It is a software intermediary that allows two applications to speak to each other.**
> **An API is a set of programming code that enables data transmission between one software product and another. It also contains the terms of this data exchange.**

Two ways to think about it:

- **As a contract** — the API defines _what_ one application can ask of another, and _what it will get back_.
- **As a translator** — the two applications don't need to know each other's internals; they only need to speak the API's language.

**APIs serve numerous purposes. Generally, they can simplify and speed up software development.**

**You use them constantly:**

- Opening Facebook → the app calls an API to fetch your feed.
- Sending an instant message → the app calls an API to deliver it.
- Checking the weather → the app calls a weather API to get the forecast.

> **You don't see the API, but you interact with its results every time you use an app.**

**Beginner framing:** an API is a _menu_ at a restaurant. You don't go into the kitchen and cook; you order from the menu, and the kitchen delivers. The menu is the contract.

**Intermediate framing:** an API is an **abstraction boundary**. It hides implementation details behind a stable interface, so the provider can change internals without breaking consumers. This is the same principle as functions, modules, or classes — applied _across_ applications.

**Junior-dev framing:** you'll consume APIs constantly (`fetch`, `axios`, SDK libraries). You'll also _build_ them — every FastAPI route you write later in the bootcamp is an API endpoint. An API is the interface between your backend and the world.

---

### 5.2 The advantages of APIs

> **"There is no information exchange without an API. There is no digital transformation without an API. The Open API is the real revolution!"**
> — Bertrand Lafforgue, Microsoft Commercial Data Platform Director

The listed advantages:

| Advantage                    | What it means                                                                                                                                              |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Automation**               | With APIs, **computers rather than people manage the work.** Agencies can update workflows to be faster and more productive.                               |
| **Application**              | APIs can access **application components**. The delivery of services and information is more flexible.                                                     |
| **More scope**               | An **application layer** can be created to distribute information and services to new users. APIs can be **customized** for personalized experiences.      |
| **Unlimited access to data** | An API allows **all public information** generated by government for general use to be accessible to all citizens without exclusivity.                     |
| **Efficiency**               | When access is provided to an API, **generated content can be published automatically** and is available for each channel. Easier to share and distribute. |
| **Integration**              | APIs make it easier to **embed content from any site or application** — smoother information flow, integrated user experience.                             |
| **Personalization**          | Any user or company can **personalize the content and services** they use most.                                                                            |
| **Adaptation**               | Needs evolve and APIs **anticipate changes**. Data transfer is easily supported and information is examined more closely.                                  |

**The summary line:**

> **Basically, APIs are developer-friendly, easily accessible, and incredibly flexible.**

**The bigger picture:** APIs turn software from a **closed product** into an **open platform**. Once an API exists, _other_ developers can build things you didn't imagine — which is why APIs are often described as _the_ enabling technology of modern software.

---

### 5.3 REST API — the most popular web API architecture

> **REST (Representational State Transfer) is a very popular web API architecture.**
> **A REST API is an API that must have certain architectural constraints or principles.**

**The four constraints:**

| Constraint                     | What it means                                                                                                       | Why it matters                                                        |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Client-server architecture** | The interface is **separated from the backend and data storage**.                                                   | Allows flexibility; different components can **evolve independently** |
| **Statelessness**              | **No client context is stored on the server between requests.**                                                     | Servers can scale horizontally; each request carries what it needs    |
| **Cacheability**               | Clients can **cache responses** — so a REST API response must **explicitly state whether it can be cached** or not. | Improves performance and reduces server load                          |
| **Layered system**             | The API works **whether communicating directly with a server or through an intermediary** (e.g., a load balancer).  | Enables proxies, gateways, CDNs, and other infrastructure layers      |

**The key sentence:**

> **The REST architecture uses the original instructions of the HTTP protocol.**

In other words: REST doesn't invent a new protocol — it **uses HTTP's existing verbs, URLs, and responses** in a disciplined way.

---

### 5.4 The five REST rules

> **Rule #1: The URL must operate as a resource identifier.**
> **Rule #2: HTTP verbs must function as the identifiers of operations.**
> **Rule #3: HTTP responses must operate as representations of resources.**
> **Rule #4: Links are like a relationship between resources.**
> **Rule #5: A parameter, like an authentication token, must exist.**

**In plain terms:**

| Rule                             | Meaning                                                                            | Example                                                 |
| -------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------- |
| **1. URL = resource**            | URLs name _things_, not actions                                                    | `/users/42` (the user), not `/getUser?id=42`            |
| **2. Verbs = operations**        | The HTTP method says _what to do_ with the resource                                | `GET /users/42` (read), `DELETE /users/42` (remove)     |
| **3. Response = representation** | The server responds with a _representation_ of the resource — usually JSON or HTML | `GET /users/42` → `{"id": 42, "name": "..."}`           |
| **4. Links = relationships**     | Resources can _link to_ other resources                                            | A user might include `"orders_url": "/users/42/orders"` |
| **5. Parameters = auth context** | Requests carry context — like an **authentication token**                          | `Authorization: Bearer <token>`                         |

**The unifying principle:**

> **REST is about _nouns_ (URLs) and _verbs_ (methods).** Resources are named; actions are the methods applied to them.

**Beginner framing:** in REST, a URL is like a file path to a _thing_. The method says what to do with that thing. `/users/42` is "user #42"; `GET` says "show it to me"; `DELETE` says "remove it."

**Intermediate framing:** REST is **a design style**, not a standard. An API can be "RESTful" without being perfectly REST — many real APIs are "REST-ish." The five rules are the guiding principles; strict adherence varies.

---

### 5.5 HTTP methods — the full set

> **HTTP methods define a set of query methods that indicate the action we want to perform on the indicated resource.**
> **Although they have names, these methods are often called HTTP verbs.**
> **Each implements a different semantic, but some common functionalities can be shared by different methods.**

| Method      | What it does                                                                                                               |
| ----------- | -------------------------------------------------------------------------------------------------------------------------- |
| **GET**     | Requests a **representation of the indicated resource**. Should only be used to **retrieve data**.                         |
| **HEAD**    | Requests a response **identical to GET but with the body omitted** — you only get the **headers**.                         |
| **POST**    | **Sends an entity** to the indicated resource. Usually results in a **change of state** or **side effects** on the server. |
| **PUT**     | **Replaces all current representations** of the resource targeted by the request content.                                  |
| **DELETE**  | **Deletes the specified resource**.                                                                                        |
| **CONNECT** | Builds a **tunnel** to the server identified by the target resource.                                                       |
| **OPTIONS** | Describes the **communication options** with the targeted resource.                                                        |
| **TRACE**   | Performs a **round-trip test message** following the path of the target resource.                                          |
| **PATCH**   | Applies **partial modifications** to a resource.                                                                           |

**The two pairs worth memorizing:**

- **`GET` vs `HEAD`** — same request, but `HEAD` omits the body. Useful for checking if a resource exists or has changed without downloading it. (`GET` = "give me the data"; `HEAD` = "tell me about the data, don't send it.")
- **`PUT` vs `PATCH`** — `PUT` **replaces** the whole resource; `PATCH` **modifies** part of it. (`PUT` = "here's the new version, replace it"; `PATCH` = "here's the change, apply it.")

**The less common ones (you'll rarely write them by hand, but tools use them):**

- **`CONNECT`** — used for HTTPS tunneling through proxies.
- **`OPTIONS`** — used in **CORS preflight** requests (the browser asks "can I make this cross-origin request?").
- **`TRACE`** — diagnostic; echoes the request back. Often disabled in production for security reasons.

**Beginner framing:** HTTP methods are _verbs_ — what you want the server to _do_ with a resource.

**Intermediate framing:** the method matters for **semantics and caching**. `GET` is cacheable; `POST` is not (by default). `OPTIONS` triggers preflight in CORS. Choosing the right verb shapes how the whole system behaves.

**Junior-dev framing:** in a framework like FastAPI, each method is a decorator — `@app.get`, `@app.post`, `@app.put`, `@app.delete`. Using the wrong verb on a route doesn't just look sloppy — it can break clients, proxies, and caches downstream.

---

## 6. Worked Example — a REST API in action

> **Scenario:** a mobile app shows a user's profile page with their posts, and lets them delete a post.

**The API endpoints (RESTful design):**

| Action                       | Method   | URL               | What happens                                         |
| ---------------------------- | -------- | ----------------- | ---------------------------------------------------- |
| **Load profile**             | `GET`    | `/users/42`       | Server returns user #42's representation             |
| **Load posts**               | `GET`    | `/users/42/posts` | Server returns a list of posts by user #42           |
| **Delete a post**            | `DELETE` | `/posts/7`        | Server deletes post #7                               |
| **Update profile**           | `PUT`    | `/users/42`       | Server replaces user #42 with the new representation |
| **Update profile partially** | `PATCH`  | `/users/42`       | Server updates only the provided fields              |

**How REST's rules apply at each step:**

1. **URL = resource** (`/users/42`, `/posts/7`) — URLs are _nouns_, not actions.
2. **Verbs = operations** (`GET`, `PUT`, `PATCH`, `DELETE`) — verbs are how you ask for what you want.
3. **Responses = representations** — the server replies with JSON, HTML, or similar.
4. **Links = relationships** — the profile response might include `"posts_url": "/users/42/posts"`.
5. **Parameters = auth** — the request includes an `Authorization` header.

**The statelessness constraint in action:**

- Each request must carry the auth token.
- The server doesn't remember the previous request.
- If a `DELETE` fails, the client retries with the same token — no "session" needed.

**What this example teaches:**

- **REST makes APIs predictable.** Once you know the pattern (URL = resource, method = action), you can guess the endpoint for any operation.
- **The verbs carry meaning.** `PUT` replaces; `PATCH` modifies; `DELETE` removes. The client and server agree on the meaning without extra negotiation.
- **The rules aren't arbitrary.** They allow caching, scaling, and clear contracts — which is _why_ REST became the dominant style.

---

## 7. Common Pitfalls

- ❌ **Thinking REST is a protocol.** REST is an _architecture style_ built _on top of_ HTTP. HTTP is the protocol; REST is how you use it.
- ❌ **Putting actions in URLs.** `/deleteUser?id=42` is RPC-style, not REST. The right REST form: `DELETE /users/42`.
- ❌ **Using `POST` for everything.** `GET` retrieves, `POST` creates, `PUT` replaces, `PATCH` modifies, `DELETE` removes. Using the right verb is part of the API's contract.
- ❌ **Confusing `PUT` and `PATCH`.** `PUT` _replaces_ the whole resource; `PATCH` _modifies_ part of it. Mixing them up causes silent data loss.
- ❌ **Assuming REST is required.** It's not — GraphQL, gRPC, and RPC-style APIs are also valid. REST is _popular_, not mandatory.
- ❌ **Forgetting statelessness.** With REST, each request must carry what it needs. Sessions break the statelessness constraint.
- ❌ **Ignoring cacheability.** `GET` responses are cacheable by default; the API must _explicitly_ state cache policy. Without it, caching silently fails or misbehaves.

---

## 8. Hands-On Exercises

1. **Identify the API (10 min).** For each app you use today, name one API it likely calls. Example: _weather app → weather API_. Aim for three apps and three APIs.
2. **REST vs. RPC (10 min).** Convert each RPC-style URL into a REST-style one:
   - `POST /createUser` → ?
   - `GET /getPost?id=7` → ?
   - `POST /deleteComment/42` → ?
3. **The right verb (15 min).** For each operation, pick the right HTTP verb and justify in one sentence:
   - (a) fetch a user's list of orders,
   - (b) update a user's email address (only that field),
   - (c) replace an entire user profile,
   - (d) delete a comment,
   - (e) check whether a resource exists without downloading it.
4. **`PUT` vs `PATCH` in practice (15 min).** Design two `curl` commands for updating `user/42`:
   - one that **replaces** the entire resource,
   - one that **updates just the email field**.
     Which method did you use for each, and why?
5. **Design a small API (20 min).** For a simple to-do app, list:
   - the resources (URLs),
   - the methods for each operation,
   - one example response for each endpoint.

---

## 9. Checkpoint Questions

1. What does **API** stand for, and what is it in one sentence?
2. Name **three advantages** APIs provide, and briefly explain each.
3. What does **REST** stand for, and what is it?
4. Name the **four REST constraints** and briefly explain each.
5. What are the **five REST rules**? (You don't need to memorize the exact wording — explain the idea of each.)
6. Name all **nine HTTP methods** from this skill.
7. What is the difference between **`PUT` and `PATCH`**?
8. What is the difference between **`GET` and `HEAD`**?
9. Why does REST insist on **statelessness**, and what does that mean for how the client makes requests?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
