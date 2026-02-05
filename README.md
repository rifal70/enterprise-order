# enterprise-order
Enterprise Order Management Platform built with Spring Boot microservices architecture, demonstrating scalable system design, service decoupling, event-driven communication, and production-ready engineering practices.

## Problem
Sistem order perlu dipisah

## Architecture Overview
<img width="844" height="865" alt="architecture" src="https://github.com/user-attachments/assets/603dfdf3-2d71-4e21-bff4-946b2e0488f7" />

## Tech Stack Decision
Kenapa Spring Boot?
- Cocok untuk sistem besar struktur modular, dependency injection, mudah di maintain
- Ecosystem matang Security, Data, Cloud, Messaging sudah ada
- Production proven	dipakai di sistem enterprise skala besar
- Scalability	Stateless design + mudah di-containerize
- Team Collaboration Convention over configuration

Trade-off:
- Startup time lebih lambat dibanding Go/Node
- Konfigurasi bisa kompleks tapi ditukar dengan stabilitas & maintainability jangka panjang

Kenapa PostgreSQL?
- Relational consistency, sistem order butuh transaksi kuat
- Complex query support	join, indexing, analytics
- Scalability	bisa vertical & read-replica
- Reliability	mature
- Feature lengkap	JSONB, indexing advanced, constraint kuat

Trade-off:
- Scaling write lebih kompleks dibanding NoSQL

Kenapa Redis?
- Caching data user	untuk mengurangi beban DB
- Session/token untuk store	fast read/write
- Idempotency key	untuk cegah double order
- Rate limiting	Counter cepat

Trade-off:
- Data bisa hilang karena bukan primary storage
- Perlu strategi invalidasi cache

## Service Communication
Sync vs Async

## Scalability Strategy
Stateless design, caching

## How to Run
docker-compose up
