---
layout: post
title: "Spring Boot Bookstore API – What I Built and What I Learned"
date: 2025-07-06
categories: [Java, Spring Boot, Projects, Backend]
---

🚀 **Spring Boot Bookstore REST API** is one of the most structured backend projects I've worked on — a robust and production-ready RESTful web service built using **Spring Boot**, **Hibernate**, and **PostgreSQL**. It supports full CRUD and partial update operations for managing books and authors.

---

### 📚 What I Built

The application was designed with **clean architecture principles** in mind. Key features include:

- ✅ **CRUD + PATCH** for books and authors
- 🔄 **Pagination** for listing books
- 🔧 **DTO ↔ Entity mapping** for data abstraction
- 🧪 **100% test coverage** using **JUnit 5** and **AssertJ**
- 🐳 **Dockerized deployment** to **AWS LightSail**

The goal was to build a backend API that follows **best practices** like separation of concerns, test-driven development, and RESTful principles — all of which I learned and implemented step-by-step.

---

### 🎓 What I Learned from DevTiro

I followed the [DevTiro Spring Boot YouTube series](https://www.youtube.com/@DevTiro) — and it was a game-changer for understanding real-world backend development. Some core takeaways:

- How to structure a layered architecture (Controller → Service → Repository)
- How to write clean, testable code with **DTOs and mappers**
- Writing integration tests using **JUnit + Spring Boot Test** with test containers
- Configuring and using **Spring Data JPA** effectively
- Clean Git-based project management and Docker integration

This project taught me more than any tutorial ever could — because I didn’t just follow along, I extended and deployed it!

---

### ☁️ Deployment

The API is containerized using Docker and deployed to **AWS LightSail**, making it production-ready. I also used environment-specific profiles and configuration best practices to ensure scalability.

---

### 🔗 GitHub Repository

You can check out the full code here:  
👉 [raZer99/springboot-bookstore-api](https://github.com/raZer99/springboot-bookstore-api)

---

Thanks for reading! If you’re learning Java backend development, I highly recommend DevTiro’s content — and building something end-to-end like this to truly master Spring Boot. 💡
