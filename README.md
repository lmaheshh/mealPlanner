# Meal Planner

A Spring Boot application with a PostgreSQL database.

## Prerequisites

- [Java 17+](https://adoptium.net/)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

## Running the App

### 1. Start the database

Open Docker Desktop and make sure the engine is running, then in a terminal from the project root:

```
"C:\Program Files\Docker\Docker\resources\bin\docker.exe" compose up -d
```

Or if `docker` is on your PATH:

```
docker compose up -d
```

This starts a PostgreSQL container (`mealplanner-db`) on port `5432`.

### 2. Start the Spring Boot app

Run via your IDE (VS Code / IntelliJ) or with Maven:

```
./mvnw spring-boot:run
```

The app will be available at: **http://localhost:8080**

---

## Stopping

To stop the database container:

```
docker compose down
```

To also delete the database volume (resets all data):

```
docker compose down -v
```

> **Note:** If you delete the volume, Postgres will reinitialize with the credentials in `docker-compose.yml` on next startup. You'll need to do this if you see a password authentication error on startup.

---

## Configuration

Database connection settings are in [src/main/resources/application.properties](src/main/resources/application.properties).

| Property | Value |
|---|---|
| URL | `jdbc:postgresql://localhost:5432/mealplanner` |
| Username | `mealplanner` |
| Password | `mealplanner` |
