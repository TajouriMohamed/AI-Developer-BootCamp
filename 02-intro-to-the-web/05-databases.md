# Skill 5 — Databases

> **Superskill:** Intro to the Web
> **Level:** Beginner → Intermediate → Junior Developer

---

## Table of Contents

1. [Overview](#1-overview)
2. [Why It Matters](#2-why-it-matters-for-you-as-a-developer)
3. [Prerequisites](#3-prerequisites)
4. [Key Concepts](#4-key-concepts)
5. [Concepts Explained](#5-concepts-explained)
6. [Worked Example](#6-worked-example--a-small-student-database)
7. [Common Pitfalls](#7-common-pitfalls)
8. [Hands-On Exercises](#8-hands-on-exercises)
9. [Checkpoint Questions](#9-checkpoint-questions)

---

## 1. Overview

> **Databases are systematic collections of data. They support the storage and manipulation of data. They simplify data management.**

That's the definition. The rest of this skill answers three questions:

1. **Why do we need a database** instead of files or spreadsheets?
2. **What's the difference between SQL and NoSQL** — the two dominant families?
3. **What is a DBMS**, and which ones will you actually use?

The Facebook example makes it concrete: a social platform needs to store, manipulate, and present data — activities, messages, likes, friend networks. **If we stored all this data in files, it would be next to impossible to utilize it.** Databases exist because files don't scale to real applications.

---

## 2. Why It Matters (for you, as a developer)

- **Every non-trivial app has data.** Users, posts, orders, messages, sessions — all of it lives in a database, and how you design that storage shapes everything else.
- **The SQL vs. NoSQL choice is architectural.** It affects schema flexibility, scaling strategy, and which tools make sense later.
- **You'll interact with databases constantly.** Every backend route you write (FastAPI, Express, etc.) will query a database. Every AI app in this bootcamp that stores conversations or documents will too.
- **It's the boundary between your code and persistent state.** Understanding databases means understanding where data lives, how it's shaped, and what guarantees you get.

---

## 3. Prerequisites

- Skill 2 (Web architecture — servers and where content is stored).
- Skill 4 (servers and APIs — the DBMS is what a server talks to).

---

## 4. Key Concepts

1. **Database** = a **systematic collection of data** that supports **storage and manipulation**.
2. **Files don't scale** to real applications — databases exist to make data usable.
3. **Databases are needed** because companies must manage **large volumes** while ensuring **integrity, security, and accuracy**.
4. **Many types exist** — relational, object-oriented, distributed, data warehouses, NoSQL, graph, OLTP — chosen based on purpose.
5. **SQL** = _Structured Query Language_ — the language for talking to relational databases.
6. **NoSQL** = _not only SQL_ — a family of non-relational databases with **flexible schemas**, chosen for **scale, performance, and ease of use**.
7. **The SQL vs. NoSQL distinction** is about **philosophy**: relational vs. non-relational, fixed schema vs. dynamic, vertical vs. horizontal scaling.
8. **A DBMS** (Database Management System) is the software that sits between you and the database — **storing, accessing, protecting, and managing** the data.

---

## 5. Concepts Explained

### 5.1 What a database is

> **Databases are systematic collections of data. Databases support the storage and manipulation of data. Databases simplify data management.**

**The Facebook example:**

A social media platform needs to:

- **store** data — users, posts, messages, likes,
- **manipulate** it — add, edit, delete, link,
- **present** it — to the right person, at the right time,
- **share** it across a network of friends.

> **If we stored all this data in files, it would be next to impossible to utilize it.**

**Why files fail** (at scale):

- **No standard way to query.** You'd write custom parsing code for every operation.
- **No concurrency control.** Two users editing at once would corrupt data.
- **No integrity guarantees.** Broken references, orphaned records, no constraints.
- **No efficient access patterns.** Finding "all posts by user 42 in March" would mean scanning everything.

**Beginner framing:** a database is an **organized store of data** — one designed to be queried, updated, and shared safely.

**Intermediate framing:** a database is a **system** with a **data model** (how records relate), a **query language** (how you ask for things), and **guarantees** (transactions, consistency, durability). Those guarantees are what separate a database from a folder of files.

**Junior-dev framing:** a database is **where your app's state lives**. The server (Skill 2) doesn't hold data in memory between requests — it _queries_ the database. That separation is what lets servers restart, scale horizontally, and stay stateless.

---

### 5.2 Why we need a database

> **Today, companies have to manage large volumes of data while also ensuring data integrity, security, and accuracy.**

**Spreadsheets vs. databases:**

- Spreadsheets are **great tools for calculations and inputting data**.
- But for **substantial amounts of data** — customer records, employee data, business inventory — **a more efficient data management tool is the better option**.

> **In today's digital age, substituting spreadsheets with databases is a sure-fire way for business growth.**

**The trade-off, in a table:**

|                    | **Spreadsheet**                 | **Database**                         |
| ------------------ | ------------------------------- | ------------------------------------ |
| **Best for**       | Small data, ad-hoc calculations | Large data, structured access        |
| **Concurrency**    | Weak — edits conflict           | Strong — multi-user safe             |
| **Integrity**      | Manual                          | Built-in (constraints, transactions) |
| **Query language** | Formulas, limited               | SQL or query API                     |
| **Scalability**    | Limited                         | Designed to scale                    |

**Types of databases:**

| Type                | What it is                                                                |
| ------------------- | ------------------------------------------------------------------------- |
| **Relational**      | Tables with rows and columns; relationships between tables (SQL)          |
| **Object-oriented** | Data stored as objects — models with attributes and behavior              |
| **Distributed**     | Data spread across multiple physical locations                            |
| **Data warehouses** | Optimized for analytics and reporting, not daily transactions             |
| **NoSQL**           | Non-relational — key-value, document, column, graph                       |
| **Graph**           | Optimized for relationships between entities                              |
| **OLTP**            | Online Transaction Processing — fast, high-volume transactional workloads |

> **The best database for a specific organization depends on the organization's purposes, plans, and projects.**

**A brief history** (useful for context):

- **1960s** — network and hierarchical databases.
- **1980s** — object-oriented databases.
- **Today** — the most-used databases are **SQL, NoSQL, and cloud databases**.

---

### 5.3 SQL — the language of relational databases

> **SQL stands for "Structured Query Language."**
> **It's a language that allows communication with databases to properly manage its data.**

**Is SQL a programming language?**

- **Yes, SQL is a language.** It offers **looping, logic directives, variables**, and so on.
- But **it's not a language in the same sense as Java or C++**. It's declarative — you describe _what_ you want, not _how_ to compute it step by step.

> **According to W3Schools: "SQL is a standard language for storing, manipulating and retrieving data in databases."**

**How SQL is used:**

- An application might be programmed in **Python, PHP, or Ruby**.
- **Databases are not designed to recognize these languages** — historically, they recognize only **SQL** (though this has changed significantly in recent years).

**The two concepts unique to database programming:**

1. **Markup** — SQL has its own syntax. A programmer must learn it before using it effectively.
2. **Tables** — a database may be represented as **a number of tables**. Each table has its own **columns and rows** and represents **a set of data**.

**Beginner framing:** SQL is how you _talk_ to a relational database. You write queries; the database answers.

**Intermediate framing:** SQL is **declarative** — you describe the result you want, and the database engine figures out the execution plan. This is different from imperative languages (Python, Java) where you describe the steps.

**Junior-dev framing:** every ORM (SQLAlchemy, Prisma, Sequelize) is a layer _on top of_ SQL. Knowing SQL means you can debug what your ORM generates and write efficient queries when the ORM's defaults are wrong.

---

### 5.4 SQL commands — the common set

> **When working with databases, a programmer might write commands such as:**

| Command               | What it does                           |
| --------------------- | -------------------------------------- |
| **`CREATE DATABASE`** | To create a database                   |
| **`CREATE TABLE`**    | To create tables                       |
| **`SELECT`**          | To find / extract data from a database |
| **`UPDATE`**          | To make adjustments and edit data      |
| **`DELETE`**          | To delete data                         |

> **These are just the most common commands. The more complicated the database is, the more commands you'll need.**

**Beginner framing:** these five commands cover most day-to-day database operations. `CREATE` makes things; `SELECT` reads; `UPDATE` edits; `DELETE` removes.

**Intermediate framing:** those five are the **DDL** (`CREATE`) and **DML** (`SELECT`, `UPDATE`, `DELETE`) core. Real SQL also includes `INSERT` (create rows), `ALTER` (modify schema), `DROP` (remove tables or databases), `JOIN` (combine tables), and more. The five here are the entry point.

**Junior-dev framing:** the CRUD pattern from Skill 4 maps almost directly:

| CRUD       | SQL                                     |
| ---------- | --------------------------------------- |
| **C**reate | `INSERT` (or `CREATE TABLE` for schema) |
| **R**ead   | `SELECT`                                |
| **U**pdate | `UPDATE`                                |
| **D**elete | `DELETE`                                |

---

### 5.5 NoSQL — the flexible alternative

> **NoSQL stands for "not only SQL" — originally referring to non-SQL or non-relational.**
> **It's a database that provides a mechanism for the storage and retrieval of data.**

**The definition, more precisely:**

> **NoSQL is an approach to database design that provides flexible schemas for the storage and retrieval of data beyond the traditional table structures found in relational databases.**

**Why it became popular:**

- While NoSQL databases have existed for many years, they **became more popular in the era of cloud, big data, and high-volume web and mobile applications**.
- They are chosen today for their attributes around **scale, performance, and ease of use**.

**The four common types:**

| Type          | How it stores data                                 |
| ------------- | -------------------------------------------------- |
| **Key-value** | A dictionary — keys map to values                  |
| **Document**  | JSON-like documents (nested structures)            |
| **Column**    | Wide-column stores — rows with many sparse columns |
| **Graph**     | Nodes and edges — optimized for relationships      |

**Beginner framing:** NoSQL databases store data in shapes _other than tables_ — usually documents (JSON-like), key-value pairs, or graphs. You trade strict structure for flexibility and scale.

**Intermediate framing:** NoSQL is a _family_, not a single thing. Each type (document, key-value, column, graph) solves a different problem. "NoSQL" describes what it's _not_, not what it _is_ — which is why "not only SQL" is the more accurate expansion.

---

### 5.6 Examples of NoSQL databases

> **Many NoSQL databases were designed by technology companies like Google, Amazon, Yahoo, and Facebook to provide more effective ways to store content or process data for huge websites.**

| Database             | Type                  | Notable for                                                                                            |
| -------------------- | --------------------- | ------------------------------------------------------------------------------------------------------ |
| **Apache CouchDB**   | Document              | Open-source; JSON documents; **JavaScript as its query language**                                      |
| **Apache Cassandra** | Wide-column           | Open-source; handles **large amounts of data across multiple servers**; clustering across data centers |
| **MongoDB**          | Document              | Open-source; **JSON-like documents** and schema; **the database component of the MERN stack**          |
| **Redis**            | Key-value (in-memory) | **In-memory** store; used for **session caching, message queues**, and other specific applications     |
| **Elasticsearch**    | Document + search     | Document-based database with a **full-text search engine**                                             |

**Beginner framing:** these are the names you'll hear in job postings. You don't need to know them all now — just recognize the families.

**Intermediate framing:** two are especially worth knowing early:

- **MongoDB** — the most common document database, and the "M" in **MERN** (MongoDB, Express, React, Node).
- **Redis** — not usually the _primary_ database, but pervasive as a **cache**, **session store**, and **message queue** (you'll see it in the AI bootcamp for exactly these purposes).

**Junior-dev framing:** in the AI bootcamp specifically, you'll likely encounter **Redis** (caching, sessions) and possibly **a vector database** later for embeddings — both are NoSQL in spirit.

---

### 5.7 SQL vs. NoSQL — the fundamental difference

> **The fundamental difference between SQL and NoSQL is not that complicated. Each has a different philosophy for how data should be stored and retrieved.**

| #     | **SQL**                                                         | **NoSQL**                                               |
| ----- | --------------------------------------------------------------- | ------------------------------------------------------- |
| **1** | **Relational**                                                  | **Non-relational**                                      |
| **2** | Uses **SQL** (Structured Query Language); **predefined schema** | **Dynamic schemas** for **unstructured data**           |
| **3** | **Vertically scalable** (bigger machine)                        | **Horizontally scalable** (more machines)               |
| **4** | **Table-based**                                                 | **Document, key-value, graph, or wide-column**          |
| **5** | Better for **multi-row transactions**                           | Better for **unstructured data** like documents or JSON |

**The five differences in plain terms:**

1. **Relational vs. non-relational** — SQL organizes data into tables with defined relationships; NoSQL doesn't require that structure.
2. **Schema** — SQL requires you to _declare_ the shape of your data upfront (columns, types); NoSQL lets the shape vary row by row or document by document.
3. **Scaling** — SQL scales _up_ (a bigger server); NoSQL scales _out_ (more servers). This shapes cost and architecture.
4. **Storage model** — SQL uses tables; NoSQL uses whatever model fits the problem.
5. **Use cases** — SQL shines for **transactions** (money transfers, order systems); NoSQL shines for **unstructured data** (logs, documents, JSON payloads).

**Beginner framing:** SQL is _structured_ and _predictable_; NoSQL is _flexible_ and _scalable_. Neither is "better" — they solve different problems.

**Intermediate framing:** the choice depends on your **access patterns**, not your preferences. Multi-row transactions and complex joins → SQL. High-volume writes and flexible documents → NoSQL. Many production systems use **both** — SQL for core business data, NoSQL for caches, logs, and search.

**Junior-dev framing:** you'll often be told "use Postgres" (SQL) or "use MongoDB" (NoSQL) — the right answer depends on the app. Learn to ask: _does this data have a strict shape? Does it need transactions? Does it need to scale horizontally?_ Those three questions usually decide it.

---

### 5.8 Database Management System (DBMS)

> **A database typically requires a comprehensive database software program known as a Database Management System (DBMS).**
> **A DBMS serves as an interface between the database and its end users or programs.**

**What a DBMS does:**

- Allows users to **retrieve, update, and manage** how information is organized and optimized.
- Facilitates **oversight and control** of databases — **performance monitoring, tuning, backup, and recovery**.

**Using a DBMS allows us to:**

- **Securely store large volumes of data** for long periods of time.
- **Access data efficiently.**
- **Control access** to data by multiple users at the same time — **one user's actions should not affect the other.**
- **Create new databases** and specify their schemas.
- **Support a data model.**
- **Query and modify** the database's data.
- **Have data redundancy** (i.e., replication and backups).
- **Have more flexibility than files.**
- **Have data consistency and integrity.**

**Beginner framing:** a DBMS is the _software_ that manages the database — think of it as the operating system for your data.

**Intermediate framing:** the DBMS handles concurrency, transactions, backups, and query planning — _you_ don't have to build any of that. That's the whole point of using one.

**Junior-dev framing:** when you use PostgreSQL, MySQL, or MongoDB, you're using a DBMS. You _don't_ build the storage layer yourself; you use the DBMS's guarantees. That separation is what lets your app scale.

---

### 5.9 The most known DBMS

| DBMS                     | Type | Notable for                                                                                                                                              |
| ------------------------ | ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **MySQL**                | SQL  | Free and open source; **probably the best-known DBMS**                                                                                                   |
| **PostgreSQL**           | SQL  | Free and open source; **more functionality** than MySQL, a little less known                                                                             |
| **SQLite**               | SQL  | Free and open source; **lightweight but extremely limited** in functionality                                                                             |
| **Oracle**               | SQL  | **Paid**; used by large companies; **one of the most complete** DBMSs                                                                                    |
| **Microsoft SQL Server** | SQL  | Microsoft's DBMS; **many editions** for different audiences and workloads — from single-machine to large Internet-facing apps with many concurrent users |

**Beginner framing:** all five are relational DBMSs. MySQL and SQLite are common starters; PostgreSQL is common in production; Oracle and SQL Server dominate large enterprises.

**Intermediate framing:** the differences aren't just features — they're **philosophies**:

- **SQLite** — embedded, single-file, no server process. Great for local development and small apps.
- **MySQL** — popular, fast, good defaults. Widely supported.
- **PostgreSQL** — feature-rich, standards-compliant, excellent for complex queries.
- **Oracle / SQL Server** — enterprise-grade, paid, heavy support for large organizations.

**Junior-dev framing:** if you're starting a project and don't know what to pick, **PostgreSQL** is the safest default for relational data. For a tiny project or a local prototype, **SQLite** is fine. The AI bootcamp will later introduce you to specific databases used for AI apps (often Postgres + pgvector, or a dedicated vector DB).

---

## 6. Worked Example — a small student database

> **Imagine a library. We could create a database that stores data about students in the GoMyCode community.**

**Step 1 — create the database:**

```sql
CREATE DATABASE gomycode;
```

**Step 2 — create the table:**

```sql
CREATE TABLE students (
  id INT PRIMARY KEY,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  email VARCHAR(100),
  enrolled_on DATE
);
```

**Step 3 — read data:**

```sql
SELECT first_name, email
FROM students
WHERE enrolled_on >= '2024-01-01';
```

**Step 4 — update data:**

```sql
UPDATE students
SET email = 'new@example.com'
WHERE id = 42;
```

**Step 5 — delete data:**

```sql
DELETE FROM students
WHERE id = 42;
```

**What this example teaches:**

- **Each of the five common commands has a role**: _`CREATE DATABASE`_, _`CREATE TABLE`_, _`SELECT`_, _`UPDATE`_, _`DELETE`_.

- **The table is the fundamental unit** — one table, columns, rows, and values.

- **SQL is declarative** — you say what you want (students enrolled in 2024), and the database figures out how to find them.

`WHERE` **clauses control scope** — `DELETE FROM students` (no `WHERE`) would delete all students; that's a classic mistake.

---

## 7. Common Pitfalls

- ❌ **Thinking databases are just big spreadsheets.** They're fundamentally different — with schemas, transactions, concurrency, and query languages.
- ❌ **Confusing SQL (the language) with a DBMS (MySQL, PostgreSQL).** SQL is the language; MySQL is one implementation of a DBMS that speaks it.
- ❌ **Assuming NoSQL means "no SQL at all."** The accurate expansion is **"not only SQL"** — NoSQL databases can support SQL-like query languages too.
- ❌ **Picking SQL vs. NoSQL based on fashion.** Decide based on access patterns: transactions and complex queries → SQL; flexible documents and horizontal scale → NoSQL.
- ❌ **Skipping the DBMS layer.** A database alone is just storage; the DBMS is what gives you safety, concurrency, and reliability.
- ❌ **Deleting** without a `WHERE`. `DELETE FROM students` deletes every row. Always check your conditions.
- ❌ **Assuming a database doesn't need backups.** Redundancy, backups, and recovery are DBMS responsibilities — make sure they're enabled.
- ❌ **Thinking one database fits all workloads.** Many production systems use multiple databases — SQL for core data, NoSQL for caches, search, logs.

---

## 8. Hands-On Exercises

1. **Database vs. spreadsheet (10 min).** Pick one task you use a spreadsheet for. List three reasons it would benefit from a database (or three reasons it wouldn't). Be specific.
2. **Type matching (10 min).** For each scenario, say whether SQL or NoSQL fits better, and why:
   - (a) a bank's transaction ledger,
   - (b) a product catalog with diverse attributes,
   - (c) session storage for a high-traffic web app,
   - (d) a social graph of who follows whom,
   - (e) a large analytics dashboard.
3. **SQL command drill (15 min).** Write the SQL commands for:
   - (a) create a database called `library`,
   - (b) create a table called `books` with `id`, `title`, `author`, `year`,
   - (c) find all books by "Isaac Asimov",
   - (d) update the title of book #3,
   - (e) delete all books published before 1900.
4. **The five SQL commands (10 min).** Match each command to its purpose and identify which CRUD operation it implements.
5. **DBMS comparison (10 min).** For each scenario, name a reasonable DBMS choice and justify in one sentence:
   - (a) a personal note-taking app on your laptop,
   - (b) a startup's new web app,
   - (c) a large bank's transaction system,
   - (d) a quick local test for a Python script.
6. **MERN connection (10 min).** Look up what **MERN** stands for. Which database is the "M"? Why might someone choose a document database for a JavaScript-heavy web app?

---

## 9. Checkpoint Questions

1. In one sentence, what is a **database**, and what does it do?
2. Why do we need databases instead of files or spreadsheets — name three reasons.
3. What does **SQL** stand for, and what is it used for?
4. Name the **five most common SQL commands** and what each does.
5. What does **NoSQL** stand for — and why is "not only SQL" more accurate than "non-SQL"?
6. Name three examples of NoSQL databases and what each is known for.
7. What is the **fundamental difference** between SQL and NoSQL? Name at least three of the five distinctions.
8. What is a **DBMS**, and what does it do for you?
9. Name three DBMSs and one characteristic of each.

_(Answers are implied throughout Section 5 — try to answer before re-reading.)_
