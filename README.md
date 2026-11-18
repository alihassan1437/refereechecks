# RefereeChecks

**If you are Claude (or any designer) redesigning this site: read
[`PRODUCT.md`](PRODUCT.md) first.** It is the product + redesign brief —
what the product is, the design history, and the hard rules (including the
section-fit rule and the legal copy rules). The frozen product plan is in
`docs/MASTER-PLAN.md` for depth.

RefereeChecks is the **verified reference passport for care workers**
(give a reference once, carry it to every job). Planning and the frozen
master plan live in this repo under `docs/`; the product's own files are
here.

## Layout

```
refereechecks/
├── PRODUCT.md                 ← product + redesign brief — read first
├── README.md                  ← this file
├── docs/
│   ├── MASTER-PLAN.md         ← frozen product plan (1,199 lines, §§1–20)
│   └── HNRY-STYLE-NOTES.md    ← design analysis of hnry.com.au that informed v4
└── site/                      ← public marketing website (deploy root for Cloudflare Pages)
    ├── index.html             ← single-page site (hero, stats, how it works, photo band, audiences, trust, pricing, FAQ)
    └── assets/
        ├── css/
        │   └── styles.css     ← the design system + all page styles
        ├── js/
        │   └── app.js         ← menu, scroll reveals
        └── img/               ← real photos (Pexels, see credits below)
```

## Website

- Static HTML/CSS/JS only. **No auth, no backend, no forms** — CTAs scroll to pricing or
  use `mailto:` links. No pilot/recruitment content anywhere on the page.
- Design system v6 (in `assets/css/styles.css`): Hnry-style grammar adapted to the
  RefereeChecks brand (analysis in `docs/HNRY-STYLE-NOTES.md`) — deep forest ink `#0C2B26`,
  vivid sun yellow `#FAC600`, confetti accents (green `#1CB78D`, orange `#F07F38`,
  pink `#EA4B94`, blue `#017FBC`) on warm cream `#FFFBF0` and pastel grounds.
  Inter throughout (800-weight tight sentence-case headlines), Caveat for hand-written
  sticker annotations. Pill buttons (one primary sun, one secondary outline), cards 28px
  radius, photos 32px radius, sticker chips with hard offset shadows. Assets are
  cache-busted with `?v=6`. Hero v6: the hero's right column is the photo alone
  (the animated mini reference card was removed — the delivered-pack panel in
  How-it-works carries the explanation now).
- SECTION-FIT RULE (Ali, standing): every section is composed to fit one viewport
  (~860px desktop) with nothing cut mid-element at the fold — achieved by content
  sizing and SPLITTING oversized sections (How-it-works, Who, and Pricing are each
  two sections), never by 100vh/scroll-snap/JS measuring.
- Copy follows the frozen plan's legal rules: no "screening / cleared to work / compliance
  check" claims, the mandatory not-a-check disclaimer appears wherever references are
  described, integrations described as roadmap only, no testimonials or invented stats.
  Photos are imagery only — never captioned as customers or testimonials.

## Photo credits

All photos are real photographs from **Pexels**, used under the
[Pexels License](https://www.pexels.com/license/) (free to use; attribution not
required). No AI-generated people, no watermarked previews.

| File | Source | What it shows |
|---|---|---|
| `img/hero-home.jpg` | [Pexels #7345443](https://www.pexels.com/photo/7345443) | Senior woman receiving groceries from a young caregiver in a cozy living room |
| `img/band-kitchen.jpg` | [Pexels #7446778](https://www.pexels.com/photo/7446778) (Gustavo Fring) | Elderly woman in a wheelchair receiving help with medication from a caregiver in a modern kitchen |
| `img/band-wheelchair.jpg` | [Pexels #18509799](https://www.pexels.com/photo/18509799) | Elderly woman in a wheelchair engaging with a caregiver in a bright care home |
| `img/who-jobseeker.jpg` | [Pexels #6129496](https://www.pexels.com/photo/6129496) | Smiling healthcare worker in blue scrubs standing confidently indoors |
| `img/who-referee.jpg` | [Pexels #7345460](https://www.pexels.com/photo/7345460) | Healthcare professional smiling while consulting with an elderly man |
| `img/who-employer.jpg` | [Pexels #6129499](https://www.pexels.com/photo/6129499) | Group of diverse healthcare professionals smiling in a hospital hallway |

## Deploy

Cloudflare Pages project `refereechecks`, deploying the contents of `site/`:

```bash
CLOUDFLARE_API_TOKEN=<secure-vault-surrogate> npx wrangler pages deploy ~/workspace/refereechecks/site --project-name refereechecks
```

Live URL: https://refereechecks.pages.dev/ (real domain `refereechecks.com`
to be attached once purchased).
