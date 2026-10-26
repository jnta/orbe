# Implementation guidance

Status: stack choices are decisions; architecture and contracts below are proposed guidance. The inspected repository is a Flutter scaffold; Drift, Riverpod, fonts, modules and brand assets are not yet implemented. No dependency versions are prescribed here.

## Architecture

Use feature-oriented modules over shared infrastructure. Separate presentation, application operations and persistence. Drift owns SQL tables, constraints, transactions and migrations. Repositories expose domain-oriented operations. Riverpod provides dependencies and observable application state; widget-local ephemeral state need not enter persistent storage.

Keep persisted domain records independent of widget composition. Store widget instance ID, module/type ID, order, supported size preference and configuration version. Missing or disabled module types should retain recoverable configuration rather than silently deleting it.

Use stable record IDs, explicit units/currency where relevant and deliberate timestamp semantics. Resolve local date versus instant versus recurring schedule before building habits/training. For financial amounts use an explicitly defined exact representation, not binary floating point. Add foreign keys and validation at persistence boundaries, not only in forms.

## Local-only boundary

No remote services are necessary for ordinary operation. Bundle fonts/icons and required assets. Review dependencies for hidden network initialization, telemetry and dynamic asset fetching. Keep diagnostics local and redact personal values. Inspect platform permissions and OS backup behavior before claiming that all copies stay on the device.

Local storage uses platform-appropriate application directories. File picker operations are explicit user actions. Do not treat a file path supplied by an archive as a trusted destination. If archives are used, reject traversal paths and bound sizes/counts before extraction.

## Backup and export contract

A proposed backup envelope includes format identifier, format version, application/schema versions, creation time, record counts, payload list and integrity hashes. Hashes detect accidental corruption; they do not prove authenticity or provide encryption. Include attachment references and files if that feature exists, plus workspace settings and any required metadata.

Obtain a consistent snapshot using a supported SQLite snapshot/backup approach or controlled coordinated database closure. Copying only the main database file while WAL writes are active is not a reliable backup procedure. Write output to a temporary destination, verify it, then finalize atomically where supported. Report partial-file cleanup failures honestly.

Portable JSON export documents field types, units, nullability, date conventions and relationships. CSV is a supplementary per-module format, not a complete relational restore format. User-facing labels must distinguish full backups from partial exports.

## Import and restore pipeline

1. Read selected input with resource limits; identify supported format/version.
2. Validate structure, checksums, identifiers, relationships, units and compatibility without touching live data.
3. Show scope/counts and any omissions; reject unsupported future versions with an actionable message.
4. For replacement, require confirmation and successfully create a recovery snapshot first.
5. Stage and migrate restored data separately; validate before the final database swap or transaction commit.
6. Activate the validated data, invalidate relevant Riverpod state and restore coherent navigation/focus.
7. On interruption or failure, retain a valid original database and report what happened.

Serialize restore with ordinary writes; avoid UI access to a half-restored database. A full restore must not silently merge. Introduce merge only after conflict and duplicate rules are specified. Test Android-to-Linux and Linux-to-Android portability before advertising it.

Encryption needs a separate documented format and threat model, including key derivation/storage, authentication, recovery and wrong-password behavior. Do not invent cryptography or imply that plain SQLite is encrypted.

## Flutter visual implementation

Map semantic color and text roles into ThemeData/ColorScheme and TextTheme; add a ThemeExtension for module accents, spacing and motion where needed. Keep brand artwork as versioned assets once approved. Use a suitable vector pipeline and tested raster variants for platform icons. Confirm font and icon licenses and bundle assets locally.

Use layout constraints and content needs for adaptive behavior. Preserve semantic widget order across Android and Linux. Provide keyboard focus traversal, tooltips where helpful, semantic names/values, non-drag move actions and reduced-motion behavior. Persist ordering after a successful reorder operation, with failure feedback and rollback if persistence fails.

## Validation plan

| Area | Evidence required before release |
| --- | --- |
| Persistence | CRUD constraints, restart durability, transactions and migrations from prior schemas |
| Recovery | Round trips, corrupt/truncated input, unsupported versions, full disk and interrupted restore |
| Privacy | No core network dependency, dependency/permission review and redacted diagnostics |
| Workspace | Stable order, adaptive widths, missing-module behavior and accessible reordering |
| Visual system | Real contrast checks, scaled text, focus states, reduced motion and actual asset legibility |
| Platforms | Representative Android and Linux devices, including cross-platform restore |

Run repository analysis and tests when application implementation begins. For this documentation-only change, check file scope, internal links and consistency; no application behavior or screen implementation is introduced.

## Suggested implementation order

Approve the first module and data contract; establish Drift migrations and Riverpod boundaries; implement a local record vertical slice; deliver tested backup/restore and export/import; persist modular workspace configuration; then implement the approved visual assets and tokens. Treat each stage as independently reviewable and keep data recovery ahead of visual refinement.
