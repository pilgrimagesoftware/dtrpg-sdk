## Purpose
Define which parts of SDK behavior come from the shared API specification and which parts are intentionally implemented by hand so language SDKs evolve consistently.

## Requirements

### Requirement: SDK generation boundaries must be defined centrally
The SDK meta-repository MUST define what behavior is generated from the shared API specification and what behavior is implemented manually in each language SDK.

#### Scenario: Adding new API surface area
- **WHEN** the API specification gains new operations or models
- **THEN** maintainers can determine which parts are expected to be generated and which parts require handwritten language-specific wrappers

### Requirement: Shared API inputs must remain aligned across SDKs
The SDK meta-repository MUST treat the shared API specification as the common contract source for generated client behavior.

#### Scenario: Updating the shared API submodule
- **WHEN** the shared API specification is updated in the SDK meta-repository
- **THEN** downstream SDK repositories use that shared contract as the basis for regeneration and adaptation
