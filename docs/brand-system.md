# Orbe — brand system

## Confirmed identity

**Decision:** Portal symbol and custom lowercase `orbe` wordmark with a personalized `o`, within the Orbit direction. Use “Orbe” in prose and `orbe` for the artwork. Earlier `orbe.`, uppercase and alternative symbol ideas are exploration, not competing approved signatures.

Portal is the selected concept name. Its final geometry was not recoverable from the referenced conversation. The construction rules below are a **proposal**, not a recreation of approved artwork.

## Proposed construction brief

Develop Portal as a simple geometric threshold/opening related to a nucleus and orbital continuity. Favor a clear silhouette, deliberate negative space and few parts. Test recognition before adding orbital detail. Avoid literal door illustrations or complex nested rings.

Build the custom `o` from the same curve logic and opening relationship as Portal. Keep `r`, `b` and `e` optically compatible in weight, counters, terminals and spacing. A reader must identify the word at small sizes. Do not substitute a UI font's plain `o` and call it the final wordmark.

No SVG paths, exact aperture angles or final kerning are approved here. Prepare vector masters and optical small-size variants in a later artwork task, without creating application screens.

## Proposed versions and proportions

Define **S** as symbol height and **x** as wordmark lowercase body height. Normalize candidate artwork for comparison; optical adjustment takes precedence over mechanical alignment.

| Item | Working rule |
| --- | --- |
| Primary horizontal signature | Portal left; wordmark right; symbol height approximately 1.25x |
| Horizontal separation | Start at 0.35S; refine optically |
| Stacked signature | Portal centered above wordmark; reserved for constrained aspect ratios |
| Symbol-only | App icon, launcher and small recognition contexts |
| Wordmark-only | Places where the name is primary and symbol repetition adds noise |
| Clear space | At least 0.25S around a lockup; standalone wordmark uses 0.25x |
| Initial minimum test sizes | Symbol 20 logical px; wordmark 64 logical px wide; lockup 96 logical px wide |

These are prototype test thresholds, not validated reproduction minima. Test at actual rendered pixel sizes and print sizes if print use is introduced. Below a viable threshold, use an optical variant or another signature rather than removing arbitrary parts.

## Color and application

Prepare monochrome dark-on-light and light-on-dark masters first. A restrained accent version may follow after the monochrome silhouette works. Use semantic surface/ink roles from [design tokens](design-tokens.md), preserving sufficient logo visibility in context.

Keep proportions and internal spacing intact. Do not stretch, rotate, add bevels/glow, fill counters with busy imagery or replace letters with unrelated icons. Do not use the Portal symbol as a generic button, status badge or progress indicator; the wider geometric vocabulary supplies those functions.

Android launcher artwork must fit platform masks with safe internal padding; Linux needs clean scalable artwork and tested raster exports. Do not bake a particular launcher mask into every master. Final platform asset dimensions are an implementation verification task.

## Typography and delivery checklist

Inter and Space Grotesk are candidate supporting fonts, not final wordmark source artwork. Bundle selected font files and their licenses; confirm actual glyph coverage and redistribution terms before shipping.

Brand approval requires: vector masters; horizontal/stacked/standalone variants; positive/reversed monochrome; optional accent version; optical small-size version if needed; documented final proportions and clear space; legibility tests at minimum sizes; launcher mask tests; and an asset/version manifest. None of these finished assets is claimed to exist in this documentation.
