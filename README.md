# Intuit Crash Course

A personal project to get hands-on with the tech stack used by the Intuit TurboTax Tax Filing team before starting an internship. The goal is to build a simplified tax filing application that mirrors the real-world architecture: a Spring Boot backend that orchestrates tax return submissions, a React frontend for user interactions, PostgreSQL for persistence, Redis for caching, and Kubernetes for deployment.

## Tech Stack

| Layer       | Technology              |
|-------------|-------------------------|
| Backend     | Java 21, Spring Boot    |
| Frontend    | React                   |
| Database    | PostgreSQL              |
| Cache       | Redis                   |
| Build       | Maven                   |
| CI/CD       | Jenkins (or GitHub Actions) |
| Deployment  | Kubernetes (k8s)        |
| Docs        | mdbook                  |

## Project Structure

```
intuit-crash-course/
  backend/          # Spring Boot application (Java 21, Maven)
  frontend/         # React application
  k8s/              # Kubernetes manifests
  doc/              # mdbook documentation
  .claude/          # Claude project files
```

## Build Plan

### Phase 1 - Foundation

- [ ] Initialize Spring Boot project with Java 21 and Maven
- [ ] Initialize React frontend with Vite
- [ ] Set up PostgreSQL schema for tax returns
- [ ] Set up Redis for session/caching
- [ ] Create basic project documentation with mdbook

### Phase 2 - Backend API

- [ ] Implement tax return CRUD endpoints (REST API)
- [ ] Add data validation and error handling
- [ ] Integrate PostgreSQL with Spring Data JPA
- [ ] Add Redis caching layer
- [ ] Write unit and integration tests

### Phase 3 - Frontend

- [ ] Build tax return form UI
- [ ] Build "Finish and File" review/print page
- [ ] Connect frontend to backend API
- [ ] Add basic routing and state management

### Phase 4 - Filing Workflow

- [ ] Implement tax return submission orchestration
- [ ] Simulate e-Filing handoff (mimicking the EFE sister team)
- [ ] Add return status tracking (submitted, accepted, rejected)
- [ ] Implement print/download functionality for filed returns

### Phase 5 - Deployment

- [ ] Dockerize backend and frontend
- [ ] Write Kubernetes manifests (deployments, services, ingress)
- [ ] Set up CI/CD pipeline
- [ ] Deploy to a local k8s cluster (minikube or kind)

## Documentation

Documentation is built with [mdbook](https://rust-lang.github.io/mdBook/). To view:

```bash
cd doc && mdbook serve --open
```

## License

MIT
