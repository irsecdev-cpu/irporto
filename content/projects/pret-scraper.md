---
title: Pret Scraper
date: 2026-03-27T00:00:00.000Z
draft: false
summary: Project overview for pret-scraper.
---

## PriceGuard: Real-Time Price Monitoring System

A full-stack, high-performance price tracking engine built with Java 21 (LTS) and Spring Boot 3.4. This project features automated scraping, persistent storage, and a web dashboard, all fully containerized.

## Key Features

Automated Scraping: Real-time data extraction from e-commerce platforms using JSoup.
Data Persistence: Historical tracking in PostgreSQL 16.
Web Dashboard: Clean HTML/JS interface to visualize price trends at a glance.
REST API: Instant access to tracked products via JSON endpoints.
Containerized Infrastructure: Single-command setup via Docker Compose with Healthchecks.

## Tech Stack

Backend: Java 21 (LTS), Spring Boot 3.4, Spring Data JPA.
Frontend: HTML5, CSS3, JavaScript (Fetch API).
Infrastructură: Docker & Docker Compose, PostgreSQL 16.
Security: Dotenv (.env) for secure credential management.

## Prerequisites

Docker and Docker Compose installed (Arch Linux tested).
Git (for cloning).

## Getting Started (The Easy Way)

Clone & Setup:

```bash

git clone https://github.com
cd price-scraper

```

Configure Environment:
Create a .env file based on the example:

```bash

cp .env.example .env


```

Launch Everything:

```bash

docker-compose up --build -d

```

Monitor Logs:

```bash

docker logs -f price-scraper-app

```

Endpoints & Visualization

Web Dashboard: `<http://localhost:8080>` (Main interface)

API Access: `<http://localhost:8080/api/products>` (JSON data)

Project Status

Full Dockerization (Multi-stage build & Healthchecks)

JPA Persistence Layer (PostgreSQL)

REST API & Web Dashboard

Automated monitoring with @Scheduled tasks

Implement Telegram/Email alert system

Automated monitoring with @Scheduled tasks

Implement Telegram/Email alert system

License
Distributed under the MIT License
