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
