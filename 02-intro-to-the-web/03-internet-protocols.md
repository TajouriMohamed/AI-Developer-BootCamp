# Skill 3 — Internet Protocols

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--a-url-becomes-an-http-request)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

Two ideas sit at the heart of this skill:

- **Network protocols** — the **rules** that let devices exchange data at all.
- **HTTP** — the **specific protocol** the Web is built on, which defines how messages are formatted and transmitted.

The analogy that makes it click:

> **Speaking the same language simplifies communication between two people.**
> **Network protocols make it possible for devices to interact because of predetermined rules built into their software and hardware.**

Without protocols, two connected computers would be like two people shouting in different languages: the _connection_ exists, but no _communication_ happens.

---

## 2. Why It Matters (for you, as a developer)

- **Every web request you write is an HTTP request.** Fetch, forms, APIs, image loads, AJAX, GraphQL — all of it rides on HTTP.
- **HTTP methods are your verbs.** `GET`, `POST`, `PUT`, `DELETE` are the vocabulary you'll use every day — and choosing the right one is part of designing a clean API.
- **It explains what your tools are doing.** When you see a `404` or a `500` in DevTools, you're reading an HTTP response. When you call `fetch()`, you're making an HTTP request.
- **It's the layer everything else sits on.** The client-server model from Skill 2 becomes _concrete_ once you understand the protocol that connects them.

---

## 3. Prerequisites

- Skill 1 (Internet vs. Web).
- Skill 2 (Web architecture — clients and servers).

---

## 4. Key Concepts

1. **Network protocols are rules, conventions, and data structures** that dictate how devices exchange data.
2. Protocols control **all aspects** of communication: sending, receiving, formatting, addressing, error-checking.
3. **A protocol specifies** (at minimum):
   - the **format of data packets**,
   - the **addressing system**,
   - the **error-checking procedures**.
4. **HTTP = HyperText Transfer Protocol** — the underlying protocol of the Web.
5. HTTP defines **how messages are formatted and transmitted**, and **what actions servers and browsers should take** in response to commands.
6. HTTP **request methods** pick the desired action — the most common are **GET, POST, PUT, DELETE**.

---

## 5. Concepts Explained

### 5.1 Network protocols — the rules of the road

> **Network protocols are a set of rules, conventions, and data structures that dictate how devices exchange data across networks.**

**What they control:**

> **All aspects of network communication** — from sending and receiving messages, to formatting files for different types of messages.

**The language analogy:**

> **Just as speaking the same language simplifies communication between two people, network protocols make it possible for devices to interact — because of predetermined rules built into devices' software and hardware.**

**What a protocol specifies:**

| Specifies                      | What it means                                                                       |
| ------------------------------ | ----------------------------------------------------------------------------------- |
| **The format of data packets** | How the bytes are structured — headers, payload, terminators                        |
| **The addressing system**      | How devices are identified and reached — IP addresses, ports, domains               |
| **Error-checking procedures**  | How the receiver knows the message arrived intact — checksums, retransmission rules |

**Beginner framing:** a protocol is an _agreement_. Both sides know the rules in advance, so they can talk without negotiating every time.

**Intermediate framing:** protocols **layer**. TCP handles reliable delivery; IP handles addressing and routing; HTTP handles application-level requests and responses. Each layer assumes the one below it works. This is why it's called the "protocol stack."

**Junior-dev framing:** you don't usually implement protocols — you _use_ them. Your HTTP client library, your web framework, and your browser already speak the protocols. Your job is to know what they promise so you can build on top of them.

**Examples of protocols you'll encounter (briefly):**

| Protocol         | What it does                                   |
| ---------------- | ---------------------------------------------- |
| **HTTP / HTTPS** | Web content — the subject of this skill        |
| **TCP**          | Reliable, ordered delivery of bytes            |
| **IP**           | Addressing and routing across networks         |
| **DNS**          | Resolving human-readable names to IP addresses |
| **TLS**          | Encryption for HTTPS, email, and more          |
| **SMTP / IMAP**  | Email sending and retrieval                    |
| **WebSocket**    | Persistent bidirectional connections           |

You don't need to know all of these yet. You just need to know **HTTP is one protocol among many**, built on top of others.

---

### 5.2 HTTP — the protocol of the Web

> **HTTP stands for HyperText Transfer Protocol. HTTP is the underlying protocol used by the Web.**
> **This protocol defines how messages are formatted and transmitted.**
> **It also determines what actions web servers and browsers should take in response to various commands.**

**The classic example:**

> **When you enter a URL in your browser, this sends an HTTP command to the web server asking it to fetch and transmit the requested web page.**

So the _whole_ Web — every page, every asset, every API call — is a conversation conducted in HTTP.

**HTTP is a request-response protocol.**

- The **client** (browser, app, `fetch()` in code) sends a **request**.
- The **server** receives it, does something, and sends back a **response**.

**Both requests and responses have a defined shape:**

- **Request:** method + URL + headers + (optional) body.
- **Response:** status code + headers + (optional) body.

You'll explore the exact shapes in later skills. For now: **HTTP is the format the conversation takes**.

**Beginner framing:** HTTP is the language browsers and servers speak. You write a URL; your browser translates that into an HTTP request; the server answers in HTTP.

**Intermediate framing:** HTTP is **stateless** — each request is independent. That statelessness is what allows servers to scale horizontally, and it's why sessions, cookies, and tokens exist: they carry state _across_ requests. (You'll meet this in backend skills.)

**Junior-dev framing:** every `fetch()`, every form submission, every page load is an HTTP request. When your API "isn't working," it's almost always an HTTP problem — wrong method, wrong URL, wrong headers, wrong status. Knowing the protocol is how you debug it.

---

### 5.3 HTTP methods — the verbs of the Web

> **The HTTP request contains different types of methods to pick out the desired action from the server.**

**The most common methods:**

| Method     | Purpose                                      | Typical use                                |
| ---------- | -------------------------------------------- | ------------------------------------------ |
| **GET**    | **Retrieve data** from the server            | Loading a page, fetching a list of items   |
| **POST**   | **Submit data** to the server                | Creating a new resource, submitting a form |
| **PUT**    | **Update data** that's already on the server | Replacing an existing resource             |
| **DELETE** | **Delete data** from the server              | Removing a resource                        |

**The pattern to internalize:**

> **GET = read. POST = create. PUT = update. DELETE = remove.**

This is the backbone of **CRUD** (Create, Read, Update, Delete) — the four operations almost every API supports. Once you see the pattern, you'll spot it everywhere.

**A few important conventions:**

- **GET should be safe and idempotent** — calling it should never change server state, and calling it twice should behave the same as calling it once.
- **POST usually creates something new** — calling it twice often creates two resources (which is why double form submissions are a known problem).
- **PUT is idempotent** — calling it twice has the same effect as calling it once.
- **DELETE is idempotent** — deleting something twice leaves it equally deleted.

You'll go deeper on these properties (and on status codes, headers, and body formats) in later skills. For now: **know what each verb _means_.**

**Beginner framing:** the method is _what you're asking the server to do_. "Please read me this page" (GET). "Please save this form" (POST). "Please update this record" (PUT). "Please delete this item" (DELETE).

**Intermediate framing:** the method is part of the _contract_. Servers, proxies, and caches all behave differently based on method — caching `GET` responses is standard; caching `POST` responses is dangerous. Choosing the right verb is part of designing a **predictable API**.

**Junior-dev framing:** in a typical backend framework (FastAPI, Express, Rails), you'll write a **route handler per method**. `@app.get("/items")`, `@app.post("/items")`, `@app.put("/items/{id}")`, `@app.delete("/items/{id}")`. The method _is_ part of your URL's identity.

---

## 6. Worked Example — a URL becomes an HTTP request

> **Scenario:** you type `https://example.com/articles/42` into your browser and press Enter.

**Step-by-step, showing how protocols and HTTP interact:**

1. **The browser parses the URL:** protocol `https`, host `example.com`, path `/articles/42`.
2. **DNS resolves `example.com`** to an IP address — _that's a protocol doing its job._
3. **A TCP connection is opened** to the server — _another protocol._
4. **TLS encrypts the connection** — because the URL says `https` (_another protocol_).
5. **The browser constructs an HTTP request:**

```text
GET /articles/42 HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0 ...
Accept: text/html
```

**The method is GET** — the browser is _asking to read_ a resource.

6. **The request travels** across the Internet to the server.
7. **The server parses the request**, identifies the method (`GET`) and path (`/articles/42`), fetches the article, and builds a response:

```text
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1234

<!DOCTYPE html>...
```

8. **The browser renders the response** — the HTML body.

**What this example teaches:**

- **Protocols stack:** DNS → TCP → TLS → HTTP → HTML, each doing its part.
- **HTTP is the _application-level_ protocol** — the one your browser and server understand as _requests and responses_.
- **The method (GET) is part of the request** — it tells the server _what kind of action_ the client wants.
- **Every request is a conversation with a defined shape** — method, path, headers, body on the way in; status, headers, body on the way out.

---

## 7. Common Pitfalls

- ❌ **Using "protocol" and "format" as synonyms.** A protocol _specifies_ the format; it's not _the same as_ the format.
- ❌ **Thinking HTTP is the only protocol.** DNS, TCP, TLS, SMTP, WebSocket — many protocols coexist in every request.
- ❌ **Confusing "GET" with "browser navigation."** `GET` is also how `fetch()` retrieves JSON from an API. Method ≠ tool.
- ❌ **Using POST when GET would do (or vice versa).** The method is part of the contract — pick it deliberately.
- ❌ **Assuming servers remember requests.** HTTP is stateless; sessions and tokens exist to carry state across requests.
- ❌ **Skipping protocols you don't understand yet.** You don't need to implement them — but you do need to know _what they promise_.

---

## 8. Hands-On Exercises

1. **The four methods (10 min).** For each action, say which HTTP method fits best, and why:

- (a) fetching the list of a user's orders,
- (b) creating a new comment,
- (c) updating a user's profile,
- (d) deleting a task from a to-do list.

2. **Spot the protocol (10 min).** Open DevTools → Network, load any website, and identify:

- which requests are HTTP,
- which are HTTPS,
- how long the DNS lookup took (Chrome shows this in the timing breakdown).

3. **Method semantics (15 min).** Explain in your own words:

- why GET should never change server state,
- why POST is not safe to submit twice,
- why PUT and DELETE are idempotent.

4. **Build a small request (10 min).** In a terminal, run:

```text
curl -X GET https://example.com
```

Then try `curl -I` (heads only) and `curl -v` (verbose). Note the **method** and **status line** in the output. 5. **What does a protocol specify? (10 min).** Write down one example each of:

- the **format** of a data packet,
- the **addressing system**,
- an **error-checking procedure**.
  _Hint: think of IP addresses, port numbers, and checksums._

---

## 9. Checkpoint Questions

1. In one sentence, what is a **network protocol**?
2. Name the **three things** a protocol typically specifies.
3. What does **HTTP** stand for, and what is it used for?
4. In the HTTP request-response model, what does the **client** send, and what does the **server** send back?
5. Name the four most common HTTP methods and what each does.
6. Why is it useful to have **different methods** instead of just one?
7. What does it mean for HTTP to be **stateless**?

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
