# Microservice

## Definitions
- Monolith: A single codebase for all features, including (ARBD): authentication, routing, business logic, database
- Microservice: A single codebase for 1 feature, each codebase contains: auth, routing, business logic, database
  - Self-contained
    - Each service works independently 
    - One service failing will not effect other services

## 2 rules
- Database-Per-Service
- Service does not access database from other service directly

## Why?
- Independent: Scale, Uptime (Crash)
- Schema changes: service communicate by interface, knowing nothing about implementation details.
- Optimal db for a service: Service A sql, service B noSql

## Challenges of Microservice:
- #1 Store data and access data between services

## Communicating between services
### :one: SYNC
- What: 1 service uses data from multiple other services, does not maintain its own db, calls to services are in order
- Pros and cons
  - PROS
    - 🍬 Easy to reason
    - 🆓 No extra space for another db
  - CONS
    - 🚸 Create dependency: 1 fails, others fail
    - 🐌 Slow
    - 🕸️ Web of requests
### :two: ASYNC
