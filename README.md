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
- Service A sql, service B noSql
