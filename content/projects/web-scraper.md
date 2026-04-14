---
title: Web Scraper
date: 2026-03-17T00:00:00.000Z
draft: false
---

## summary: Project overview for web-scraper

## Python Web Scraper

A high-performance utility for extracting and processing web data (headlines),
built with **BeautifulSoup4** and **Requests**.
This project demonstrates real-time data stream processing concepts.

### High-Level Features

**Data Streaming:** Uses a generator (`yield`) to extract titles one by one, avoiding unnecessary RAM usage.
**Robust HTTP&#x3A;** Includes `User-Agent` headers to simulate browser behavior and prevent server blocking.
**JSON Export:** Automatically saves extracted data into a structured format (`.json`) using `pathlib`.
**Dependency Management:** Fully managed via **Poetry** for perfect execution environment reproducibility.

### Project Structure

```text

web-scraper/
├── src/
│   └── web_scraper/
│       ├── __init__.py
│       └── main.py          # Scraping logic and JSON export
├── pyproject.toml           # Dependencies (requests, bs4)
└── README.md

```

Installation and Usage (Arch Linux)
Install DependenciesEnsure you are in the project folder and run:bashcd web-scraper
poetry install

Run the ScraperYou can execute the script directly using the configured command:bashpoetry run scrape

Usage ExampleUpon execution, the script accesses the configured source (e.g., Hacker News)
displays the top headlines in the terminal, and creates a headlines.json

file:json[
    "Show HN: A high-level folder organizer in Python",
    "Why Arch Linux is great for developers",
    "Mastering Python Generators"
]

Permissions and SafetyThe script automatically checks HTTP status codes (200 OK) and manages disk write permissions for the output file.
This project is part of a series of practical examples for mastering the Python ecosystem

License
Distributed under the MIT License
