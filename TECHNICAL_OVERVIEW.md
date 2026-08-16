# RAZE OS Home — Technical Overview

## Platform

- Android
- Dedicated kiosk deployment

## Primary Language

- Kotlin

## Core Technologies / Concepts

- Android SDK
- Jetpack components
- Kotlin Coroutines
- Room
- SQLite
- WebSocket communication
- REST/API integrations
- IoT integrations
- Camera-related processing
- Persistent event storage
- Structured decision knowledge
- Kiosk controls

---

## Major Architectural Areas

### Device Integration Layer

Communicates with supported household devices and translates external events into application-level state and actions.

### Deterministic Household State

Maintains the physical-world state used by the UI, automation and reasoning context.

### Room / Context Layer

Associates available signals with household rooms and areas so the system can reason about combinations of occupancy, motion, doors, cameras, devices and time.

### Automation

Runs supported deterministic and contextual automation workflows against the available device infrastructure.

### Autonomous Reasoning

Evaluates household context, evidence, available capabilities, policies and existing decision knowledge before selecting supported actions.

### Action Bridge

Connects eligible reasoning decisions to the existing device/action infrastructure instead of granting the reasoning layer unrestricted hardware control.

### Verification

Separates action execution from confirmation of the expected physical result.

### Event Persistence

Stores household and reasoning events so historical decisions can be reconstructed without regenerating UI through an LLM.

### Feedback Pipeline

Associates user corrections with the original reasoning context and converts applicable natural-language feedback into structured information.

### Decision Knowledge

Stores scoped knowledge that future reasoning can query while keeping learned information separate from deterministic sensor truth.

### Presentation

Provides the persistent Android kiosk UI, household pages and Household Learning timeline/bubble interface.

---

## Production Scale

The real household environment currently contains approximately **48 physical devices**.

The production project contains roughly **600 source/project files**.

These numbers describe the current personal project environment and are not claims of customer deployments or commercial adoption.

---

## Architectural Principle

The most important technical boundary can be summarized as:

```text
Sensors / Devices → Physical Truth

Reasoning → Contextual Decision

Action Infrastructure → Supported Execution

Verification → Result Confirmation

Knowledge → Future Decision Context
```

Keeping those responsibilities separate is what allows the project to combine AI reasoning with real household automation without treating generated text as the physical-world authority.