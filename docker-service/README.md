# DeployCraft Dockerization Service 🐳

## Project Overview

This project demonstrates how to containerize a static web application using Docker and Nginx.

It is a practical demonstration of DeployCraft's Dockerization service, designed to help developers package and run applications consistently across environments.

## Technology Stack

- Docker
- Nginx Alpine
- HTML
- Docker CLI

## Project Structure

```text
docker-service/
├── app/
│   └── index.html
├── Dockerfile
└── README.md
```

## Prerequisites

- Docker Desktop or Docker Engine
- Git
- A terminal

## Deployment Instructions

### 1. Clone the repository

```bash
git clone YOUR_REPOSITORY_URL
cd deploycraft-portfolio/docker-service
```

### 2. Build the Docker image

```bash
docker build -t deploycraft-web:v1 .
```

### 3. Run the container

```bash
docker run -d -p 8080:80 \
  --name deploycraft-container \
  deploycraft-web:v1
```

### 4. Access the application

Open:

http://localhost:8080

### 5. Verify the container

```bash
docker ps
docker logs deploycraft-container
curl -I http://localhost:8080
```

### 6. Stop and remove the container

```bash
docker stop deploycraft-container
docker rm deploycraft-container
```

## Key Docker Concepts Demonstrated

| Concept | Implementation |
|---|---|
| Base image | nginx:alpine |
| Image creation | docker build |
| Container execution | docker run |
| Port mapping | 8080:80 |
| Container verification | docker ps |
| Container cleanup | docker stop / rm |

## Business Application

DeployCraft offers Dockerization assistance for developers and small teams.

This demonstration showcases a basic static web application containerization workflow. Production applications may require additional configuration, security hardening, environment management, and deployment-specific testing.

---

**DeployCraft — Build. Automate. Deploy.**