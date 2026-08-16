# RAZE OS Home — Real-World Scenarios

The strongest way to evaluate this project is to look at what it does with real household context.

These scenarios describe workflows implemented for the creator's actual home environment.

## Entrance Security

A human detected at a configured entrance can trigger a security workflow that captures current camera evidence and sends a notification through Telegram.

The point is not merely that a camera detects a person. The detection becomes an event that can drive a larger household workflow.

## Contextual Humidity Automation

Where the required device infrastructure exists, room humidity can be considered together with other device states and household context before an automation decision is made.

This demonstrates the difference between reading a sensor and reasoning from multiple signals.

## Empty Room + Active Device

The system can combine occupancy/room information with device state.

If a room is considered unoccupied while a supported device remains active, that state can become evidence for an appropriate action.

## Dreame Cleaning Timing

The robot vacuum workflow can observe whether relevant room doors are closed. Instead of blindly starting the robot, the system can postpone cleaning and reassess the household until a more suitable time to clean the home.

## Overnight Security Memory

A configured exterior-door event during night hours can be retained as household security information and surfaced later, allowing an overnight event to become part of the next relevant household interaction.

## Guest / Room Context

When a guest arrives in a configured room, movement and room context can participate in prepared rules. For example, the environment can be prepared for a media scenario according to previously configured behavior.

## Why These Scenarios Matter

Each scenario uses the same underlying idea:

```text
Signal A + Signal B + Context
             ↓
      Household state
             ↓
        Decision
             ↓
          Action
             ↓
       Verification
```

That shared architecture is what turns a set of device integrations into a household operating system.

## Scope Disclosure

These are real project behaviors, not claims of universal compatibility. Exact operation depends on the configured household hardware, permissions, credentials and integration capabilities.