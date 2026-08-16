# Raze OS Home — Features

## Smart Home Control

Raze OS Home provides a dedicated interface for monitoring and controlling connected household devices.

The system is designed around persistent kiosk operation, allowing the Android device to function as a permanent household control panel.

---

## Device Monitoring

Connected devices can expose their current state to the application.

Examples include:

- relays
- lights
- switches
- sensors
- cameras
- household devices

Device state is used as part of the deterministic household state and can also become evidence available to the reasoning layer.

---

## Room Awareness

Household information is organized around rooms and household areas.

The system can combine available signals to determine contextual room state.

Depending on available devices, these signals can include:

- motion
- presence
- door state
- camera information
- device state
- other deterministic household events

A room without a dedicated presence sensor can therefore use other available evidence, while rooms with stronger presence signals can benefit from those signals directly.

---

## Autonomous Actions

The reasoning architecture can identify situations where a supported action may be appropriate.

Actions are executed through the existing device/action infrastructure rather than allowing the reasoning layer to directly manipulate arbitrary hardware.

---

## Action Verification

An important distinction is maintained between:

- action requested
- action executed
- action verified

A command being sent does not automatically mean that the physical result has been confirmed.

The system can distinguish outcomes such as:

- SUCCESS
- VERIFICATION_FAILED
- VERIFICATION_UNKNOWN

---

## Evidence

Reasoning decisions can retain the evidence used to reach the decision.

This allows the user to inspect why an action was taken rather than receiving only a generic AI-generated explanation.

---

## Confidence

Reasoning events can include a confidence value associated with the decision.

Confidence is presented as supporting information rather than being treated as a replacement for deterministic sensor truth.

---

## Household Learning

The Household Learning interface presents persisted household patterns and autonomous reasoning events.

Users can review:

- recently learned information
- confirmed decisions
- contradicted decisions
- verification results
- confidence
- previous confirmations

---

## User Feedback

Users can provide feedback about autonomous decisions.

Correct feedback can confirm an associated decision.

Incorrect feedback can request an explanation from the user.

Natural-language feedback can then be processed by the existing feedback pipeline.

---

## Knowledge

The system maintains structured decision knowledge rather than simply incrementing a generic "correct" counter.

Knowledge can retain relationships to:

- room
- action
- trigger
- context
- reasoning task
- correlation
- provenance

This makes subsequent reasoning capable of considering previous user feedback without treating it as universal household truth.

---

## Persistent Events

Reasoning and household events are persisted so the UI can display historical decisions without requiring an LLM call every time the page is opened.

---

## Kiosk Operation

The application is designed for dedicated Android hardware.

The kiosk interface can remain active as a permanent household dashboard while protecting the underlying Android environment from normal user interaction.

---

## Performance

The system is designed to avoid generating every UI card through a fresh AI request.

Persisted events and structured metadata can be mapped directly into UI representations.

This reduces unnecessary inference and network activity.