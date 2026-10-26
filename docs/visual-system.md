# Orbit Geometric OS — visual system

Status: selected direction; numerical styling and component behavior remain proposals. This document defines a visual language, not application screens.

## Core idea

A personal universe organized through connected instruments. Nucleus expresses identity and origin; orbit expresses continuity and cycles; module expresses a distinct area of life. The system should feel personal, precise, quiet and recognizably digital.

Use softened geometry, a consistent grid, dark neutral layers and restrained accents. Information hierarchy comes from placement, scale and weight before color. Avoid literal planets, galaxies, rockets, decorative rings, neon spectacle and pervasive glass effects.

## Modular workspace

Widgets are instruments with stable identity, clear purpose and defined size categories. Their content and actions should remain understandable across available space. Exact grid columns, breakpoints and widget dimensions are open until content is known.

Rearrangement needs an explicit mode or affordance, visible placement feedback, cancel/undo where practical, and non-drag alternatives. Persist semantic order and size preference, not only screen coordinates. Adapt that order to platform width without unexpectedly rearranging the user's priorities. Keep destructive record deletion separate from removing a widget.

## Form and material

Prefer opaque surfaces with subtle tonal separation. Use borders where necessary to identify controls; shadows supplement rather than establish all hierarchy. Reserve pills for compact tags or status; use circles/arcs only when they carry meaning. Keep a coherent radius family and alignment rhythm.

Dark-first is the selected direction. It does not settle the timing of a light theme. Prepare semantic tokens so another theme can be added without changing domain logic. A light variant must be designed and validated independently before release.

## Typography and color

Proposed pairing: Inter for operational text and Space Grotesk for restrained identity headings or large highlights. The custom wordmark is separate artwork, not ordinary typed text. Use tabular numerals for aligned comparable values and preserve locale formatting.

Neutral surfaces dominate. Module accent colors identify context, while semantic colors communicate success, warning, error and information consistently across modules. A finance accent must not imply a positive balance: use sign, label and semantic state as well. Candidate values and mappings are in [design tokens](design-tokens.md).

## Symbol grammar

| Primitive | Intended meaning |
| --- | --- |
| Point/nucleus | Record, origin, presence |
| Ring | Domain or whole |
| Arc | Measured progress or cycle |
| Segment | Stage or part |
| Line | Relationship or flow |
| Rounded module | Functional block |
| Grid/cell | Workspace organization |

Functional icons must have familiar meanings and accessible labels. Proposed icon construction uses a 24-unit grid and consistent 2-unit strokes with optically adjusted curves. Choose one licensed icon family before implementation. Custom domain symbols may extend it, but should not replace familiar action icons with abstract puzzles. Hide decorative geometry from accessibility semantics.

## Motion

Motion communicates continuity, origin, rearrangement or confirmation. Prefer short transitions with restrained easing; avoid perpetual orbiting decoration or elastic movement that slows operation. Arc animation must reflect real progress; unknown duration must not masquerade as a measured percentage.

Honor platform reduced-motion settings. Replace spatial movement with an immediate state update or brief fade. State, focus and success must remain understandable without animation. Haptics are optional, platform-dependent reinforcement.

## Accessibility and states

Document default, hover, focus, pressed, selected, disabled, loading and error behavior for every future interactive component. Focus must remain visible and distinct from selection. Hover cannot be the only way to reveal an action.

Target at least 4.5:1 text contrast for ordinary text, 3:1 for large text and meaningful control boundaries/focus indicators. Verify actual foreground/background pairs, opacity and every interactive state before approval. Never encode module, status or chart series solely through color. Support text scaling without clipped fixed-height text containers, screen-reader names and logical reading order. Use at least 48 logical-pixel touch targets as the initial interaction target, with desktop density adapted without sacrificing accessibility.

Keep keyboard traversal predictable on Linux, announce reorder results, return focus after dialogs, and provide text equivalents for charts. Accessibility requirements are release criteria; candidate palette values alone do not establish compliance.
