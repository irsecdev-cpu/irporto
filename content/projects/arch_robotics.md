---
title: Arch Robotics
date: 2026-03-16T00:00:00.000Z
draft: false
summary: An industrial automation project integrating Computer Vision, PLC Logic, and Functional Safety.
---

## Industrial Automation & Robotics Control System

This project simulates a complete industrial production line control system, integrating Computer Vision, PLC Logic, and
Functional Safety It is specifically developed for automated production environments.

### System Architecture

The system comprises four main modules that operate concurrently:

PLC Simulator (`plc_server.py`): This is the core of the system, responsible for managing memory (registers), motor movement (Motion Control), and safety monitoring (Watchdog).
Vision System (`detect_obj.py`): Utilizes `OpenCV` to process video streams for detecting parts on the conveyor belt and sends a "Heartbeat" signal to the PLC.
HMI Panel (`hmi_panel.py`): A modern graphical user interface built with `CustomTkinter`, designed for operators to display the parts counter and alarm status in real-time.
Robot Commander (`move_robot.py`): This control script sends positioning commands (X/Y/Z) to the robotic arm.

### Safety Features (Industrial Grade)

Heartbeat & Watchdog: The Vision system emits a pulse every 100ms. If the PLC does not detect a pulse change within 2 seconds, it triggers an Emergency Stop.
Safety Latching: In the event of a failure, the system latches (locks) to prevent automatic restarting, even if the error resolves, necessitating a Manual Reset (Register 10).
Motion Interpolation: Motor movement is simulated gradually to avoid mechanical shocks (Soft Start/Stop).

### Installation & Execution (Arch Linux)

Prerequisites

Ensure that `poetry` is installed:

```bash

sudo pacman -S python-poetry

```

Run the System

```bash

poetry install
poetry run python plc_server.py

```

License
Distributed under the MIT License.
