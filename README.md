# 🌐 ConnectSphere – Scalable Social Media Backend Platform

ConnectSphere is a **Spring Boot–based backend platform** designed to power a **social media application** with modern, scalable, and event-driven architecture.  
It supports **user authentication, posts, likes, comments, follow system, personalized feeds, and real-time notifications** using **Kafka and Redis**.

---

## 📖 Extended Description

**ConnectSphere** is a **production-grade social media backend system** built using **Java and Spring Boot**, focusing on **scalability, performance, and clean architecture**.

The project demonstrates how a real-world social media backend works by combining:
- **JWT-based authentication & authorization**
- **Follow graph–based feed generation**
- **Event-driven notifications using Kafka**
- **Caching with Redis for high-performance feeds**

### 🔐 Security & Authentication
ConnectSphere uses **Spring Security with JWT** to secure APIs.  
Only authenticated users can:
- Create posts
- Like or comment on posts
- Follow/unfollow users
- Access personalized feeds
- Fetch notifications  

Public APIs are limited to **register and login** only.

### 👥 Follow System & Feed Generation
- Users can follow and unfollow other users.
- The **feed service** fetches posts only from followed users.
- Feed results are **cached in Redis** to reduce database load and improve response times.
- Pagination is supported for large feeds.

### 📝 Posts, Likes & Comments
Users can:
- Create posts
- Like/unlike posts
- Add comments to posts
- Search posts by hashtag

All actions are designed to mimic real social media behavior.

### 🔔 Event-Driven Notifications (Kafka)
ConnectSphere uses **Apache Kafka** to handle notifications asynchronously:
- Likes
- Comments
- Follow events  

These events are:
1. Published to Kafka topics
2. Consumed by notification consumers
3. Stored in the database
4. Ready for real-time delivery (WebSocket-ready design)

This makes the system **loosely coupled and highly scalable**.

### 🧠 Architectural Goals
This project serves as a **reference architecture** for:
- Social media platforms
- Event-driven microservice-style systems
- Kafka + Redis based applications
- Interview-ready system design projects

---

## 📌 Features

- 🔐 **JWT-based Authentication & Authorization**
- 👤 **Follow / Unfollow Users**
- 📝 **Post Creation**
- ❤️ **Like / Unlike Posts**
- 💬 **Comment on Posts**
- 📰 **Personalized Feed (Follow-based)**
- ⚡ **Redis Caching for Feeds**
- 🔔 **Kafka-based Notification System**
- 📡 **RESTful APIs**
- 🧩 **Layered Architecture**
- 🚀 **Scalable & Event-Driven Design**

---

## 🏗️ Tech Stack

### Backend
- Java 8+
- Spring Boot
- Spring Security
- JWT Authentication
- Spring Data JPA
- Hibernate

### Messaging & Caching
- Apache Kafka
- Redis

### Database
- MySQL / PostgreSQL

### Tools
- Maven
- Git & GitHub
- Postman
- Docker (optional)

---

## 📂 Project Structure

```bash
ConnectSphere/
│── src/
│   ├── main/
│   │   ├── java/com/socialmedia/application
│   │   │   ├── controller/        # REST Controllers
│   │   │   ├── service/           # Business logic
│   │   │   ├── repository/        # JPA Repositories
│   │   │   ├── model / entity     # Domain models
│   │   │   ├── dto/               # Request/Response DTOs
│   │   │   ├── security/          # JWT & Security Filters
│   │   │   ├── kafka/             # Kafka Producers & Consumers
│   │   │   ├── config/            # Redis, Security, Kafka Config
│   │   │   └── ConnectSphereApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── schema.sql / data.sql
│   └── test/                      # Unit & Integration Tests
│
├── postman/                        # Postman Collection
├── pom.xml
├── README.md
└── Dockerfile (optional)
