# Architecture

## System Overview

```
                         +------------------+
                         |   React Frontend |
                         |   (Vite + React) |
                         +--------+---------+
                                  |
                                  | REST API
                                  |
                         +--------v---------+
                         |  Spring Boot API |
                         |    (Java 21)     |
                         +--+----------+----+
                            |          |
                  +---------+          +----------+
                  |                               |
          +-------v-------+             +---------v--------+
          |  PostgreSQL    |             |      Redis       |
          |  (persistence) |             |     (cache)      |
          +----------------+             +------------------+
```

## Components

### Backend (Spring Boot)

The backend is a REST API built with Spring Boot and Java 21. It is responsible for:

- Managing tax return data (CRUD operations)
- Orchestrating the filing workflow (save, validate, submit)
- Simulating the handoff to an e-Filing service (mimicking the EFE team)
- Generating printable/downloadable return documents

Key layers:
- **Controller**: REST endpoints
- **Service**: Business logic and orchestration
- **Repository**: Data access via Spring Data JPA
- **Model/Entity**: Domain objects mapped to database tables

### Frontend (React)

The frontend provides:

- A tax return input form
- A "Finish and File" review and print experience
- Return status tracking
- An agent-facing view for filed return information

### Database (PostgreSQL)

Stores tax return data, user information, and filing status history.

### Cache (Redis)

Used for:
- Caching frequently accessed return data
- Session management
- Rate limiting (optional)

## API Design

The API follows REST conventions:

| Method | Endpoint                  | Description                |
|--------|---------------------------|----------------------------|
| POST   | `/api/returns`            | Create a new tax return    |
| GET    | `/api/returns/{id}`       | Get a tax return by ID     |
| GET    | `/api/returns`            | List all returns           |
| PUT    | `/api/returns/{id}`       | Update a tax return        |
| DELETE | `/api/returns/{id}`       | Delete a tax return        |
| POST   | `/api/returns/{id}/file`  | Submit a return for filing |
| GET    | `/api/returns/{id}/status`| Get filing status          |
| GET    | `/api/returns/{id}/print` | Get printable return       |
