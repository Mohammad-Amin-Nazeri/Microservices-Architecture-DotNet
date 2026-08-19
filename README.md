# 🧩 Microservices Architecture with .NET

A practical microservices solution built with **ASP.NET Core**, demonstrating service isolation, API Gateway patterns, synchronous and asynchronous communication, and polyglot persistence.

## 🚀 Services

- **Catalog** — Product management with MongoDB
- **Basket** — Shopping cart with Redis and gRPC integration
- **Discount** — Discount service with PostgreSQL and gRPC
- **Ordering** — Order processing with CQRS, MediatR, Clean Architecture and SQL Server
- **Ocelot API Gateway** — Centralized API routing
- **Shopping Aggregator** — Aggregates data from multiple services
- **EventBus.Messages** — Shared integration event contracts

## 🏗️ Architecture

```text
                        Client
                           │
              ┌────────────┴────────────┐
              ▼                         ▼
       Ocelot API Gateway      Shopping Aggregator
              │                         │
       ┌──────┼─────────┐       ┌───────┼────────┐
       ▼      ▼         ▼       ▼       ▼        ▼
    Catalog  Basket  Ordering  Catalog Basket  Ordering
                │
                ├──── gRPC ────► Discount
                │
                └── RabbitMQ ──► Ordering
```

The services use their own persistence technologies:

```text
Catalog   → MongoDB
Basket    → Redis
Discount  → PostgreSQL
Ordering  → SQL Server
```

## 🔄 Communication

- **REST** for standard service APIs
- **gRPC** for synchronous internal communication
- **RabbitMQ / MassTransit** for asynchronous messaging
- **Ocelot** for API Gateway routing
- **Shopping Aggregator** for combining data from multiple services

## 🛠️ Tech Stack

- C# / ASP.NET Core Web API
- .NET
- Ocelot
- RabbitMQ
- MassTransit
- gRPC
- Docker & Docker Compose
- MongoDB
- Redis
- PostgreSQL
- SQL Server
- CQRS
- MediatR
- FluentValidation
- AutoMapper

## 📂 Structure

```text
Microservices-Architecture-DotNet/
├── ApiGateways/
│   ├── OcelotApiGw/
│   └── Shopping.Aggregator/
│
├── BuildingBlocks/
│   └── EventBus.Messages/
│
├── Services/
│   ├── Catalog/
│   ├── Basket/
│   ├── Discount/
│   └── Ordering/
│
├── docker-compose.yml
└── *.sln / *.slnx
```

## ▶️ Run with Docker

The repository includes Docker Compose configuration for the application services and supporting infrastructure such as MongoDB, Redis, PostgreSQL, SQL Server, RabbitMQ, pgAdmin and Portainer. fileciteturn157file0

```bash
docker compose up --build
```

## ⭐ Highlights

- Independent services with separate data stores
- REST, gRPC and event-driven communication
- API Gateway and aggregation patterns
- CQRS and Clean Architecture in Ordering
- Containerized local environment

## 👨‍💻 Author

**Mohammad Amin Nazeri**

- GitHub: https://github.com/Mohammad-Amin-Nazeri
- LinkedIn: https://www.linkedin.com/in/mohammad-amin-nazeri/

⭐ If you find the project useful, consider giving it a star.
