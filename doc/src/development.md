# Development Environment

## Prerequisites

| Tool       | Version  | Purpose                        |
|------------|----------|--------------------------------|
| Java (JDK) | 21+     | Backend runtime                |
| Maven      | 3.9+    | Build and dependency management|
| Node.js    | 20+     | Frontend runtime               |
| npm/yarn   | latest  | Frontend package management    |
| Docker     | 24+     | Containerization               |
| kubectl    | 1.28+   | Kubernetes CLI                 |
| minikube   | latest  | Local Kubernetes cluster       |
| PostgreSQL | 16+     | Database                       |
| Redis      | 7+      | Cache                          |
| mdbook     | latest  | Documentation                  |

## Installation

### Java 21

```bash
# Arch Linux
sudo pacman -S jdk21-openjdk

# Verify
java --version
```

### Maven

```bash
# Arch Linux
sudo pacman -S maven

# Verify
mvn --version
```

### Node.js

```bash
# Arch Linux
sudo pacman -S nodejs npm

# Verify
node --version
npm --version
```

### Docker

```bash
# Arch Linux
sudo pacman -S docker
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
# Log out and back in for group change to take effect
```

### PostgreSQL

```bash
# Arch Linux
sudo pacman -S postgresql

# Initialize and start
sudo -u postgres initdb -D /var/lib/postgres/data
sudo systemctl enable --now postgresql

# Create database
sudo -u postgres createuser --interactive  # create your user
sudo -u postgres createdb intuit_crash_course
```

### Redis

```bash
# Arch Linux
sudo pacman -S redis
sudo systemctl enable --now redis
```

### Kubernetes (minikube)

```bash
# Arch Linux
sudo pacman -S minikube kubectl

# Start cluster
minikube start
```

## Running the Project

### Backend

```bash
cd backend
mvn spring-boot:run
```

The API will be available at `http://localhost:8080`.

### Frontend

```bash
cd frontend
npm install
npm run dev
```

The app will be available at `http://localhost:5173`.

### Documentation

```bash
cd doc
mdbook serve --open
```

## IDE Setup

### IntelliJ IDEA (recommended for Java/Spring Boot)

- Import as Maven project
- Set Project SDK to Java 21
- Install Spring Boot plugin

### VS Code (for React frontend)

- Install extensions: ESLint, Prettier, ES7+ React snippets
- Install extension: Extension Pack for Java (if working on backend too)
