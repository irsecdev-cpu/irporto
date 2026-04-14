---
title: Proiect My CV Flask
date: 2026-03-29T00:00:00.000Z
draft: false
summary: Project overview for proiect_flask.
---

## Flash Resume Builder & AI Auditor

A professional web application to manage, import, and analyze resumes using AI. Built with Python 3.12, Flask, SQLite, and Hybrid AI (Cloud/Local).

## Features

Dual AI Analysis:
Cloud GPT-4o-mini integration for expert recruiter feedback.
Local: Private, on-device analysis via Ollama (Llama3).
Audit Mode: Toggle `app.config['AUDIT_MODE'] = True` to simulate AI results instantly. No API costs, no GPU, no balance required.
Flash Import: Automated data extraction (Name, Email, Experience) from existing PDF resumes.
One-Click PDF: High-quality PDF generation using WeasyPrint with print-optimized CSS.
Data Management: Built-in features to delete individual resumes or wipe the entire test database for a clean start.

## Quick Start (Docker - Recommended)

### Prepare Environment

```bash

touch resumes.db

```

### Launch Services

```bash

docker-compose up --build -d

```

### Access

Open `<http://localhost:5000>`

### Local AI Setup (Optional)

To use the local Llama3 model without Audit Mode:

```bash

docker exec -it resume_ollama ollama run llama3

```

## Configuration (app.py)

| Variable           | Description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| AUDIT_MODE = True  | (Default) Simulation mode. Instant results, no API keys or Ollama required. |
| AUDIT_MODE = False | Production. Requires OPENAI_API_KEY and a running Ollama container.         |

Project Structure

app.py: Flask core, SQLAlchemy models, AI routes, and Debug/Delete endpoints.
templates/: Jinja2 layouts including list.html (Dashboard) and analysis.html (AI Results).
docker-compose.yml: Multi-container orchestration (Flask Web + Ollama).
pyproject.toml: Dependency management (OpenAI, Flask, WeasyPrint, PDFMiner).
resumes.db: Local SQLite storage (Persistent via Docker volumes).

## Maintenance & Debugging

Delete Individual: Use the "Delete" button on any resume card in the dashboard.
Hard Reset: Access `<http://localhost:5000/debug/clear-all>`
to wipe all resumes from the database instantly.

## Manual Installation (Local)

Requires Python 3.11+, Poetry, and system-level Gtk+ libraries.

```bash

#Install dependencies
poetry install
#Run (For Real Mode, export your key first)
export OPENAI_API_KEY='your-key-here'
poetry run python app.py

```

## System Notes

Arch Linux: Ensure your kernel is up-to-date for Docker veth network stability.
AI Connectivity: In Real Mode, the app communicates with Ollama at
`<http://ollama:11434>`

License
Distributed under the MIT License
