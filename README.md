# Cinema System

A Spring Boot application designed for managing cinema bookings, integrated with PostgreSQL and containerized with Docker.

The application is deployed and publicly accessible:
[https://cinemaapp-cbhdb4h8f6gqbfht.polandcentral-01.azurewebsites.net/](https://cinemaapp-cbhdb4h8f6gqbfht.polandcentral-01.azurewebsites.net/)

---

## Tech Stack

* **Backend:** Java 21, Spring Boot 3, Spring Security (JWT), Hibernate / JPA
* **Database:** PostgreSQL (Neon Serverless PostgreSQL in Production)
* **DevOps & Infrastructure:** Docker, Docker Compose, GitHub Actions (CI/CD), Azure

---

## Getting Started (Local Development)

Follow these steps to run the application locally:

### 1. Clone the repository 

### 2. Configure

Copy the example environment files to set up your local configuration:

```bash
cp .env.example .env
cp src/main/resources/application.properties.example src/main/resources/application.properties
```

Open the created .env and application.properties files, and replace the placeholder values with your actual local configuration settings.

### 3. Build and Run

Start the application along with the PostgreSQL database container:
```bash
docker compose up --build
```
Once the containers are up and running, the local instance will be available at: http://localhost:8080

## Deployment Architecture

**Production**: Deployed as a single container on Azure Web Apps, connecting directly to a Neon PostgreSQL cloud instance.

**Continuous Integration**: GitHub Actions automatically builds the Docker image and triggers deployment upon pushing to the main branch.
