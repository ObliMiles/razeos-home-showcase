# Smart Home Integrations

RAZE OS Home was developed around a real household rather than a simulated device lab. The current environment contains approximately **48 physical devices** across the integrated ecosystem.

## eWeLink / Sonoff

The production environment uses eWeLink-connected devices including relays, switches and sensors. Device events can contribute to deterministic state, room context, automation and reasoning evidence.

Examples include:

- relay state
- motion
- door state
- presence-related signals
- device availability
- device actions

## Cameras / RTSP

Camera workflows provide visual and human-detection context. Camera events can participate in security workflows and household presence reasoning.

A configured entrance human-detection event can trigger camera evidence and Telegram notification workflows.

## Xiaomi

Xiaomi devices are exposed through the dedicated Xiaomi area of the application and can participate in the wider household environment according to their supported capabilities.

## Dreame

Dreame robot-vacuum functionality is integrated into the household automation environment.

One real scenario uses room/door context to avoid starting a cleaning cycle while relevant rooms are inaccessible, reassessing later for a better opportunity.

## Telegram

Telegram is used as an operational notification channel, including security alerts and evidence delivery.

## Voice Interaction

Voice-assistant functionality provides another entry point into the same household environment, allowing voice requests to participate in existing device, room and prepared-rule workflows.

## Security / Occupancy

Security and occupancy functionality combines the available camera, sensor, identity and household-context infrastructure.

## Integration Boundary

RAZE OS Home does not claim universal compatibility with arbitrary hardware. The delivered product contains the integrations and workflows already implemented; a buyer can extend the system for additional hardware after acquisition.

The public repository intentionally omits credentials, private configuration and device-specific secrets.