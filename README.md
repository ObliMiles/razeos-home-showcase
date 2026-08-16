# Raze OS Home

## Autonomous Smart Home Operating System for Android Kiosks

Raze OS Home is a dedicated Android-based smart home control and automation platform designed for wall-mounted kiosk devices.

The project combines smart home control, real-time device and sensor monitoring, camera-based presence information, room awareness, automation, household activity analysis, autonomous reasoning, verification, learning, and user feedback into a single persistent interface.

Unlike a conventional smart home dashboard, Raze OS Home is designed to operate as a dedicated home interface that can continuously observe available household signals, reason about context, execute supported actions, verify outcomes, and retain structured knowledge from user feedback.

---

## What Makes Raze OS Home Different

Raze OS Home is built around a separation between deterministic household truth and the reasoning layer.

Sensors and deterministic device integrations remain the source of truth for physical state.

The reasoning layer does not directly redefine sensor truth, invent device capabilities, or authorize actions outside the system's available capabilities.

This separation allows autonomous reasoning to operate without turning the AI layer into an uncontrolled source of household state.

---

## Core Capabilities

- Android-based dedicated smart home kiosk
- Persistent wall-mounted home interface
- Smart device monitoring and control
- eWeLink device integration
- Xiaomi device integration
- Camera and presence-related signals
- Room-level household state
- Real-time device status
- Household activity monitoring
- Financial / household tracking interfaces
- Learned household patterns
- Autonomous reasoning layer
- Action execution and verification
- Reasoning event persistence
- Evidence-based reasoning explanations
- Confidence information
- User feedback on autonomous decisions
- Structured learning from feedback
- Narrow-scope decision knowledge
- Knowledge lifecycle management
- Persistent reasoning and household events

---

## User Interface

The kiosk interface is organized into dedicated pages for different areas of the household system.

The current page topology includes:

1. eWeLink
2. Camera
3. Xiaomi
4. Dreame
5. Finance / Household Tracking
6. Household Learning
7. Telegram Archive
8. Autonomous Reasoning

The exact UI and device capabilities depend on the connected household environment.

---

## Autonomous Reasoning

Raze OS Home contains an autonomous reasoning architecture designed to evaluate available evidence and context before taking supported actions.

A reasoning cycle can involve:

1. Observing available household signals
2. Building a deterministic household state
3. Evaluating contextual information
4. Considering existing decision knowledge
5. Selecting an eligible action
6. Executing the action
7. Verifying the resulting state
8. Persisting the reasoning event
9. Presenting the result to the user through the household learning interface

Reasoning events can include:

- action
- explanation
- evidence
- confidence
- execution result
- verification result
- provenance information

---

## Learning and Feedback

Users can review autonomous decisions and provide feedback.

A decision can be marked as correct or incorrect.

Incorrect decisions can optionally receive natural-language feedback from the user.

The feedback pipeline converts the user's explanation into structured knowledge while maintaining a narrow scope around the original reasoning context.

Knowledge can progress through lifecycle states such as:

LEARNED → CONFIRMED → CONTRADICTED → DEPRECATED

The purpose is not to turn a single user statement into a global household rule.

Instead, learned information remains associated with relevant context such as:

- room
- action
- trigger
- reasoning task
- correlation
- provenance

---

## Architecture

The project is structured into separate layers for:

- deterministic household state
- device integrations
- event persistence
- reasoning
- action execution
- verification
- knowledge
- feedback
- user interface

This separation allows individual subsystems to evolve without making the reasoning layer responsible for physical-world truth.

See:

- [Architecture](ARCHITECTURE.md)
- [Autonomous Reasoning](AUTONOMOUS_REASONING.md)
- [Learning and Feedback](LEARNING_AND_FEEDBACK.md)

---

## Technology

The project is an Android application built primarily around Kotlin and the Android ecosystem.

Major technologies and concepts include:

- Kotlin
- Android
- Jetpack components
- Coroutines
- Room
- SQLite
- WebSocket communication
- REST/API integrations
- IoT device integrations
- Camera-related processing
- persistent event storage
- structured knowledge storage

---

## Intended Use

Raze OS Home is suitable for:

- smart home enthusiasts
- IoT developers
- Android developers
- automation developers
- kiosk applications
- residential automation systems
- AI-assisted home automation research
- developers looking for an existing smart home reasoning foundation

---

## Project Status

Raze OS Home is a functioning real-world project developed and tested on Android kiosk hardware.

The project has been developed iteratively around actual smart home devices, sensors, cameras, automation scenarios, and household workflows.

---

## Source Code Availability

This repository is a public showcase and technical documentation repository.

The production source code is intentionally not included here.

The complete project, including its production source code, is available as a separate acquisition.

---

## Acquisition

The complete project can be acquired as a full software project.

The exact scope of the sale, source code, project files, documentation, and transfer terms are provided separately to interested buyers.

For acquisition inquiries, contact the project owner through the marketplace where this project is listed.