# Raze OS Home — Architecture

## Architectural Principle

Raze OS Home separates physical-world truth, reasoning, action execution, verification, knowledge, and presentation.

The reasoning layer is intentionally not the authority for physical sensor state.

---

## High-Level Architecture

```text
Sensors / Devices / Cameras
          │
          ▼
Deterministic Device & State Layer
          │
          ▼
      Room / World State
          │
          ▼
   Autonomous Reasoning
          │
     ┌────┴────┐
     ▼         ▼
 Knowledge   Action Bridge
     │         │
     │         ▼
     │     Device Action
     │         │
     │         ▼
     │     Verification
     │         │
     └────┬────┘
          ▼
     Home Events
          │
          ▼
 Household Learning UI
          │
          ▼
      User Feedback
          │
          ▼
   Feedback Pipeline
          │
          ▼
 Decision Knowledge Store
          │
          ▼
 Future Reasoning
 
 Deterministic Truth

Physical household state is derived from deterministic integrations and state processing.

The AI/reasoning layer does not directly replace this state.

This prevents natural-language reasoning from becoming an uncontrolled source of sensor truth.

Reasoning Layer

The reasoning architecture evaluates:

current household state
available evidence
policy constraints
capabilities
previous decision knowledge
contextual information

The result can be an action candidate with an explanation and evidence.

Action Layer

Actions are passed through the existing action infrastructure.

The reasoning layer does not directly gain arbitrary access to devices.

Verification

After an action, the system can evaluate whether the expected resulting state was observed.

This distinction allows the UI to communicate whether:

the action succeeded
the expected result was not observed
the result could not be verified
Event Persistence

Reasoning events are persisted through the existing HomeEvent architecture.

A reasoning event can contain structured metadata describing the action and its context.

The UI can therefore reconstruct the reasoning card without invoking an LLM.

Household Learning Integration

The existing Household Learning page is reused as the user-facing surface for autonomous reasoning.

Reasoning action events are mapped into the existing Household Learning insight model.

No separate reasoning-history page is required.

Feedback Architecture

User feedback is connected to the original reasoning event through provenance information.

Relevant identifiers can include:

reasoningTaskId
correlationId
provenanceEventId
roomKey
actionKey

This prevents feedback from being attached to an unrelated decision.

Knowledge Scope

Decision knowledge is intentionally scoped.

A piece of feedback about one decision should not automatically become a global rule for the entire household.

UI Principle

The UI is a presentation layer over persisted state.

It should not independently invent:

device state
sensor state
capabilities
reasoning evidence

The UI displays information produced by the underlying system.



---


# 4. `AUTONOMOUS_REASONING.md`


```markdown
# Autonomous Reasoning


Raze OS Home includes an autonomous reasoning architecture designed to make context-aware decisions from available household evidence.


## Reasoning Pipeline


```text
World State
    ↓
Evidence Collection
    ↓
Context Evaluation
    ↓
Knowledge Lookup
    ↓
Policy / Capability Checks
    ↓
Action Candidate
    ↓
Action Execution
    ↓
Verification
    ↓
Home Event
    ↓
Household Learning UI
Evidence-Based Decisions

A reasoning decision can reference multiple pieces of evidence.

Examples may include:

motion state
presence state
door state
camera-derived signals
time context
existing device state
previously recorded knowledge

The reasoning explanation should describe the evidence actually available to the system.

It must not invent sensor observations.

AI Boundaries

The AI layer is not:

a sensor
a presence authority
a device capability registry
an action authorization system
a replacement for deterministic household state

This boundary is intentional.

Action Results

Reasoning events distinguish between execution and verification.

SUCCESS

The action was executed and the expected result was verified.

VERIFICATION_FAILED

The action was executed, but the expected resulting state was not confirmed.

VERIFICATION_UNKNOWN

The action was sent or attempted, but the resulting state could not be reliably verified.

Explainability

Reasoning events can preserve:

what the system decided to do
why it decided to do it
which evidence supported the decision
confidence
execution result
verification result

This information can later be displayed through the Household Learning interface.



---


# 5. `LEARNING_AND_FEEDBACK.md`


```markdown
# Learning and Feedback


Raze OS Home provides a structured feedback mechanism for autonomous decisions.


## Correct Feedback


When the user confirms that an autonomous action was correct, the decision knowledge associated with that action can be confirmed.


Repeated confirmation increases the confirmation information associated with the same scoped knowledge instead of blindly creating duplicate records.


---


## Incorrect Feedback


When the user marks an action as incorrect, the system can request an explanation.


Example:


> My mother was on the balcony, not in the room.


The feedback is associated with the original reasoning context before entering the structured feedback pipeline.


---


## Natural Language Feedback


The feedback pipeline can extract structured information from natural-language user explanations.


Possible structured information includes:


- wrong aspect
- user claim
- room
- reason
- scope
- previous decision context


The exact interpretation depends on the feedback processing pipeline and available context.


---


## Knowledge Lifecycle


Knowledge can progress through:


```text
LEARNED
   ↓
CONFIRMED


LEARNED
   ↓
CONTRADICTED


CONFIRMED / CONTRADICTED
   ↓
DEPRECATED
Narrow Scope

Feedback is intentionally scoped to the relevant reasoning context.

For example:

I was on the balcony.

does not automatically become:

The living room is always empty whenever I am on the balcony.

The system should retain contextual relationships instead of creating unrestricted household rules.

Future Reasoning

Previously recorded decision knowledge can be queried by subsequent reasoning sessions.

The knowledge is used as contextual information rather than replacing deterministic sensor truth.



---


# 6. `SMART_HOME_INTEGRATIONS.md`


Burada **gerçekten kullandığın entegrasyonları** anlatacağız; olmayanı eklemeyeceğiz.


```markdown
# Smart Home Integrations


Raze OS Home is designed to operate as a central Android-based interface for connected household devices.


## eWeLink


The application integrates with eWeLink-connected household devices and can process device events such as relay, motion, door, and presence-related signals depending on the device.


Examples include:


- smart relays
- lights
- motion sensors
- door sensors
- presence sensors
- cameras


---


## Xiaomi


Xiaomi devices can be integrated into the household environment and exposed through the dedicated Xiaomi interface.


The exact available capabilities depend on the connected Xiaomi hardware and integration configuration.


---


## Camera


Camera-related information can contribute to household context and presence detection.


Camera-derived signals remain distinct from deterministic sensor state.


---


## Device State


Device state can be used for:


- UI status
- room context
- automation
- reasoning evidence
- action verification


---


## Hardware-Dependent Capabilities


The exact behavior of the system depends on the connected devices.


Raze OS Home does not assume that every room has identical sensors or capabilities.