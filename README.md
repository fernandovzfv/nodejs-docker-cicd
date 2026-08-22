# Node.js Docker CI/CD API

A containerized Node.js & Express REST API with PostgreSQL integration.

## Features

- **Express.js API** with `/health` and CRUD task endpoints (`/tasks`).
- **PostgreSQL Database** integration via `pg` connection pool.
- **Multi-stage Dockerfile** optimized for production with security best practices (non-root user).
- **Docker Compose** orchestration with automated database health checks and persistent volume storage.

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/health` | Application health check |
| `GET` | `/tasks` | List all tasks |
| `POST` | `/tasks` | Create a new task (`{ "title": "string" }`) |
| `PATCH` | `/tasks/:id` | Update task status (`{ "completed": boolean }`) |

## Quick Start with Docker

```bash
# Build and run containers
docker compose up --build -d

# Check logs
docker compose logs -f

# Stop containers
docker compose down
```

## Running Locally (Without Docker)

1. Make sure a local PostgreSQL instance is running.
2. Configure `.env` with your database credentials.
3. Install dependencies and start the app:

```bash
npm install
npm run dev   # Development mode with nodemon
# or
npm start     # Production mode
```
