# Security and Public Repository Boundary

This repository is a public showcase, not the production source repository.

## Intentionally Excluded

The public repository does not contain:

- production API keys
- access tokens
- passwords
- private configuration
- Android signing keys
- device-specific credentials
- private household secrets
- production source code

## Screenshots

Screenshots are provided to demonstrate the UI and system surfaces. Device-specific identifiers and secrets should not be treated as part of the public product documentation.

## Buyer Delivery

The production project delivered to the buyer is transferred separately from this public showcase. Credentials and environment-specific configuration must be replaced or reconfigured for the buyer's deployment.

## Reasoning Safety Boundary

The reasoning layer is not intended to redefine deterministic physical state or act as an unrestricted hardware authorization layer.

The architecture separates:

```text
Physical truth
      ↓
Reasoning
      ↓
Supported action infrastructure
      ↓
Verification
```

This distinction is important for a system intended to operate around real household devices.

## Buyer Responsibility

After transfer, the buyer is responsible for securing their own credentials, API accounts, network environment, devices and deployment infrastructure.