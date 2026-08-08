# Dockerized Node.js REST API

A REST API built with Node.js, Express, and PostgreSQL, fully containerized using Docker and Docker Compose.

## 🚀 Technologies

* Node.js
* Express.js
* PostgreSQL
* Docker
* Docker Compose
* `pg` PostgreSQL client
* dotenv

## 🏗️ Architecture

```text
                  Docker Compose
                       │
             ┌─────────┴─────────┐
             │                   │
             ▼                   ▼
      Node.js API          PostgreSQL
       Container            Container
          │                    │
          └─────────┬──────────┘
                    │
              Docker Network
```

## 📁 Project Structure

```text
node-docker-api/
├── src/
│   ├── server.js
│   └── db.js
├── .dockerignore
├── .gitignore
├── Dockerfile
├── docker-compose.yml
├── package.json
├── package-lock.json
└── README.md
```

## ⚙️ Features

* REST API using Express
* PostgreSQL database
* Full CRUD operations for users
* Dockerized Node.js application
* PostgreSQL running in Docker
* Docker Compose orchestration
* Environment variable configuration
* PostgreSQL health check
* Persistent PostgreSQL volume
* Container-to-container networking

## 🔌 API Endpoints

| Method | Endpoint     | Description              |
| ------ | ------------ | ------------------------ |
| GET    | `/`          | Check API status         |
| GET    | `/db-test`   | Test database connection |
| GET    | `/users`     | Get all users            |
| GET    | `/users/:id` | Get a single user        |
| POST   | `/users`     | Create a user            |
| PUT    | `/users/:id` | Update a user            |
| DELETE | `/users/:id` | Delete a user            |

## 🐳 Run with Docker

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd node-docker-api
```

### 2. Create `.env`

Create a `.env` file in the project root:

```env
PORT=3000

POSTGRES_HOST=db
POSTGRES_PORT=5432
POSTGRES_DB=myapp
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
```

> `.env` is ignored by Git and should not be committed.

### 3. Start the application

```bash
docker compose up -d --build
```

### 4. Check containers

```bash
docker compose ps
```

The API and PostgreSQL containers should be running, with PostgreSQL showing as healthy.

### 5. Test the API

Open:

```text
http://localhost:3000
```

Test users:

```text
http://localhost:3000/users
```

## 🗄️ Database

PostgreSQL data is stored using a Docker named volume:

```text
postgres_data
```

This allows database data to persist when the PostgreSQL container is recreated.

## 🛑 Stop the application

```bash
docker compose down
```

To stop the containers while keeping the database volume:

```bash
docker compose down
```

To remove the containers **and database volume**:

```bash
docker compose down -v
```

> Be careful with `-v` because it removes the PostgreSQL data volume.

## 📚 What I Learned

This project helped me learn:

* Building REST APIs with Express
* Connecting Node.js to PostgreSQL
* CRUD operations
* Environment variables
* Dockerfiles
* Docker images and containers
* Docker Compose
* Container networking
* PostgreSQL health checks
* Persistent Docker volumes
* Git and GitHub project management
