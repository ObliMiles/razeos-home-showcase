# RAZE OS Home — Data, Events and Knowledge

RAZE OS Home treats household events, reasoning decisions and learned information as different but connected forms of data.

The goal is continuity: a decision made today can remain understandable tomorrow, and user feedback can become useful to future reasoning without becoming an uncontrolled household rule.

---

## Home Events

Household and reasoning events are persisted through the application's event architecture.

A reasoning action event can retain structured metadata such as:

- what the system did
- why it acted
- evidence available at decision time
- execution result
- verification result
- confidence
- room
- action key
- correlation/provenance
- timestamp

This makes the event independently inspectable after the action has finished.

---

## Reasoning → UI

The production flow is conceptually:

```text
Reasoning Action
      ↓
Home Event
      ↓
Reasoning Event Mapper
      ↓
Household Learning Insight
      ↓
Existing Timeline / Bubble UI
```

The UI does not need to call an LLM merely to recreate an old reasoning card.

---

## Provenance

Feedback must remain attached to the decision that generated it.

Relevant provenance dimensions include:

- reasoning task
- correlation ID
- original event
- room
- action key
- timestamp

This prevents a correction about one action from accidentally being applied to an unrelated action.

---

## Decision Knowledge

Decision knowledge represents information learned from the user's interaction with autonomous decisions.

It can represent confirmation, contradiction, contextual preferences and other structured information produced by the feedback pipeline.

The knowledge layer is intentionally separate from deterministic household truth.

```text
Current sensor/device state
        ≠
Learned decision knowledge
```

Knowledge can influence future reasoning, but it should not rewrite what a physical sensor currently reports.

---

## Feedback Lifecycle

A typical correction can follow this path:

```text
User reviews reasoning card
        ↓
Correct / Incorrect
        ↓
Original reasoning context recovered
        ↓
Natural-language feedback (when needed)
        ↓
Feedback processing pipeline
        ↓
Structured decision knowledge
        ↓
Future reasoning lookup
```

The system is designed to keep this knowledge scoped around the relevant room/action/reasoning context.

---

## Why This Matters

A conventional automation system often stores a rule such as:

> If X happens, do Y.

RAZE OS Home can additionally retain the context of why an autonomous decision was made, whether the expected result was verified, and what the user subsequently thought about that decision.

That provides a foundation for an adaptive household system rather than a static collection of automation rules.