# Orbe — concise PRD

Status: product constraints are **decisions**; release sequencing and detailed behaviors below are **proposals** unless marked otherwise.

## Purpose

Give one person a coherent place to record, review and organize their life across modules, while retaining control of their data. Primary use is on Android and Linux, including long periods without connectivity. Success means useful daily operation and dependable recovery without an account or service.

## Product decisions

- Flutter application for Android and Linux.
- Privacy-first, offline and local-only. No account, backend, cloud sync, analytics or remote dependency for core use.
- SQLite persistence through Drift; Riverpod for application state and dependencies.
- Modular workspace with rearrangeable widgets, using the Orbit Geometric OS visual direction.
- User-controlled backup, export and import.

## Proposed MVP

| Capability | Requirement | Acceptance |
| --- | --- | --- |
| Local records | Create, read, update and delete records in the first approved module | Records remain correct after restart, without connectivity |
| Workspace | Add, remove and reorder module widgets | Stable widget identity and order survive restart; removal never deletes domain records |
| Accessible reordering | Offer explicit move actions as well as dragging | Keyboard and assistive technology can perform every reorder operation |
| Backup | Create a consistent, versioned snapshot of all supported data and workspace preferences | Restore into a clean supported installation reproduces records and layout |
| Export | Produce documented portable data, initially JSON; CSV may be offered per module | Export includes schema/version metadata and preserves identifiers, dates and units |
| Import | Validate format and compatibility before changing live data | Malformed or unsupported input leaves the live database unchanged |
| Recovery | Confirm replacement and make a recovery snapshot before destructive restore | Interrupted restore preserves the previous valid database or commits the complete new one |

Finances, training and habits are candidate initial modules mentioned in the repository README. Studies, goals and projects are visual/domain explorations from the Orbit proposal. None establishes a committed six-module MVP. Select the first vertical slice before implementation; each additional module needs its own compact requirements.

## Data ownership and privacy

All ordinary reads and writes remain on the device. Bundle required fonts and assets. Avoid identifiers, record contents and financial/health data in logs. Ask for file access only when needed for a user-selected operation. Explain that user-selected external storage or OS-managed device backups can place a copy outside Orbe's own storage.

Local-only does not imply encrypted storage or protection from a compromised OS. Database encryption, an app lock and encrypted portable backups remain open security decisions. Until encryption exists, clearly label exported files as potentially sensitive. Do not claim medical or financial advisory functionality.

## Import and portability contract — proposed

Distinguish full backup/restore from portable export/import. A full backup includes all supported application data and referenced local attachments, if attachments are introduced. A portable export is documented for independent use and may omit app-specific cache/state, with omissions stated.

For MVP, use explicit full replacement for restore, with preview counts, compatibility checks and confirmation. Defer merge import until duplicate identity, conflict resolution and relationship handling are specified. Do not infer that copying a file between Android and Linux provides automatic sync. Promise cross-platform restore only after round-trip tests.

## Non-goals

Cloud synchronization, collaboration, social features, advertising, remote AI services, platform replacement and application screen design are outside this scope. No app screens are specified by this documentation.

## Quality and release gates

- Core workflow works with networking unavailable and no sign-in.
- Database migrations preserve representative old data; failed migration is recoverable.
- Backup/restore and export/import round trips are tested on both supported platforms.
- Text scaling, keyboard navigation, screen-reader labels and reduced motion are verified.
- Empty, invalid, full-disk and interrupted-file-operation cases produce actionable messages without data loss.
- Measure startup, common writes and widget reordering on representative Android/Linux hardware before setting performance budgets; no unsupported performance promise is made here.

## Open product choices

First module and record schema; recurrence/timezone behavior; attachments; import merge semantics; encryption and key recovery; manual versus scheduled backups; retention; supported OS versions and database size targets. Manual backup/export is the proposed initial release scope.
