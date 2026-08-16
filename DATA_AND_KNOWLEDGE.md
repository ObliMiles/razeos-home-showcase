# Data and Knowledge

Raze OS Home uses persisted events and structured knowledge to maintain continuity between reasoning sessions.

## Home Events

Household and reasoning events can be persisted and later consumed by UI and reasoning components.

This prevents the UI from having to regenerate historical reasoning information through an LLM.

---

## Reasoning Metadata

Reasoning action events can retain metadata such as:

- what
- why
- evidence
- result
- confidence
- correlation
- timestamp
- room
- action

---

## Decision Knowledge

Decision knowledge represents user-confirmed or user-corrected information associated with a specific reasoning context.

---

## Provenance

Knowledge and feedback should retain a relationship to the original reasoning event.

Relevant identifiers include:

```text
reasoningTaskId
correlationId
provenanceEventId
roomKey
actionKey
timestamp
This makes the origin of learned information traceable.

UI Data Flow
Persisted HomeEvent
       ↓
Reasoning Event Mapper
       ↓
Household Learning Insight
       ↓
Existing Timeline Adapter
       ↓
Household Learning Card

No new reasoning database is required for UI rendering.



---


# 9. `SECURITY.md`


Bunu özellikle koy. Alıcıya profesyonel görünür.


```markdown
# Security and Data Handling


## Source Code


This public repository does not contain the production source code.


The repository is intended as a product showcase and technical overview.


---


## Credentials


Production credentials, API keys, tokens, private configuration files, Android signing keys, and device-specific secrets are intentionally excluded.


---


## Device Information


Device identifiers and household-specific configuration should not be exposed in public documentation.


Screenshots and examples should use sanitized or fictional identifiers where appropriate.


---


## AI Safety Boundaries


The reasoning layer is not intended to override deterministic sensor truth.


AI-generated reasoning cannot independently:


- redefine physical sensor state
- invent device capabilities
- authorize arbitrary actions
- replace deterministic device integrations


Actions remain constrained by the application's existing capabilities and policy architecture.


---


## Production Configuration


The production project contains environment- and deployment-specific configuration that is intentiona