# RefereeChecks — product + redesign brief

**Read this file first.** It is the whole brief for redesigning the RefereeChecks
public website. The frozen product plan lives in `docs/MASTER-PLAN.md` (depth,
only if you need it). The live site is https://refereechecks.pages.dev/.

## What the product is

RefereeChecks is a **verified reference passport for care-sector workers**
(aged care & disability support, NSW first, then Australia-wide).

The problem: reference checks are slow. A job seeker chases their old
supervisor, the supervisor fills in the same 10–20 minute form for every
employer, and manual phone references take 3–7 business days (industry
referencing norm 10–15 days). Meanwhile ~80% of cold calls from unknown
numbers go unanswered.

The product: a referee gives a reference **once**, from a verified account.
Every future employer request arrives **pre-filled** with that standing
reference. The referee gets a fixed **3-business-day window** to update it
for the specific role, confirm it as-is, decline, or revoke — and if they
don't act, the standing reference is released automatically, **labelled
honestly as exactly what it is**. The candidate carries a verified link into
any job application. Employers verify free and pay per delivered reference.

Three audiences, one account each (the same person is often all three in
care work): **job seekers** (candidates) carry the passport; **referees**
(previous employers/supervisors) give and manage references; **new
employers / recruiters** pull verified references.

## Verification (the thing that makes it believable)

Two independent axes, both shown on every delivered reference:

- **Axis 1 — Identity:** document IDV + liveness. Two honestly labelled
  bases, never blurred: **DVS-verified** (matched against Australian
  government issuer records) and **Document-checked** (document authenticity
  + liveness only — this does NOT query government records and must never be
  marketed as if it does).
- **Axis 2 — Affiliation:** did this referee actually hold the claimed role
  at the claimed employer? A ladder: **LinkedIn corroboration** (ops-reviewed,
  labelled "Profile-corroborated" — LinkedIn is self-reported, it corroborates,
  it does not prove, and it is never the top stamp alone) → **company-email
  attestation** (proves control of a work email at the employer's domain) →
  **employer/HR confirmation** (top rung).

Every delivered reference carries a provenance label, always visible to the
employer:

- **A — "Updated for this role"**: the referee edited answers in the window.
- **B — "Confirmed for this role"**: the referee reviewed and confirmed
  unchanged in the window.
- **C — "Standing reference"**: released by default at window close, with the
  mandatory wording that the referee was notified and did not update it.
  A defaulted reference must never be presented as role-specific.

Bespoke employer questions the standing reference does not cover are shown as
**NOT COVERED** — never silently skipped, never fabricated. Evaluative
content expires after 12 months; facts are permanent. Candidates cannot
cherry-pick: all references for an employment travel together
(all-or-nothing). The platform never sells data.

## Pricing (final, GST-inclusive — do not change these numbers)

- **Candidate — Passport Certification: A$39** one-off, charged only when the
  first reference reaches STANDING. Unlimited employment records, up to 3
  referees per employment. Referees are always free.
- **Employer — Check (shortlist stage): A$6**, instant, factual layer only.
- **Employer — Full Request (offer stage): A$12** (A$6 if it delivers
  factual-only).
- **Agency plans: Starter A$79/mo, Growth A$149/mo, Scale A$299/mo**
  (pulls included, overage A$9 / A$8 / A$6).

## Design history (why the site looks like this, and why it is still not good)

- **v1** — light theme, deep teal. Rejected by the owner: arrangement, text
  sizes and colours all wrong.
- **v2** — premium forest + gold redesign. Rejected on composition: hero card
  cut off, sections sprawling and half-cut at the fold, a huge empty panel.
- **v3** — section-fit fix: sections split so each fits one viewport.
- **v4** — rebuilt in the design language of **hnry.com.au** (see
  `docs/HNRY-STYLE-NOTES.md`): bold, friendly, real photos of real people,
  pill buttons, confetti accents, hand-written sticker annotations.
- **v5/v6** — hero overlap fixes: an animated reference card was covering the
  hero photo and a sticker was clipped. The card was removed entirely; the
  hero is now **photo-only**.
- **Owner's verdict after v6: still not good.** You have a **free hand on the
  DESIGN** — layout, composition, typography, colour, imagery, section order.
  What you must NOT change: the **copy, facts and prices** (rewrite wording
  only where the new design needs it, never change a fact, a price, or a
  legal claim). Keep every section's content; reorganise how it is presented.

## HARD RULES for any redesign

1. **SECTION-FIT (standing owner rule, non-negotiable).** Every section must
   be composed to fit within the viewport — no half-cut cards, panels or
   headings at the fold. If a section's content is too much for one viewport,
   SPLIT it into 2–3 sections. Achieve fit by content sizing and splitting
   (smaller headings/text/cards/padding), **NEVER** by `100vh`, scroll-snap,
   or JS measuring tricks.
2. **Style reference is hnry.com.au** — bold, friendly, confident; one deep
   ink colour + one vivid yellow + confetti accents; pill buttons; big real
   photos in large rounded frames; hand-written annotation font for playful
   asides. Adapt the grammar, do not copy Hnry's brand or assets.
   (Observed tokens in `docs/HNRY-STYLE-NOTES.md`.)
3. **Real photos only.** Never AI-generated people, never watermarked stock
   previews. Photos are imagery only — **never captioned as customers,
   testimonials, or real users of the product**. Current photos are free-licence
   Pexels images, credited in `README.md`.
4. **NEVER mention "pilot" anywhere on the public site.** (The product plan
   has a NSW care pilot in `docs/MASTER-PLAN.md` — that is internal, and the
   word must not appear in any public copy, meta, or comment.)
5. **Legal copy rules.** Never claim the product is "screening", that anyone
   is "cleared to work", or that it is a "compliance check" — those phrases
   appear only inside disclaimers/negations, e.g. "RefereeChecks is not a
   screening service and does not replace NDIS worker screening, WWCC or
   police checks." No invented stats, testimonials, client logos, or results.
   Integrations (JobAdder, Employment Hero) are **roadmap only** — never
   presented as live. "Verified" claims must follow the verification section
   above (DVS-verified vs Document-checked, never blurred).
6. **No auth, no backend, no forms yet.** Static site only. CTAs scroll to
   pricing or use `mailto:` links. Mobile + desktop friendly, one consistent
   button system, everything aligned.
7. **Verify in RENDERED PIXELS.** After any redesign, screenshot the live
   render at **1920px and 1366px widths** (950px-tall viewport) and confirm
   every section fits with nothing cut, clipped, or overlapping. Never verify
   from CSS maths alone — two earlier "verified" claims were voided by
   real-pixel checks.

## Repo layout

```
refereechecks/
├── PRODUCT.md                 ← this file — read first
├── README.md                  ← repo overview, deploy instructions
├── site/                      ← deploy root (Cloudflare Pages)
│   ├── index.html             ← single-page site
│   └── assets/
│       ├── css/styles.css     ← design system + all page styles
│       ├── js/app.js          ← menu, scroll reveals
│       └── img/               ← 6 real photos (Pexels)
└── docs/
    ├── MASTER-PLAN.md         ← frozen product plan (1,199 lines)
    └── HNRY-STYLE-NOTES.md    ← hnry.com.au design analysis
```

## Deploy

Cloudflare Pages project `refereechecks`, deploying the contents of `site/`:

```bash
CLOUDFLARE_API_TOKEN=<secure-vault-surrogate> npx wrangler pages deploy site --project-name refereechecks
```

Live URL: https://refereechecks.pages.dev/ — real domain
`refereechecks.com` to be attached once purchased. Cache-bust changed
assets with a bumped `?v=N` query (currently `?v=6`).

## Current site structure (for orientation)

Hero (photo-only) → key facts strip → How it works (split in two: steps
01–02 + delivered-pack panel, then steps 03–04 + "Not covered" note) →
Labels (A/B/C) → photo band → Who it's for (job seekers, then referees +
employers) → Trust (6 items) → Pricing (three sides) → Agency plans →
FAQ → footer.
