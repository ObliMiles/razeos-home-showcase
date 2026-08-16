# RAZE OS Home — Kiosk and User Interface

## The Product Is Designed to Live on the Wall

RAZE OS Home is not primarily a phone dashboard.

It is designed for a dedicated Android device that can remain mounted in the home and act as a persistent household interface.

The kiosk experience is therefore built around continuous availability, large touch targets, persistent navigation and screen-protection behavior appropriate for unattended operation.

---

## Main Household Surfaces

The showcase captures the major application areas, including:

- eWeLink device control and state
- Camera
- Xiaomi
- Dreame
- Finance / household tracking
- Household Learning
- Telegram archive / security information
- Autonomous reasoning
- Agent/system functionality

The exact page capabilities depend on the connected household environment.

---

## Household Learning UI

Household Learning is not merely a statistics screen.

It is also the user-facing surface for autonomous reasoning history.

Reasoning cards can present:

- the action taken
- the room/context
- why the system acted
- evidence used
- confidence
- execution outcome
- verification outcome
- provenance
- user feedback state

The same existing timeline/bubble infrastructure is reused rather than maintaining a second parallel reasoning-history UI.

---

## Feedback Interaction

Users can review an autonomous decision and mark it as correct or incorrect.

For an incorrect decision, the application can ask the user to explain what was wrong in natural language. That explanation is associated with the original reasoning event before entering the structured feedback pipeline.

The resulting knowledge can then be considered by future reasoning without modifying deterministic sensor truth.

---

## Screen Protection

Because the device is intended to remain active in the home, the application includes screen-protection behavior for periods of inactivity.

The kiosk experience is designed so transient interaction surfaces do not become the permanent state of the display when the device transitions into its unattended/screen-protection state.

---

## Visual Showcase

The `screenshots/` directory contains current UI captures of the major application surfaces.

The repository also includes `RazeOsHome.pptx` as a presentation-oriented overview for prospective buyers.