---
title: Psihopromanager
date: 2026-03-26T00:00:00.000Z
draft: false
summary: Project overview for PsihoproManager.
---

## PsihoproManager

A complete patient management system with automated PDF contract generation, built with .NET 10, SQL Server, QuestPDF, and Blazor WebAssembly, fully containerized with Docker.

## Tech Stack

Backend: ASP.NET Core 10.0 (Web API)
Frontend: Blazor WebAssembly (.NET 10) hosted on Nginx
Database: Microsoft SQL Server 2019
PDF Generation: QuestPDF (Fluent API)
Containerization: Docker & Docker Compose

## Installation & Setup (Docker)

Clone the repository:

```bash

git clone `<repository-url>`
cd PsihoproManager

```

Set permissions for PDF storage (Linux/macOS):

```bash

sudo chmod -R 777 ./pdf_storage

```

Start the application:

```bash

sudo docker-compose up --build -d

```

Access the application:
Frontend UI: `<http://localhost:8080>`
API/Swagger: `<http://localhost:5000/swagger/index.html>`
Database: localhost, 1433 (User: sa, Password: YourSecure Password123!)

Project Structure
./Controllers: API endpoints for patient and document management.
./Models: Shared data models used by both Backend and Frontend.
./PsihoproManager.Client: Blazor WASM frontend application.
./pdf_storage: Local folder mapped to /app/data where generated PDFs are stored.

Core Functionalities
Patient Management: Add, List, and Delete patients.
Contract Generation: Create instant PDF contracts using QuestPDF.
Document Management: Download and auto-delete files associated with patients.
Persistence: Database and PDF files are preserved using Docker volumes.

Development & Troubleshooting
CORS: The API is configured to allow requests from the frontend at  `<http://localhost:8080>`
Database Init: On the first run, the database is automatically created via context.Database.EnsureCreated().
Nginx Config: Uses a custom nginx.conf to handle Blazor\\'s Single Page Application (SPA) routing.
Testing Example (curl)

Add Patient / Generate Contract

```bash

curl -X POST "http://localhost:5000/api/Pacienti" \\
\-H "Content-Type: application/json" \\
\-d '{"nume": "John Doe", "cnp": "1234567890123", "email": "[john@email.com](mailto:john@email.com)"}'

curl -X POST "http://localhost:5000/api/Pacienti/1/generate-contract"

```

License
Distributed under the MIT License
