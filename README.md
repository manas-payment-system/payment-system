# 💳 Payment System

A simulated payment processing system built with industry-standard engineering practices.

## 📌 Project Overview
This system simulates core payment operations — user accounts,
transactions, balance management, and basic fraud detection.

## 👥 Team Roles
| Role | Responsibilities |
|------|-----------------|
| Project Manager (Eldos) | Planning, documentation, reporting |
| Backend Engineer (Adilet) | Architecture, code, pull requests |
| QA / DevOps (Emir) | Testing, CI/CD, monitoring |

## 🛠️ Tech Stack
| Layer | Technology |
|-------|-----------|
| Language | Java 21 |
| Framework | Spring Boot 3 |
| Database | PostgreSQL |
| Message Broker | RabbitMQ |
| Cache | Redis |
| Containerization | Docker / Docker Compose |
| Testing | JUnit 5 + Testcontainers |

## 🗓️ Weekly Progress
- [x] Week 1 — Project Management (Linear)

# Stack Decision Document
**Project:** Payment System  
**Date:** March 2025  
**Author:** Backend Engineer

## Decision

### Backend
- **Java 21 + Spring Boot 3**
  - Industry-standard for enterprise payment systems
  - Strong ecosystem for REST APIs and async processing
  - Built-in support for transactions and security

### Database
- **PostgreSQL**
  - ACID compliance — critical for financial transactions
  - Strong consistency guarantees
  - Reliable for audit logs and transaction history

### Message Broker
- **RabbitMQ**
  - Async processing of payment events
  - Decouples payment initiation from processing
  - Retry and dead-letter queue support

### Cache
- **Redis**
  - Session management and rate limiting
  - Fast lookup for account balances
  - Idempotency key storage (prevent duplicate payments)

### Containerization
- **Docker + Docker Compose**
  - Consistent environment across all team members
  - Easy local setup of PostgreSQL, RabbitMQ, Redis

### Testing
- **JUnit 5 + Testcontainers**
  - Testcontainers spins up real DB/broker in tests
  - No mocking of infrastructure — real integration tests

## Alternatives Considered
| Layer | Chosen | Alternative | Reason Rejected |
|-------|--------|-------------|-----------------|
| DB | PostgreSQL | MySQL | Weaker JSON support |
| Broker | RabbitMQ | Kafka | Overkill for this scale |
| Cache | Redis | Memcached | Less feature-rich |
