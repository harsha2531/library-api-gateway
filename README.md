
---

## 4. `api-gateway`

**Repository About description:**  
> Spring Cloud Gateway acting as the single entry point for all backend services, with routing based on service discovery.

```markdown
# API Gateway

## Mandatory Information

- **Student Name**: [B.K. Harsha Nimeda Sirithunga]
- **Student Number**: [2301691058]
- **Slack Handle**: [@Harsha_Nimeda]
- **GCP Project ID**: [indigo-splice-491917-q2]

## Project Description

The **API Gateway** is the front controller for the Library Management System backend. It routes client requests to the appropriate microservice (book, member, or order) using Spring Cloud Gateway and Netflix Eureka service discovery. It also centralizes cross-cutting concerns like authentication, logging, and rate limiting (future enhancements).

## Technology Stack

- Java 25
- Spring Boot 3.4.5
- Spring Cloud Gateway
- Spring Cloud Netflix Eureka Client
- Spring Cloud Config Client

## Setup / Getting Started Instructions

### Prerequisites
- Java 25
- Maven
- Config Server (running on port 8888)
- Eureka Server (running on port 8761)

### Configuration

The gateway fetches its configuration from the Config Server (via `bootstrap.yml`). The following routes are defined:

| Path pattern      | Target service | Example |
|------------------|----------------|---------|
| `/api/books/**`   | book-service   | `GET /api/books/1` |
| `/api/members/**` | member-service | `POST /api/members` |
| `/api/orders/**`  | order-service  | `PUT /api/orders/1/return` |

### Run the Gateway

```bash
mvn spring-boot:run
