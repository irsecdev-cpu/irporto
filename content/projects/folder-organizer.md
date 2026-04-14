---
title: Folder Organizer
date: 2026-03-17T00:00:00.000Z
draft: false
summary: Project overview for folder-organizer.
---

Folder Organizer CLI
A high-performance Python automation utility designed to keep your Downloads folder clean and organized.
This project leverages advanced programming concepts and is managed using Poetry.
High-Level Features
Optimized Performance: Utilizes Python sets for (O(1)) lookups and generators for minimal memory footprint.
Custom Decorators: Includes a @monitor_performance decorator for precise execution time tracking.
Modern Path Management: Built with pathlib for seamless cross-platform compatibility (Linux, Windows, macOS).
Poetry Integration: Configured as a system script via project.scripts.

Project Structure

```text

folder-organizer/
├── src/
│   └── folder_organizer/
│       ├── init.py
│       ├── main.py          # Main logic and entry-point
│       └── decorators.py    # Performance monitoring decorators
├── pyproject.toml           # Poetry configuration and dependencies
└── README.md

```

Installation & Usage
Prerequisites
Ensure you have Poetry installed on your system (e.g., on Arch Linux):

```bash

sudo pacman -S python-poetry

```

Setup
Clone the repository and install dependencies in an isolated virtual environment:bashcd folder-organizer

```bash

poetry install

```

Running the UtilityYou can run the organizer directly using the command defined in pyproject.toml:

```bash

poetry run organize

```

Configuration & Categories
The script automatically sorts files into the following categories:
Images: .jpg, .png, .webp, etc.Documents: .pdf, .docx, .txt, etc.
Archives: .zip, .7z, .tar.gz, etc.
Executables: .exe, .app
image, .deb, etc.

Sample Output

```bash

--- Starting cleanup in: /home/user/Downloads ---
Moved: final_report.pdf -> Documents/
Moved: vacation.jpg -> Images/

Total files processed: 2
Done! Cleanup took 0.0124 seconds.

```

License
Distributed under the MIT License
