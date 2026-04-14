---
title: My Django
date: 2026-03-17T00:00:00.000Z
draft: false
summary: A modern Django project configured for scalability and security, featuring Custom User models and Docker integration.
---

This is a modern Django implementation designed for scalability and security, utilizing a custom user model and fully containerized environments.

## Tech Stack

Framework: Django 5.x
Dependency Management: [Poetry](https://python-poetry.org)
Database: MariaDB 10.11
Infrastructure: Docker & Docker Compose
Authentication: Custom User Model with Avatar support
Styling: Custom CSS (Green Theme)

## Installation & Setup (Docker)

**Clone the repository:**

```bash

git clone `<repository-url>`
cd my_django

```

Environment Configuration (.env):
DATABASE_URL=mysql://user:password@db:3306/my_django_db
SECRET_KEY=your_secret_key_here
DEBUG=True

Launch & Initialize:

```bash

docker-compose up --build -d
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser

```

The application will be available at: `<http://localhost:8000>`

Project Structure
    core/: Main project configurations.
    users/: Custom user model (CustomUser).
    accounts/: Login, Sign Up, Profile Editing.
    media/: User-uploaded content (Avatars).
    templates/: UI layers (Green aesthetic).

Local Development (Without Docker)
If you prefer to run the project natively:

```bash

poetry install
poetry shell
python manage.py runserver

```

License
Distributed under the MIT License.
