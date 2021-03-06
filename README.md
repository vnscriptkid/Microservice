# Microservice

## Definitions
- Monolith: A single codebase for all features, including (ARBD): authentication, routing, business logic, database => single point of failure
- Microservice: A single codebase for 1 feature, each codebase contains: auth, routing, business logic, database
  - Self-contained
    - Each service works independently => Increase reliability
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
    - π¬ Easy to reason
    - π No extra space for another db
  - CONS
    - πΈ Create dependency: 1 fails, others fail
    - π Slow
    - πΈοΈ Web of requests
### :two: ASYNC
- What: business service, created for a specific purpose, maintains it's own customized db, data inside database is constructed by listening to the services that it needs
through a event bus
- Pros and cons
  - βοΈ βοΈ indirect dependency (to get info only)
  - βοΈ π  fast (immediate access to data it needs)
  - β π­ data duplications
