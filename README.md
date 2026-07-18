# DriveThruRPG SDK

Meta-repository organizing SDK implementations of the [DriveThruRPG API](https://api.drivethrurpg.com) across
multiple languages, plus the shared API contract they're built against.

## Languages

| Language | Repository | Status | Package |
|---|---|---|---|
| Go | [dtrpg-sdk.go](https://github.com/pilgrimagesoftware/dtrpg-sdk.go) | Implemented | [pkg.go.dev](https://pkg.go.dev/github.com/pilgrimagesoftware/dtrpg-sdk.go) |
| Rust | [dtrpg-sdk.rs](https://github.com/pilgrimagesoftware/dtrpg-sdk.rs) | Implemented | [crates.io](https://crates.io/crates/dtrpg-sdk) |
| Swift | [dtrpg-sdk.swift](https://github.com/pilgrimagesoftware/dtrpg-sdk.swift) | Implemented | [Swift Package Index](https://swiftpackageindex.com/pilgrimagesoftware/dtrpg-sdk.swift) |
| Python | [dtrpg-sdk.py](https://github.com/pilgrimagesoftware/dtrpg-sdk.py) | In development | not yet published |
| Node/TypeScript | [dtrpg-sdk.js](https://github.com/pilgrimagesoftware/dtrpg-sdk.js) | In development | not yet published |

Each language SDK is an independently versioned repository, submoduled here under its language directory (`go`,
`rust`, `swift`, `python`, `js`). "Implemented" means the SDK provides configuration, authentication/session
lifecycle, and a library client (orders, product lists, download preparation), backed by CI and a release pipeline.
"In development" repositories are tracked SDK family members that have not yet reached that bar.

## API contract

The `API` submodule in each language repository points at [dtrpg-api](https://github.com/pilgrimagesoftware/dtrpg-api),
the source of truth for `openapi.yaml`. Each SDK generates or hand-maintains its client bindings from that shared
contract, so API changes propagate to every language by updating the `API` submodule reference.

## Adding a new language

See the umbrella `dtrpg` repository's `docs/git-repos.md` and the OpenSpec change under
`openspec/changes/add-python-node-sdk-family/` for the parity bar a new SDK language must reach and how its
implementation is coordinated against `dtrpg-api`.
