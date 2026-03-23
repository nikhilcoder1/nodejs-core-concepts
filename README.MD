# Node.js Concepts Mastery

> **A structured, hands-on repository to learn and master Node.js — from core fundamentals to production-ready backend patterns.**

<br>

![Node.js](https://img.shields.io/badge/Node.js-18.x%2B-339933?style=flat-square&logo=node.js&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![npm](https://img.shields.io/badge/npm-9.x%2B-CB3837?style=flat-square&logo=npm&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-orange?style=flat-square)

---

## Table of Contents

- [About the Repository](#about-the-repository)
- [Learning Roadmap Covered](#learning-roadmap-covered)
- [Folder Structure](#folder-structure)
- [Concept-wise Explanation](#concept-wise-explanation)
- [Getting Started](#getting-started)
- [Code Examples](#code-examples)
- [Key Learnings & Takeaways](#key-learnings--takeaways)
- [Best Practices Covered](#best-practices-covered)
- [Use Cases](#use-cases)
- [Future Enhancements](#future-enhancements)
- [Contributing Guidelines](#contributing-guidelines)
- [License](#license)
- [Author](#author)

---

## About the Repository

### Why This Repository Exists

Learning Node.js is often fragmented — tutorials jump between concepts, documentation is dense, and most beginner projects skip the internals entirely. This repository was built to fix that.

**Node.js Concepts Mastery** is a structured, concept-driven learning resource that takes you through Node.js the right way: methodically, with clear examples, real explanations, and a codebase organized the way production projects are.

### What Problems It Solves

- **Scattered learning** — All core Node.js concepts are organized in one place, not spread across 50 different blog posts.
- **No context for *why*** — Every concept here is explained with purpose, not just syntax.
- **Missing internals** — Topics like the Event Loop, Streams, and Buffers are often skipped; they're front and center here.
- **Interview unpreparedness** — The concepts covered are precisely what backend interviews test.

### Who Should Use This

| Audience | Benefit |
|---|---|
| Beginners to Node.js | Structured path from zero to confident backend developer |
| Frontend devs moving to backend | Fills the gaps in server-side and runtime understanding |
| Interview candidates | Covers all commonly tested Node.js concepts |
| Self-taught developers | Provides structure and depth often missing from tutorials |

---

## Learning Roadmap Covered

```
Phase 1 — Foundations
  ├── Node.js Runtime & Architecture
  ├── CommonJS Modules (require / module.exports)
  └── ES Modules (import / export)

Phase 2 — Core Modules
  ├── File System (fs)
  ├── Path Module
  ├── OS Module
  └── Events Module (EventEmitter)

Phase 3 — Asynchronous Node.js
  ├── The Event Loop (in depth)
  ├── Callbacks & Callback Hell
  ├── Promises & Promise Chaining
  └── Async / Await

Phase 4 — Streams & Buffers
  ├── Readable & Writable Streams
  ├── Piping Streams
  └── Buffers & Binary Data

Phase 5 — Networking
  ├── HTTP Module (raw server)
  ├── Routing without frameworks
  └── Express.js Basics

Phase 6 — Backend Engineering
  ├── Environment Variables (.env / dotenv)
  ├── Error Handling Strategies
  └── Node.js Best Practices
```

---

## Folder Structure

```
nodejs-concepts-mastery/
│
├── 01-fundamentals/
│   ├── intro.js                  # Node.js globals, process, __dirname
│   └── runtime-overview.md       # How Node.js works under the hood
│
├── 02-modules/
│   ├── commonjs/
│   │   ├── math.js               # module.exports example
│   │   └── app.js                # require() usage
│   └── esmodules/
│       ├── utils.mjs             # export syntax
│       └── main.mjs              # import syntax
│
├── 03-fs-module/
│   ├── read-file.js              # fs.readFile (async)
│   ├── write-file.js             # fs.writeFile
│   ├── append-file.js            # fs.appendFile
│   ├── file-exists.js            # fs.existsSync
│   └── promises-fs.js            # fs/promises API
│
├── 04-event-loop/
│   ├── event-loop-demo.js        # setTimeout, setImmediate, process.nextTick
│   ├── phases.md                 # Visual breakdown of event loop phases
│   └── microtasks-vs-macrotasks.js
│
├── 05-async-patterns/
│   ├── callbacks.js              # Traditional callback pattern
│   ├── callback-hell.js          # The problem — pyramid of doom
│   ├── promises.js               # Promises and .then() chaining
│   ├── promise-all.js            # Promise.all / Promise.allSettled
│   └── async-await.js            # async/await with try/catch
│
├── 06-streams-buffers/
│   ├── readable-stream.js        # Creating a readable stream
│   ├── writable-stream.js        # Writing via streams
│   ├── pipe-demo.js              # Piping streams efficiently
│   └── buffers.js                # Buffer.from, Buffer.alloc
│
├── 07-http-module/
│   ├── basic-server.js           # Raw HTTP server
│   ├── routing.js                # Manual routing (GET/POST)
│   └── json-response.js          # Serving JSON from raw HTTP
│
├── 08-express-basics/
│   ├── server.js                 # Express app setup
│   ├── routes/
│   │   └── users.js              # Modular route file
│   └── middleware/
│       └── logger.js             # Custom middleware example
│
├── 09-env-variables/
│   ├── .env.example              # Template for environment variables
│   ├── config.js                 # Centralized config using dotenv
│   └── usage.js                  # Accessing process.env safely
│
├── 10-error-handling/
│   ├── sync-errors.js            # try/catch for sync code
│   ├── async-errors.js           # Error propagation in async/await
│   ├── event-emitter-errors.js   # Handling 'error' event
│   └── global-handler.js         # process.on('uncaughtException')
│
├── 11-best-practices/
│   ├── project-structure.md      # Recommended project layout
│   ├── naming-conventions.md     # File, variable, function naming
│   └── security-basics.md        # Input validation, env safety
│
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

---

## Concept-wise Explanation

### 01 — Node.js Fundamentals
Node.js is a JavaScript runtime built on Chrome's V8 engine that executes JS outside the browser. It is non-blocking and event-driven, making it ideal for I/O-heavy backend operations.
> Code: `01-fundamentals/intro.js`

---

### 02 — Modules (CommonJS & ES Modules)
Node.js uses the CommonJS module system (`require` / `module.exports`) by default, while modern Node.js also supports ES Modules (`import` / `export`) via `.mjs` files or `"type": "module"` in `package.json`.
> Code: `02-modules/commonjs/` and `02-modules/esmodules/`

---

### 03 — File System (fs Module)
The `fs` module provides APIs to interact with the file system — reading, writing, deleting, and watching files. The `fs/promises` API offers a clean async interface without callbacks.
> Code: `03-fs-module/`

---

### 04 — Event Loop & Async Nature
The Event Loop is the core mechanism that allows Node.js to perform non-blocking I/O despite being single-threaded. Understanding phases (timers, I/O, poll, check) is critical for writing predictable async code.
> Code: `04-event-loop/event-loop-demo.js`, `04-event-loop/phases.md`

---

### 05 — Callbacks, Promises, Async/Await
Node.js evolved from callback-based patterns to Promises and then `async/await`. Each pattern is demonstrated — including the infamous callback hell — so you understand both the problem and its solution.
> Code: `05-async-patterns/`

---

### 06 — Streams & Buffers
Streams allow processing large data (files, network) piece by piece without loading it all into memory. Buffers represent fixed-length binary data and are frequently used when working with TCP streams, file I/O, and cryptography.
> Code: `06-streams-buffers/`

---

### 07 — HTTP Module
Node.js ships with a built-in `http` module capable of creating production-grade servers without any third-party library. Understanding raw HTTP helps you appreciate what frameworks like Express abstract away.
> Code: `07-http-module/`

---

### 08 — Express Basics
Express is a minimal, unopinionated web framework for Node.js. This section covers app setup, routing, request/response handling, and writing custom middleware.
> Code: `08-express-basics/`

---

### 09 — Environment Variables
Environment variables keep sensitive configuration (API keys, DB URIs) out of source code. This section demonstrates using `dotenv` with a centralized config module.
> Code: `09-env-variables/`

---

### 10 — Error Handling
Robust Node.js applications handle errors at every level — synchronous, asynchronous, EventEmitter, and unhandled promise rejections — gracefully and without crashing.
> Code: `10-error-handling/`

---

### 11 — Best Practices
Covers project structure conventions, naming standards, security basics, and patterns used in production Node.js codebases.
> Code: `11-best-practices/`

---

## Getting Started

### Prerequisites

Ensure the following are installed on your system:

- [Node.js](https://nodejs.org/) `v18.x` or higher
- [npm](https://www.npmjs.com/) `v9.x` or higher

Verify your setup:

```bash
node --version   # v18.x.x or higher
npm --version    # 9.x.x or higher
```

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/your-username/nodejs-concepts-mastery.git
cd nodejs-concepts-mastery
```

**2. Install dependencies**

```bash
npm install
```

**3. Set up environment variables**

```bash
cp 09-env-variables/.env.example 09-env-variables/.env
# Edit .env and fill in your values
```

### Running Examples

Each concept folder contains standalone scripts. Run any example directly:

```bash
# Run a specific concept example
node 03-fs-module/read-file.js

# Run async patterns demo
node 05-async-patterns/async-await.js

# Start the raw HTTP server
node 07-http-module/basic-server.js

# Start the Express server
node 08-express-basics/server.js
```

---

## Code Examples

### Reading a File with fs (Async)

```javascript
// 03-fs-module/read-file.js
const fs = require('fs');
const path = require('path');

const filePath = path.join(__dirname, 'sample.txt');

fs.readFile(filePath, 'utf-8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err.message);
    return;
  }
  console.log('File contents:', data);
});
```

---

### Reading a File using fs/promises (Modern)

```javascript
// 03-fs-module/promises-fs.js
const fs = require('fs/promises');
const path = require('path');

async function readFile() {
  try {
    const filePath = path.join(__dirname, 'sample.txt');
    const data = await fs.readFile(filePath, 'utf-8');
    console.log('File contents:', data);
  } catch (err) {
    console.error('Failed to read file:', err.message);
  }
}

readFile();
```

---

### Basic HTTP Server

```javascript
// 07-http-module/basic-server.js
const http = require('http');

const PORT = process.env.PORT || 3000;

const server = http.createServer((req, res) => {
  if (req.method === 'GET' && req.url === '/') {
    res.writeHead(200, { 'Content-Type': 'application/json' });
    res.end(JSON.stringify({ message: 'Welcome to Node.js Mastery' }));
    return;
  }

  res.writeHead(404, { 'Content-Type': 'application/json' });
  res.end(JSON.stringify({ error: 'Route not found' }));
});

server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}`);
});
```

---

### Async/Await with Proper Error Handling

```javascript
// 05-async-patterns/async-await.js
const fs = require('fs/promises');

async function processUserData(userId) {
  try {
    const rawData = await fs.readFile(`./data/user-${userId}.json`, 'utf-8');
    const user = JSON.parse(rawData);
    console.log(`Loaded user: ${user.name}`);
    return user;
  } catch (err) {
    if (err.code === 'ENOENT') {
      console.error(`User file not found for ID: ${userId}`);
    } else {
      console.error('Unexpected error:', err.message);
    }
    throw err;
  }
}

processUserData(42);
```

---

### Piping Streams (Efficient File Copy)

```javascript
// 06-streams-buffers/pipe-demo.js
const fs = require('fs');
const path = require('path');

const source = fs.createReadStream(path.join(__dirname, 'large-file.txt'));
const destination = fs.createWriteStream(path.join(__dirname, 'output.txt'));

source.pipe(destination);

source.on('error', (err) => console.error('Read error:', err.message));
destination.on('finish', () => console.log('File copied successfully via stream.'));
```

---

### EventEmitter Pattern

```javascript
// 04-event-loop/event-loop-demo.js
const { EventEmitter } = require('events');

class OrderService extends EventEmitter {
  placeOrder(orderId) {
    console.log(`Order ${orderId} placed.`);
    this.emit('orderPlaced', { orderId, timestamp: Date.now() });
  }
}

const service = new OrderService();

service.on('orderPlaced', ({ orderId, timestamp }) => {
  console.log(`[Listener] Processing order ${orderId} at ${timestamp}`);
});

service.placeOrder('ORD-1001');
```

---

## Key Learnings & Takeaways

By completing this repository, a developer will be able to:

- Explain how the **Node.js runtime and V8 engine** work together
- Differentiate between **CommonJS and ES Modules** and choose the right one
- Perform all common **file system operations** using both callback and promise APIs
- Understand and explain the **Event Loop**, its phases, and execution order
- Write clean async code using **Callbacks, Promises, and Async/Await**
- Use **Streams and Buffers** for memory-efficient data processing
- Build a functional **HTTP server from scratch** without any framework
- Structure and build an **Express.js application** with routing and middleware
- Manage application config using **environment variables** safely
- Implement **layered error handling** across sync and async code
- Apply **industry-standard best practices** in backend Node.js projects

---

## Best Practices Covered

**Clean Code**
- Descriptive variable and function names
- Single-responsibility functions
- Avoiding deeply nested logic

**Modular Structure**
- One concept per file
- Route and middleware separation in Express
- Centralized configuration via `config.js`

**Async Handling**
- Always `await` or `.catch()` Promises — never leave them floating
- Avoid mixing callback and Promise patterns
- Use `Promise.all` for concurrent independent operations

**Error Handling**
- Never swallow errors silently
- Always use specific error codes (`err.code`) for actionable responses
- Register `process.on('uncaughtException')` and `process.on('unhandledRejection')` handlers

**Security Basics**
- Never hardcode credentials — use `.env`
- Validate all external input
- Keep dependencies updated (`npm audit`)

---

## Use Cases

### Real-World Backend Development

| Concept Learned | Real-World Application |
|---|---|
| HTTP Module / Express | REST API development |
| fs Module | Log management, file uploads, config loading |
| Streams | Video/audio streaming, large CSV processing |
| Event Loop | Understanding performance bottlenecks |
| Error Handling | Building fault-tolerant production services |
| Environment Variables | Multi-environment deployments (dev/staging/prod) |

### Interview Preparation

These are among the most frequently asked Node.js interview topics at backend engineering roles:

- How does the **Event Loop** work in Node.js?
- What is the difference between `process.nextTick()` and `setImmediate()`?
- Explain **Streams** and their advantage over buffering full files.
- What is the difference between **CommonJS and ES Modules**?
- How do you handle **unhandled promise rejections** in Node.js?
- What are **Buffers** and when would you use them?

All of these are covered — with code — in this repository.

---

## Future Enhancements

The following topics are planned for upcoming additions:

- [ ] **Express.js Deep Dive** — Middleware chains, error middleware, Router separation
- [ ] **REST API Project** — A complete CRUD API with Express
- [ ] **Authentication** — JWT-based auth, bcrypt password hashing, refresh tokens
- [ ] **MongoDB Integration** — Mongoose ODM, schemas, CRUD operations
- [ ] **Testing** — Unit and integration testing with Jest and Supertest
- [ ] **WebSockets** — Real-time communication using the `ws` library
- [ ] **Rate Limiting & Security** — Helmet, CORS, express-rate-limit
- [ ] **Deployment** — Environment setup, PM2, Docker basics

Contributions toward any of these are welcome — see the Contributing section below.

---

## Contributing Guidelines

Contributions are welcome and appreciated. To keep quality high, please follow these steps:

1. **Fork** the repository
2. **Create a feature branch**
   ```bash
   git checkout -b feature/add-streams-example
   ```
3. **Write clean, well-commented code** following the existing style
4. **Test your example** locally before submitting
5. **Commit with a clear message**
   ```bash
   git commit -m "feat(streams): add transform stream example"
   ```
6. **Push and open a Pull Request** with a description of what was added and why

**Contribution ideas:**
- Additional code examples for existing concepts
- Concept explanation improvements
- New sections from the Future Enhancements list
- Bug fixes or typo corrections

Please open an issue before starting large additions.

---

## License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

See the full [LICENSE](./LICENSE) file for details.

---

## Author

**Nikhil** : 
Backend Developer | Node.js Enthusiast

Building structured learning resources for the next generation of backend engineers.

[![GitHub](https://img.shields.io/badge/GitHub-nikhilcoder1?style=flat-square&logo=github)](https://github.com/nikhilcoder1)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-nikhil-pandey-b428702b6?style=flat-square&logo=linkedin)](https://linkedin.com/in/nikhil-pandey-b428702b6)

---

<div align="center">

If this repository helped you, consider giving it a ⭐ — it helps others find it too.

</div>