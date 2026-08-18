# Microservices Architecture with .NET

A practical microservices solution built with .NET, demonstrating service isolation, API Gateway patterns, synchronous and asynchronous communication, and polyglot persistence.

## Architecture

```text
Client
  |
  +--> Ocelot API Gateway
  |
  +--> Shopping Aggregator
          |
          +--> Catalog
          +--> Basket
          +--> Ordering

Basket <---- gRPC ----> Discount
Basket ---- RabbitMQ ----> Ordering
```

### Services

- **Catalog** — Product management with MongoDB
- **Basket** — Shopping cart with Redis and gRPC integration
- **Discount** — Discount API with PostgreSQL
- **Ordering** — Order processing with CQRS, MediatR, Clean Architecture and SQL Server
- **Ocelot API Gateway** — Centralized API routing
- **Shopping Aggregator** — Aggregates data from multiple services
- **EventBus.Messages** — Shared integration event contracts

## Technologies

`.NET` · `ASP.NET Core Web API` · `Ocelot` · `RabbitMQ` · `MassTransit` · `gRPC` · `Docker` · `MongoDB` · `Redis` · `PostgreSQL` · `SQL Server` · `CQRS` · `MediatR` · `FluentValidation` · `AutoMapper`

## Project Structure

```text
ApiGateways/
  OcelotApiGw/
  Shopping.Aggregator/

BuildingBlocks/
  EventBus.Messages/

Services/
  Catalog/
  Basket/
  Discount/
  Ordering/

Docker Compose
Solution
```

## Running

The solution includes Docker Compose configuration for the services and supporting infrastructure such as MongoDB, Redis, PostgreSQL, SQL Server, RabbitMQ, pgAdmin and Portainer.

## Highlights

- Independent microservices with separate data stores
- REST, gRPC and asynchronous messaging
- API Gateway and aggregation patterns
- CQRS and Clean Architecture in the Ordering service
- Containerized local environment

## Author

**Mohammad Amin Nazeri**

[GitHub](https://github.com/Mohammad-Amin-Nazeri) · [LinkedIn](https://www.linkedin.com/in/mohammad-amin-nazeri/)

⭐ If you find the project useful, consider giving it a star.

---

<details>
<summary>فارسی</summary>

## معماری Microservices با .NET

یک پیاده‌سازی عملی از معماری Microservices با تمرکز بر جداسازی سرویس‌ها، API Gateway، ارتباطات همزمان و غیرهمزمان و استفاده از چند نوع دیتابیس.

### سرویس‌ها

- **Catalog** — مدیریت محصولات با MongoDB
- **Basket** — سبد خرید با Redis و gRPC
- **Discount** — سرویس تخفیف با PostgreSQL
- **Ordering** — پردازش سفارش با CQRS، MediatR، Clean Architecture و SQL Server
- **Ocelot API Gateway** — مسیریابی متمرکز API
- **Shopping Aggregator** — تجمیع اطلاعات چند سرویس
- **EventBus.Messages** — قراردادهای رویدادهای بین سرویس‌ها

### تکنولوژی‌ها

.NET، ASP.NET Core، Ocelot، RabbitMQ، MassTransit، gRPC، Docker، MongoDB، Redis، PostgreSQL، SQL Server، CQRS، MediatR، FluentValidation و AutoMapper

</details>
