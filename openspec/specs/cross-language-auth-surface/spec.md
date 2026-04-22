## Purpose
Define the shared authentication concepts that every language SDK must preserve even when each implementation uses its own language-native ergonomics.

## Requirements

### Requirement: Authentication concepts must be consistent across SDKs
The SDK meta-repository MUST define shared expectations for authentication concepts exposed by all language SDKs.

#### Scenario: Comparing authentication behavior between SDKs
- **WHEN** maintainers review two language SDKs that implement authentication
- **THEN** they can map both implementations to the same shared authentication concepts

### Requirement: Language-specific ergonomics may refine but not contradict shared auth behavior
Each language SDK MAY expose authentication using idioms that fit the language, but it MUST preserve the shared semantics defined at the SDK meta-repository level.

#### Scenario: Adapting auth flows for a specific language
- **WHEN** a language SDK adds convenience wrappers or idiomatic method names around authentication
- **THEN** those wrappers still preserve the shared authentication lifecycle and meanings
