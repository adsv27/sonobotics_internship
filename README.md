# Full-Stack Internal Fleet Management & Telemetry Platform

**TypeScript** · **React** · **Node.js/Express** · **Python** · **PostgreSQL** · **systemd**

A web application and distributed backend platform designed for central device administration, event queue management, data persistence, and interactive data visualization. Developed during a software engineering internship at Sonobotics.

> Note on Source Code: Source code and internal architecture details are confidential under intellectual property agreements. This writeup outlines full-stack software development methodologies, user interface design, and testing frameworks.
>
> Contact: Aditya Sivaraman (adityasivaraman07 [at] gmail [dot] com)

---

## What It Does

The platform connects remote edge services, local gateway workers, a central REST API server, and an administrative web dashboard to streamline central operations, data collection, and device configuration.

| Component | Stack | Role / Description |
| :--- | :--- | :--- |
| Edge Service Module | Python, systemd | Local service agent running background tasks, payload generation, and network requests. |
| Gateway Receiver | Python | Intermediate service layer that processes incoming edge payloads and proxies structured requests to the backend REST API. |
| Application Server | Node.js, Express, PostgreSQL | Central REST API server managing authentication, configuration queues, data persistence, and database logging. |
| Administrative UI | React, TypeScript, Yarn | Web dashboard providing event management, status monitoring, and interactive data chart visualization. |

---

## Software Architecture & Data Flow

The software stack utilizes a decoupled, client-server model to ensure reliable state management and administrative control across distributed services.

### 1. Service Provisioning & Configuration Dispatch
When a new service initializes, it registers via the gateway layer. The gateway validates client credentials with the database and returns current operating parameters and configuration profiles.

### 2. Event Logging & State Verification
Connected clients periodically report operational state updates. The application server validates received telemetry against backend records to track service status and log operational events.

---

## Technical Features & Subsystems

### Web Dashboard & Automated Testing Framework
- End-to-End Automated Testing Framework: Built an integrated automation test suite. Replaced manual, single-iteration testing workflows with a multi-cycle execution engine capable of running continuous end-to-end system tests from a single initial setup.
- Session Management: Implemented session-aware administrative controls for service registration windows.
- Interactive Dashboard Interface: Built a 24-hour visual event grid for configuring, revising, and tracking system execution logs.
- High-Density Data Visualization: Integrated interactive time-series charts featuring debounced pan/zoom controls and dynamic dataset downsampling for performant UI rendering.
- UI/UX Enhancements: Designed a responsive layout with collapsible navigation panels, persistent form state management, and real-time status feeds.

### Backend Services & Database Architecture
- Data Persistence Layer: Schema design in PostgreSQL for managing client registrations, revision histories, job logs, and time-series telemetry datasets.
- Database Logging: Added structured query logging and server terminal outputs to streamline backend request verification during integration testing.

### Edge Environment Integration
- Background Service Management: Configured and deployed Linux background processes using systemd units and log monitoring tooling.
- Integration Testing: Executed hardware-in-the-loop and software integration tests to verify cold-boot initializations and automated service startup routines.

---

## Future Enhancements

- Peripheral Auto-Discovery: Extend the registration workflow to automatically detect connected hardware peripherals and validate them against central database records.

---

## Project Context

Developed as part of a software engineering internship at Sonobotics.

Contact: Aditya Sivaraman (adityasivaraman07 [at] gmail [dot] com)
