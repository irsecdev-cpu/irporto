---
title: My React
date: 2026-03-20T00:00:00.000Z
draft: false
summary: Project overview for my_react.
---

Social OS Dashboard: From Junior to Enterprise
A professional demonstration project designed to showcase the transition from a monolithic structure to a scalable, layered architectural pattern in React.

Architectural Overview
The project implements a Layered Architecture, strictly separating concerns to decouple business logic from the UI:

Presentation Layer (UI): Atomic components styled with Tailwind CSS v4 (Oxide Engine).
Business Logic Layer: Logic decoupled into Zustand Stores with built-in persistence.
Data Access Layer (DAL): Dedicated services in src/services for external API communication.
Quality Assurance: Comprehensive unit testing suite powered by Vitest and JSDOM.

Key Features

Global State Persistence: Application state survives page refreshes via the persist middleware.
Real-time Analytics: Integrated click-tracking system within the global data flow.
Intelligent Auto-Sorting: The UI dynamically reorders elements using useMemo, promoting the most accessed links to the top.
Unit-Tested Store: Business logic is 100% covered by tests (e.g., addLink, trackClick).
Data Integrity: Store-level validation to prevent rendering errors and ensure data consistency.

Project Structure
text

src/
├── components/      # Atomic UI (Common & Layout)
├── features/        # Business modules (Dashboard, AddLinkForm)
├── store/           # State Management & Store Tests (Zustand + Vitest)
├── services/        # API calls and raw data processing
├── test/            # Testing infrastructure (setup & mocks)
└── App.jsx          # Main orchestrator and sorting logic

Getting Started

Install dependencies:

```bash
npm install
```

Run unit tests:

```bash
npm run test
```

Launch the Dashboard:

```bash
npm run dev
```

Testing the Evolution
To observe the robustness of this architecture:

Vitest Suite: Run tests to see how trackClick logic is mathematically validated.
Analytics Engine: Click a link and watch the counter increase as the card automatically climbs the list.
State Debugging: Use Redux DevTools (compatible with Zustand) to monitor link/track_click actions in real-time.

License
Distributed under the MIT License.
