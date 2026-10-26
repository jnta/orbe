# Orbe project documentation

English consolidation · 26 October 2026 · documentation only

Orbe is a private, offline, local-only personal operating system built with Flutter for Android and Linux. “Operating system” describes an integrated personal workspace, not a replacement for the device OS.

## Reading order

1. [Product requirements](prd.md): purpose, scope and acceptance criteria.
2. [Visual system](visual-system.md): Orbit Geometric OS principles and behavior.
3. [Brand system](brand-system.md): Portal symbol and custom lowercase wordmark.
4. [Design tokens](design-tokens.md): provisional numerical specification.
5. [Implementation guidance](implementation.md): architecture, persistence and validation.

## Authority and status

- **Decision**: explicitly requested in the current brief or chosen by the user in the recoverable conversation.
- **Direction**: guidance from the recovered Orbit proposal, consolidated for consistency; not proof that every detail received final approval.
- **Proposal**: a new working specification that requires visual or implementation validation.
- **Open**: unresolved choice; do not silently treat it as settled.

The current request governs conflicts. The repository README describes a Flutter scaffold with Android/Linux targets and no implemented modules or local storage. These documents describe intended behavior, not completed functionality. No application screens or production brand artwork are included.

## Decision register

| Topic | Status | Basis |
| --- | --- | --- |
| Privacy-first, offline, local-only; Flutter Android/Linux | Decision | Current request; platforms also in repository README |
| SQLite through Drift; Riverpod; backup/export/import | Decision | Current request; not installed in inspected scaffold |
| Orbit Geometric OS; dark-first; rearrangeable modular widgets | Decision | Current request and recovered Orbit direction |
| Portal symbol; custom lowercase `orbe` with personalized `o` | Decision | Explicit user choice in referenced conversation |
| Neutral surfaces, restrained module colors, functional geometry, purposeful motion | Direction | Recoverable Orbit proposal |
| Inter + Space Grotesk | Proposal | Recommended, not finalized, in recovered proposal |
| Exact palette, type scale, logo proportions and motion values | Proposal | Working specifications in this documentation |
| Initial module depth and order, final logo paths, encrypted backup format | Open | No recoverable final decision |

## Source limitations

Source: [Ideias para aplicativo pessoal](chatgpt-conversation://6adfae55-64c4-83e9-8070-aff333de2316), plus the current documentation request and inspected repository README/pubspec.

The retrieved conversation contains the full Orbit identity proposal and explicit Portal/wordmark selection. Later assistant brand responses are opaque content references, so their exact specifications could not be recovered. “Option A” is interpreted only as the visible proposal's brand-system workstream. No missing geometry or colors are presented as historical facts.

Changes to a decision should record the reason and update all affected documents. Promote a proposal only after explicit acceptance or documented validation appropriate to that decision.
