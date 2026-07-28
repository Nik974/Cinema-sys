# Cinema System

A cinema ticket booking application with role-based access.

The application is deployed and publicly accessible:
[https://cinemaapp-cbhdb4h8f6gqbfht.polandcentral-01.azurewebsites.net/](https://cinemaapp-cbhdb4h8f6gqbfht.polandcentral-01.azurewebsites.net/)

---

## Screenshots

<table>
  <tr>
    <td><img width="1908" height="904" alt="Zrzut ekranu 2026-07-28 222455" src="https://github.com/user-attachments/assets/ee64511c-73ba-4eb5-9061-c87b8b2107a1" />
</td>
    <td><img width="1919" height="895" alt="Zrzut ekranu 2026-07-28 223359" src="https://github.com/user-attachments/assets/5b6e9d8e-de6a-40af-9777-254ee81856d3" />

</td>
  </tr>
  <tr>
    <td align="center"><b>Movie list</b></td>
    <td align="center"><b>Login page</b></td>
  </tr>
  <tr>
    <td><img width="1917" height="903" alt="Zrzut ekranu 2026-07-28 223813" src="https://github.com/user-attachments/assets/5aca4d35-c542-42e7-9729-9123614ea5d6" />

</td>
    <td><img width="1907" height="897" alt="Zrzut ekranu 2026-07-28 222706" src="https://github.com/user-attachments/assets/54e55022-11f1-4af0-8b37-e39b0831d9cd" /></td>
  </tr>
  <tr>
    <td align="center"><b>Session booking</b></td>
    <td align="center"><b>Seat selection</b></td>
  </tr>
  <tr>
    <td><img width="1894" height="900" alt="Zrzut ekranu 2026-07-28 222850" src="https://github.com/user-attachments/assets/82fa0980-29a9-470e-a55d-ad6ccf97639f" />
</td>
    <td><img width="1898" height="900" alt="Zrzut ekranu 2026-07-28 222910" src="https://github.com/user-attachments/assets/ffbeb16a-39af-47b4-b10a-37433979d670" />
</td>
  </tr>
  <tr>
    <td align="center"><b>Admin: manage movies</b></td>
    <td align="center"><b>Admin: manage reservations</b></td>
  </tr>
</table>

---

## Tech Stack

* **Backend:** Java 21, Spring Boot 4, Spring Security (JWT), Hibernate / JPA
* **Database:** PostgreSQL (Neon Serverless PostgreSQL in Production)
* **DevOps & Infrastructure:** Docker, Docker Compose, GitHub Actions (CI/CD), Azure
---
## Features
- JWT-based authentication and authorization
- RESTful API built with Spring Boot 4
- Two user roles: **ADMIN** and **USER**
    - Admin: manage movies, sessions, view all bookings
    - User: browse movies, book seats, view own bookings


---
## Testing
The project includes:
- Unit tests (JUnit) covering business logic
- Controller tests using WebClient (integration-style testing of REST endpoints)

---
## Database Schema
<details>
<summary>View database diagram</summary>

<img width="960" alt="schema-pic" src="https://github.com/user-attachments/assets/4ee4a4ee-967e-4af3-827f-7e2a2fad5921" />


</details>


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
