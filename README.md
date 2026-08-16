# RAZE OS Home

## A Real Smart Home Operating System — Not Another Dashboard

RAZE OS Home is a complete Android-based smart home operating system designed for a dedicated wall-mounted kiosk.

It was built for one real household and evolved into a system that connects smart devices, sensors, cameras, room context, automation, security, autonomous reasoning, action verification and household learning inside one persistent Android application.

This repository is a **public showcase and technical due-diligence package**. The production source code is intentionally not published here.

> **The interesting part is not that it can turn a light on. The interesting part is that the house can give the system enough context to decide when it should.**

---

## What Is Being Sold?

The complete project and production source code are available for an **exclusive acquisition**.

The intended transfer allows the buyer to modify, rebrand, commercialize, redistribute or sell the resulting product as they choose. The seller does not intend to retain a continuing ownership claim or reuse the sold project after an exclusive transfer. Final legal terms are established in the purchase agreement.

The public repository does not contain production credentials, private configuration, signing keys or the production source tree.

**Asking price: US$12,500**

---

## Why It Is Different

Most smart-home applications are dashboards: the user tells the system what to do and the system executes it.

RAZE OS Home was developed around a broader idea: the home can observe context, connect information from different systems, make supported decisions, act, verify the result and learn from user feedback.

The architecture deliberately separates deterministic physical-world truth from reasoning. Sensors and device integrations establish household state; reasoning evaluates context and supported capabilities; actions pass through the existing action infrastructure; results can be verified; feedback can become scoped decision knowledge.

```text
Real household signals
        ↓
Deterministic household state
        ↓
Context + evidence + knowledge
        ↓
Autonomous reasoning
        ↓
Supported action
        ↓
Real device
        ↓
Verification
        ↓
Persisted event
        ↓
User feedback
        ↓
Scoped knowledge
        ↓
Future reasoning
```

The current implementation has reached the **reasoning + real action + verification + learning** stage.

---

## Real-World Scale

The current household environment contains approximately **48 physical devices** across the integrated ecosystem.

The production Android project is roughly **600 source/project files** in size and was developed incrementally through sustained real-world use.

The project has not previously been commercially distributed. There are no fabricated customer, revenue or market-adoption claims behind this listing.

---

## Working Integration Surface

The current implementation includes working integrations and workflows around:

- eWeLink
- Sonoff devices
- cameras / RTSP workflows
- human / presence detection
- Telegram
- Xiaomi
- Dreame
- voice-assistant functionality
- security workflows
- occupancy / room awareness
- automation
- autonomous reasoning
- action verification
- household learning
- natural-language feedback
- structured decision knowledge

The exact behavior of a feature depends on the connected hardware, permissions and configuration.

---

## Five Real Household Examples

### Entrance security

Human detection at a configured entrance can trigger camera evidence and a Telegram notification.

### Contextual automation

Where the required infrastructure exists, humidity can be evaluated together with other device-state context before an automation decision is made.

### Empty room + active device

Room occupancy context and active device state can become combined evidence for a supported autonomous action.

### Dreame cleaning timing

Room/door context can cause cleaning to be delayed while relevant doors are closed, with the system reassessing for a better opportunity later.

### Overnight security memory

A configured exterior-door event during night hours can be retained as security context and surfaced later.

These are examples from the actual household environment, not hypothetical feature ideas.

---

## Security

The application includes working security flows around:

- face recognition / authorization
- face verification for sensitive operations
- camera human detection
- Telegram security notifications
- image/evidence delivery
- emergency countdowns
- phone-call flows
- cancellation evidence
- security context
- occupancy/presence

---

## Learning and Feedback

Autonomous decisions can be reviewed by the user.

A correct decision can be confirmed. An incorrect decision can request a natural-language explanation. The feedback is linked to the original reasoning context and processed into structured, narrow-scope decision knowledge.

The knowledge layer can influence future reasoning without replacing deterministic sensor truth.

---

## Kiosk Experience

The application is designed for a continuously available wall-mounted Android display.

The showcase includes surfaces for eWeLink, Camera, Xiaomi, Dreame, Finance/household tracking, Household Learning, Telegram/security information, autonomous reasoning and agent/system functionality.

See `screenshots/` and `RazeOsHome.pptx` for the visual product overview.

---

## Why Buy Instead of Building It?

Because the difficult part is not another Android screen.

The difficult part is making hundreds of components, integrations and state flows cooperate over a long-running real household workflow.

This project already contains the foundation for Android kiosk operation, IoT integrations, device state, cameras, room awareness, security, automation, reasoning, action execution, verification, learning, feedback and structured knowledge.

> **You can build your own smart home operating system. The expensive part is making all the wires talk to each other. This one already does.**

---

## Public Showcase Contents

- [Features](FEATURES.md)
- [Architecture](ARCHITECTURE.md)
- [Data and Knowledge](DATA_AND_KNOWLEDGE.md)
- [Kiosk and UI](KIOSK_AND_UI.md)
- [Technical Overview](TECHNICAL_OVERVIEW.md)
- [Smart Home Integrations](SMART_HOME_INTEGRATIONS.md)
- [Real-World Scenarios](REAL_WORLD_SCENARIOS.md)
- [Buyer Due Diligence](BUYER_DUE_DILIGENCE.md)
- [Security](SECURITY.md)
- [Sale](SALE.md)
- [Presentation](RazeOsHome.pptx)

## Screenshots

See `screenshots/` for current application captures.

---

## Important Disclosure

RAZE OS Home is a real personal project developed for the creator's own household. It has not been commercially distributed. The showcase makes no claims about customers, revenue, market share or universal hardware compatibility.

The value being offered is the existing engineering work, architecture, source code, integrations, real-world workflows and transferable project foundation.