# Agent guidance for Orbe

These instructions apply throughout this repository.

## Project context

Before starting work, read:

1. [README.md](README.md) for repository status, supported platforms and development commands.
2. [docs/readme.md](docs/readme.md) for consolidated project context, the decision register, documentation status and source limitations.

Read the relevant detailed documents for the task:

- [Product requirements](docs/prd.md)
- [Visual system](docs/visual-system.md)
- [Brand system](docs/brand-system.md)
- [Design tokens](docs/design-tokens.md)
- [Implementation guidance](docs/implementation.md)

Keep these documents as the source of detailed context rather than duplicating them here. Inspect the current code before treating documentation about implementation status as current fact.

## Working principles

- Preserve the privacy-first, offline, local-only direction and Flutter support for Android and Linux.
- Follow the documented SQLite/Drift and Riverpod decisions when implementing persistence and application state.
- Distinguish confirmed decisions from proposals, visual explorations and open questions. Do not present provisional fonts, colors, proportions or token values as approved specifications.
- Preserve the selected Orbit direction, Portal symbol and custom lowercase `orbe` wordmark when working on branding.
- Do not infer authorization to build application screens from the visual documentation alone; implement screens when the task requests them.
- Inspect existing files and preserve unrelated material. Update affected documentation when the requested work changes an established decision or implementation status.

## Validation

For application changes, run the relevant checks documented in the root README, including `flutter analyze` and `flutter test` when appropriate. Report checks that could not be run.

For documentation-only changes, verify relative links, file-name casing and consistency with the decision register. Application tests are unnecessary unless behavior or code also changes.
