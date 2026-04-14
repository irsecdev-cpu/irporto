---
title: Flask Advanced App
date: 2026-03-18T00:00:00.000Z
draft: false
summary: Project overview for flask-advanced-app.
---

A robust Flask API managed with Poetry, featuring Pydantic data validation, automatic Swagger documentation, and an integrated Audit Log system.

## Features

Modern Dependency Management: Powered by `Poetry` for isolated and consistent environments.
Strict Validation: Input data is validated via `Pydantic` models (e.g., minimum string lengths, positive price constraints).
Interactive Documentation: Built-in Swagger UI via `Flasgger`.
Audit Logging: Automatic tracking of deletions and price updates in the database.
Search & Sort: Advanced filtering with partial name matching and price-based sorting.

## Installation & Setup

Install dependencies:

```bash

poetry install

```

Run the application:

```bash

poetry run python run.py

```

The API will be available at: `<http://127.0.0.1:5000>`

API Documentation (Swagger)

Explore and test all endpoints directly from your browser: 127.0.0.1

Core Endpoints

Items Management (/items)

GET /items?sort=asc|desc: List all products (sorted by price).
POST /items: Create a new item.
Payload: {"name": "Laptop", "price": 999.99, "sku": "LP-100"}

Individual Item Operations (/items/`<sku>`)

GET /items/`<sku>`: Retrieve specific product details.
PATCH /items/`<sku>`: Update name or price.
DELETE /items/`<sku>`: Remove a product (triggers an Audit Log entry).

Search & History

GET /search?q=keyword: Partial name search (case-insensitive).
GET /audit: View the full history of modifications and deletions.

Project Structure

```text

├── app/
│   ├── routes.py    # API logic and Pydantic schemas
│   └── models.py    # SQLAlchemy models (Item, AuditLog)
├── pyproject.toml   # Poetry configuration & dependencies
├── run.py           # Application entry point
└── README.md        # Current documentation

```

License
Distributed under the MIT License
