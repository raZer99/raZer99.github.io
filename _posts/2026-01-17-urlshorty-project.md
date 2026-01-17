---
layout: post
title: "urlShorty – Building a High-Performance URL Shortener with Spring Boot, Redis, Docker, and React"
date: 2026-01-17
categories: [Backend, Spring Boot, Redis, Java, Docker, React, Full Stack]
---

🚀 **urlShorty** is a full-stack **URL shortening service** built using **Spring Boot**, **Redis**, **Docker**, and a modern **React frontend**.

The project was created as a **learning-focused backend system**, emphasizing **low-latency lookups**, **atomic operations**, **clean REST design**, and **frontend-backend integration**.

---

### 🏗️ What I Built

I developed **urlShorty**, an end-to-end URL shortener that converts long URLs into compact, shareable links and redirects users efficiently using standard HTTP semantics.

#### 🖥️ Backend – Spring Boot + Redis
- **Tech Stack:** Java 17, Spring Boot, Spring Web, Spring Data Redis, Redis, Docker
- **Core Design:** - Uses **Redis atomic counters** (`INCR`) to generate globally unique IDs.
  - Converts numeric IDs into **Base62-encoded short keys**.
  - Guarantees zero collisions and $O(1)$ performance.

📂 **Repositories:**
- **Backend:** [raZer99/urlShorty-backend](https://github.com/raZer99/urlShorty-backend)
- **Frontend:** [raZer99/url-shorty-ui](https://github.com/raZer99/url-shorty-ui)

---

### 🧮 Redis Data Model (Visual Overview)

The system uses Redis as a high-speed primary datastore to manage the ID counter and the URL mappings:

- global:id      -> 1042 (Atomic Counter)
- g              -> [https://google.com](https://google.com) (Short Key -> Original)
- h              -> [https://facebook.com](https://facebook.com)

---
### 🔄 How urlShorty Works (End-to-End Flow)
User Submission: User submits a long URL via the UI or REST API.

ID Generation: Backend increments a Redis atomic counter (INCR global:id).

Encoding: The numeric ID is encoded into a Base62 short key.

Storage: Mapping is stored in Redis: shortKey → originalUrl.

Response: The short key is returned to the client.

Redirect: When the short URL is accessed, the backend issues an HTTP 302 redirect to the original URL.

---

### 🌐 REST API Overview
1. Shorten URL
POST /api/shorten?url=https://google.com

Response: g (Plaintext short key)

2. Redirect
GET /api/g

Action: Redirects (302) to https://google.com

---

### 🎨 Frontend – React UI
The frontend is built with React and focuses on clarity and aesthetics.

UI Features:

Dark Mode: Modern, high-contrast theme.

Responsive: Fully centered layout with large typography.

Real-time Interaction: Instant URL shortening.

Convenience: Clickable short URLs for easy testing.

Error Handling: Graceful feedback for invalid inputs.

Frontend Stack: React (Create React App), JavaScript (ES6+), Custom CSS, Fetch API.

---

### 🐳 Dockerized Development
The backend and Redis run locally using Docker Compose:

Bash

docker compose up --build
Benefits of this setup:

Reproducible local environment across different machines.

No local Redis installation required.

Production-like learning experience.

---

### 🎓 What I Learned
Building urlShorty helped me understand and practice:

REST API design and the nuance of HTTP redirects.

Redis atomic operations (INCR) to solve concurrency issues.

Base62 encoding for creating compact, human-readable identifiers.

Docker-based service orchestration for multi-container apps.

CORS handling and browser security policies.

Debugging real-world edge cases (URL normalization, redirects).

---

### 💡 Why This Project Matters
urlShorty reflects how real-world URL shorteners (like Bitly) are designed:

Minimal storage: Efficient key-value pairs.

Fast lookups: In-memory speed with Redis.

Stateless backend: Logic that scales easily.

Separation of concerns: Clean split between data, logic, and presentation.

---

### 🔮 Possible Enhancements
URL expiration (TTL): Set keys to expire after a certain time using Redis EXPIRE.

Rate limiting: Prevent abuse using Redis-based throttling.

Click analytics: Track how many times a link is clicked.

Authentication: Allow users to manage their own private links.

---

### Made by raZer 👾
