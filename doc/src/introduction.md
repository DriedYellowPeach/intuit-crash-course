# Introduction

This project is a simplified tax filing application built to mirror the tech stack and architecture of the Intuit TurboTax Tax Filing team.

## What This Project Covers

- **Backend**: A Spring Boot (Java 21) service that orchestrates tax return submissions, saves returns to PostgreSQL, and simulates handing off filing data to a downstream e-Filing service.
- **Frontend**: A React application providing a tax return form, a "Finish and File" review/print experience, and basic agent-facing views.
- **Infrastructure**: Redis for caching, Kubernetes for deployment, and Maven for builds.

## Mapping to the Real Team

| This Project                        | TurboTax Tax Filing Team                     |
|-------------------------------------|----------------------------------------------|
| Tax return CRUD API                 | Backend orchestration of tax returns         |
| Simulated e-Filing handoff          | Sending data to the EFE (e-Filing) team      |
| Print/download return               | "Finish and File" print experiences          |
| React frontend                      | AppFabric-based dynamic experiences          |
| Kubernetes deployment               | IKS (Intuit Kubernetes Service)              |
| Maven build                         | Maven + Jenkins CI/CD                        |
