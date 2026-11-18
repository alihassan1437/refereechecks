# Hnry design analysis — hnry.com.au (fetched 2026-11-18)

Source: live homepage HTML + their production stylesheet
(`hnry.com.au/assets/css/stylesheet.css`), analysed directly. Hex counts are
actual occurrence counts in that CSS file. Items marked *(estimate)* are
inferred from composition, not measured in code.

## Palette (observed in their CSS)

| Role | Hex | Uses in CSS | Notes |
|---|---|---|---|
| Ink / primary dark | `#272754` | 188 | Deep indigo-navy. Headlines, text, dark blocks, footer. THE dominant colour. |
| Secondary purple | `#5d5096` | 45 | Buttons, links, mid-tone blocks |
| Lavender tint bg | `#efefff` | 38 | Pale lavender section backgrounds |
| Signature yellow | `#fac600` | 24 | Primary CTA fill, highlights, stickers |
| Green accent | `#1cb78d` / `#33b082` | 20 / 11 | Confetti accent, success, alternate CTA |
| Orange accent | `#f07f38` | 14 | Confetti accent, alternate CTA |
| Body grey | `#454545` | 12 | Secondary text |
| Blue accent | `#017fbc` | 12 | Links/accents |
| Pink accent | `#ea4b94` | 10 | Confetti accent |
| Pale yellow | `#fce37e`, `#ffda47`, `#fff8db` | 7/3/3 | Sticker fills, soft highlights |
| Lavender greys | `#e9e9f3`, `#dcd9f0`, `#8f8ca8` | 9/6/8 | Borders, muted text, chips |

Pattern: one deep ink + one vivid yellow + a rainbow of confident accent
colours used as *confetti* (one accent per card/chip), on white and pale
lavender grounds. Nothing is muted or "premium-subtle" — it's bold and flat.

## Typography (observed)

- **Body/UI font: Inter** (loaded from rsms.me/inter) — same family we already use.
- **Accent font: "Shantell Sans" 600** — a hand-drawn marker font, used for
  playful annotations, scribbles and sticker-style asides. Loaded from Google Fonts.
- Headline voice: very large, tight, confident, **sentence case** with a
  trademark-style promise — "Never think about tax again™". Short, punchy,
  benefit-first. Section headers use the same voice ("Everything you get
  with Hnry…", "A suite of tools, built with sole traders in mind.").
- Copy tone: casual, contractions everywhere, "PS:" asides, exclamation-light
  but warm. *(Voice observed in page text.)*

## Shapes & components (observed)

- **Pill radii everywhere**: `border-radius: 999px/9999px` (19 uses) — buttons
  and chips are fully rounded. Cards run large radii too: `28px` and
  `1.25rem` (20px) recur; circles `50%` for avatars/icon discs.
- CTA buttons exist in a **colour series** — yellow `#fac600`, purple
  `#5d5096`, green `#33b082`, orange `#f07f38` (`.btn-cta` variants in CSS) —
  same shape, different confident fills.
- Photos: big, real photos of real customers — hero is a **carousel of large
  photographic slides** (AVIF), review cards pair a person's photo with their
  quote and job title ("Linh — Project Manager"). Product visuals sit in
  large rounded frames.
- Sections alternate: white → pale lavender `#efefff` → deep ink `#272754`
  blocks, with feature cards laid over the tint grounds.
- Personality: friendly fintech — rounded, colourful, sticker-like chips and
  hand-font annotations layered over an otherwise clean Inter grid.
  *(Composition observed from homepage structure + image usage.)*

## How RefereeChecks v4 adapts this (not copies)

- Ink role: Hnry's indigo `#272754` → our deep forest `#0C2B26` (brand stays ours).
- Signature CTA: Hnry yellow `#fac600` adopted almost as-is — it is a natural
  brightening of our existing gold (`#C9A227`/`#D4AF37`) — pill buttons, ink text.
- Confetti accents kept as a system: green `#1CB78D`, orange `#F07F38`,
  pink `#EA4B94`, blue `#017FBC` — used one-per-element (our A/B/C label chips
  and trust icons map onto this perfectly).
- Pastel grounds: lavender `#efefff` → our pastel set (mint, peach, sky, blush)
  on warm cream `#FFFBF0`.
- Headlines: Inter, sentence case, bigger and tighter; hand-font annotations
  in **Caveat** (a different marker font than Hnry's Shantell Sans — same
  playful role, our own choice).
- Radii: cards 28px, photos 32px, buttons/chips 999px pills, sticker chips
  slightly rotated with hard offset shadows.
- Real photos in big rounded frames woven through hero, photo band and the
  three audience cards — imagery only, never captioned as customers.
