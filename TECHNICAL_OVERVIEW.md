# Technical Overview

## Platform

Android

## Primary Language

Kotlin

## Core Technologies

- Android SDK
- Jetpack
- Room
- SQLite
- Kotlin Coroutines
- WebSocket communication
- REST/API integrations
- IoT integrations

## Architectural Areas

### Device Integration

Responsible for communication with connected smart home devices.

### World State

Represents deterministic information about the household environment.

### Reasoning

Evaluates contextual information and produces eligible action decisions.

### Action Bridge

Connects reasoning decisions to supported device actions.

### Feedback

Processes user feedback about previous decisions.

### Knowledge

Stores structured decision knowledge for future reasoning.

### Event Persistence

Stores household and reasoning events.

### Presentation

Provides the persistent kiosk interface and Household Learning timeline.