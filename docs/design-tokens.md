# Design tokens — working specification

Status: **proposal throughout**. Values enable consistent exploration; they are not recovered final brand decisions or a validated accessibility palette. All dimensions are Flutter logical pixels unless otherwise stated.

## Color primitives and semantic aliases

| Token | Candidate value | Purpose |
| --- | --- | --- |
| color.surface.canvas | #101318 | Main dark background |
| color.surface.base | #191E26 | Primary module surface |
| color.surface.raised | #232B36 | Elevated contextual surface |
| color.border.subtle | #354151 | Nonessential separators |
| color.border.control | #708198 | Meaningful control boundary |
| color.text.primary | #F1F4F8 | Primary text |
| color.text.secondary | #BAC5D4 | Supporting text |
| color.text.muted | #9BA9BC | Lower emphasis, still readable |
| color.action.primary | #9BB8FF | Principal action/focus accent |
| color.action.onPrimary | #101318 | Text on primary fill |
| color.focus.ring | #B8CCFF | Keyboard focus |
| color.status.success | #7DD9AC | Confirmed successful result |
| color.status.warning | #F3CC79 | Warning |
| color.status.error | #FF999F | Error |
| color.status.info | #9BB8FF | Information |

Subtle borders must not be the sole boundary of an interactive control. Do not apply reduced opacity indiscriminately to text. Accent colors are candidate foregrounds on dark surfaces; do not assume white text on an accent fill passes contrast. Create and check explicit `onAccent` pairs when needed.

## Candidate domain accents

| Domain | Token suffix | Candidate |
| --- | --- | --- |
| Finance | finance | #7DD9AC |
| Training | training | #FFAB86 |
| Studies | studies | #9BB8FF |
| Habits | habits | #C4AAFF |
| Goals | goals | #F3CC79 |
| Projects | projects | #76D7DE |

Use `color.module.<suffix>` for context, never as an implicit status. These mappings do not commit the module roadmap. Add labels, shapes or line patterns to disambiguate repeated hues.

## Typography

| Role | Family proposal | Size / line height | Weight |
| --- | --- | --- | --- |
| identity | Space Grotesk | 32 / 40 | 500 |
| heading | Space Grotesk | 24 / 32 | 500 |
| section | Inter | 20 / 28 | 600 |
| body | Inter | 16 / 24 | 400 |
| label | Inter | 14 / 20 | 500 |
| caption | Inter | 12 / 16 | 400 |
| data | Inter, tabular numerals | 24 / 32 | 600 |

Line heights are logical-pixel targets at default scale; derive relative height factors for Flutter. Respect user text scaling. Avoid using caption styling for essential instructions. Use available licensed weights rather than synthetic bold. Locale, long strings and negative/large numbers need explicit validation.

## Geometry and interaction

| Family | Proposed tokens |
| --- | --- |
| Spacing | space.1=4, .2=8, .3=12, .4=16, .6=24, .8=32, .12=48 |
| Radius | radius.small=8, .medium=12, .large=20; full only for semantic pills/circles |
| Stroke | stroke.hairline=1, stroke.icon=2, stroke.focus=2 |
| Focus | focus.offset=2; visible outside the control where space permits |
| Targets | target.touchMin=48; visual icon size independent of hit area |
| Motion | duration.fast=120ms, .standard=180ms, .spatial=240ms |
| Easing | easing.standard=cubic(0.2,0,0,1) |
| Reduced motion | duration.reduced=0ms; optional short nonspatial fade if appropriate |

Do not turn the largest motion value into a mandatory delay before an action completes. Grid columns, breakpoints and widget spans remain open; they must follow content and platform constraints.

## Token lifecycle

Keep primitives separate from semantic roles, and roles separate from component overrides. Components should consume roles, not hard-coded hex colors. A future light theme remaps roles. Add state tokens for focus, pressed, selected and disabled after checking combinations; do not invent state colors independently in each component.

Before promoting this set: calculate actual contrast pairs; verify rendered text at scaling settings; test distinguishability and focus on all surfaces; review typography with Portuguese and English; then record approved values and version. These are documentation tokens only, not generated Dart or JSON assets.
