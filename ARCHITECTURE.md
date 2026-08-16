# RAZE OS Home — Architecture

## Architectural Goal

RAZE OS Home is built as a household operating layer rather than a collection of unrelated device screens.

The central design principle is a separation between **deterministic physical-world truth** and **autonomous reasoning**.

Sensors and device integrations establish what the household is actually reporting. Reasoning can interpret that state, combine context, consult previously learned decision knowledge and select supported actions. The reasoning layer is not allowed to become the source of physical sensor truth.

This boundary is one of the most important architectural properties of the project.

---

## High-Level Flow

```text
Physical Devices / Sensors / Cameras
                │
                ▼
      Device Integration Layer
                │
                ▼
     Deterministic Household State
                │
        ┌───────┴────────┐
        │                │
        ▼                ▼
   Automation       Reasoning Context
                         │
                         ▼
                  Knowledge Lookup
                         │
                         ▼
                Policy / Capability
                    Evaluation
                         │
                         ▼
                  Action Candidate
                         │
                         ▼
                   Action Bridge
                         │
                         ▼
                    Real Device
                         │
                         ▼
                    Verification
                         │
                         ▼
                    Home Event
                         │
                         ▼
               Household Learning UI
                         │
                         ▼
                  User Feedback
                         │
                         ▼
             Structured Decision Knowledge
                         │
                         └──────► Future Reasoning
```

---

## Deterministic Household Truth

The application maintains a deterministic representation of available household state.

Examples include:

- relay state
- switch state
- motion state
- door state
- presence / occupancy signals
- camera-derived human detection
- device availability
- room association
- other integration-specific state

The UI and reasoning systems consume this information rather than inventing it.

A reasoning explanation may describe evidence from the state, but it does not get to redefine what a physical sensor reported.

---

## Device Integration

The real household implementation includes integrations and workflows around eWeLink/Sonoff devices, cameras and RTSP-related processing, Xiaomi, Dreame, Telegram and other application services.

The integration layer is responsible for translating external device events and capabilities into application-level state and actions.

The production environment currently contains approximately **48 physical devices**.

---

## Room and Context Layer

Household information is associated with rooms and areas so that device state can become contextual information.

For example, a room can be evaluated using combinations of:

- occupancy/presence evidence
- motion
- door state
- camera evidence
- active devices
- time context
- other household events

Rooms do not all have identical hardware. Stronger evidence can be used where stronger sensors are available, while other rooms can fall back to their available deterministic signals.

---

## Autonomous Reasoning

The current reasoning architecture has progressed beyond generating explanations alone. In the active implementation it can participate in:

1. Context observation
2. Evidence evaluation
3. Existing decision-knowledge lookup
4. Action selection within available capabilities
5. Real action execution
6. Verification of the expected outcome
7. Event persistence
8. User review and feedback
9. Structured learning for future reasoning

This is the intended **reasoning + action + verification + learning** loop.

---

## Action Boundary

The reasoning layer does not receive unrestricted arbitrary device access.

A reasoning decision is routed through the application's existing action infrastructure and the capabilities/policies already available to the system.

This matters because an LLM or reasoning component should not be treated as a direct hardware authorization layer.

---

## Verification

Execution and verification are separate concepts.

A command being issued does not automatically prove that the physical-world result occurred.

Reasoning events can preserve outcome information such as:

- successful execution and verification
- execution followed by failed verification
- execution where the expected result could not be reliably verified

This distinction is surfaced to the learning/reasoning history rather than being hidden behind a generic success message.

---

## Event Persistence

Household and reasoning events are persisted through the application's event architecture.

Reasoning action events can retain structured metadata including:

- what the system did
- why it did it
- supporting evidence
- result
- confidence
- room
- action key
- correlation/provenance
- timestamp

The Household Learning interface can therefore reconstruct reasoning cards from persisted data without asking an LLM to regenerate historical cards every time the page opens.

---

## Learning and Feedback

The existing Household Learning surface is reused for autonomous reasoning events.

A user can confirm a decision or mark it incorrect. Incorrect feedback can request a natural-language explanation and associate that explanation with the original reasoning context.

The resulting structured knowledge remains scoped to the relevant decision context instead of becoming an unrestricted household rule.

Typical provenance dimensions include:

- room
- action
- reasoning task
- correlation
- provenance event
- timestamp

---

## Knowledge Boundary

Decision knowledge influences future reasoning, but it does not replace deterministic sensor truth.

For example, a learned preference about an action in one room should not be allowed to rewrite a sensor's current state.

This gives the system two different concepts:

```text
What the house is reporting now
        ≠
What the system has learned about decisions
```

Both can be useful, but they have different authority.

---

## UI Principle

The UI is a presentation layer over persisted application state.

It should display:

- actual device state
- actual room context
- persisted reasoning events
- verification outcomes
- structured feedback

It should not independently invent device capabilities, sensor state or reasoning evidence.

---

## Project Scale

The production Android project is a large codebase of roughly **600 source/project files**. Its architecture has been developed incrementally around an actual household environment and long-running device workflows.

The public showcase intentionally documents the architecture without publishing the production source tree or credentials.