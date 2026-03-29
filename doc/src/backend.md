# Backend

## Overview

The backend is a Spring Boot application using Java 25 and Maven. It provides REST APIs for tax return management and filing orchestration.

## Project Layout

```
backend/
  src/
    main/
      java/com/example/taxfiling/
        controller/       # REST controllers
        service/          # Business logic
        repository/       # Spring Data JPA repositories
        model/            # Entity classes
        dto/              # Data transfer objects
        config/           # Spring configuration
        exception/        # Custom exceptions and error handling
      resources/
        application.yml   # Application configuration
  pom.xml                 # Maven build file
```

## Key Dependencies

- `spring-boot-starter-web` - REST API
- `spring-boot-starter-data-jpa` - Database access
- `spring-boot-starter-data-redis` - Redis caching
- `spring-boot-starter-validation` - Input validation
- `spring-boot-starter-test` - Testing
- `postgresql` - PostgreSQL JDBC driver
- `lombok` - Boilerplate reduction

## Configuration

Application configuration is in `application.yml`:

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/intuit_crash_course
    username: ${DB_USERNAME}
    password: ${DB_PASSWORD}
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
  data:
    redis:
      host: localhost
      port: 6379

server:
  port: 8080
```

## Testing

```bash
# Run all tests
mvn test

# Run with coverage
mvn test jacoco:report
```
