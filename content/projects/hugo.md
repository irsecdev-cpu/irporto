---
title: My Developer Portfolio
date: 2026-03-30T00:00:00.000Z
draft: false
summary: Project overview for portofolio.
---

## My Developer Portfolio (Hugo)

This is my portfolio website built with **Hugo** using the **PaperMod** theme. The project centralizes all my applications and software experiments in a modern, fast interface.

## Tech Stack

SSG: [Hugo](https://gohugo.io) (v0.159.1+ extended)
Theme: [PaperMod](https://github.com)
Deployment: GitHub Pages / Local Disk
Format: Markdown (Goldmark compliant)

## Project Structure

`content/projects/`: Markdown files for each project (Laravel, Django, Robotics, etc.).
`assets/`: Static resources processed by Hugo (custom CSS, JS).
`static/img/`: Images and logos used in pages.
`layouts/`: Custom HTML templates for theme overrides.

## Installation & Local Development

Prerequisites

Ensure you have Hugo installed (Extended version):

```bash
sudo pacman -S hugo

```

Clone & Start

```bash

#Clone the repository
git clone <portfolio-repo-url>
cd my-portfolio
#Start the development server
hugo server -D

```

The site will be available at `<http://localhost:1313/my-portofolio/>`

### Docker Development (Recommended)

Build and start the portfolio with security hardening and healthchecks:

```bash

docker-compose up -d --build

```

License
Distributed under the MIT License
