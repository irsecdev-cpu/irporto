---
title: My Fastapi App
date: 2026-03-19T00:00:00.000Z
draft: false
summary: Project overview for my-fastapi-app.
---

Modern FastAPI & MariaDB Product Catalog

[![FastAPI](https://img.shields.io)](https://fastapi.tiangolo.com)
[![MariaDB](https://img.shields.io)](https://mariadb.org)
[![SQLAlchemy 2.0](https://img.shields.io)](https://www.sqlalchemy.org)
[![Docker](https://img.shields.io)](https://www.docker.com)

A production-ready product management solution featuring a high-performance asynchronous backend and a sleek, mobile-first Server-Side Rendered (SSR) interface.

Core Features

Fully Asynchronous: Built on `SQLAlchemy 2.0` (Async) and `aiomysql` for non-blocking database operations.
Mobile-First UI: Responsive design with a sticky search bar, intuitive navigation, and interactive product cards.
Smart Search: Server-side filtering for products and categories with optimized query performance.
Data Integrity: Full CRUD API with strict type-safety and validation via `Pydantic`.
Containerized: Seamless development and deployment using Docker and Docker Compose.

Tech Stack

Backend: FastAPI (Python 3.11+)
Database: MariaDB
ORM: SQLAlchemy 2.0 (Mapped Style)
Migrations: Alembic
Frontend: Jinja2 Templates & Bootstrap 5
Dependency Management: Poetry

## Quick Start (Docker)

Spin up the containers:

```bash
docker-compose up -d --build
```

Initialize Database (Migrations):

```bash
docker-compose exec api alembic upgrade head
```

\*\*Seed Data (Optional):

Generate 5 categories and 100 random items using `Faker`:

```bash

docker-compose exec api python -m my_fastapi_app.seed

```

## API & UI Access Points

| Endpoint                                | Description                      |
| :-------------------------------------- | :------------------------------- |
| <http://localhost:8000>                 | **Web Interface** (Home/Catalog) |
| <http://localhost:8000/items/{id}/view> | **Product Detail View**          |
| <http://localhost:8000/docs>            | **Swagger UI** (Interactive API) |
| <http://localhost:8000/redoc>           | **ReDoc** (Alternative API Docs) |

## Development Workflow

### Database Schema Updates

When modifying `models.py`, generate and apply a new migration:

```bash

# Generate migration script
docker-compose exec api alembic revision --autogenerate -m "describe_changes"

# Apply changes to MariaDB
docker-compose exec api alembic upgrade head

```

License
Distributed under the MIT License
