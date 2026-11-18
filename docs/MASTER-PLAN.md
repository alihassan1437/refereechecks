# MASTER PLAN — RefereeChecks (verified reference ecosystem)

**Status: FROZEN — v1.0 of the plan, frozen 18 November 2026.**
**Owner:** Ali Hassan. **Entity:** to be incorporated as a Pty Ltd (see §20, Ali's gates).
**This document supersedes all drafts** in this folder: `VERDICT.md`, `product-spec.md`, `integrations.md`, `build-plan.md`, `harden-product.md`, `harden-legal.md`, `harden-redteam.md`, `harden-business.md`, `harden-buildops.md`, `domain-names.md`, `ali-input-verification-ladder.md`. Where any draft disagrees with this plan, **this plan wins**. All conflicts found between drafts are resolved in writing in §17 (Reconciliations). Research inputs (`incumbents.md`, `portability.md`, `demand-economics.md`) remain as evidence, not instructions.
**Change rule:** this plan changes only through §18 (Change Control). "Decided in freeze" marks points a source file left open that this plan closes with reasoning.

---

## Contents

1. Product definition, name & domain
2. Why this exists (validation basis, compressed)
3. Roles & unified identity
4. Verification architecture
5. The reference — anatomy, types & the final question set
6. Core flows (collection, edit-or-default, freshness, revocation, disputes)
7. Labelling — final
8. Anti-gaming, fraud & platform security
9. Pricing — final
10. Integrations sequence — final
11. Build plan — blocks, timeline, frozen scope line
12. Operations plan
13. Legal & compliance summary
14. Pilot design — metrics, targets, kill criteria (final)
15. Financial model
16. Go-to-market & expansion (summary)
17. Reconciliations — every conflict, decided
18. Change control
19. Launch-gate checklist (owners)
20. Ali's remaining gates
Appendix A — The 18 lawyer questions
Appendix B — Source map

---

## 1. Product definition, name & domain

**Name: RefereeChecks.** Primary domain: **refereechecks.com** — checked by Ali himself and independently confirmed unregistered/available via Verisign RDAP (HTTP 404) on 18 Nov 2026. Ali registers it the moment he approves this plan (§20). **refereecheck.com.au** (registry-verified available by the domain agent, 18 Nov 2026) is registered alongside as a defensive/AU-local domain. The singular refereecheck.com is parked by a 2024 registrant with **no published asking price** (Sedo lists it as not for sale; the only route is a GoDaddy broker at a A$145.41 fee before any negotiation) — the plural .com avoids that entirely. refereechecks.io / .co may be added as cheap defensive registrations.

**Why this name (Ali's Mapflyover rule — the name must match the search; domain decision updated by Ali, 2026-11-18 ~00:51 ACST):** "referee checks" is the exact **plural** phrase used in AU job ads and recruitment packs — AU job ads literally say *"referee checks will be undertaken."* The name = the search, in AU English. The .com (rather than launching on the .com.au) keeps NZ and later expansion open and sidesteps the parked singular .com completely. The global head term "reference check" is contested by parked domains (referencecheck.com/.com.au both held) and is won with content instead — a `/reference-check` hub on the site — the same two-phrase play HiveRef runs. The name serves all three sides neutrally: candidates hear "my referee checks", referees instantly trust the sender name in a request email/SMS (the anti-phishing test), employers hear the exact name of the task they are buying.

**SMS sender ID consequence:** "RefereeChecks" is 13 characters — over the ACMA Register's 11-character limit (§12.7). The registered sender ID will therefore be a shortened corresponding form (e.g. **"RefChecks"**, 9 characters) that corresponds to the business name/trademark on an official record, exactly as the Register requires; the precise ID is confirmed at registration in Block 0. This changes nothing else in the notification design.

**Trademark flag (not cleared — Ali's gate):** "REFEREE®" is a registered US trademark of Referee, Inc. (a US employment-verification company). "Referee" is a generic word in AU English for the person giving a reference, so descriptive AU use is a different posture, but the word alone may be unregistrable as a mark. A formal IP Australia search (classes 9, 35, 42, 45) + ASIC business-name check is required before brand commitment (§20). The rejected working name "RefVault" is retired: it matches no search query anyone types.

**Product, in one paragraph:** A verified reference passport for care-sector workers. A referee gives a reference **once**, from a verified account with a persistent platform email identity. Every future employer request arrives **pre-filled** with that standing reference; the referee gets a fixed **3-business-day window** to update it for the specific role, confirm it as-is, decline, or revoke — and if they don't act, the standing reference is released automatically, **labelled honestly as exactly what it is**. Candidates carry a verified link into any application. Employers verify free, pay per delivered pull. Launch sector: **aged care & disability support, NSW first** (376,300 workers nationally, ~26% casual turnover, a workforce already trained on portable worker-paid credentials — NDIS Worker Screening $112–163, WWCC $112–139, police checks $42–65).

**Design principles (non-negotiable, carried from validation):**
1. **Facts port; opinions expire.** Factual layer is permanent; evaluative layer expires at 12 months and is age-labelled everywhere.
2. **Disclosure only against a specific application**, candidate-authorised, to a verified employer. No browsing, no talent-pool search, no speculative pulls — ever. This is a permanent constitutional rule, not a v1 scope choice (it is what preserves defamation qualified privilege and APP 6 compliance).
3. **The referee is the reusable asset.** Referee experience must be *less* work than the status quo (a 3–5 minute pre-filled confirmation vs a 10–20 minute fresh form), and referees get a value loop (§6.6), not just less pain.
4. **Completeness over curation.** All-or-nothing per employment (§8.1). Candidates cannot cherry-pick.
5. **Every state is labelled.** An employer can always reconstruct exactly what the referee did and didn't do, and when (§7). The platform never fabricates, interpolates, or AI-summarises referee content into a delivered reference.
6. **Sold honestly.** Candidates can read what's stored (APP 12) — the product trades referee candour for speed and verifiability, and says so. Referees are told at collection: *"Write only what you'd stand behind in writing. The candidate can read this."*
7. **We never sell data.** No sale, rent, licence or exchange of personal data — reference content, referee data, candidate data, application data — to anyone, for any price, in any form. No advertising, no profiling, no "anonymised insights" products derived from reference content in v1–v2. Published on the site and written into the pilot agreement.

---

## 2. Why this exists (validation basis, compressed)

- **The pain is verified:** manual phone references take 3–7 business days; industry-standard referencing time is 10–15 days; even Xref averages 18 hours. ~80% of cold calls from unknown numbers go unanswered (Pew). Median time-to-fill is ~60 days and candidates abandon slow processes. Referees repeat 10–20-minute forms from scratch for every employer. Xref (ASX) books A$21.3M FY25 doing this — real money, modest pool.
- **The referee side is unbuilt by everyone:** SEEK Pass (candidate-side reuse, free, walled inside SEEK, 15M+ credentials) and Xref.me (launched May 2026, 80K profiles by Oct 2026) both leave the referee stateless — a one-time link, answering fresh every time, identity verification optional/signal-based at best. **Nobody has built the referee account + verified referee identity layer. That is the open position, and it is closing.**
- **The proving precedent is in Ali's own sector:** AU employers already accept worker-held portable credentials (NDIS Worker Screening, WWCC, police checks) when there is (1) a verification lookup, (2) a standard format, (3) freshness rules. A $39 reference passport sits inside proven willingness to pay.
- **Where portability fails, we do not go:** childcare/education (safer-recruitment requires direct-from-referee collection — candidate-carried references are structurally excluded), professional/senior hiring (bespoke probe + negligent-hiring liability stays with the employer). The NHS Digital Staff Passport (retired Dec 2025 after 4 trusts) is the cautionary precedent: portability grows inside bounded ecosystems, not the open market — hence sector + state density before breadth.
- **The executioner is employer trust.** If hiring managers read a candidate-carried reference as a cherry-picked testimonial and run their own check anyway, the platform is an extra step and dies. Every design decision in this plan is pointed at that metric, and the pilot (§14) measures it directly. Runner-up executioner: referee completion rate on an unknown brand (requests mistaken for phishing is documented even for incumbents).

---

## 3. Roles & unified identity

**One person = one identity account** (decided in freeze, from product hardening §A4 — this replaces the spec's separate `User` / `Referee` / `EmployerUser` person-entities in the data model). In care, the same person is routinely a candidate (casual at agency B), a referee (supervisor at provider A), and an employer user (rostering manager who hires). Roles are **capabilities** layered on one account bound to one verified identity (document-hash dedupe applies across all roles):

- **Candidate capability** — owns a Reference Passport: identity, Employment Records (+ Placement/Volunteer Experience Records, §5.3), the references attached to each, a shareable verified link, a per-application authorisation inbox, and a full audit trail of every pull.
- **Referee capability** — owns every reference they have given or been asked for, in one dashboard. Holds a **platform email identity**: `firstname.lastname@refs.refereechecks.com` (numeric suffix on collision) plus a short handle (`refereechecks.com/r/<handle>`). All reference requests route to this identity and land in the one dashboard. The account belongs to the person, not a job: if the referee changes employers, the account and past references persist; affiliation-at-time-of-writing and current affiliation are displayed separately.
- **Employer User capability** — membership of one or more **EmployerOrgs** (the org is a separate ABN-verified entity; the person holds a role in it). Org roles (role model frozen now; team seats ship v1.1, pilot runs single-user-per-org): **Admin** (billing, API keys, team, settings), **Recruiter** (creates requests; sees deliveries for requests they created), **Viewer** (sees deliveries explicitly shared with them). Default delivery visibility is creator + Admins; org-wide visibility is an Admin setting, default OFF. Named individual users only — no shared logins; every request names the individual recruiter and the end employer + role, and the candidate's audit trail shows the person's name ("pulled by J. Smith at BrightCare for Support Worker, BrightCare Aged Care").
- **Conflict-of-interest block (structural):** a person cannot act as employer user on a request for a candidate where they are also a referee on that candidate's passport.
- **Platform Admin (internal):** verification review queues, fraud console, correction/dispute case management, suppression workflow. **No admin can edit referee content** — admins can only suppress a reference pending case resolution (audit-logged, disclosed to affected parties). Admin content access is break-glass: evaluative content is viewable only by opening a case; the view is audit-logged with the case ID. Routine queues show metadata, not content.
- **Age floors (decided in freeze):** candidate accounts from age 16; referees and employer users 18+ (they must be able to give the legal attestations).

---

## 4. Verification architecture

Verification has **two independent axes**, and every delivered reference displays both:

- **Axis 1 — Identity:** is this person who they claim to be? (Document IDV + liveness; DVS basis where available.)
- **Axis 2 — Affiliation:** did this referee actually hold the claimed role at the claimed employer? (Ali's ladder, §4.2.)

### 4.1 The verification-basis label (legal wins — see §17 R2)

Two distinctly-labelled bases, never blurred in UI or copy:

- **DVS-verified** — document details matched against Australian government issuer records via an AU gateway-connected provider (FrankieOne/greenID class). **Only this basis may carry the words "verified against government records."**
- **Document-checked** — document authenticity + liveness only (Veriff class). Labelled exactly that. Veriff does **not** query the DVS and must never be marketed as if it does (ACL s 29 exposure, and it would quietly downgrade the moat).

**Launch position (frozen):** the pilot launches on the **Document-checked** basis (Veriff self-serve — same-day onboarding, published pricing US$0.80–1.39/check ≈ A$1.25–2.20) with honest labels, **and** the FrankieOne/greenID application runs in parallel from Week 1 (it is a compliance dependency, not a v1.1 upgrade). When the DVS path is live, new verifications are DVS-verified and existing referees are offered a no-cost upgrade; nobody is forced to re-verify on a vendor switch (we store provider + decision + basis). Our IVS access category (own participation agreement vs identity-service-provider model) must be confirmed in writing with the provider pre-launch (Lawyer Q18).

**Hard rule (red-team D-01):** no reference is deliverable at any tier until the referee has passed document IDV + liveness. A referee who has not passed may *draft* a reference only. There is no "domain-attested-only" deliverable tier — domains and mailboxes are free; documents and faces are not.

**No ID documents are ever stored by us.** The provider holds documents; we store provider, session ID, decision, assurance level, timestamp, document *type* — never images, never full document numbers, never raw webhook payloads (field-allowlist persistence, tested pre-launch). The dedupe key is an **HMAC-SHA256 of the normalised document identifier with a KMS-held pepper** — never a plain salted hash (document numbers are low-entropy and brute-forceable after a database leak otherwise).

### 4.2 The referee verification ladder (Ali's design input, integrated)

When a candidate claims e.g. Woolworths experience and nominates a referee there, the referee's **affiliation** at that employer is established by climbing a ladder — highest successful rung wins, and the rung reached is labelled on the employer view:

1. **LinkedIn corroboration (Ali's rung 1).** The referee supplies their LinkedIn profile link; an ops reviewer checks it is visible and credible and shows the referee working at the claimed employer in a role that plausibly supervised the candidate (signals: profile age, connections, tenure consistency with the claimed supervision period, role plausibility, employer-page match). Label: **"Profile-corroborated."** LinkedIn is self-reported — it corroborates, it does not prove. It is a human/assisted ops-queue review (LinkedIn blocks scraping; the check is never automated scraping) and is costed in ops minutes (§12). It never substitutes for IDV + liveness (Axis 1) and never by itself lifts a reference above Tier 1.
2. **Company-email attestation (Ali's rung 2).** The referee proves control of an email address at the claimed employer's domain (one-time code). Displayed to employers as exactly that — "controls a work email at {employer domain}" — never overstated as proof of job title. This is the explicit fallback when LinkedIn is absent or unconvincing, and the standard rung for current staff.
3. **Employer / HR confirmation (top rung).** The issuing employer's own verified account confirms the referee held a supervisory/HR role there (the collect-at-exit path, §6.3), **or** HR factual confirmation via the HR Factual Route (§6.4). Gated by §4.4 — a fresh ABN cannot mint this.

A verified referee at the claimed employer also indirectly corroborates the candidate's claim (a verified Woolies supervisor refereeing you is evidence you were there). Referees who have left the employer and lost the mailbox are covered by rung 1 + the Tier 1 reason label, or rung 3 via HR.

### 4.3 Assurance tiers — final (spec definitions win; per-reference, from evidence)

| Tier | Name | Requires |
|---|---|---|
| **Tier 3** | Employer-confirmed | Referee IDV + liveness + work-email control, **and** issuing employer's verified account confirms the referee's role — confirmer must pass §4.4 gates. Typically collect-at-exit |
| **Tier 2** | Identity-verified | Referee IDV + liveness + work-domain email control (ladder rung 2) |
| **Tier 1** | Identity-checked | Referee IDV + liveness passed; work-email layer incomplete (reason displayed — e.g. referee has left that employer; affiliation may be LinkedIn-corroborated per §4.2 rung 1) |

- **No Tier 0.** A reference cannot enter a passport as deliverable below Tier 1.
- Tier is **point-in-time evidence, frozen at collection**: a Tier 3 reference stays Tier 3 after the referee leaves that employer — it certifies what was true when the reference was written. No decay. (Departure triggers a contact-channel confirmation prompt and a departure date on the affiliation record.)
- **Defunct/uncorroborated employer cap (D-09):** references for employers that are deregistered, have no ABN record, or cannot be corroborated are capped at Tier 1 permanently and labelled "employer no longer operating — details not independently corroborated." Faking via a dead employer buys the weakest label in the product.
- Every reference displays: tier + verification basis (DVS-verified / Document-checked) + affiliation evidence (which ladder rungs were met).

### 4.4 Employer verification & the Tier 3 gate

- **Registration:** ABN validated against the ABR (active, entity name match), business-domain email control, authorised-representative declaration, payment method on file before paid pulls.
- **Request privileges** (sending requests, not merely registering) additionally require (D-15): the domain matches the entity's public footprint (website on the domain naming the entity, or a sector-register listing) or the account goes to manual review; care providers are cross-checked against the NDIS / aged-care provider registers; display-name ≠ ABR entity-name mismatches are **blocked, not warned**. Manual approval applies throughout the pilot.
- **Tier 3 conferral gate (D-05 — the cheapest high-value forgery in the drafts, now closed):** an employer account can confer Tier 3 only if (a) its ABN has been active ≥12 months **or** it appears on a sector register (NDIS Commission provider register / My Aged Care directory); (b) the account is ≥90 days old with a payment method on file; (c) the employment confirmed is with **that same ABN entity** — an employer can never confirm a referee's role at a different organisation. New/unregistered employers' exit references launch at Tier 2 max, labelled "employer confirmation pending." (An AU sole-trader ABN is free and near-instant and ABNs are public — without this gate, a candidate could mint Tier 3 for a confederate in an afternoon.)
- **Tier 3 sampling audits (D-07):** the platform manually verifies a random 5% of Tier 3 confirmations per month, calling the employer's independently sourced number (from the sector register, not the account). The audit's existence is publicised; results feed risk scoring.
- **Continuous eligibility (product hardening §C5):** ABN status is re-checked at **request creation** and again **at the moment of delivery**. A cancelled ABN mid-request puts the request into **SUSPENDED_EMPLOYER**: candidate and referees notified factually, windows freeze, no delivery. Reinstatement within 14 days resumes with windows extended by the suspension; otherwise the request closes `CLOSED_EMPLOYER_INELIGIBLE`. Deregistration within 30 days *after* a delivery triggers candidate notification.

### 4.5 Candidate verification

Candidate document IDV (same provider flow as referees) is **required before a passport can be Certified and before it can carry the verified public link/badge** (spec wins over the build plan's deferral — red-team D-20, buildops adjudication #2). Draft building stays email + mobile OTP so the funnel isn't hurt; the trust artefact is never issued to an unverified identity. Candidate↔referee document-hash cross-check runs at collection: **a referee whose verified identity matches the candidate's is a hard block** (self-reference). Legal name changes re-bind via provider re-verification; former names are retained only in the internal audit record, never displayed.


---

## 5. The reference — anatomy, types & the final question set

### 5.1 Anatomy

A **Reference** attaches to one (Candidate × Employment Record × Referee) triple, in two layers:

- **Factual layer** — employer legal/trading name, candidate role/title, employment type, start/end dates, setting, referee relationship + supervision period, rehire-eligibility flag where the referee is authorised to state it. **Permanent.** Corrections only via §6.7.
- **Evaluative layer** — the standardised sector question set (§5.4) on scales + optional bounded comments. **Expires 12 months** after collection or last reconfirmation. After expiry it is retained (audit, candidate access) but **not deliverable** until reconfirmed; the factual layer remains deliverable, labelled.

**Versioning:** every referee edit creates a new immutable **Reference Version**; the newest is the *standing version*. Delivered pulls are **snapshots** — content-hashed at delivery, the hash recorded in the audit row and on the employer's receipt. An employer who received v2 keeps v2 even if v3 is created later. Post-delivery edits within 24h of a delivery trigger a notice to the receiving employer ("the standing version changed after your delivery; your snapshot is unchanged").

### 5.2 Reference types held in the passport (v1)

| Type | Description |
|---|---|
| **Factual Confirmation** | Factual layer only. The first-class output for dates-only corporate referees/HR — *not* a failed reference, a distinct product |
| **Standard Evaluation** | Factual + evaluative layers via the sector question set |
| **Exit Reference** | Either of the above, issued through the employer's offboarding flow (§6.3), flagged "Issued at exit — {date}", Tier 3 when employer-confirmed |

**Not in v1:** free-form uploaded testimonial letters (unverifiable, unmappable — and candidate-carried letters are exactly what safer-recruitment regimes reject). Structured content only.

### 5.3 Experience Records (Placement / Volunteer) — decided in freeze

New graduates are the care funnel's widest point, and placement supervisors are real supervised-work referees. Alongside Employment Records, the passport holds **Experience Records** (Placement / Volunteer): TAFE/clinical placement supervisors and volunteer coordinators act as referees under *identical* verification and consent rules, with the question set adapted (F3/F9 reworded for placement/volunteer engagement; E11 becomes "Would you accept this person again in a similar placement/volunteer role?"). The record is permanently labelled **Placement** or **Volunteer** — never presented as employment. Informal experience (e.g. caring for a family member) may be listed as unreferenced text only — no referee flow in v1.

### 5.4 The standard question set — FINAL (Aged Care & Disability Support, v1)

Design rules: closed formats wherever possible; every evaluative item is about *observed work*, never protected attributes or the candidate's health; completable in ~8–10 minutes fresh, ~3 minutes pre-filled. "Not in a position to judge / Prefer not to state" is an explicit, non-penalised option on every evaluative item. Referee attestation precedes submission: *"This is true to the best of my knowledge, and I understand it may be shown to prospective employers and to the candidate."* The set is **frozen as legally reviewed** (§13): any future item addition requires a discrimination + APP 3 screen before shipping.

**Part F — Factual layer (permanent)**

| # | Item | Format |
|---|---|---|
| F1 | Employer (legal/trading name) and service setting | Pre-filled from employment record, referee confirms/corrects. Setting: Residential aged care / Home & community care / Disability — SIL / Disability — community & day programs / Respite / Other |
| F2 | Candidate's role/title(s) with this employer | Short text |
| F3 | Employment type | Casual / Part-time / Full-time / Agency-engaged |
| F4 | Employment start and end date (or "current") | Dates (month/year precision allowed) |
| F5 | Your relationship to the candidate | Direct supervisor / Roster or service coordinator / HR or management / Colleague (not supervisor) — plus supervision period (from–to) |
| F6 | Supervision exposure | Shifts/hours under your supervision: <20 / 20–100 / 100–500 / 500+ |
| F7 | Direct care duties performed (multi-select, tick only what you observed) | Personal care / Medication support / Manual handling & transfers / Community access / Domestic assistance / Behaviour support (per BSP) / Documentation & progress notes / Transport |
| F8 | Reason for leaving | Resigned / End of contract / Redundancy / Still employed / Other / Prefer not to state *(candidate's own statement shown separately if provided — discrepancies are displayed, not adjudicated)* |
| F9 | Rehire eligibility (factual) | "To your knowledge, is the candidate eligible for rehire by this employer?" Yes / No / No policy or not in a position to state |

**Part E — Evaluative layer (12-month expiry; scale: Consistently / Usually / Sometimes / Rarely / Never observed + Not in a position to judge)**

| # | Item |
|---|---|
| E1 | **Reliability** — attended rostered shifts as scheduled and on time |
| E2 | **Reliability of communication** — gave timely notice of unavailability; responded to roster communications |
| E3 | **Documentation** — progress notes, charts and incident reports accurate and on time |
| E4 | **Safe practice** — followed care/support plans, manual-handling procedures, infection control |
| E5 | **Medication support** — strictly as directed and within scope of role *(only shown if F7 includes medication support; otherwise auto-marked "not applicable")* |
| E6 | **Respect & person-centred practice** — dignity; choice, privacy, culture, communication needs |
| E7 | **Communication & escalation** — clear with clients, families, team; recognised and escalated concerns appropriately |
| E8 | **Safeguarding (closed format)** — "To the best of your knowledge, while employed here was the candidate the subject of a *substantiated* complaint, investigation finding, or disciplinary outcome relating to the safety, wellbeing or property of a client?" Options: **No, not to my knowledge / Yes / Prefer to discuss with the employer directly / Not in a position to know**. A "Yes" unlocks one optional short factual comment. The word "substantiated" is not to be softened in copy or tooltips. See §13.4 for the fences on "prefer to discuss" (final retain/remove call reserved to defamation counsel — Lawyer Q5) |
| E9 | **Trust & boundaries** — client money, property, confidential information; professional boundaries |
| E10 | **Teamwork & feedback** — professional with colleagues/supervisors; responded constructively to feedback |
| E11 | **Rehire judgement** — "Would you employ this person again in a similar role?" Definitely yes / Yes / With reservations / No / Not in a position to judge |
| E12 | **Overall recommendation** — Strongly recommend / Recommend / Recommend with reservations / Do not recommend / Not in a position to judge |
| E13 | **Strengths** *(optional free text, 280 chars)* |
| E14 | **Development areas** *(optional free text, 280 chars — framed as "what should a new employer support them with?")* |

**Mandatory disclaimer in every delivered pack and on the public question-set page:** *"This reference is not a worker screening check, police check, or working-with-children check, and does not satisfy any obligation under the Aged Care Act 2024 (Cth) or the NDIS worker screening rules."* E8 never replaces mandated screening, and the pack says so.

**Free-text screening (build requirement, legal §2.5):** every free-text submission/edit (E13/E14, E8 comment) passes an automated screen (profanity; protected-attribute and health terms; allegation keywords; PII patterns). Flags route the version to **held** — it cannot go STANDING until a trained admin clears it under a written rubric ("return to referee with guidance"; admins never edit referee words). Referee-facing guidance at the field: *"Describe observed work only. Do not allege misconduct — formal outcomes belong in E8's closed options."* Inline instruction on F8/E8/E13/E14: *"Do not include information about the candidate's health, medical conditions, or any protected attribute."*

### 5.5 Passport contents & caps — final

Per employment: factual layer + evaluative layer (if given) + type flag + assurance tier + verification basis + version history + status (Standing / Evaluative expired / Revoked). Multiple references per employment (e.g. supervisor evaluation + HR factual) are stored and delivered as a bundle.

- **Unlimited Employment Records; up to 3 referees per employment** (supervisor + HR + second supervisor covers every real care pattern). This overrides the build plan's "up to 3 standing references" per passport — the cap is per employment, not per passport (a casual care worker holding 2–3 concurrent jobs is the wedge user; a per-passport cap would kill the product for exactly them).
- The public verification page shows the 3 most recent employments by default with full history one click away; pulls always include the whole record. Display pagination is not curation; the completeness indicator counts the whole record.
- **Dormancy:** after 24 months without login the passport enters dormant state — the public link still resolves (links in old applications must not rot), evaluative content will in practice have expired, one reactivation email is sent. No data is deleted for dormancy.

---

## 6. Core flows

### 6.1 Collection — candidate-initiated (primary)

1. Candidate adds an Employment Record and nominates a referee (name + work email or platform identity).
2. **Candidate pre-briefing is a required step** before any referee contact ("your ex-manager has been told to expect this" — the referee must never be surprised by us).
3. Referee is invited. The invitation names the candidate and the employer in the subject line, explains the verification steps before any link click is required, and is sent from the platform domain — designed against the documented "mistaken for phishing" failure. If new, the referee completes verification (§4) and claims/creates their account.
4. Referee completes the sector question set for that employment — or factual-only, with the reason captured ("company policy limits me to factual confirmation" is a stored, displayable fact, not a failure). **Sequence the friction:** the referee drafts the reference *before* IDV is requested ("verify once, never fill this form again"); the reference becomes deliverable only once IDV + liveness pass (§4.1).
5. Referee reads and accepts the **collection consent** (§6.5) and attests to truthfulness.
6. Reference enters the passport as STANDING v1. Candidate is notified the moment a reference is collected (who/what/when) — before it can be delivered anywhere (APP 5.2 as a product behaviour).

**Referee-first collection:** a verified referee can pre-register candidates they supervise and issue references proactively; the candidate claims them into their passport by accepting. Same consent, same set.

**Collection quality gates:** the referee's declared supervision period must overlap the candidate's claimed employment dates; mismatches route to a clarification step, not silent acceptance. One standing reference per (candidate × employment × referee).

### 6.2 The verification-timing rule (unit-economics load-bearing)

**Verify-on-demand:** a passport is free to build and collect in draft; referee IDV is consumed at candidate certification **or** at the first employer request, whichever comes first — not at nomination. IDV-ing every nominated referee upfront would leak ~A$3–5 per abandoned passport and roughly double effective cost per paid passport. This sequencing is built in from the start, not optimised later.

### 6.3 Collect-at-exit — the supply engine (concierge in v1.0)

Without collect-at-exit the vault always lags one job behind — the most recent employer, the one hirers most want, is never in it. Exit collection is the only flow that fixes coverage of the latest role.

- **v1.0 form: concierge / admin-triggered.** Ali or an operator initiates the exit flow for a founding employer; the referee experience is identical to normal collection; the employer's verified account confirms the referee's role → Tier 3, flagged "Issued at exit." **No employer self-serve offboarding UI and no HRIS/payroll triggers in v1.0** (self-serve is v1.1; automation is v2). If the concierge form slips, founding employers onboard referees via the standard candidate-initiated flow for the pilot's first half (pre-agreed slip list, §11).
- **Free to employers during the pilot** — it is the supply engine; charging for it would tax our own moat. Post-pilot: included free in the Scale plan; a standalone SKU (A$59/mo per organisation) launches only on the trigger in §16 (≥5 non-Scale employers asking — inbound pull, not a sales push).
- Pitch to the employer (approved copy, substantiation-checked): *"Issue it once, at exit, and never field a reference call for this person again — every future request is handled here, with your referee's standing answers."*

### 6.4 The referee-refusal fallback ladder (per employment, each rung labelled)

1. **Alternate referee** for the same employment (manager's manager, another supervisor, HR) — normal flow.
2. **HR Factual Route:** a lightweight factual-confirmation flow completable by *any* authorised person at the employer (HR/payroll) via single-use verified link + work-domain email + attestation — **no full referee account required**. Produces a Tier 1 **Factual Confirmation**. This deliberately captures the large dates-only corporate supply instead of losing it.
3. **Candidate documentary evidence:** candidate uploads separation certificate / payslips / contract, displayed under the explicit label *"Candidate-provided documents — not referee-verified."* Never called a reference, never badged.

The employment's status then reads e.g. *"Reference unavailable — referee declined to participate; documentary evidence provided."* A referee decline is a fact about the referee, recorded neutrally — never rendered as a black mark against the candidate beyond the absence itself.

### 6.5 Consent — the pre-authorisation (the legal engine)

At collection the referee gives informed consent via a plain-language APP 5 notice (plain-language summary presented in the UI; formal text one tap below) + explicit acceptance, covering:

- Storage and disclosure to **verified employers, for roles the candidate applies to and authorises** — 12 months (evaluative) / until revoked (factual);
- **Default release, in plain words, separately ticked:** *"If you don't respond within the window when an employer asks, the standing reference is released as-is, and the employer is told you were notified and didn't update it."* Default-submit is consented, not buried;
- Notification on every disclosure + one-tap revoke;
- The candidate can read the reference (APP 12) — stated **before** the referee writes anything;
- Revocation is prospective: it stops future disclosures; past delivered snapshots are not recalled (stated plainly).

Candidate consent at passport creation names the categories the passport may hold — including "formal workplace outcomes (complaints/investigation findings) recorded by referees" and "information a referee volunteers that relates to your health or capacity at work" — so APP 3.3 consent exists before any E8 answer is collected. Per-application authorisation (§6.8) covers each share.

**The permanent product gate (legal §1.3):** every disclosure stays inside the triangle — verified employer + specific application + candidate authorisation. Any future feature outside that triangle (analytics products, benchmarking, talent search) is a new purpose requiring new consent. No exceptions, no "we're probably exempt" reasoning anywhere (§13.1).

**Notification + audit (both sides):** referees are notified on every request naming them, every delivery (who/role/when/label), and every reconfirmation ask. Candidates see the full pull history in their dashboard. There is no silent pull — delivery writes the audit records in the same transaction as the delivery itself.

### 6.6 The referee value loop (why a busy supervisor acts the tenth time)

Friction reduction gets the *first* reference; only value gets the tenth. Four parts, all adopted:

1. **Hire-outcome notifications.** At request resolution the employer is prompted (one tap) to mark the outcome: hired / not hired / pending (prompted again at +14 days). On "hired," the referee is notified: *"Sarah, whose reference you gave, was hired at {Agency}."* Outcome marking is also a trust control: it becomes mandatory for continued request privileges beyond a monthly allowance (§8.2, D-22).
2. **Referee Credits.** Each completed reference, in-window confirmation/edit, and reconfirmation earns credits: 1 credit = A$1 off pulls when that referee (as an employer user in any org they belong to) pulls references, capped at 50% of any invoice; non-transferable, never cash-redeemable, expire in 24 months. **Accrual starts at launch; redemption activates with agency plans (v1.1)** (decided in freeze — pilot pull revenue is unaffected because pilot agencies are free anyway, and the promise is visible from day one).
3. **Verified Referee recognition.** A public, referee-controlled profile ("Verified Referee since 2027 · 14 references given · Aged care & disability") with a LinkedIn-addable credential link — counts, sectors, tenure only. **Never** ratings or scores derived from reference content (a rated referee is a referee who stops writing honestly). Ships v1.1 (decided in freeze).
4. **Time-saved receipt.** After each resolved window and quarterly in digest: *"This request took you ~2 minutes vs ~15 by phone. This year: 9 references, ~2 hours saved, 4 people hired."*

### 6.7 Revocation, correction, disputes (APP 12/13 as features)

- **Revocation:** referee one-tap revoke per reference (or per candidate, or global pause). Effect: immediately non-deliverable; open tasks resolve as REVOKED (§6.8); candidate notified neutrally ("a reference is no longer available" + the standard line that referees may withdraw for any reason, including leaving the sector — normalising withdrawal so it carries no accusation). Employer-side, revocation mid-window is indistinguishable from decline (§6.8) — signalling "withdrawn" would publish an implication the referee never consented to.
- **Candidate access (APP 12):** self-serve, free, immediate in-product — everything stored about them, including referee content. Redaction line: the referee's *private* contact details (personal phone/email) are redacted as third-party PI; referee identity, role, and all content about the candidate are **not** redacted. Manual requests answered within 30 days. Any partial refusal issues written reasons + the complaint pathway (internal → OAIC) from a pre-built template.
- **Factual disputes (adjudication with teeth):** candidate may attach documentary evidence (separation certificate, payslips, contract). Acknowledge ≤2 business days; referee asked to confirm/correct (7 days); if the referee doesn't respond or disputes it, an admin adjudicates on the evidence. Where evidence is conclusive, admin applies an **audit-logged factual override** labelled on the pack: *"Corrected by RefereeChecks on documentary evidence, {date}. Referee notified."* The referee may appeal an override once, with counter-evidence. During a dispute the reference remains deliverable but the disputed field carries a "disputed — evidence on file" marker. Employers who previously received the wrong fact are notified of the correction (mandatory, templated) — and a delivered pull later corrected has its fee credited and the corrected pack re-delivered free (§9).
- **Evaluative disputes:** never adjudicated, never badged. The candidate's remedy is the **response statement** (§5/§6.8: attached to the reference and delivered **inline** with it — for E8 content, the employer cannot read the flag without the candidate's reply beside it) plus, for alleged defamatory content, the suppression workflow (admin suppresses pending review; suppression is disclosed to candidate + referee; complaints mechanism + suppression within **7 days** nationally, §13.3).
- **Referee-initiated edits (outside any request):** allowed at any time (new immutable version). Factual changes require a reason code (error at writing / records updated / other + note). Candidate notified immediately with the fields-changed summary. Employers with an open window see the new version flagged. Past snapshot recipients are **not** notified of evaluative changes (snapshots stand) **except** factual corrections, which follow the notify-past-recipients rule. An edit that materially worsens a reference within 14 days of the candidate viewing it (an APP 12 access event) is flagged internally for a welfare/support review — not blocked, but a human looks (that pattern is the signature of a dispute or coercion).

### 6.8 The core mechanic — edit-or-default (final state machine)

**Two request depths** (one state machine):

- **Check** (shortlist stage) — **A$6.** Instant, no window. Delivers the factual layer + E11 (rehire judgement) + E12 (overall recommendation) as standing answers with Label-C-style provenance. Requires candidate authorisation; **one authorisation "for this application" covers one Check and one later Full Request for the same role** — the candidate taps once per application, not per stage. Referee protection: collection consent explicitly covers headline-item instant release; referee notification fires simultaneously with delivery; any referee may set **"Always window my references"**, which forces every release of their evaluative content — including Checks — through the window (shown to employers only as "referee requires review window").
- **Full Request** (offer stage) — **A$12** (A$6 if it delivers factual-only, §9). The windowed flow below.

**Full Request flow:**
1. Employer (verified, request-privileged) opens a Reference Request against a specific application: candidate, role applied for, relevant employment(s), and their question list (sector template, structured intake, or — v1.1 — API; §10).
2. Candidate authorises (push/email → the authorisation screen, §8.2 D-14). No authorisation → no disclosure; the request expires after 7 days (`CLOSED_EXPIRED`). The candidate may withdraw authorisation at any time before delivery (`CLOSED_WITHDRAWN`) — one tap from their audit view, pushed on every state change.
3. On authorisation, the **factual layer is released immediately** (facts are permanent; pre-authorisation covers them; this is the instant win vs a 3–15 day status quo).
4. Each relevant referee is notified and their task window opens (§6.9). The referee's form is **pre-filled with the standing version's answers**, with the employer's mapped questions shown against them (§6.10). Editing is a 3–5 minute task.
5. Window closes → outcome per referee task below. The full pack is delivered as a frozen, content-hashed snapshot with the labelling of §7.

**Request lifecycle** (one Request per application; fans out to one Referee Task per relevant reference):

```
DRAFT
  → PENDING_EMPLOYER_VERIFICATION   (employer account not yet verified)
  → AWAITING_CANDIDATE              (candidate authorisation requested; expires undisclosed after 7 days)
  → WINDOW_OPEN                     (candidate authorised; factual layer RELEASED; referee tasks created, referees notified)
  → PARTIALLY_DELIVERED             (≥1 referee task resolved, ≥1 still open)
  → DELIVERED                       (all referee tasks resolved; snapshot delivered)
  → SUSPENDED_EMPLOYER              (ABN cancelled mid-request — windows freeze; resumes on reinstatement ≤14 days, else CLOSED_EMPLOYER_INELIGIBLE)
  → CLOSED_EXPIRED                  (candidate never authorised → nothing disclosed)
  → CLOSED_WITHDRAWN                (candidate withdrew before delivery)
```

**Referee Task lifecycle:**

```
NOTIFIED ── referee edits ──────────────→ UPDATED        → delivered (Label A)
NOTIFIED ── referee releases as-is ─────→ CONFIRMED      → delivered (Label B)
NOTIFIED ── window lapses, no action ───→ DEFAULTED      → standing version delivered (Label C)
NOTIFIED ── referee declines this use ──→ DECLINED       → nothing delivered for this reference
NOTIFIED ── referee revokes reference ──→ REVOKED        → nothing delivered; reference leaves passport
NOTIFIED ── notification undeliverable ─→ UNREACHABLE    → standing version delivered at window close (Label C + unreachable flag)
(any open state) ── referee snoozes ────→ window +1 business day (once per task; §6.9)
(any open state) ── evaluative layer already expired at request time ──→ RECONFIRM_ONLY
                                     (referee asked to reconfirm/re-answer; if no action:
                                      factual layer only delivered, evaluative shown as EXPIRED)
```

**The delivery-confirmation rule (D-19):** if **no** notification channel confirms delivery, the evaluative layer does **not** default-release — factual layer only, labelled. A reference never default-releases on the strength of an email nobody received. (The UNREACHABLE delivery above applies where notification was delivered but unanswered channels later fail — where delivery was confirmed to at least one channel; where none was, factual-only applies. Decided in freeze to resolve the D-19/spec overlap.)

**What the employer sees in each state:**

| State | Employer view |
|---|---|
| `AWAITING_CANDIDATE` | "Waiting for the candidate to authorise this request." No content, no referee identity |
| `WINDOW_OPEN` | Factual layer in full (labelled Standing Facts). Per reference: referee role/relationship, assurance tier, verification basis, standing version date, evaluative age, status "Referee notified {date} — update window closes {date/time}" |
| `PARTIALLY_DELIVERED` | Resolved references in full with labels; open ones as above |
| `DELIVERED` | Complete snapshot: all references with provenance labels (§7), per-answer tags (§6.10), question-coverage summary, immutable snapshot ID + timestamp |
| Task `DECLINED` | "The referee for {Employment} declined to release a reference for this application." No content, no reason (reasons are never solicited or shown — a reason field would become a shadow reference) |
| Task `REVOKED` | Shown identically to DECLINED ("No current reference available for this employment") — the employer is **not** told a reference existed and was withdrawn |
| Task `UNREACHABLE` | Standing reference at close with Label C plus flag: "Referee could not be contacted at their verified address; released under the referee's pre-authorisation" |
| Task `RECONFIRM_ONLY`, unresolved | Factual layer + explicit panel: "Evaluative content expired {date}. The referee was asked to reconfirm and did not respond." Absence is labelled, never silently omitted |
| `CLOSED_EXPIRED` / `CLOSED_WITHDRAWN` | "This request closed without disclosure." Nothing else |

**In-window referee edits are visible to the candidate in real time** (they can read the content under APP 12 anyway — notification removes the ambush), and the candidate may withdraw authorisation until the pack reaches DELIVERED (D-35). The referee's edited version still becomes the new standing version — suppressing it would make the platform a laundering service for stale praise. The provenance banner discloses "Referee updated N answers on {date}" with fields changed.

**Additional in-request candidate prompts (decided in freeze — they keep employer behaviour inside the consent architecture during the pilot, protecting the acceptance metric's validity):**
- **Additional referee nomination:** inside a Request, an employer may ask the candidate to nominate an additional referee for a specified employment. The candidate nominates (normal collection; joins the bundle for future pulls, and for the current request if collected before window close + 2 business days, else as a post-delivery supplement the employer is notified of) or declines. A decline is shown factually: *"Candidate was asked to nominate an additional referee for this employment and did not."* No reason is solicited.
- **Unlisted employment:** an employer may flag *"We'd also like a reference for the candidate's time at {Employer}."* The candidate can add the Employment Record + nominate a referee (normal flow) or decline. State shown factually ("candidate added / candidate did not add"). The flag itself discloses nothing.

**Duplicate-application pack transfer (v1.1, decided in freeze):** where the same candidate + same end employer + similar role appears via two agencies within 60 days, the second org is told only: *"A reference pack for this candidate was delivered for this employer on {date} via another agency."* No content crosses. The **candidate** may choose "reuse my recent pack" — transferring the existing snapshot as a fresh disclosure (referee notified as usual; referees are not re-windowed; pack labelled with its original collection context). Candidate-initiated only, never automatic, never org-initiated. Certified-tier feature.

### 6.9 The window — fixed at 3 business days (final)

- **Platform-fixed, identical for everyone, not employer-configurable.** Employer-set windows are gameable both ways (a 2-day window over a weekend manufactures defaults; a friendly employer stretches windows for favoured candidates). Uniformity is part of the fairness story — and legally cleaner.
- Clock: Australia/Sydney business days (Mon–Fri excl. AU national + NSW public holidays), starting at notification delivery. All window logic runs on an injectable clock in tests (§11).
- **Why 3:** v1 referees are rostered care supervisors (nights, weekends, split shifts) — a 24–48h window falls entirely inside days-off for many, so most requests would default and the "updated" trust signal would become meaningless. 3 business days spans up to 5 calendar days. Worst case (full default) is still 2–5× faster than the 3–7 business-day manual norm (10–15 day industry referencing norm), with the factual layer already delivered day 0. At 5 days the default path converges on the manual process's best case and the speed story — the entire purchase reason — evaporates.
- **Notification cadence (final, merged):** window-open (email + SMS if enabled) → +1 business day reminder (email only) → 24h before close (email + SMS) → 4h before close (SMS, only if the referee has not acted; if the referee *opened* the action page but didn't complete, this prompt fires regardless — D-19). Candidate authorisation requests: open notification + day-2 and day-5 reminders, expiry day 7. Pull notifications to referees: **daily digest by default** (instant only on opt-in) — per-pull instant SMS would train referees to ignore the channel windows depend on.
- **Quiet hours:** no SMS 21:00–07:00 referee-local (profile setting; default Australia/Sydney). A queued message's wording is adjusted to the real remaining time. Email is unqueued but timestamped honestly.
- **Referee snooze:** once per task, the referee may snooze **+1 business day** ("I'm on days off"). The window extends; the employer sees the factual state "referee requested +1 day — window closes {new date}." Not available in the final 4 hours. We deliberately do **not** infer shift patterns — a snooze button respects rosters without surveillance.
- **Early close:** Confirm-as-is closes the referee's window immediately (and doubles as a reconfirmation, §6.11).
- **No human escalation to referees in v1** (no platform phone calls — that recreates phone tag and the phishing problem). Pilot-only exception: ops may trigger one additional email for tasks about to default where the referee has a history of engaging — an ops-console action with an audit entry.

### 6.10 Question mapping — bespoke questions vs the standard set

Employers ask their own questions; referees answered a standard set. The mapping system bridges them **without ever inventing an answer**. Mapping is a *routing* decision, never a *content* decision: the system never rewords, merges, or synthesises a referee's answer to fit a question.

**Three intake paths:**
1. **Sector template (preferred):** employer adopts the §5.4 set verbatim or as a subset → perfect mapping, full coverage. The product nudges hard toward this.
2. **Structured intake:** employer pastes/types questions; each is classified at intake and the employer sees the mapping *before* submitting ("Your question 6 doesn't match anything referees are asked — it will be sent to the referee as a new question").
3. **API intake (v1.1):** questions with optional standard `question_code`s get deterministic mapping; free-text goes through the same classifier as (2).

**v1.0 mapping is deterministic only** (decided in freeze, buildops adjudication #4): standard question codes, exact/fuzzy text match against a curated synonym table, and the employer's own pre-submission mapping preview (they confirm or correct every suggested mapping). Unmapped questions go to the referee as genuinely new questions in the pre-filled form — answerable only by referee action, never by default; if unanswered they deliver as **NOT COVERED** (§7). **No ML/LLM classifier in v1.0** — a wrong silent mapping misrepresents a referee's answer (an accuracy *and* legal risk), and pilot employers are onboarded onto the sector template anyway. Semantic mapping is v1.1, shipped only behind a measured **≥98% precision** gate on a labelled test set, and when it ships it is **de-identified before it leaves AU infrastructure** (question text + sector code only — never candidate/referee/employer identifiers; legal §1.5).

**Learning loop (bounded):** employers' unmapped questions are aggregated (anonymised) as candidate additions to future question-set versions — how the standard set converges on what the sector actually asks (a deliberate ecosystem-standardisation play), subject to the §5.4 legal screen for new items.

### 6.11 Freshness — expiry & reconfirmation

- Evaluative layer expires **12 months** after collection or last reconfirmation. Expiry is a state, not a deletion.
- **One-click reconfirmation:** candidate- or request-triggered. The referee sees their standing answers and taps "Still accurate" (extends 12 months, logged as a reconfirmation event with its own label), edits (new version, clock resets), or declines (evaluative layer stays expired). One-tap **Confirm-as-is inside a window is the same act** — it refreshes the timestamp.
- Rate limit: max 1 reconfirmation ask per reference per 90 days outside an employer request (anti-harassment).
- **Unprompted batched ping at month 9** (adopted, bounded): one message per referee covering *all* their references expiring within the next quarter — "3 of your references expire soon — review them together" — one tap per reference (still accurate / edit / let expire). No second ping if unanswered (employer requests already trigger the flow). Referees can opt out of unprompted pings entirely.
- Factual layer never expires; error paths are correction (§6.7) or revocation, not expiry.

### 6.12 Referee permanent unreachability / death

A referee-level state **UNREACHABLE-PERMANENT**, entered when: (a) 3 consecutive requests resolve UNREACHABLE across ≥90 days, or (b) all notification channels hard-bounce for 12 months, or (c) death/incapacity is credibly reported (candidate, employer, or family — admin-verified before applying). Effect: evaluative content continues to deliver until its existing 12-month expiry (the consent was explicit; the expiry clock is the safeguard), then expires permanently — never reconfirmable. Every delivery after the state is set carries the flag: *"Referee no longer contactable — this reference cannot be updated or reconfirmed."* Factual layer persists with the same flag. Account locked against new references; the platform email stops accepting new requests and auto-replies directing factual enquiries to the former employer's HR route (§6.4). Death reports are handled by a named admin workflow with a condolence-safe script — no automated message ever goes to a deceased referee's channels once reported.

### 6.13 Referee handover (supervisor changes)

**Authorship never transfers** — a reference belongs to the person who wrote it, forever. Handover applies to everything else: pending collections may be reassigned to a successor supervisor (candidate request + outgoing referee confirmation, or the employer's exit-flow admin) — the new referee starts fresh with their own verification and answers. An employer org may reassign its HR factual-contact (§6.4) at will via org Admin. On a referee's affiliation ending (self-reported or detected via bounced work email), they get one message: confirm personal channels, review references given at that employer (which remain theirs), optionally note a successor for future candidates.


---

## 7. Labelling — final

Every delivered reference carries a **provenance banner** — one of:

- **Label A — "Updated for this role":** referee edited or added answers within this request's window. Shows: referee name/role, assurance tier, verification basis, "Updated {date} for {Role} at {Employer} · Standing reference originally collected {date}".
- **Label B — "Confirmed for this role":** referee actively released the standing version unchanged within the window. Shows: "Referee reviewed and confirmed without changes on {date} for this application · Originally collected {date}". An active confirmation is a *stronger* signal than an edit and is its own class — never merged with default.
- **Label C — "Standing reference":** released by default at window close (or referee unreachable). Mandatory wording: *"Collected {date} · Referee notified of this application on {date} and did not update or withdraw it · Released under referee's standing authorisation."* The words "did not update" are mandatory — a defaulted reference must never be presented as role-specific. The UNREACHABLE variant adds: "Referee could not be contacted at their verified address."

**Per-answer provenance tags** (in the delivered pack):

| Tag | Meaning |
|---|---|
| **FOR THIS ROLE** | Referee answered/edited this within the current window (Label A) |
| **CONFIRMED** | Standing answer the referee actively confirmed for this application (Label B) |
| **STANDING** | Standing answer released by default (Label C) |
| **MAPPED** | Shown additionally when the employer's question was mapped to a standard question — the mapping is displayed: "Your question: '…' → Standard question E9 (Rehire)" |
| **NOT COVERED** | Employer question had no standing equivalent and the referee did not add an answer. Delivered as an explicit empty entry, counted in the coverage summary — never silently dropped |

**Age badges:** evaluative age shown ("Evaluative answers: 4 months old · expire {date}"; amber if >9 months; expired state per §6.8). Factual age shown as collection date only (facts don't decay; no alarm styling).

**Coverage summary** on every delivered pack: counts of employer questions answered-for-this-role / answered-standing / not covered.

**Assurance display:** tier (§4.3) + verification basis (§4.1) + affiliation evidence (§4.2) on every reference. Weak-evidence references are labelled as weak — the label system exposes them rather than laundering them.

**The QA rule (testable):** from the delivered pack alone, an employer must be able to reconstruct exactly what the referee did and didn't do, and when. Any UI copy that blurs the A/B/C distinction fails review. Delivered packs are snapshot/golden-tested in CI — any copy or structure change fails the build until a human approves the new golden file (§11).

**Non-removable in all tiers, forever** (including any future white-label): provenance labels A/B/C, assurance tiers, verification badges, snapshot ID / verify tool, and a "Powered by RefereeChecks verified reference network" line.

### 7.1 The public verification page & the verify endpoint (red-team split)

The candidate's link is public in practice (CVs, LinkedIn, job boards) — so it is designed as public:

- **Anonymous layer (link only):** candidate name, "identity verified" badge (certified passports only), per-employment **status chips only** ("Reference collected · Identity-verified referee · Current/Expired"), completeness indicator. **No dates, no employer names beyond what the candidate's CV already shows, no factual detail.**
- **Detail layer:** factual layers unlock after the viewer supplies a work email and passes an email OTP — still zero signup, still seconds — and every unlock writes an audit row (viewer email, timestamp, IP) visible to the candidate ("your passport detail was viewed by …@agency.com.au"). Evaluative content is **never** on the public page at either layer — it requires a Check/Full Request (§6.8).
- **Verify endpoint:** accepts **only the candidate-issued passport token**. There is no lookup by name, email, phone, or document — for anyone, including via the API. Responses are uniform: an invalid/unknown token returns the same shape and timing as a revoked one ("no verifiable passport at this link") — no existence oracle. Verify returns **no dates** and no reference content (date confirmation happens inside the application-scoped pull). Rate-limited per API key + per IP.
- **Token hygiene (build requirement):** passport link tokens, request IDs and snapshot IDs are ≥128-bit random, non-sequential, `noindex`/robots-excluded. Link rotation invalidates old tokens everywhere; already-issued snapshot URLs resolve to the employer's own authenticated copy, never a public URL.
- **"Verify this document" tool (public trust centre):** anyone holding a delivered pack enters its snapshot ID + the short code printed on the PDF and sees: authentic / not found, delivery date, recipient org, and whether the factual layer has since been corrected. Content itself is never shown. Every delivered PDF carries the snapshot ID + QR to this tool. Forged or stale PDFs are detectable in one step.

### 7.2 The referee platform email — system design

- **Address:** `firstname.lastname@refs.refereechecks.com` (numeric suffix on collision), on a dedicated subdomain with DNS delegated to Cloudflare for that subdomain only (main-domain mail untouched). Human-readable by design: an employer reading it parses a professional identity, not a token.
- **Inbound:** Cloudflare Email Routing → Email Worker (one catch-all rule — the 200-rules/domain limit is designed around, not hit). The worker does auth checks + raw store to R2 + queue enqueue only; parsing/matching happens asynchronously in the queue consumer. Product cap 10 MB per message (under the 25 MiB platform limit); larger rejected with a polite bounce. Attachments quarantined by default; links/files from raw mail are never rendered to referees.
- **Inbound email is never a request (D-17).** Only requests created through the authenticated platform flow (or a verified employer's account) create Referee Tasks. Inbound mail lands in a clearly separated "external mail" inbox in the referee dashboard, with SPF/DKIM/DMARC enforced: failing mail is quarantined and labelled; **no links inside external mail are rendered clickable** (copy-as-text only); external mail never carries platform action buttons. The referee-driven acquisition loop works by inviting the sender to create a real request — the email itself confers nothing.
- **Outbound:** all platform mail from the platform domain, SPF + DKIM + DMARC (p=reject) aligned, on a dedicated transactional sending subdomain separate from marketing. Referee replies from their dashboard (or via a relay address that rewrites From to their platform identity). The referee's personal email is never disclosed to employers.
- **What it's for:** (1) a stable identity that survives the referee changing jobs — what makes a *standing* reference reachable for years; (2) the acquisition loop — a referee hands the address to any future employer ("send reference requests here") and every such inbound request becomes a platform request; (3) masking.
- **Fallback:** AWS SES inbound → S3 + queue (same downstream pipeline); manual bridge: a Google Workspace catch-all operated by support while DNS is re-pointed. Referee addresses live on our subdomain, so addresses survive a routing-vendor change unchanged.

### 7.3 Notifications — channels & discipline

- **Channels:** email (AWS SES, Sydney) + SMS for time-critical referee events only (window opened, closing in 24h, final prompt). SMS via an Australian provider (ClickSend primary; Sinch Engage/MessageMedia fallback) — **the branded sender ID is registered on the ACMA SMS Sender ID Register through *each* provider before the pilot's first SMS** (§12/§13: since 1 July 2026 unregistered branded IDs are relabelled "Unverified" and threaded with suspected scams — near-fatal for this product). Fallback if registration lags: send from a dedicated numeric number (outside the Register's scope) — never from an unregistered brand ID. Alphanumeric IDs can't receive replies, so a dedicated number covers anything inviting a reply, and the opt-out path must work.
- **Specificity is the anti-phishing design:** every message names the candidate and the employer ("Sarah Chen, who worked for you at {Provider}, has applied at {Agency}"). No generic "you have a request" copy.
- **Platform mail discipline (D-18):** RefereeChecks never asks for credentials, OTPs, or ID documents by email, and says so in every message footer. All referee actions happen on the product domain via tokens (§8.3). This gives referees a bright-line test that survives contact with real phishing.
- **Streams separated (Spam Act):** transactional streams (request notices, reminders, delivery notices, reconfirmation asks) contain **zero promotional content** — no upsells, no cross-promotion, not even a footer banner. Marketing runs on a separate stream with full consent/unsubscribe compliance and a shared suppression list.
- **Cadence caps:** referee gets at most invite + the §6.9 reminders per window. Digest mode: a referee with multiple open tasks can batch notifications daily (auto-suggested at >5 open tasks); windows are unaffected.

---

## 8. Anti-gaming, fraud & platform security

### 8.1 Cherry-picking — all-or-nothing per employment

Within an Employment Record, sharing is all-or-nothing. If an employment is in the passport, **all** its standing references (every referee, favourable or not) are carried and delivered together, with a **completeness indicator** on the employer view ("2 of 2 collected references for this role included"). The candidate cannot hide or delete an individual collected reference (deletion is not a candidate capability at all — only referee revocation or expiry removes deliverability, and both are labelled states, not silent absences), cannot collect three references and present one, and cannot detach a reference from its employment while keeping the employment.

The candidate's legitimate controls are coarser and honest: (a) include or exclude an entire Employment Record — but the passport displays reference status per listed employment ("Reference collected / No reference collected / Referee declined / Evaluative content expired"), so an employment listed *without* a reference is itself a visible signal, exactly as a gap on a CV is; (b) stop sharing the passport entirely; (c) dispute/correct (§6.7) or attach a response statement. Justification: the executioner is employer trust — the moment a candidate-carried reference reads as cherry-picked, employers re-check anyway and the platform is an extra step. Completeness is the entire credibility proposition (the same reason worker-held clearances work: the NDIS check is the whole record or nothing).

### 8.2 Fraud controls (structural first, scoring second)

| Threat | Controls (frozen) |
|---|---|
| **Fake referee** (candidate's mate) | Document IDV + liveness mandatory before any delivery (§4.1); work-domain email control for Tier 2; tier labelling exposes weak-evidence references |
| **Referee mills** (bought/rented real identities) | **Velocity caps (D-02):** max **8** standing references per referee per rolling 90 days and **15** per rolling 12 months across *unrelated* employers (single-employer collect-at-exit flows exempt — volume there is expected and the employer is accountable); above the cap, references queue for manual review before becoming deliverable. **Risk scoring (D-04):** server-side score per reference from graph/content signals — referee account age vs first reference, reciprocal pairs, shared device/IP/payment instruments, employment-overlap impossibilities, text similarity across a referee's references for different candidates, employer footprint (no ABN/web presence, domain <12 months old). Above threshold → held "under review": employer sees factual layer only with an explicit "verification in progress" state, never a silent delivery. **Network ban (D-06)** keyed to the document-hash HMAC and ABN — a burned identity is burned forever, which collapses mill economics (each identity costs a real person's cooperation + a unique document + a face, and yields ≤15 saleable references/year) |
| **Self-reference** | Hard block: referee document hash == candidate document hash (works across roles by construction, §3). Soft signals (shared device fingerprint/IP at collection, same residential address on IDs, referee account created <24h before the collection request) → review queue, reference held at Tier 1 pending manual check |
| **Collusion rings** (candidates refereeing each other) | **Reciprocity/cluster detection (D-08):** reciprocal pairs (A referees B, B referees A — auto-flagged; within 90 days escalates) are capped at Tier 1 and reviewed if employments overlap in time at different employers; supervision implausibility (referee's own history doesn't overlap the claimed supervision period); closed clusters (accounts whose references point only within the set). Two or more signals → manual review before delivery. Reciprocity alone is normal in small care teams and is **not** marked on the delivered pack unless review finds collusion |
| **Fake employment** | Employer entity resolved against ABN Lookup; employment-overlap sanity (§6.1); Tier 3 only via §4.4 gates; defunct-employer cap (D-09) |
| **Fake employer harvesting** | §4.4 verification + request privileges; per-request candidate authorisation (a fake employer gets nothing without the candidate's active tap — and the authorisation screen is a verification surface, §8.2 below); **request plausibility metering (D-22):** request velocity monitored against declared hiring volume; outliers (requests ≫ plausible vacancies, pulls with no outcome marks, repeat requests for the same candidate across "different roles") are throttled and reviewed. Outcome marking is mandatory for continued request privileges beyond a monthly allowance |
| **Identity rental** (real person passes IDV, hands over the account) | **Step-up re-verification:** viewing/confirm-as-is = low friction; materially editing evaluative content, revoking, changing contact details, or a first reference for a new candidate requires a full authenticated session; anomalous context (new device + new geography + high-value action) triggers a one-time liveness re-check. **Behavioural continuity signals** (device/geography history) feed D-04 |
| **Window gaming** (referee defaults on negatives, edits only positives) | Labels make the pattern visible per delivery; aggregate referee behaviour stats are internal-only in v1 (publishing them would create a shadow rating of referees) |
| **Candidate–referee collusion** (real referee, coached answers) | Not fully preventable — mitigated by completeness (§8.1: the *other* referee for the same job also delivers), standardised scales (uniform inflation leaves pattern flags), and cross-employer outcome data over time (v2). Stated honestly in the risk register |

**Enforcement ladder (D-06, platform-wide):** signal → (1) silent risk-score increase + review queue → (2) references held non-deliverable pending manual review → (3) tier downgrade across all references touched by the actor → (4) account suspension → (5) network ban (document-hash / ABN keyed) → (6) referral pack (audit trail) to the IDV provider and, where identity crime is evidenced, police/ReportCyber. Every step above (1) is appealable by a human (§12 appeals) — automated bans without appeal will eventually ban a legitimate rostered supervisor and become the viral story instead.

**Candidate authorisation screen is a verification surface, not a notification (D-14/D-16):** it shows the employer legal entity name **as returned by the ABR** (not the typed display name), ABN, the requesting domain, employer account age, and whether this is that employer's first-ever request to this candidate. First-request triggers a friction step: *"You have never interacted with this employer on RefereeChecks. Only authorise if you have actually applied for a role with them."* Authorise requires an explicit checkbox naming the role; **one-tap grant from a push notification is removed** — deep links land on this screen, never execute the grant. Withdrawal stays prominent until DELIVERED.

**Request abuse caps (frozen):** max **3 open Requests** per (employer org × candidate); after delivery, the same org cannot re-request the same candidate + same role for **30 days**; after a candidate decline, the same org cannot re-request that candidate for **90 days** unless the candidate proactively re-authorises via their own link (employer sees only "candidate did not authorise"); **no** global "approve all future requests" toggle exists — per-application authorisation is structural, not a preference.

**Anti-blacklist structure (D-26 — the year-2 killer, designed out now):** (a) no cross-employer visibility of any kind, ever — marketed as a permanent guarantee; (b) E8 answers are delivered **only** inside the full authorised pack — never via the verify endpoint, never in status chips, never on the public page; (c) candidate response statement delivered **inline** with E8 content; (d) delivered packs are **watermarked per employer** (snapshot ID + employer ID embedded in PDF metadata/rendering) so a leaked pack identifies its source; bulk export/API access is gated on §4.4 verification + 90-day account history; ToS: packs are for the named application only, must be deleted after the hiring decision + 90 days, may not be pooled, sold, or used to build any shared database — breach = ABN-keyed network ban + referral where the Privacy Act is engaged; (e) an **annual transparency note** is published (pulls by sector, revocation rates, correction outcomes).

### 8.3 Platform security (build requirements)

- **Token discipline (D-10):** **no state change on GET, ever** (corporate mail gateways pre-fetch links — a scanner must never "confirm" a reference). Action tokens are single-use, bound to one task + one action, expire at window close or 72h, whichever is sooner, and are invalidated when the task resolves by any path. Login magic links: single-use, ≤30 min; resulting session ≤24h with refresh, device-bound where supported. Revoke and material edits require a full authenticated session, not a bare action token. **Account recovery requires re-running liveness against the original IDV record** — email control alone never recovers a referee account, because the email *is* the attack surface.
- **Audit log integrity (D-29/D-30):** audit rows are **hash-chained** (`hash = H(row content + prev_hash)`, computed server-side in the same transaction as the event). Nightly, the chain head is anchored outside platform control: an Object-Lock (retention-mode) bucket **and** an external timestamp. Any later edit or deletion breaks the chain verifiably. Firestore rules deny update/delete on audit collections to all clients; server writes use a dedicated service identity whose permissions exclude delete. Delivered snapshots are content-hashed at delivery (§5.1).
- **Founder/insider controls (D-31):** hardware-key/passkey MFA on infrastructure accounts, no SMS fallback, recovery codes offline; GCP/Cloudflare audit logging with alerts on console data access (the founder's own access is logged too — anchoring means even the founder cannot rewrite history undetectably); application admin actions require step-up auth and are audit-logged with reason codes; there is **no admin edit path for referee content in code**, so misuse requires raw database writes, which the chain makes detectable. Before the first hire with production access: deploy access ≠ data access; support tooling is scoped views (masked contact details by default). Until then, residual one-person insider risk is **accepted and recorded honestly**, not designed away on paper.
- **Resilience (D-32):** Cloudflare in front of everything: WAF managed rules + rate limits on auth, OTP, verify and request-creation endpoints **before** pilot; OTP endpoints behind Turnstile + per-number/per-IP caps (SMS pumping is a cost attack first). Public status page + a pre-written holding statement. No ransom is ever paid — decided now, not under pressure.
- **Data posture:** TLS everywhere; Firestore/R2 encryption at rest plus **field-level envelope encryption (Cloud KMS) for evaluative free-text and referee contact details** — a raw database export is not a readable leak of opinions. Role-scoped server-side authorisation on every read of a Reference; employers can only ever read references attached to a Request/Pull they own; every read of evaluative content writes an audit row. Primary data in `australia-southeast1` (Sydney). Sentry with strict PII scrubbing (no reference content, no free text, no document data; session replay **off**).
- **Review-queue SLAs (D-38):** hard blocks (document-hash match, reciprocal + overlap) never auto-clear; soft signals auto-clear if the risk score decays with clean history. Fraud-review items older than 5 business days escalate; **references under review are never auto-delivered to meet an SLA** — the SLA is met by staffing/triage, not by releasing. Notification delivery rate is monitored as a *product* metric, alarmed below 97% (the default mechanism's legitimacy depends on it, §6.8 D-19 rule).
- **IDV redundancy (D-39):** second provider (FrankieOne/greenID) integrated before referee count reaches 25,000 — the parallel Week-1 application (§4.1) is how this milestone is de-risked.

### 8.4 Trust-model defences (non-technical, pre-built)

- **The journalist test will happen in year 1** (a planted fake and a planted terrible reference). The defence is pre-built (D-33): the planted fake lands at Tier 1 with the "not independently corroborated" label — the platform never claimed more; snapshot hashes + the anchored audit chain prove what was actually delivered; a **published methodology page** states what each tier does and does *not* prove. **Standing rule: never claim the system cannot be fooled.** The claim is: "fraud here requires a real identity, leaves an anchored audit trail, and gets weaker labels the less we can corroborate."
- **The fairness path is rehearsed (D-34):** for a false negative reference — candidate sees it (APP 12), responds inline, disputes facts into the correction flow; a referee whose evaluative content draws repeated disputes is risk-scored and can lose standing-reference privileges pending review. The journalist's subject must be able to say "I saw it, I answered it, it's attached."
- **Crisis skeleton (D-37), written before the pilot and stored with the NDB plan:** founder responds personally, in the thread where it's spreading, within hours; facts first from the anchored audit log; one real fix, shipped and publicly changelogged; never litigate the complainant's character; never reveal their data beyond what they published; post-incident note added to the risk register.
- **Moat honesty (D-36):** what is *not* a moat — the dashboard UI, the edit-or-default mechanic itself (copyable in a quarter), verification (a commodity via the same providers), pricing. What is hard to copy: (1) referee platform-email identities in circulation (infrastructure, not a feature); (2) accumulated provenance history (a reference confirmed across 4 applications over 14 months is a different trust object from one collected last Tuesday — and hashes make it provable); (3) collect-at-exit relationships; (4) cross-platform/API portability into agency workflows SEEK's wall excludes. **Speed of referee-identity adoption in the care wedge is the race** (§16).


---

## 9. Pricing — final

All prices **AUD, displayed GST-inclusive everywhere, to everyone** (ACL s 48 single-price rule; invoices show the GST component separately). The company registers for GST from incorporation (§13). Net-of-GST figures are in §15.

| Side | Item | Price (incl. GST) | Notes |
|---|---|---|---|
| **Candidate** | Build passport, collect references, share link (factual/status layers per §7.1) | **Free** | Free tier is real: collect + share. Uncertified passports show "candidate identity not platform-verified" on the pack |
| **Candidate** | **Passport Certification** (one-off) | **A$39** | Charged **only when the first reference reaches STANDING** and the candidate taps "Certify" — never before. Unlocks: candidate ID-verified badge finalised, verified public link, unlimited shares/requests, correction/response centre, sharing kit (§9.1), pack transfer (v1.1). Includes up to **3 standing references** |
| **Candidate** | Additional employment record (with references) beyond the included 3 references | **A$9 each** | Covers the extra referee IDV cost; priced at cost-plus, not a profit line |
| **Candidate** | Reconfirmations | **Free, forever** (certified passports) | Charging for reconfirmation would tax the freshness mechanism that defeats the product's biggest objection. Never paywalled |
| **Candidate** | Free-tier limit | Up to **5 employer requests/month** | Certified removes the cap. **Evaluative delivery is never gated by the candidate's tier** — it flows through the employer's paid pull in both tiers (the pilot's trust metric must not be confounded by a candidate paywall) |
| **Employer** | First look via candidate link | **Free** | The cold-start bypass; non-negotiable |
| **Employer** | **Check** (shortlist: factual + E11 + E12 standing answers, instant) | **A$6** | Counts as 0.5 pull in agency plans (decided in freeze) |
| **Employer** | **Full pull** (application-specific, full pack incl. evaluative layer + bespoke question routing) | **A$12** | Charged on delivery. Includes any reconfirmation triggered inside the pull — never double-charged |
| **Employer** | **Full pull delivering factual-only** (evaluative expired/declined/not given) | **A$6** | Metered separately. (CVCheck charges ~$16.50 for a fresh streamlined check; $6 for an instant verified factual confirmation is defensible and keeps employers inside the system) |
| **Agency** | **Starter** — 3 seats, 10 pulls/mo incl., overage $9 | **A$79/mo** | Factual-only pulls and Checks count as 0.5 pull |
| **Agency** | **Growth** — 10 seats, 30 pulls/mo incl., overage $8, + JobAdder/Employment Hero integration, API + webhooks, team roles, audit export | **A$149/mo** | Integrations/API ship v1.1 (§10/§11) — plans are sold on the pilot-proven web flow first |
| **Agency** | **Scale** — unlimited seats, 80 pulls/mo incl., overage $6, collect-at-exit included, named contact | **A$299/mo** | |
| **Agency** | Annual billing | **Pay 10 months, get 12** | Month-to-month otherwise; no lock-in below Scale. Lock-in is earned by the referee graph, not contracts |
| **Founding agencies** (the 25 pilot agencies) | Pilot + **6 months free** on any tier (fair-use cap 100 pulls/mo), then founding rates **locked 24 months** from conversion | **$0 → locked** | In exchange: signed one-page pilot agreement (§14.2), honest acceptance data, weekly feedback, testimonial/logo opt-in |
| **Agency/RTO** | Candidate certification vouchers (bulk, min 20) | **A$29 each** | Turns candidate acquisition into a B2B sale where the agency prefers to pay |
| **Employer** | Collect-at-exit standalone (post-pilot, trigger-gated §16) | **A$59/mo per org** | Free in Scale; free for all during pilot (concierge) |
| **Agency** | Reconfirmation campaign on the agency's own stale files (year-2 candidate) | **A$4 per completed reconfirmation** | Noted so the API design doesn't preclude it |
| **Referee** | Everything | **Free, always** | Public policy. Paywalling a referee action would be trust-fatal |

**Rejected alternatives (on record):** employer-pays-only/candidate-free (repeats Xref's enterprise sales grind with zero density; forfeits the worker-pays precedent — this workforce already pays $112–163 for the NDIS check). Candidate-pays-only/employers-free-forever (caps the business as a consumer gadget; never builds the employer verification habit). SEEK Pass being free is not a counter-argument: it is walled, and its referee still answers fresh — the $39 buys cross-platform portability and a referee who never re-answers. Pitch line: *"SEEK Pass works on SEEK. This works everywhere — and your referee does it once."*

**Refund policy (final):** charge-at-standing means "candidate pays, referee never completes" **cannot happen** — no standing reference, no charge. No reference reaches STANDING within 45 days of first invitation → nothing charged; passport stays free-tier; re-invite/substitute at no cost. Certified, then **all** references revoked/expired within 60 days → **full $39 refund**, automatic on request. Certified with ≥1 reference standing → no change-of-mind refund (service delivered); ACL consumer guarantees apply and are stated verbatim in the terms — never contracted out of. Employer pull delivered but later factually corrected → pull fee credited, corrected pack re-delivered free. Agency plans: cancel anytime, effective end of billing month; included pulls don't roll over (stated upfront).

**Price locks (only what COGS makes safe):** pilot-year candidates — *"Your $39 certification is one-off, forever. Reconfirmations are always free. If our price ever rises, it never applies to you."* Founding agencies — plan prices + overage locked 24 months from conversion. Everyone else — 12 months' notice of any price change; existing plans honoured to the end of their current annual term. **Never promised:** lifetime pull pricing for non-founding employers; a perpetual $39 for future cohorts (IDV vendor pricing is outside our control; founding promises are sized to survive a 3× IDV price rise).

**Paywalls never block:** referee actions, candidate APP 12 access/correction, revocation. Charging a referee, or charging a candidate to *see* their own data, would be unlawful-adjacent and trust-fatal.

### 9.1 Candidate sharing kit (v1.0 marketing/build items)

(a) **Resume QR block** — downloadable PNG/PDF snippet ("Scan to verify my references") for a resume footer; (b) **profile text snippets** — one-line and short-paragraph generators for SEEK/LinkedIn "About" sections ("independently verified references" + link); (c) **email signature banner** (HTML snippet, platform-hosted image); (d) **printable one-page Reference Summary PDF** — factual layers + per-employment reference statuses + QR + verification URL, for in-person agency visits; contains **no evaluative content** (paper can't enforce disclosure rules). Apple/Google Wallet passes: rejected for v1 (build cost, low care-sector wallet usage).

### 9.2 "Passport-first" job-ad badge (v1 marketing asset)

Verified employers get a badge kit: *"Verified references accepted — apply with your RefereeChecks passport"* (image assets + embed snippet for their own ads/careers pages and JobAdder postings) plus a one-line application instruction. No job board, no listings product. Founding verifiers are encouraged to use it during the pilot; badge usage is tracked as a pilot signal — it converts private employer acceptance into the public market signal that recruits candidates.

---

## 10. Integrations sequence — final

**Design rule:** every integration runs on the same core API. ATS-specific code is a thin adapter (OAuth + field mapping + status write-back). The pattern to copy is Xref's four moves — (1) request from inside the ATS, (2) candidate/referee flow on the vendor's side, (3) status written back, (4) report linked back — with **one difference inserted into move 1: check the passport before starting a fresh chase.** That step is the entire product difference and must live inside the ATS request flow.

**v1.0 = internal API only** (decided in freeze, buildops adjudication #5). The platform is built API-first internally — the web app consumes the same service layer an external API would expose, preserving the v1.1 path at near-zero extra cost. **No external API keys, partner webhooks, or embeddable buttons in v1.0; no pilot employer gets API access.** If a pilot agency demands it, that is a change request under §18, not a quiet addition.

**Zero-integration fallbacks carry the pilot (all v1.0):** (1) verified share link (primary distribution — works even inside a SEEK application, because the candidate pastes it); (2) email/PDF delivery (PDF is a print artefact with snapshot ID + verify QR; the link is the trust); (3) referee custom-email routing (§7.2).

**Sequence (adapters are v1.1, sequenced by pilot evidence; approvals are the long pole, so applications go early):**

| # | Integration | Build effort (adapter) | Gate / when |
|---|---|---|---|
| 0 | Core API + share link + email/PDF (v1.0 platform itself) | — | None |
| 1 | **JobAdder** (AU agency + care-provider default; Xref pattern proven inside it; its Humanforce Preferred-Partner sync carries placements downstream into rostering) | 3–5 wks | Developer-account registration is human-reviewed — **application filed Week 1** |
| 2 | **Employment Hero** (open HR API — "no closed program or approval gate"; where AU care SMBs hire/onboard; ShiftCare adjacency) | 2–3 wks | None for API; directory listing via Partner Network form |
| 3 | **PageUp** (large direct care/health/public-sector employers) | 3–4 wks | Partnership agreement first — **approach once 1–2 care design partners exist to name; expect months and a mutual-customer demand** (Xref entered with 50+) |
| 4 | Workable (3rd-party tier — no mutual-customer requirement; cheapest formal marketplace listing) + Zapier/unified-API (Merge/Unified.to) long-tail coverage | 2–3 wks each | Partner agreement (rev-share); ~15-day review |
| 5 | Teamtailor (trigger pattern is a small build) | 2–3 wks | Partner application |
| 6 | Bullhorn (labour-hire expansion, §16) | 4–6 wks | Developer Program fee (dated pricing — re-confirm) + Marketplace needs ~10–15 mutual customers |
| 7 | Greenhouse / Lever / SmartRecruiters / Ashby | 3–6 wks each | Only on customer pull. Greenhouse: monthly review batch + ≥1 mutual customer; Lever: manual OAuth provisioning; Ashby: intro call + legal review |

**External API surface (v1.1, designed now so v1.0 doesn't preclude it):** `POST /v1/reference-requests` (application-scoped create; returns hosted-flow URL) · `GET /v1/reference-requests/{id}` (status + per-referee breakdown) · `POST /v1/passports/verify` (candidate-issued token in → verification summary out: identity verified y/n, referee verified y/n + method, employer/role/dates confirmed, reference age, evaluative expiry + reconfirmation status — **summary only, no content, no dates** per §7.1) · `GET /v1/passports/{id}/references` (the pull — requires candidate's single-application consent grant + verified employer + application context; returns structured reference + signed audit receipt; fires referee notification) · `POST /v1/reconfirmations` · referee account endpoints. **Webhooks** (HMAC-SHA256 signed, retry with backoff): `reference_request.created/.referee_responded/.completed/.expired`, `passport.pulled`, `passport.revoked`, `reconfirmation.completed` — plus the spec's request-lifecycle events (`request.authorised`, `request.window_open`, `referee.updated/.confirmed/.defaulted`, `request.delivered`, `request.closed`, `reference.revoked` — post-delivery revocation webhooks are limited to *factual-correction* events; a bare revocation triggers no employer webhook, per §6.7's no-signalling rule). **Embeddables:** hosted request flow (signed URL / iframe with postMessage completion), passport-verify widget. **Auth:** OAuth 2.0 client-credentials per partner org (scopes: `requests:create`, `requests:read`, `passports:verify`, `passports:pull`); scoped API keys for the long tail. **The pull is never authorised by the API key alone** — the candidate's consent grant is an auth rule, not a courtesy. The API enforces the same state machine; there is no API path that skips candidate authorisation or the window.

**SEEK — verdict (frozen): no usable integration route exists; distribution routes around SEEK.** SEEK's reference check is its own product bundled into job-ad tiers and visible only inside SEEK; the single reference integration SEEK ever opened went to Xref under a negotiated June 2024 commercial deal (followed by an exclusivity deed toward acquiring Xref); its API Partner Program is for recruitment software (seven-stage certification; candidate-data products require the partner to already be an ATS supporting job posting/apply); SEEK Pass's partner API only lets issuers push credentials *into* SEEK's passport or verify SEEK-held identity — nothing lets a third party pull reference content out. Applying to issue into SEEK Pass would feed the competitor's passport — **except** under the pre-decided scenario in §16 (if SEEK opens issuer APIs and invites third-party credentials in, we issue in as a channel, never as system of record; non-exclusive, revocable). The route around: JobAdder (agencies multi-post ads to SEEK but keep workflow in JobAdder), Employment Hero, PageUp, and the candidate-carried share link.

**Downstream, not request surfaces:** Humanforce / foundU / Deputy / ShiftCare are rostering/compliance destinations — the hiring decision happens in the three ATSs above. Humanforce compliance write-back is a v1.1 pilot item (§11); the JobAdder→Humanforce sync already gets us most of the value.

---

## 11. Build plan — blocks, timeline, frozen scope line

### 11.1 Stack (with a pre-decided fallback)

Next.js (App Router) on Cloudflare Workers + R2; Firebase Auth + Firestore in `australia-southeast1`; Cloudflare Queues/Cron for the window scheduler; Cloudflare Email Workers for inbound mail; Stripe for payments; AWS SES (Sydney) for transactional email; ClickSend for SMS. **Week-1 stack spike (timeboxed 3 days)** must prove end-to-end in staging: auth token verification, a Firestore transaction writing delivery + audit atomically, a scheduled window-close firing, an inbound email landing in a referee inbox record, and a generated PDF. **If any of these fail, the fallback is pre-decided:** the Next.js app moves to Google Cloud Run (`australia-southeast1`), Cloudflare retained for DNS/Email Routing/edge; Firestore/Auth/Stripe unchanged. Deciding the fallback now is what stops a week-6 stack failure becoming a re-plan.

**Data entities (frozen, re-cut for unified identity §3):** `Person` (one identity account; document-HMAC dedupe key; role capabilities) · `Passport` · `EmploymentRecord` / `ExperienceRecord` · `RefereeAffiliation` (person × employer, role, period, ladder evidence, confirmed-by) · `IdentityVerification` (provider, basis, status, decision token, tier evidence) · `EmployerOrg` (ABN-verified entity) · `OrgMembership` (person × org, role) · `Reference` (employment × referee, type, tier, basis, status) · `ReferenceVersion` (immutable; factual JSON + evaluative JSON + attestation + timestamps) · `QuestionSet` / `StandardQuestion` · `ReferenceRequest` (org × candidate × role, state) · `RefereeTask` (request × reference, state, window open/close) · `QuestionMapping` · `Disclosure` (audit: request, snapshot delivered, label, content hash, timestamp — written transactionally with delivery) · `ConsentGrant` (collection consents + share authorisations, **with notice version**) · `Notification` · `ReconfirmationEvent` · `RevocationEvent` · `CorrectionCase` (incl. candidate response statements, factual overrides) · `FraudFlag` / `RiskScore` · `AuditChain` (hash-chained rows, §8.3) · `ApiKey` / `WebhookSubscription` / `WebhookDelivery` (v1.1) · `Plan` / `PullCharge` / `RefereeCredit`.

**Screens (frozen inventory):** *Candidate* — onboarding + IDV; passport home (employments + status chips); add employment / nominate referee; collection tracker; share centre (link management, authorisation inbox); pull history/audit; reference viewer (everything stored); correction & response centre; sharing kit; data export; settings. *Referee* — claim + verification wizard; dashboard (action inbox with window countdowns; "References I've given" with pull counts); give-a-reference form (autosaving); edit-for-this-role form (pre-filled, mapped questions highlighted, new questions marked); one-tap action landing pages (Confirm as-is / Update / Decline / Revoke — POST-confirmed per §8.3); external-mail inbox (§7.2); notification preferences; affiliation manager; credits + time-saved views. *Employer* — org verification wizard; request composer (candidate link/ID, role, question intake with live mapping preview + coverage estimate); request tracker (state machine visualised); Check composer; delivered pack viewer (banners, tags, coverage, snapshot ID); team/API settings (v1.1); billing. *Public* — candidate verification page (§7.1); referee claim/landing pages; sector question-set page (transparency is a selling point); trust centre + verify-this-document tool (§7.1); status page.

**Mobile-first referee completion — acceptance criteria (frozen):** confirm path = SMS/email tap → magic link → one screen (who/what/deadline + standing answers summary) → Confirm button: **≤3 screens, ≤60 seconds, zero typing**. Edit path: pre-filled answers as tappable cards, single column, ≥48px tap targets, autosave per field (state survives connection drop and browser close; resume link valid for the whole window), progress indicator ("4 of 14 answers reviewed"). Performance budget: action pages <100KB, usable on 3G and low-end Android. Decline/revoke reachable from the same first screen — burying them would be a dark pattern and a consent risk.

**Accessibility & language (frozen):** WCAG 2.2 AA is a build requirement for all candidate/referee surfaces including one-tap action pages; employer console AA-targeted, audited post-pilot. All candidate/referee copy at ~Year 7 reading level; the formal consent is always preceded by its plain-language summary; copy comprehension-tested on non-technical readers pre-pilot (a tired support worker must understand the consent — §14/§19). The five highest-stakes flows — referee invitation, consent summary, window-open notification + action page, reconfirmation ask, candidate authorisation page — ship with professionally translated templates in **Mandarin, Nepali, Tagalog, Hindi, Punjabi** (per-user language setting; SMS templates included). Referee free text is accepted in any language, stored and delivered **as written**, with any machine translation alongside labelled *"Machine translation — the original text controls."* A listen button (browser TTS) on the consent summary and form introductions. Full UI internationalisation is v2, driven by which languages the v1 templates show demand for. (This amends buildops' "English only" assumption — see §17 R22.)

### 11.2 Blocks & the honest timeline

**Assumptions the estimate is valid under:** Ali solo + AI at **30 productive build hours/week** (he is simultaneously founder, salesperson, support and ops; 40-hour weeks are upside, not plan). Pilot recruitment, legal and vendor waits run in parallel elapsed time. All v1.0 vendors are self-serve or already applied for. Legal review by an engaged AU privacy/technology lawyer with ≤10 business-day turnaround per cycle; two cycles budgeted. Pen test booked by Week 8 for a Week 12–13 slot. NSW-only pilot; responsive web/PWA only. **All timings run from Freeze Day 0** = the day Ali locks legal entity + ABN + product name + domain (§20) — the freeze cannot start before that lock, because the sender ID, email subdomain, privacy policy, ToS and pen-test scope all depend on them.

| Block | Contents | Effort (focused days) | Elapsed |
|---|---|---|---|
| **0. Freeze & spikes** | Freeze sign-off; stack spike (§11.1); data model + requirements traceability matrix (every plan § → build item → test); vendor accounts + sandbox proofs (Veriff, Stripe, SES, ClickSend, ABR); **JobAdder application filed**; **FrankieOne/greenID application started**; ACMA sender-ID process started (§12); legal engagement #1 (consent/notice wording) | 8–12 | Weeks 1–3 (external waits overlap) |
| **1. Foundations** | Unified identity + role model; auth incl. magic links; Firestore schema + security rules; consent-grant store (versioned notices); **hash-chained audit log + anchoring**; admin shell + operator roles; envelope encryption (evaluative free-text + referee contact details); event-ledger instrumentation wired from day one | 10–14 | Weeks 2–5 |
| **2. Candidate** | Onboarding + **candidate IDV flow**; passport + employment/experience records; referee nomination + pre-briefing; collection tracker; public verification page (two-layer, §7.1); share/authorisation inbox; pull-history audit view; APP 12 viewer; correction/response centre; sharing kit; passport PDF + data export | 9–13 | Weeks 4–7 |
| **3. Referee** | Claim/verification wizard (IDV + liveness via provider, work-email control, document-HMAC dedupe, per-reference tier computation, **LinkedIn-corroboration ops workflow**); dashboard + action inbox with countdowns; standing-reference capture (locked F/E set) incl. free-text screening + hold queue; **platform email system** (provisioning, inbound routing/parsing/matching, external-mail inbox, dashboard reply); affiliation manager; notification preferences; credits/time-saved views | 14–19 | Weeks 5–9 |
| **4. Employer + engine** | Employer verification (ABR + domain + D-15 checklist + manual approval queue; ABN re-checks; SUSPENDED_EMPLOYER); request composer (question intake + deterministic mapping preview + coverage estimate); Check flow; **edit-or-default engine** (two coupled state machines, business-day scheduler, reminders, snooze, factual instant release, RECONFIRM_ONLY path, D-19 delivery-confirmation rule); delivered pack viewer (Labels A/B/C, per-answer tags, coverage summary, frozen snapshots, content hashes); pack PDF + verify-this-document tool; post-delivery change notices | 14–19 | Weeks 7–11 |
| **5. Trust, ops & money** | Notification service (email + SMS, cadence caps, quiet hours, suppression/bounce handling, delivery-rate monitoring); one-tap revoke + global pause; reconfirmation flows + rate limits + month-9 batch ping; correction/dispute cases + suppression; fraud controls (self-reference hard block, velocity caps, risk scoring, reciprocity/cluster reports, request metering); operator queues (§12); Stripe ($39 activation at standing, $12/$6 pull metering, Check metering, founding-verifier free flag, monthly agency invoicing, refunds, webhook reconciliation) | 10–14 | Weeks 9–12 |
| **6. Quality gates** | State-machine test suite (§11.3); authz matrix tests; accessibility remediation; load test; security self-review + OWASP ASVS checklist; **external pen test + remediation + retest**; backup/restore drill; incident-response tabletop | 12–18 (incl. remediation allowance) | Weeks 11–15 (pen test external) |
| **7. Pilot readiness** | Legal cycle #2 (ToS/privacy/consents final); insurance bound; pilot agency agreements; onboarding packs + referee help content + trust centre + methodology page + crisis playbook; support inbox + macros live; **dry-run pilot** (5 candidates, 5 referees, 2 employers, synthetic requests end-to-end incl. one default, one revoke, one correction case, one IDV exception — all via the real queues); dashboard live; go/no-go review | 6–9 | Weeks 13–16 |

**Totals:** ≈83–118 focused days gross; ≈70–90 net critical-path days after genuine overlap.

| Scenario | Freeze Day 0 → pilot start |
|---|---|
| **Plan on this (commit)** | **14–16 weeks** at 30 productive hrs/week |
| Upside (40-hr weeks, no legal/vendor surprises, pen test clean-ish) | 11–13 weeks |
| Downside (IDV fallback needed, pen-test remediation round 2, legal cycle 3, capacity drop) | 18–22 weeks |

**Feature freeze at Week 12** (no new v1.0 code; P0/P1 fixes only). **Go/no-go gate at Week 14** against §19. A pilot that starts two weeks late is recoverable; a trust product that starts with a consent or security hole is not.

**Critical path:** legal consent wording → consent/audit foundations → referee verification → window engine → delivery + feedback instrumentation → pen test → pilot agreements.

**Pre-agreed slip order** (never negotiated mid-crisis): (1) pack PDF polish → plain, correct PDF, content identical; (2) referee dashboard *reply* composer → inbound capture + notification + concierge handling; (3) employer team seats → single user per org (already the pilot default); (4) admin analytics UI → dashboard as scheduled report/export; (5) concierge collect-at-exit → standard candidate-initiated flow for the pilot's first half. **Never slips:** consent capture/versioning, audit atomicity, state-machine correctness, labelling, feedback instrumentation, security gates, accessibility basics on core flows. If an overrun reaches these, **the pilot date moves — the scope doesn't hollow out.**

### 11.3 Testing & quality gates (frozen)

- **State machine as a formal object:** the §6.8 state machines are encoded as data; every legal transition has a test; every *illegal* transition has a test proving rejection (no path from AWAITING_CANDIDATE to any delivery state; no delivery from REVOKED/DECLINED under any event ordering).
- **Property-based invariants** (randomised event sequences): (1) no evaluative content delivered before candidate authorisation; (2) no content delivered after a revoke that precedes delivery in event order; (3) expired evaluative content never delivered as evaluative content; (4) delivery + audit commit atomically — no reachable state has one without the other; (5) every task resolves exactly once, producing exactly one snapshot or an explicit non-delivery record; (6) labels are a pure function of the resolution path — a DEFAULTED task can never render Label A/B copy.
- **Fake-clock suite:** 30 days of business time simulated in seconds — AU/NSW holiday calendars, Sydney DST transitions, weekend/holiday-cluster windows, reminders at +1bd / −24h / −4h, authorisation expiry at 7 days, evaluative expiry landing mid-window (→ RECONFIRM_ONLY), reconfirmation rate limits.
- **Race tests:** referee edit vs window-close in the same second (**the event with the earlier recorded timestamp wins; ties resolve to the referee** — a frozen product rule, so engineering never has to guess); revoke vs delivery commit; duplicate scheduler firings (idempotent); notification retry storms; Stripe webhook replays.
- **Snapshot/golden tests** on delivered packs per label/cohort (§7 QA rule, enforced mechanically).
- **Soak:** staging runs accelerated synthetic traffic (hundreds of requests across simulated weeks) pre-pilot; scheduler drift, duplicate deliveries and audit gaps dashboard-checked daily.
- **Security self-checklist (all must pass):** OWASP ASVS L2 mapped; Firestore rules test suite (every role × every collection); server-side authz matrix tests per endpoint (employer A can never read employer B's pack — tested, not assumed); secrets + dependency scans in CI (blocking); SAST; rate limits + bot controls on public pages and auth endpoints; upload quarantine + type sniffing + no public URLs; token hygiene (§8.3); admin = named accounts + MFA + logged; encryption verified (evaluative free-text unreadable in a raw export); **storage audit greps production for image fields/PII patterns to prove the "no ID documents" claim before marketing uses it** (D-28).
- **Privacy Impact Assessment** reviewed by the privacy lawyer; collection notices comprehension-tested on 3 non-technical readers.
- **External penetration test — a launch gate, not a post-revenue luxury** (§15 budget: plan A$12–18K ex GST; CREST-affiliated firm preferred; grey-box, all roles, state-machine abuse cases briefed explicitly). Booked Week 8, tested Weeks 12–13 on the feature-frozen build, remediated Week 13–14, retested before go/no-go. **If Ali declines to fund it:** the only fallback is a **capped, invite-only pilot** (named friendly agencies + consenting candidates, no public signup) with the residual risk recorded as Ali's written acceptance — and the pen test becomes a hard gate before any public launch. An open pilot on self-review alone is not an available option.
- **Load:** design targets 50 concurrent authenticated users; 500 requests/day burst (4× pilot expectation); 5,000 notifications/hour queued with provider backoff; public verification page p95 <1s; API p95 <500ms. Load test at **10× pilot volume** in Block 6, including 1,000 windows closing in the same simulated hour with no duplicate deliveries.
- **Accessibility testing:** axe-core in CI on every core screen (zero critical/serious to merge); manual keyboard-only pass on the five core journeys; screen-reader pass (NVDA + VoiceOver) on referee confirm/update and employer pack review; 200% zoom/reflow; timeout warnings before any session expiry in IDV and reference forms; time pressure never conveyed by colour or animation alone; usability test with 3–5 care-sector users in the Block 7 dry-run, actively recruiting at least one screen-reader user.

### 11.4 Frozen scope line

**v1.0 — the pilot, and only the pilot:**
- Unified identity accounts (candidate / referee / employer-org single user / admin); magic-link + OTP auth; no referee passwords
- Candidate IDV gating Certified status; referee IDV + liveness + work-email control + document-HMAC dedupe; per-reference tiers (§4.3) + verification-basis labels (§4.1); LinkedIn-corroboration ops workflow
- Employer verification: ABR + domain + D-15 checklist + manual approval; ABN re-checks; Tier 3 gates (§4.4)
- Passport: unlimited employments, ≤3 referees per employment; all-or-nothing sharing; completeness indicators; Placement/Volunteer records; two-layer public verification page + verify endpoint + verify-this-document tool
- Collection: candidate-initiated + referee-first + **admin-triggered collect-at-exit**; HR Factual Route; fallback ladder (§6.4); locked question set v1; factual/evaluative split; 12-month evaluative expiry; immutable versioning; free-text screening + hold queue
- Referee platform email: address per verified referee; inbound capture → match → external-mail inbox + labelled forwarded copy; dashboard reply (slip item #2)
- Request engine: Check + Full Request; candidate authorisation (7-day expiry); factual instant release; **fixed 3-business-day window**; cadence + quiet hours + snooze; update / confirm-as-is / decline / revoke; default release with D-19 rule; UNREACHABLE + UNREACHABLE-PERMANENT; RECONFIRM_ONLY; SUSPENDED_EMPLOYER; frozen snapshots; Labels A/B/C + variants; per-answer tags; coverage summary; post-delivery change notices; in-request candidate prompts (§6.8)
- Trust & rights: versioned collection consent with explicit default-release wording; notification on every request and delivery; one-tap revoke + global pause; APP 12 access; APP 13 correction workflow + factual override; candidate response statements; suppression workflow; structural fraud controls + risk scoring + operator queues; kill switch
- Money: Stripe $39 (at standing) / $12 / $6 / Check $6 metering; founding-verifier free flag; monthly agency invoicing; refunds
- Ops & measurement: event ledger + employer feedback capture (§14) + weekly dashboard; operator queues; support inbox + macros; data export (all roles); backups + restore drill; incident runbook

**v1.1 — first 90 days post-pilot (planned, not date-promised):** external partner API (scoped keys, webhooks, embeddable request/verify button); JobAdder adapter (if approval landed + pilot agencies ask); Employment Hero adapter; Workable 3rd-party listing + Zapier/unified-API if demand appears; semantic question mapping (≥98% precision gate); employer self-serve collect-at-exit; bulk request creation; team seats + org role model live; agency subscription plans with automated invoicing; Referee Credits redemption; Verified Referee public profiles; candidate pack transfer (§6.8); FrankieOne as the DVS path / second IDV provider (hard milestone before 25,000 referees); Humanforce compliance write-back pilot; PageUp build *only if* a partnership agreement exists.

**v2 — expansion on evidence only:** labour-hire sector + Bullhorn; further sectors with their own validated question sets (childcare/education candidate-carried mode stays excluded unless the direct-collection legal position changes and is separately validated); HRIS/payroll exit-collection automation; Greenhouse/Lever/SmartRecruiters on customer pull; constrained white-label (logo/colours + cover page only — §7 non-removables always apply); full UI internationalisation; multi-region resilience; SOC 2 / ISO 27001 if enterprise buyers require; native apps only if web friction is proven to be the binding constraint.


---

## 12. Operations plan

### 12.1 Support model (pilot)

- **Channel:** single support inbox on the product domain + in-app help links that pre-fill role + request/passport ID. No phone line in v1.0; a call-back option for employers and for referees stuck in IDV. Public help centre: the sector question set, "what is a standing reference," referee FAQs — all at the §11.1 reading standard.
- **Who answers:** Ali is Tier 1 + Tier 2 during the pilot (he is also the ethnographer — support contacts *are* pilot data). **A named backup operator is a launch gate (§19):** a trained contractor/VA with a least-privilege operator account (queues + macros only; **no access to evaluative content** unless a case requires it, and that access is logged). Without a backup, Ali being sick for a week during the pilot is an operational incident.
- **Hours:** Mon–Fri 08:00–18:00 **Sydney time**, stated explicitly (Ali works ACST — the roster states Sydney hours so Darwin time never silently shortens the day).
- **SLAs (pilot):**

| Priority | Examples | First response | Resolution target |
|---|---|---|---|
| P1 — trust/safety | Suspected unauthorised disclosure, privacy incident, kill-switch event | 1 hour (incl. after-hours alert to Ali) | Containment same day; §12.4 runbook |
| P2 — blocked transaction | Employer can't access a delivered pack; referee locked out of a live window; payment taken but passport not activated | 4 business hours | 1 business day |
| P3 — stuck human | IDV failures, domain-attestation problems, unmatched platform emails | 1 business day | 3 business days |
| P4 — general | How-to, billing, feature requests | 2 business days | 5 business days |

Support acknowledgement for ordinary contacts ≤1 business day.

### 12.2 Ops console & manual queues (v1.0 build list)

Modules: employer verification queue; IDV exception queue; work-domain evidence exception queue; fraud queue (severity-ranked; high-severity SLA 24h); dispute/correction case manager; **LinkedIn-corroboration review queue** (§4.2 rung 1); deliverability monitor (bounce/undeliverable rates per referee → alternate-channel outreach task); window monitor (tasks nearing default; pilot concierge actions); suppression workflow; audit-log search (by candidate / referee / employer / snapshot ID); pilot metrics dashboard (§14, live or scheduled-report per slip list).

**Minutes per item & pilot load** (pilot scale: 300 certified passports, ~450 referees, 25 orgs, ≥120 requests over 6 weeks + 4-week recruitment ramp):

| Queue | Work per item | Min/item | Expected volume | Load |
|---|---|---|---|---|
| Employer verification approvals | ABR review, domain evidence, D-15 checklist, approve/reject + note | 10–15 | 25 orgs | ~6 hrs one-off, then <1 hr/wk |
| LinkedIn corroboration reviews | Profile credibility check per §4.2 signals | 5–10 | Subset of referees lacking work-email access (est. ~15% ≈ 65) | ~8 hrs total |
| Referee IDV exceptions | Review failure reason, offer DVS-data-only path or guided retry, record tier consequence | 15–25 | ~8% of 450 ≈ 36 | 9–15 hrs |
| Work-domain evidence exceptions | Alternative evidence (payslip/contract **sighted, not retained**), set Tier 1 with reason | 10–15 | ~12% ≈ 54 | 9–13 hrs |
| Fraud-flag reviews | Soft signals, device/IP, velocity/reciprocity reports; clear / hold at Tier 1 / contact referee | 10–20 | ~5% of referees + ~3% of passports | 6–9 hrs |
| Tier 3 sampling audits (D-07) | Independent-number call to confirm referee role | 10–15 | 5% of Tier 3 confirmations/mo | Small in pilot |
| Corrections & disputes (APP 13) | Acknowledge, referee window, adjudicate/override or attach statement, notify past recipients | 45–90 + follow-ups | ~2% of passports ≈ 6 cases | 6–10 hrs (spiky) |
| Unmatched inbound platform emails | Identify sender/intent, match manually or reply with guidance | 5 | ~5/week | ~0.5 hr/wk |
| Payment failures / refunds | Stripe review, webhook reconciliation, refunds | 10 | ~10 over pilot | ~2 hrs |
| Support contacts (all roles) | Categorised per §12.1 SLAs | 10–15 avg | ~0.3/passport + ~0.25/referee + ~2/org | 35–45 hrs over ramp+pilot (6–9 hrs/wk) |

**Steady-state pilot ops load: ~10–14 hrs/week; ramp/launch weeks 16–22 hrs/week.** Consequence, stated plainly: during the 6 pilot weeks Ali cannot also build v1.1 — v1.1 work starts **after** the pilot judgement. At scale, budget **1 support FTE per ~8,000 active passports** (IDV failures + referee help dominate) — at the year-2 base (15,000 passports) that's ~2 FTE, and it belongs in the cost model now.

**Appeals (all in-product, all with SLAs):** (a) referee appeals an account hold/fraud flag — manual review ≤5 business days; while held, their references show candidates "verification in progress," never a fraud implication; (b) candidate appeals passport/certification status; (c) employer appeals a verification rejection with additional evidence (ASIC extract, domain proof). Privacy complaints: internal review first; the OAIC path is stated in the privacy policy and in every complaint acknowledgement.

### 12.3 Comms templates (written & approved before pilot — Block 7)

Referee invitation + pre-brief explainer (candidate-sent and platform-sent variants) · window-open / reminder / final-reminder notifications (email + ≤160-char SMS variants) · delivery notices (referee, candidate, employer) + pull receipts · IDV failure guidance (per provider failure class, plain English) · employer verification approval/rejection · correction-case acknowledgement, referee correction request, outcome notices (incl. past-recipient factual-correction notice) · revocation confirmation (referee) + neutral candidate notice · support macros (top 15 expected contacts per role) · incident templates (§12.4) · pilot agency onboarding pack + referee one-page help sheet + candidate FAQ · crisis holding statement (§8.4).

### 12.4 Incident response runbook (skeleton — full version is a Block 6 deliverable, tabletop-tested before pilot)

**Sev-1 = privacy/trust incident** (unauthorised disclosure, wrong-recipient delivery, consent bypass, credential compromise, IDV-data exposure). Others scale down from this.

1. **Detect & declare (0–1 hr):** any operator can declare Sev-1. Ali paged (SMS + phone). Incident log opened (timestamps, decisions, who knew what when).
2. **Contain (same hour):** **kill switch** — one admin action halts all new disclosures and window-close deliveries platform-wide (requests pause in WINDOW_OPEN; nothing is deleted). Revoke affected sessions/credentials; suppress affected references; suspend affected employer accounts. Preserve logs and snapshots — containment never destroys evidence.
3. **Assess:** scope (subjects, data classes, recipients, time window). Privacy lawyer engaged + insurer notified within 24 hrs of a suspected eligible breach. **OAIC NDB:** if there are grounds to *suspect* an eligible data breach, complete the assessment expeditiously — statutory outer limit 30 calendar days (s 26WE); **operating target 72 hours** for scoping at pilot scale. Decision recorded either way; all incidents (notifiable or not) go in the breach register.
4. **Notify:** once there are reasonable grounds to *believe* an eligible data breach occurred, notify the **OAIC and affected individuals as soon as practicable** — pre-drafted statement (what happened, data classes, what we're doing, what individuals can do, contact point). Referees and candidates notified separately (their risks differ). If individuals can't be contacted directly, publish and promote the notification.
5. **Recover:** root-cause fix; targeted retest of the affected path if technical; staged re-enable — disclosures resume only on Ali's written go after lawyer review for Sev-1.
6. **Review (within 10 business days):** blameless post-incident review; actions into the backlog as P1; incident register updated; pilot kill criterion (§14) assessed honestly if the incident was serious.

Non-privacy incidents (outage, notification backlog, Stripe failure) follow the same skeleton minus OAIC steps, with the status page updated at declaration, +2 hrs, and resolution.

### 12.5 Backups, DR, export & exit

- **Backups:** Firestore PITR where available + **daily scheduled export** to a Sydney-region bucket (7 daily, 5 weekly retained); R2 objects versioned; infra/config in git; vendor configurations documented in a runbook, not just consoles. **Restore drill before pilot** and monthly during pilot (restore last export to staging; verify counts + a sample passport end-to-end).
- **DR targets (pilot-proportionate): RPO 24 hrs** (daily export; PITR improves where enabled — measure and record the real figure at the drill), **RTO 8 business hours** for core read/request flows, **2 business days** for full service incl. email routing. Single-region (Sydney) accepted for the pilot; multi-region is v2.
- **Data portability (feature, v1.0):** after re-authentication — candidate export = machine-readable JSON (profile, employments, references incl. versions, consent history, full pull/audit history) + human-readable PDF passport, via expiring signed link (24 hrs). Referees export references given + disclosure history; employers export requests, delivered snapshots, receipts. Portability is both an APP-aligned trust feature and the honest answer to "am I locked in?" — and it is the platform's own vendor-exit path (IDV *decision tokens* are portable; IDV evidence is held by the provider and is not — disclosed in the privacy policy).
- **Account deletion:** self-serve request → 30-day cooling-off → deletion of personal content with documented retention exceptions (audit integrity, payment/tax records) stated in plain language at deletion time.

### 12.6 Vendor table — decision, fallback, switching cost

Rule: the product talks to an internal interface, never a vendor SDK directly, wherever the vendor is substitutable. Switching costs assume the rule was followed.

| Function | Decision (v1.0) | Fallback | Switching cost |
|---|---|---|---|
| **IDV** (document + liveness; DVS path) | **Veriff** hosted flow, self-serve tier (Document-checked basis, §4.1). Store decision token + assurance level only. Contract asks: 12-month price lock, ≥90-day notice of pricing/terms change, AU data-handling disclosure wording | **FrankieOne** (AU-native, orchestrates greenID/DVS) — application in parallel from Week 1; emergency degraded path: greenID DVS data-check only → **Tier 1 with reason shown** (never labelled as equivalent to liveness) | 1–2 wks dev + comms; existing verifications keep their tier from the original provider's decision record; no referee re-verifies on a switch |
| **Transactional email** | **AWS SES** (Sydney), dedicated `notify.` subdomain, SPF/DKIM/DMARC p=reject, bounce/complaint suppression wired to the notification service | **Postmark** — domain authentication pre-configured during Block 5 so the fallback is warm | 2–4 days incl. DNS auth + warm-up |
| **SMS** | **ClickSend** (AU; certified for the Sender ID Register; PAYG ≈ A$0.072/msg entry tier). Registered alphanumeric sender ID for one-way alerts + dedicated number for reply-inviting messages | **Sinch Engage (MessageMedia)** — the Register authorises **per provider**, so **both providers are registered during Blocks 0/5**, not during an outage | 3–5 days dev + parallel registration lead time (§12.7) |
| **Referee email routing** | **Cloudflare Email Routing → Email Worker**, one catch-all on `refs.refereechecks.com` (§7.2) | **AWS SES inbound** → S3 + queue (same downstream pipeline); manual bridge: Google Workspace catch-all | 1–3 days + DNS propagation; addresses survive unchanged |
| **Payments** | **Stripe standard charges** — the platform is the seller of its own service (**not** Connect/marketplace; no third-party payouts in v1.0). Candidates by card; agencies on **Stripe Invoicing, monthly in arrears** (kills per-pull card fees) | Agencies: manual Xero invoicing same-day; candidate payments have no realistic instant fallback (Stripe outage = activation pauses; verified agencies' pulls continue on invoice trust during pilot) | 1–2 wks for a processor change (saved payment methods don't port cleanly) |
| **Monitoring** | **Sentry** (strict PII scrubbing; session replay off) + **Better Stack** (public status page) + Cloudflare/Firebase native alerting (queue depth, scheduler failures, bounce rates) | Self-hosted GlitchTip (Sydney) if residency review objects; UptimeRobot as status fallback | 2–3 days |
| **Analytics** | **Canonical = the §14 event ledger** (own database, AU region) + generated dashboard. Marketing pages only: **Plausible** (cookieless, aggregate). **No Google Analytics, no third-party product analytics on authenticated surfaces** | Metabase (self-hosted, read-only ledger replica) | Ledger is ours — none; dashboard tooling ~2 days |

### 12.7 ACMA SMS Sender ID Register — process & lead time (verified Nov 2026)

Since 1 July 2026, an alphanumeric sender ID used to message AU mobiles must be on the ACMA SMS Sender ID Register or carriers replace it with **"Unverified."** Process: (1) choose the sender ID — max 11 alphanumeric characters, must correspond to the business name/trademark on an official record (for RefereeChecks: the shortened corresponding form decided in §1, e.g. "RefChecks"); (2) apply **through each SMS provider** (the provider submits; registration authorises *that provider*); (3) the organisation's **authorised contact (as listed on the ABR)** receives an ACMA email and must **confirm in ACMA Assist, logging in with myID** — the application does not proceed without this step, and the myID email must match an ABR authorised-contact / service-of-notice email (if Ali's ABR contact details are stale, fix them first — the most common stall); (4) provider + ACMA review. Lead-time evidence: ~2 weeks end-to-end (AWS guidance); 7–10 business days per attempt (Klaviyo — a rejection restarts the clock); 2–3 business days when the contact confirms promptly (Sinch). **Planning figure: 15 business days from first submission, started Week 1**, absorbing one rejection/resubmission. The pilot never sends from an unregistered ID; if registration is somehow still pending at pilot start, SMS is limited to the dedicated number and email carries the window flow — pre-decided here, not improvised.

---

## 13. Legal & compliance summary

*This section hardens design decisions; it is not legal advice. The 18 questions in Appendix A must be answered in writing by an Australian solicitor (privacy + defamation + employment) before launch. The §19 legal gates may not be waived on the basis of this summary.*

### 13.1 Threshold rulings

- **We are an APP entity from day one.** The Privacy Act small-business exemption does not reliably apply: s 6D carves out businesses that *trade in personal information* regardless of turnover, and the platform's entire business is collecting and disclosing personal information for a fee. Full APP compliance is a launch requirement. No feature may be justified internally by "we're probably exempt."
- **Operate through a Pty Ltd, never as a sole trader.** The two structural liabilities — defamation republication and privacy breach — are personal and recurring (every pull is a fresh publication). The company is the APP entity, the DVS applicant, the contracting party in all ToS, and the insured.
- **The employee-records exemption (s 7B(3)) does not apply to us** — candidates are applicants, not our employees; referees are not our employees. No design element relies on it.
- **Credit reporting (Part IIIA) is out of scope by definition** — employment references are not credit information; we are not a credit reporting body. Watch item: any future expansion into tenancy screening or financial vetting reopens the analysis before build. (We voluntarily mirror Part IIIA-style access/correction/dispute practices because they are the market's trust grammar.)
- **Labour-hire licensing: outside the definition; the boundary is "supply + pay."** The platform never supplies a worker to do work and never pays a worker for work — it supplies *information about* a worker to a hirer who employs directly. **Boundary markers (any one crossing = stop + licence advice):** (a) platform contracts to provide staff (on-hire); (b) platform payrolls casuals placed with hosts; (c) platform charges contingent on a worker commencing work bundled with ongoing supply/pay obligations; (d) "agency plans" evolving into managed staffing. The separate state "employment agent" patchwork (WA Employment Agents Act 1976; QLD Private Employment Agents Act 2005 — candidate-charging is the sensitive element) is Lawyer Q10: our characterisation is that we do not introduce candidates to employers, do not charge for placement, and the candidate fee buys a *credential service* — to be confirmed before marketing into WA/QLD.

### 13.2 Privacy Act — APPs end-to-end (design locks)

- **Six distinct APP 5 collection notices** (short-form at point of collection + link to full policy; each logged with version + timestamp against the consent record): (1) candidate signup + ID check (incl. the DVS consent notice — express consent with prescribed content is a condition of DVS use); (2) referee invitation/claim + verification (referee's own PI, DVS consent, *and* the forward-looking disclosure authorisation); (3) reference submission (candidate notified the moment a reference about them is collected — §6.1); (4) employer representative signup; (5) request/API metadata; (6) complaints/support/correction cases. A single website privacy policy discharges none of these.
- **APP 3:** collect only what's reasonably necessary. The candidate's passport-creation consent expressly names the sensitive-adjacent categories (§6.5) so APP 3.3 consent exists before E8 content is collected. Referee-side guardrails + pre-STANDING screening per §5.4.
- **APP 6:** default-submit is lawful **only** because disclosure to verified employers for candidate-authorised applications is the *stated primary purpose* at collection, with default release acknowledged in plain words as a separate tick (§6.5). The triangle gate is permanent.
- **Consent under power imbalance** (the model's softest legal spot): maximise and document voluntariness indicia — candidate-initiated carrying is the primary flow; referee consent is given to the platform, not extracted by an employer; revoke is one tap, free, prospective, no detriment imposed by us. Residual risk is accepted and insured (Lawyer Q2). The statutory tort for serious invasion of privacy (in force 10 June 2025) is noted as a second cause of action outside the APP framework.
- **APP 8 (cross-border):** a maintained **vendor/APP 8 register** (vendor, data classes, countries, APP 8 basis, DPA on file); the privacy policy names countries. Known offshore processing: Veriff (Estonia/EU — highest-sensitivity flow; DPA + GDPR adequacy noted, disclosed), Stripe (US), cloud subprocessors behind Firebase/Google even with Sydney residency. Contractual floor for every processor: breach notice to us within 48 hours, no secondary use, **no training on our data**, deletion on exit. Question mapping is de-identified before leaving AU infrastructure (§6.10).
- **APP 11 (security):** §8.3 is the minimum launch bar (encryption in transit/at rest + envelope encryption on evaluative free-text; no ID document images/numbers beyond provider decision tokens; least-privilege admin with MFA and full access logging; admin technically unable to edit referee content; pre-launch + annual pen test; vendor ISO 27001/SOC 2 evidence in the APP 8 register). Penalty context: serious/repeated interference — greater of A$50M / 3× benefit / 30% adjusted turnover.
- **NDB:** the §12.4 runbook *is* the NDB plan skeleton — drafted pre-launch, rehearsed once (tabletop, Block 6/7).
- **APP 12/13:** §6.7 implements them as features (free self-serve access; 30-day manual benchmark; redaction line; correction workflow; response statement = the APP 13.5 association mechanism and a defamation-reasonableness asset).
- **ADM transparency (APP 1.7–1.9, commences 10 Dec 2026):** the privacy policy ships with an ADM section **from day one** (before the legal deadline): it names the automated processes (question-mapping routing, fraud-signal holds, default-submit), the PI classes they use, and states that **adverse fraud outcomes are human-reviewed before they take effect**. No fully-automated adverse decision about a person exists in v1.
- **Privacy policy checklist (APP 1):** entity identity (Pty Ltd name/ABN) + contact; kinds of PI per role; how collected (incl. from third parties); purposes (mirroring §6.5 verbatim); usual disclosures; overseas recipients **by country**; access/correction how-to; complaint how-to (internal timeframe → OAIC); ADM section; retention summary (§13.5); versioning + change notification.

### 13.3 Defamation — design to the strictest jurisdiction (WA/SA floor)

Defamation is actionable where matter is published (read) — *Dow Jones v Gutnick*. We publish into every state/territory, and the "uniform" Acts are not fully uniform: **WA has no serious-harm element** and no digital-intermediary defence; **SA deliberately declined** the s 31A-type defence (in force NSW/VIC/ACT/TAS/NT; QLD from 26 Dec 2025). Limitation is **1 year from each publication** — and default-submit creates a new publication at every pull, indefinitely.

- **Controls (all launch requirements):** an accessible complaints mechanism + takedown/suppression within **7 days** of complaint *nationally* (s 31A spec applied even in SA/WA, where it earns no statutory defence but evidences reasonableness); concerns-notice handling workflow + offer-of-amends playbook; never rely on the serious-harm threshold in product decisions (it doesn't exist in WA).
- **Qualified privilege is earned by the design, not assumed:** the platform needs its *own* privilege (the referee's does not automatically cover us), judged on our conduct — §6.5/§6.8's disclosure discipline (specific application + candidate authorisation + verified employer), the window (a live chance to withdraw/correct before *each* fresh publication), provenance labels, 12-month evaluative expiry, candidate response statements, referee truth attestation, 7-day suppression. Disclosure outside a genuine application destroys the recipient-interest limb (*Bashford v Information Australia*) — hence the permanent no-browsing rule (§1).
- **We are a publisher, not a conduit.** We select, label, assemble and initiate delivery — primary publication. Innocent dissemination and the s 10C storage exemption are unavailable to the delivered pack (*Fairfax v Voller*). Do not architect or insure on intermediary immunity. Referee truthfulness warranties in the referee ToS are collected but treated as near-worthless against individuals — **insurance is the real control** (§13.6).
- **Free-text screening** (§5.4) exists because once a version goes STANDING it will be republished on default-submit without further human eyes — screening at submission is the only checkpoint.

### 13.4 E8 "Prefer to discuss directly" — kept, fenced

Retained (removing it forces a false Yes/No binary on a safeguarding question — worse outcomes, and referees route around the platform entirely), with fences: (1) a neutral employer-facing explainer delivered with every such selection — *"Referees also choose this where their employer's policy requires verbal discussion of formal outcomes. It is not, by itself, a finding about the candidate."*; (2) we never broker, schedule, record, or summarise the call; employer ToS states the platform does not verify or endorse anything said off-platform; (3) per-referee selection rates are monitored (a high share = pattern abuse = shadow negative reference → review). **Final retain/remove call is reserved to defamation counsel (Lawyer Q5).**

### 13.5 Sector regulation & marketing law

- **Aged Care Act 2024 (in force 1 Nov 2025) / NDIS:** worker screening obligations (police certificate ≤3 years or NDIS Worker Screening Clearance) are the **provider's, non-delegable** — and none of them is a "reference." **Banned-claims list** (site, app, sales decks, API docs): "compliance check," "screening," "cleared to work," "meets Aged Care Act/NDIS requirements," "replaces police checks," or any juxtaposition implying equivalence. Mandatory pack disclaimer per §5.4. The passport is sold as **speeding the reference step that sits alongside** mandated screening — never bundled into a "compliance pack" SKU.
- **WWCC:** v1 does **not** collect, verify, display or reference WWCC status (state-varied regimes; disability includes under-18 participants). The pack disclaimer names WWCC explicitly. Employer ToS: employers remain solely responsible for all role-specific mandated checks. **Any future credentials-wallet feature requires fresh legal review — it changes our regulatory character.** (This overrules the product-hardening credentials-panel proposal for v1 — §17 R21. Credential *bundling partnerships* in §16 are referral arrangements where the partner performs the check and receives a referral click, never reference content — a different thing.)
- **Fair Work / discrimination:** **marketing rule (permanent):** the passport is a candidate-carried *accelerant* ("attach it and skip the reference wait"). Copy must never instruct or encourage employers to require a passport, filter applicants by passport status, or treat absence as a negative signal. Employer ToS: the employer remains solely responsible for lawful, non-discriminatory hiring decisions. Employer flows keep a visible **no-passport path** ("candidate doesn't have a passport? send a standard request") — absence of a passport renders as *absence of data*, never a flag. The question set contains no item eliciting a protected attribute (reviewed item-by-item, §5.4) and is frozen as reviewed. **No candidate ranking, scoring, sorting, or filtering feature may ever be built** — a legal constraint, not a product preference.
- **ACL:** all prices GST-inclusive single totals (§9). **Claims discipline:** approved claim forms only — "Referee identity verified" + the tier/basis label (§4.1 wording); "Facts instantly. Full reference within 3 business days — or the standing reference, labelled as such." Any new headline claim requires a filed **substantiation note** (evidence, dated) before publication. The A/B/C labels are also the ACL defence: the product tells the buyer exactly what they received.
- **UCT (unfair contract terms):** all three ToS are in the regime (candidates and referees are consumers; nearly every care agency is a "small business"). Drafting rules: no unilateral price/terms variation without ≥30 days' notice + no-penalty exit; no withholding a candidate's own data; no charge for APP 12 access; no penalty for revocation; liability caps proportionate (Lawyer Q12 sets the figure against insurance limits); indemnities mutualised where the counterparty is a consumer (referee indemnity limited to their truthfulness warranty); termination for convenience on short notice, no exit fees, prepaid unused pull credits refunded; plain-English summaries atop each ToS. The ACCC's June 2025 Mable undertaking (same sector, same clause types) is the template of what gets targeted. Candidate activation stays **one-off** (no candidate subscription in v1). Agency plans: monthly rolling, renewal reminder before each of the first three renewals and before any price change, one-click cancel effective at period end, no minimum term, no cancellation fee, renewal terms in the same font size as the price at signup.
- **Consumer guarantees:** the $39 candidate service is a consumer service; guarantees (due care and skill, fitness for disclosed purpose, supply within reasonable time) cannot be excluded. Support SLAs and the refund policy (§9) are drafted to the guarantees; ToS contain no exclusion language.
- **Spam Act / DNCR:** §7.3 stream separation. Do Not Call Register confirmed out of scope for v1 (we make no outbound calls); any v2 phone outreach triggers DNCR washing + the telemarketing industry standard before the first call.

### 13.6 Insurance — PI + cyber are necessary and *not sufficient*

Required stack, bound **before any real data is collected** (§19): **professional indemnity** (service failure, erroneous verification, negligent misstatement in delivered packs) + **cyber & privacy liability** (breach response, OAIC investigation defence, notification costs — insurer notification conditions wired into §12.4) + an **express defamation/media-liability extension** (standard PI wordings commonly *exclude* defamation — our single most probable large claim; limits set against the uncapped aggravated-damages/costs reality; non-economic loss is capped ~A$478K indexed under the uniform Acts) + management liability once the Pty Ltd trades. **Budget A$4,000–8,000/yr combined** at A$1–2M limits (above the ~A$1.2K medians for generic small-business PI/cyber — a data-dense employment platform with defamation exposure prices above median). The broker's risk questions (the §8.3/APP 11 controls) are a build checklist — the security posture *is* the premium.

### 13.7 Retention schedule — final (legal §8.2 wins; implemented as deletion jobs, not intentions)

| Record | Retention | Then |
|---|---|---|
| Delivered snapshots + disclosure/audit logs + consent records | **7 years** from delivery | Destroy |
| Reference versions (standing + superseded) | Life of passport + 7 years after last delivery or account closure, whichever is later | Destroy evaluative content; factual layer de-identified for aggregate statistics only |
| Evaluative content (deliverability) | Non-deliverable at 12 months (§6.11) — retention ≠ deliverability | As above |
| IDV decision tokens (no document images/numbers held) | Life of account + 7 years | Destroy |
| Financial records / tax invoices | 7 years | Destroy |
| Complaint/correction case files | 7 years from closure | Destroy |
| Notification/delivery logs | 2 years | Destroy |

Floors: defamation limitation (1 year, extendable to 3 — defence requires the snapshot, consent record and notification log); Corporations Act s 286 (7-year company financial records); tax records (5 years); APP 11.2 (destroy/de-identify when no longer needed — the schedule *is* the documented justification per row). Lawyer Q15 confirms.

### 13.8 DVS usage terms

Under the Identity Verification Services Act 2023, DVS access is lawful only under a participation agreement with the Attorney-General's Department, via a Gateway Service Provider — with express individual consent before each check, use only for the stated purpose, security/handling conditions, and an **annual compliance self-audit + statement**. Default architecture: contract with an AU provider in the **identity-service-provider model** (provider runs DVS + liveness, returns decision tokens) **and** obtain written confirmation of our IVS access category pre-launch; if the provider's terms require our own participation agreement, we apply (decision ~2–3 weeks per AGD guidance) — scheduled Week 1 alongside JobAdder. DVS consent language is embedded in the §13.2 notices. DVS results are never the sole basis for an adverse decision — a manual review path exists for failed checks (also the fairness control for candidates/referees whose documents are thin for non-fraud reasons: recent migrants, unstable housing histories).


---

## 14. Pilot design — metrics, targets, kill criteria (final)

### 14.1 Shape

- **Where/who:** NSW aged care & disability. Recruit through RTO placement partnerships, care-worker communities, Ali's own job-seeker networks, and founding-agency candidate pools (§16).
- **Duration:** 6 weeks, plus a 4-week recruitment run-in before the pilot clock starts (candidate recruitment starts 4 weeks early, in the same postcodes the agencies hire in). **Extension rule:** if delivered packs <80 at week 6, extend once by 2 weeks before judging.
- **Volume targets:** **300 certified passports** · **≥450 verified referees** (~470 standing references) · **25 founding agencies/providers** verified as employers (minimum viable pilot: 15) · **≥120 real employer requests** through the edit-or-default flow against live vacancies.
- **Ops posture:** concierge-grade (§12). Founder personally onboards the first 10 agencies, reviews every employer verification, reads every default-submitted report in weeks 1–2, and concierge-reviews every first pull per referee in weeks 1–2. The pilot is as much ethnography as software.

### 14.2 The pilot agreement (one page, plain English, digitally signed — contents frozen)

1. Parties + term: 6-week pilot from first live request; either party may exit anytime, no penalty, no fees for the pilot period.
2. What the agency gets: verified employer account, free pulls (fair use ≤100/month), free first-look links, founder support channel.
3. **What the agency promises (the consideration for free service):** (a) run real requests against real vacancies (no test data in the acceptance metric); (b) **committed request volumes + a named contact + a start date** — signatures without volume don't count toward the 25; (c) answer the one-question post-resolution prompt honestly ("Was this sufficient, or did you run your own check?") — the acceptance-data clause; (d) a 15-minute weekly feedback call.
4. Data handling: references disclosed only against a specific candidate-authorised application; a delivered pack may be shared only with the named end employer for that application; no retention beyond the agency's normal recruitment records; no on-sale or third-party disclosure (mirrors §1's never-sell policy).
5. Conversion offer: founding rates (§9) if a paid plan starts within 30 days of pilot end; rates locked 24 months.
6. Testimonial/logo: opt-in checkbox, separate from agreement validity — never bundled consent.
7. Privacy annex (half-page): the collection/disclosure flow in one diagram; both parties' Privacy Act obligations acknowledged.

### 14.3 Measurement — definitions that cannot be gamed

Instrumentation is v1.0 build scope (§11 Blocks 1 + 5), not post-launch analytics. The canonical source is the **event ledger** (server-side, append-only; no reference content, no free text, no ID numbers): candidate funnel events (`candidate.signup → idv_started/passed/failed → employment.added → referee.nominated → referee.prebrief_sent → passport.activated`, `link.shared`, `authorisation.requested/granted/expired`, `correction.requested`, `export.downloaded`); referee funnel (`referee.invited → landing_viewed → account_claimed → idv_started/passed/failed → domain_attested → tier3_confirmed → reference.draft_started/submitted/standing`, `referee.email_routed/unmatched`); request lifecycle (`request.created → window_opened → task.notified/reminder_1/reminder_final → task.updated/confirmed/defaulted/declined/revoked/unreachable/reconfirm_only → pack.delivered/viewed → feedback.capture1/capture2 → pull.charged`); trust & safety (`consent.granted` [with notice version], `consent.revoked`, `notification.sent/bounced`, `fraud.flag_raised/cleared`, `case.opened/resolved`, `suppression.applied/lifted`, `killswitch.activated`); money (`payment.succeeded/failed/refunded`, `invoice.issued/paid`). Every event carries actor role + pseudonymous IDs, request/task/reference IDs where relevant, resolution label, tier, employer type, UTC timestamp.

**Capture point 1 — at delivery (in-product, employer pack view).** The pack view ends with a panel (dismissal is logged; the request cannot be marked "closed" until answered):

> **"Was this reference pack enough for your next step with this candidate?"**
> 1. Yes — we're proceeding **without** any other reference check
> 2. Yes — but we still ran / will run our own check (policy or habit)
> 3. No — we ran / will run our own check because this wasn't enough
> 4. No — and we didn't proceed, partly because of reference concerns
> 5. Candidate didn't progress for reasons unrelated to references
> 6. Still deciding

If 3 or 4: a reason code is required (§14.4). If 2: reason code optional, with "internal policy always requires our own check" as a first-class code (it separates *product* failure from *policy* failure — opposite responses).

**Capture point 2 — at +7 days (email + in-app, one screen):**

> "Thinking about the reference pack you received for **[Candidate]** for **[Role]** on **[date]**:
> 1. Did your organisation contact any referee directly, use another reference service, or otherwise run a separate reference check for this candidate? — **No / Yes, phone call / Yes, another provider / Yes, our internal process / Don't know**
> 2. Did the pack give you enough to make your next hiring decision without that extra check? — **Yes / Partly / No**
> 3. Where is the candidate now? — **Progressed to next stage / Offer made / Started work / Did not progress — reference concerns / Did not progress — unrelated / Still in process**"

Non-response: Capture-1 reminders at day 2 and day 7 after delivery (in-app only); one email for Capture 2. Ali additionally makes a 10-minute call to the first 20 employers; call notes are stored against the request but **never overwrite** the structured answers.

**Locked definitions:**
- **Acceptance (headline)** = Capture-1 type-1 answers ÷ delivered packs with a Capture-1 or Capture-2 answer. **Target ≥60%.**
- **Conservative acceptance** = type-1 answers ÷ **all** delivered packs (unknowns counted against us). Reported alongside; the kill decision uses the headline **only if feedback completeness ≥80%**, otherwise the conservative figure.
- **Default acceptance** = same calculation restricted to **pure-default packs** (every delivered reference resolved DEFAULTED or UNREACHABLE). Mixed packs (any UPDATED/CONFIRMED) and active-only packs are separate cohorts. **Target ≥45% for pure-default.**
- **Feedback completeness** = delivered packs with any structured outcome ÷ all delivered packs. **Target ≥80%** — below 70%, acceptance numbers are indicative only and cannot pass the gate.
- **Time-to-reference** = candidate authorisation → full pack delivery (median + p90), and request creation → delivery. Defaults will dominate the p90 — report both honestly.
- **Referee completion rate** = invited referees who reach a standing reference within 7 days ÷ **all invited referees (all channels)**. Target ≥70%; kill <40%. (The §15/§16 funnel uses deliberately conservative planning assumptions — ~55% of invited referees verifying, ~47% reaching standing — for volume and cash planning. The funnel is a planning model; this metric is the success bar. If the pilot lands at funnel assumptions, that is the reshape zone between kill and pass, judged honestly — §17 R17.)
- **IDV step completion** = referees who complete document + liveness ÷ referees who start it. Target ≥60%. (Restated in freeze: since no reference delivers without IDV (§4.1), "IDV completion among delivering referees" is 100% by construction and measures nothing — the funnel step is the metric.)
- **Candidate conversion** = accounts → paid certified passports. Target ≥35% (funnel plans ~33% of accounts; ~75–80% of candidates with ≥1 standing reference certify under charge-at-standing sequencing).
- **Weekly dashboard** (generated every Monday 08:00 Sydney; reviewed by Ali same day): north star (delivered packs, acceptance cohorts, completeness, traffic lights vs §14.5); speed (median/p90, % <4h / <1 business day / at window close); coverage & labels (A/B/C distribution, mean coverage %, NOT COVERED by theme); supply funnel (candidates by stage, referee completion, IDV pass/fail/abandon by step, tier mix, median referee completion time); demand funnel (orgs verified, requests per org, % with a 2nd request, founding utilisation); reason codes (R1–R10 + verbatim R10, top 3 themes with Ali's action note); money (activations, pulls charged, refunds, **actual variable cost per certified passport vs the A$25 kill line**); ops & trust (queue depths + oldest item, support contacts by category, revocations, complaints, incidents, notification bounce rate, SMS delivery failures); **kill-criteria tracker** (each §14.5 criterion, current value, distance to line — the decision is visible forming for six weeks, no surprises at pilot end).

### 14.4 Reason codes (locked list)

| Code | Meaning | Product response it points to |
|---|---|---|
| R1 | Referee didn't update it — I don't trust a default | Label/provenance redesign; reconfirmation nudges |
| R2 | Content too generic — scales don't tell me enough | Question-set revision |
| R3 | My questions weren't covered | Mapping/coverage improvement |
| R4 | Referee credibility / tier not sufficient | Verification tier policy |
| R5 | Reference too old / evaluative content expired | Freshness + reconfirmation flow |
| R6 | Our compliance/safeguarding policy requires direct collection | Sector/employer is structurally out of scope |
| R7 | Candidate's history looks incomplete | Completeness presentation |
| R8 | Couldn't access / technical problem | Fix the tech |
| R9 | We always run our own check regardless (policy/habit) | Not a product failure — segment out of the headline read |
| R10 | Other (free text, 280 chars, required if selected) | Reviewed weekly |

Label wording is a tested variable in pilot weeks 1–3 via R1 rates by cohort (e.g. "Referee notified {date}, chose not to amend their standing reference" vs "submitted by default") — wording experiments happen on *labels*, never on the underlying honesty (§7).

### 14.5 Success targets & kill criteria (final — one consistent set)

**Success targets:**

| Metric | Target |
|---|---|
| Employer acceptance (headline, §14.3) | **≥60%** |
| Pure-default acceptance | **≥45%** |
| Feedback completeness | **≥80%** |
| Median time-to-reference | **<4 hours** (vs 3–7 day baseline) |
| Referee completion (7-day, all channels) | **≥70%** |
| IDV step completion | **≥60%** |
| Active confirm/edit share of resolved windows | **25–50%** (healthy band: <10% suggests referees don't care — a consent-quality problem; >70% suggests default is unnecessary) |
| Candidate account → certified | **≥35%** |
| Agencies making a 2nd request within the pilot | **≥50%** |
| Referee revocations | **<2%** of referees; **zero** privacy incidents |

**Kill criteria (decided in advance, honoured at pilot end — or earlier on incident):**

1. **Headline acceptance <30%** after ≥40 real requests — employers treat it as a testimonial and re-check anyway; the core thesis is false in its friendliest market.
2. **Pure-default acceptance <20% while active (confirmed/edited) acceptance is healthy** — the edit-or-default mechanism specifically is rejected; the product collapses into "another collection tool" competing with Xref on their turf.
3. **Referee completion <40%** despite pre-briefing and reminders — supply cannot be built on an unknown brand; passport inventory stays empty.
4. **Any serious privacy/data incident**, or a referee discovering a disclosure they didn't understand they'd authorised — immediate stop. Trust products don't get a second incident.
5. **Fully-loaded variable cost per certified passport >A$25** with no credible path below ~A$15 — the $39 price cannot carry the model. (Frozen-plan actual: A$6.65–9.80, §15 — ~2.5× headroom.)
6. **Zero agencies willing to pay $12/pull** in post-pilot conversion conversations despite accepting references — acceptance without willingness to pay means it's a feature, not a business.

**Pass** = acceptance ≥60% (with completeness ≥80%), pure-default ≥45%, referee completion ≥70%, ≥50% of agencies making a second request. Between pass and kill is the reshape zone — judged against the reason-code evidence, not vibes.

---

## 15. Financial model

### 15.1 Unit economics — recomputed net of GST (frozen)

All prices are GST-inclusive (§9). Net revenue = incl. ÷ 1.1. GST is registered from incorporation, so GST on purchases (Stripe fees, AU SMS, pen test, legal) is recoverable as input credits; vendor costs below are kept at their gross planning figures (conservative).

| Item | Incl. GST | **Net revenue** |
|---|---|---|
| Passport certification | $39 | **$35.45** |
| Full pull | $12 | **$10.91** |
| Check / factual-only pull | $6 | **$5.45** |
| Additional employment record | $9 | **$8.18** |
| Certification voucher | $29 | **$26.36** |
| Agency Starter / Growth / Scale | $79 / $149 / $299 per mo | **$71.82 / $135.45 / $271.82** |
| Exit-collection standalone | $59/mo | **$53.64** |

**Variable cost per certified passport (2 referees — the standard passport):**

| Item | A$ | Basis |
|---|---|---|
| Referee IDV × 2 | 2.50–4.40 | Veriff published US$0.80 (Essential) – US$1.39 (Plus) ≈ A$1.25–2.20 each; retries not charged (bills decisions, not attempts) |
| **Candidate IDV × 1** | **1.25–2.20** | **Added in freeze** (D-20 — the build plan's unit economics omitted it because it had deferred candidate IDV) |
| Tier-3/DVS fallback allowance (~10% of referees) | ~0.80 | A$4–6 blended × 10% × 2 referees |
| Candidate + referee OTP SMS | ~0.30 | ~4 SMS @ ~A$0.06–0.072 (AU provider PAYG) |
| Lifecycle notifications | ~0.35 | Email ≈ free (SES ~US$0.10/1k); ~4 SMS + sender-ID amortisation |
| Stripe fee on $39 | 1.36 | AU domestic 1.7% + $0.30 ≈ $0.96; conservative figure allows international-card mix (2.9% + $0.30 = $1.43) |
| Storage/serving per passport-year | <0.10 | Firestore + R2 at KB scale |
| **Total variable** | **≈ A$6.65–9.80** | |

**Contribution per certified passport = $35.45 − $6.65–9.80 = A$25.65–28.80 (72–81% margin on net revenue). The model still works on net figures** — and the kill line (variable >$25, §14.5 #5) retains ~2.5× headroom. Verify-on-demand sequencing (§6.2) is what protects this: with it, worst-case sunk IDV per *unpaid* passport ≈ A$0 (Tier-1-equivalent drafting only, ~A$0.40 of SMS). If every nominated referee were IDV'd upfront regardless of payment, abandoned-passport leakage at ~50% completion would roughly double effective acquisition cost per paid passport — survivable, but it eats the support buffer.

**Per pull:** variable ≈ A$0.10–0.60 (referee notification ~$0.07; serving <$0.02; Stripe $0.50 *only if* card-charged per pull — agencies are invoiced monthly in arrears to kill per-pull card fees) vs net $10.91 (full) / $5.45 (Check/factual-only) → **~90–99% margin**. The pull is nearly pure margin, as designed; the business is won or lost on passport volume and acceptance, not pull COGS.

**Voucher contribution:** $26.36 net − $6.65–9.80 = **A$16.56–19.71** (corrects the business file's ~$21, which was computed gross and pre-candidate-IDV).

**LTV & CAC ceilings (recomputed, net):** LTV per certified passport ≈ $35.45 certification + expected pulls (year-2 base: 9,000 pulls / 15,000 passports ≈ 0.6 × $10.91 ≈ $6.55) + credential-bundle referral expectation (~40% attach × ~$6 ≈ $2.40) ≈ **A$44.40 net revenue**, ≈ **A$35.90 contribution** after variable costs. At a 3:1 contribution-to-CAC discipline: **CAC ceiling ≈ A$12 per certified passport** (≈A$4 per account created) — the freeze figure (the business file's $13–14 was computed on gross revenue). Ali's ~$75 CAC ceiling from other projects **does not transfer** to this business. Channels in §16 sit at A$0–5 — inside the ceiling. Paid social (est. A$35–90 per certified passport) is 3–6× over the ceiling and is therefore a capped A$1,500 data-buying test only. **Agency LTV:** Growth net $135.45/mo × ~14-month expected retention ≈ A$1,900 net revenue at >90% margin → **agency CAC ceiling ≈ A$400–600**, which comfortably funds founder-led sales (~3–5 founder-hours per signed agency). Agencies, not candidates, are where paid acquisition money belongs in year 1.

### 15.2 Cash to pilot verdict — ONE reconciled table

The business lens totalled ~A$16.3K. That figure **excluded the penetration test entirely** and budgeted insurance at a generic small-business level (A$3.5K) that did not include the defamation/media extension the legal lens requires. The table below is the single frozen budget — each line appears **once**, sourced, with the superseded figure noted so nothing is double-counted or silently dropped.

| # | Item | Plan (A$) | Range (A$) | Source / note |
|---|---|---|---|---|
| 1 | Build-phase infra (~2 months) | 400 | 400 | Business §5.1 (Cloudflare/Firebase/SMS/email at build-plan rates) |
| 2 | IDV minimums + usage (build tail + pilot) | 800 | 800 | Business §5.1 (Veriff US$49–99/mo minimum + per-check headroom) |
| 3 | SMS / email / sender-ID registration | 300 | 300 | Business §5.1 |
| 4 | Legal (privacy policy, six collection notices, three ToS, pilot agreement, consent wording — AU privacy/tech lawyer) | 6,000 | 4,000–8,000 | Business §5.1 + legal §10 scope. Non-negotiable: the consent design is the product |
| 5 | Insurance — PI + cyber **with defamation/media extension** (1 year) | 6,000 | 4,000–8,000 | Legal §7.2. **Supersedes** business §5.1's A$3,500 generic estimate (which priced PI+cyber medians without the defamation extension) — not additive to it |
| 6 | **Penetration test + retest** (5–8 tester-days, CREST-affiliated preferred) | 15,000 | 12,000–18,000 **ex GST** | Buildops §7.2. **Absent from the business budget** — added once here. Quoted ex GST; the GST is recoverable as an input credit once registered, so the ex-GST figure is the true economic cost |
| 7 | Candidate acquisition (paid test cap $1,500 + materials/printing $300) | 1,800 | 1,800 | Business §5.1 / §2.1 |
| 8 | Company/admin (Pty Ltd registration ~$600, domain, accounting setup) | 1,400 | 1,400 | Business §5.1 (ASIC fee ~A$597 at 2026 rates — verify at filing) |
| | **Subtotal** | **31,700** | **24,700–38,700** | |
| | Contingency (15%) | 4,755 | — | IDV overage + legal scope creep are the likeliest draws |
| | **TOTAL CASH TO PILOT VERDICT** | **≈ A$36,000** | **≈ A$28,000–45,000** | **Plan on ~A$36K** |

**Sequencing (decided):** legal review and insurance bind in **weeks 6–7** of the build (immediately before real referee data is collected), not week 1; the pen test is booked week 8 (deposit only) and paid on delivery weeks 12–13. A kill decision before those gates sinks only ~**A$5K** (infra + IDV + SMS + marketing + company/admin ≈ $4,700). Founder labour is Ali's, uncashed.

**The pen-test fork (Ali's decision, §20):** if Ali declines to fund the pen test, the fallback is the capped invite-only pilot (§11.3) and cash-to-verdict falls to ≈A$16–24K — with the residual risk recorded as his written acceptance and a hard pen-test gate before any public launch. The default in this frozen plan is: **fund it.**

### 15.3 Break-evens (recomputed on frozen figures)

1. **Run-cost break-even:** steady-state running costs ≈ **A$910/mo** (platform ~$230 + insurance amortised ~$500/mo at $6K/yr + comms/misc ~$180) → covered by **~33 certified passports/month** (at ~$27.25 mid contribution) **or ~6–7 agency plans**. (The business file's 18–20 passports/mo used the superseded $3.5K insurance figure; corrected here.)
2. **Pilot-cash recovery:** A$36K ÷ $27.25 certification contribution ≈ **~1,320 certified passports**; including expected lifetime pull + bundle contribution (~$35.90) ≈ **~1,000 certified passports**. (The business file's ~500 used the $16.3K total and gross contribution; both inputs are superseded.)
3. **Founder-income break-even:** not modelled as a number — Ali's draw is his decision. Stated so nobody mistakes (1) or (2) for "the business pays Ali." At base case (§15.4), year-1 leaves the first real founder-salary capacity in year 1's second half.

### 15.4 Year-1 scenarios (12 months from public launch; pilot occupies months 1–3)

Volumes reuse the VERDICT year-2 model logic, scaled to a launch year starting with a 300-passport pilot. Revenue shown GST-inclusive (as customers pay it) with net-of-GST alongside (as it is recognised).

| Line | Conservative | Base | Upside |
|---|---|---|---|
| Candidate accounts (cumulative) | 6,000 | 15,000 | 30,000 |
| Completed passports (≥1 standing reference) | 2,500 (42%) | 7,000 (47%) | 15,000 (50%) |
| Paying certifications @ $39 | 1,800 → $70,200 | 4,500 → $175,500 | 9,500 → $370,500 |
| Paid pulls (blended $11.40 incl.) | 1,200 → $13,700 | 4,500 → $51,300 | 12,000 → $136,800 |
| Agency plans | 8 × $120 × 6 mo → $5,800 | 25 × $135 × 7 mo → $23,600 | 60 × $160 × 8 mo → $76,800 |
| Exit-collection standalone ($59/mo) | 2 orgs → $700 | 6 orgs → $2,500 | 15 orgs → $8,900 |
| **Year-1 revenue (incl. GST)** | **≈ A$90K** | **≈ A$253K** | **≈ A$593K** |
| **Year-1 revenue (net of GST)** | **≈ A$82K** | **≈ A$230K** | **≈ A$539K** |

Sanity anchor, repeated deliberately: Xref books ~A$20M after 17 years across all products and countries. Base-case year-1 of ~A$250K for a one-sector wedge is ambitious but inside the shape of the possible; upside assumes the RTO channel fires at scale. The VERDICT's year-2 base model (15,000 passports, ~A$456K revenue) remains the year-2 reference point.

### 15.5 Funding decision (frozen)

**Bootstrap to pilot verdict; raise nothing before it.** The pilot verdict costs ~A$36K and answers the only question that determines whether this business exists (employer acceptance). Raising before that answer buys nothing except dilution at the worst possible valuation; raising *after* a ≥60% acceptance result, with 25 agency relationships and a formed referee graph, is a different conversation — and may still be unnecessary if base-case cash flow holds. If post-pilot growth capital is ever needed, the trigger is defined now: **only to fund the NSW density-threshold push (§16) or the labour-hire entry (§16), never to fund discovery.**

---

## 16. Go-to-market & expansion (summary)

**First 300 candidates (pilot cohort, NSW care) — three channels, all inside the ~A$12 CAC ceiling:**
1. **RTO placement partnerships (target ~120).** CHC33021 Certificate III in Individual Support had 101,140 enrolments nationally in 2025 (NCVER) across 669 RTOs; every student completes 120+ hours of work placement — and **the placement supervisor is a referee the student already has**, at the exact moment they start job-hunting (§5.3 makes that reference collectable). Pitch to the RTO is employability: *"Your graduates leave with a verified reference from their placement supervisor — collected once, carried into every application."* Named targets: TAFE NSW (via individual campus relationships, not head office), Kirana Colleges, Nurse Training Australia / Care Plus Training (Burwood NSW), InterCare Training, and NSW community RTOs (Novaskill, VERTO, ARC Training, ETC — smaller cohorts, faster decisions, regionally dense). Deal shape: free for students during pilot; optional voucher purchase later at $29. CAC ≈ founder time.
2. **Care-worker communities (target ~100).** National Facebook groups for support workers and aged-care workers, plus Ali's own job-seeker peer networks. The founder story is the content: *"I job-hunted in this sector. My reference took 9 days. I built the fix."* Help-first posts; group admins ban ads, not members with a story. CAC ≈ A$0–3.
3. **Founding-agency candidate pools (target ~80).** Each founding agency invites its own incoming applicants via an agency-branded invite link — highest intent (the candidate is mid-application) and it closes the loop: the agency that will *pull* the passport is the one that *seeded* it. CAC = A$0.

**First 25 agencies:** identified by (1) NSW care labour-hire agencies and mid-size providers hiring support workers weekly on JobAdder (the ATS footprint is the tell — it also pre-qualifies them for the Growth-tier integration story); (2) providers repeatedly advertising the same support-worker roles on SEEK (repeat ads = churn = reference pain); (3) agencies/providers in the same suburbs as the RTO cohorts (geographic density). Mix: ~15 labour-hire/staffing agencies, ~10 direct providers. Signer: the person who owns time-to-fill — Operations/Recruitment Manager or HR/People & Culture lead. Founder-led; ~40–50 conversations for 25 signatures. The pitch (verbatim): *"Your reference checks take 3–7 days and your referees ignore your calls. Our candidates arrive with a verified reference passport — referee identity-checked once, reference given once. You see the facts instantly, free, and if you want the full reference for a specific application, the referee gets 3 business days to update it for your role — or it releases automatically. Pilot agencies pay nothing for 6 months. All we ask is that you tell us honestly, per request, whether the reference was enough or whether you still ran your own check."*

**Funnel (planning model — assumptions stated; §14.3 holds the success-bar definitions):** 900 accounts → 540 passports built (60%) → ~920 referee invitations (1.7 avg) → ~505 referees verified (55%) → ~430 referees / ~470 standing references (85% of verified complete ≥1) → ~380 candidates with ≥1 standing reference (~70% of built) → **300 certified passports** (~79% of those with a standing reference; ≈33% of all accounts) → 25 founding agencies → **≥120 real requests** → target ≥60% acceptance → **~10 agencies converting to paid** (40% planning assumption).

**Density threshold (the strategy in one set of numbers):** NSW holds ~32% of the national care workforce ≈ ~120,000 workers; at ~26% turnover, ~31,000 change jobs each year — that *flow* is the market. An agency processing ~500 hires/year builds a habit when it meets passports weekly ≈ 10% penetration of the active job-changer flow in its patch. **Default-useful threshold = 3,000 active NSW care passports + 2,500–3,000 verified referees** (~40% of the addressable referee pool, where pre-verified referees become the median case and collection cost collapses — the IDV step, the slowest and leakiest, is already done). Pilot exit (300 / ~450) is proof, not density. **All growth spend stays inside NSW care until the threshold is reached** (or multi-state agency demand pulls expansion). Density before breadth is this arithmetic, not a slogan.

**Moat — the honest version:** nothing stops Xref shipping referee accounts next quarter; the mechanic, tech, integrations and pricing are all copyable and are **not** moats. What is genuinely hard to copy is accumulated position: (1) a *formed* referee graph — verified identities, standing consents and platform-email habits are non-portable, and converting transactional referee emails into consented accounts is the same cold-start we face, so whoever claims the referee first owns the default; (2) provenance history, which cannot be backfilled; (3) the care-sector question set becoming the sector standard (§6.10 learning loop); (4) referee-side trust in one sector, suburb by suburb. Net: a **12–18 month head-start asset** that becomes durable only at the density threshold. Spend the head start on referee accounts and NSW care density, not on features.

**SEEK Pass scenarios (pre-decided):** stays walled (base case) → we win everywhere off-SEEK. SEEK acquires Xref (revival possible) → the combined entity still lacks referee accounts/standing consent; a price umbrella forms. SEEK Pass adds referee accounts (the dangerous one) → defence is the formed graph + cross-platform reach SEEK structurally won't offer; our depth becomes care + labour hire and the agency channel. SEEK opens issuer APIs → **we issue into SEEK Pass as a channel, never as system of record** (non-exclusive, revocable; our graph and consents stay ours).

**Expansion — triggers, not dates:**
- **Labour hire (expansion #1):** enter when ALL of: pilot acceptance ≥60% overall and ≥45% pure-default · ≥10 agencies on paid plans · referee completion ≥65% sustained over 8 weeks · 3 labour-hire agencies signed to a pilot agreement. First sub-sectors: care labour hire (adjacent), then warehousing/logistics, then construction.
- **Second state:** when EITHER the NSW density threshold is reached OR ≥5 multi-state agencies on paid plans request activation in that state. **VIC first, QLD second.** NT is Ali's home but is *not* a launch state for density reasons — stated plainly so it isn't relitigated.
- **New Zealand: parked.** Trigger to revisit: an AU agency group on a paid plan with NZ operations requests it, AND AU revenue >A$250K/yr run-rate. No self-initiated NZ expansion before both.
- **Collect-at-exit standalone ($59/mo):** launches when ≥5 non-Scale employers ask (inbound pull).
- **Credential-bundling partnerships (fit2work/Equifax class, CVCheck class):** referral model — target 10–20% revenue share on referred checks (≈A$5–13 per completed check) or a fixed A$5–8 per completed referral [negotiation targets]. Co-sold bundle: "Police check + certified reference passport — A$89" on the partner's rails or ours. Two rules: the partner never receives reference content (a referral click, not data), and bundling never makes the passport look government-affiliated.
- **Switching costs (honest):** candidates low-to-moderate (leaving abandons standing references and referee consents — real, but hostage design would poison the trust brand); referees moderate and growing (every reference and confirmation lives in one dashboard; the platform email is on their professional correspondence); agencies moderate once integrations land (plans are month-to-month by design — retention must come from the graph, not contracts).


---

## 17. Reconciliations — every conflict between the drafts, decided in writing

Each row: the conflict, where it came from, **the frozen decision**, and the reason. "Decided in freeze" items (§§5.3, 6.6, 6.8, 9, 14.3 and elsewhere) are the points a source file left open that this plan closed.

| # | Conflict (sources) | **Frozen decision** | Reason |
|---|---|---|---|
| R1 | **Timeline:** build-plan ~8 weeks vs harden-buildops 14–16 weeks | **14–16 weeks** from Freeze Day 0 (upside 11–13, downside 18–22); feature freeze Week 12; go/no-go Week 14 (§11.2) | The 8 weeks priced the MVP *summary*; the full spec adds candidate IDV, the tier engine, mapping/coverage accounting, immutable snapshots, RECONFIRM_ONLY, APP 13 cases, fraud queues, the referee email *inbox*, instrumentation, pen test and pilot prep — none of which were in the 8-week blocks |
| R2 | **"Verified" basis:** spec promises DVS verification via an AU provider; build plan substitutes Veriff (which does not query the DVS) | **Legal wins on labels.** Two bases, never blurred: **DVS-verified** (issuer-record match via AU gateway) vs **Document-checked** (authenticity + liveness). Only DVS-verified may be called "verified against government records." Pilot launches Document-checked with honest labels; FrankieOne/greenID application runs from Week 1 as a compliance dependency (§4.1) | Marketing a Veriff-only check as government-record verification is an ACL s 29 false representation and silently downgrades the moat |
| R3 | **Candidate IDV:** spec §2.3 requires it before a passport is Verified/shared; build plan §1.2 defers it to v1.1 | **Spec wins: required** before Certified status and the verified public link (red-team D-20; buildops adjudication #2). Draft building stays OTP-only (§4.5) | Without it, anyone can build a passport in a victim's name; deferring it invalidates the "verified" claim on every public link |
| R4 | **Window:** spec fixed 3 business days; build plan employer-settable 2–5 days | **Platform-fixed 3 business days**, identical for everyone, never employer-configurable (§6.9) | Employer-set windows are gameable both ways (manufactured defaults; favouritism). Uniformity is testable, explainable to referees, and legally cleaner |
| R5 | **Tier definitions + the cheap mill path:** build plan's Tier 1 = domain attestation only, with a "domain-attested-only usable reference" fallback; spec requires document ID + liveness for every tier | **Spec definitions win** (§4.3); the build-plan fallback is **deleted** (D-01): no deliverable reference without document IDV + liveness — a non-IDV referee may draft only | Domains and mailboxes are free and unlimited; documents and faces are not. The fallback was the single cheapest referee-mill path in the design |
| R6 | **Tier 3 conferral:** spec confers Tier 3 on any verified employer's confirmation | **Gated (D-05):** ABN active ≥12 months **or** sector-register listing; account ≥90 days + payment method; same-entity confirmations only; 5%/month random audits (D-07) (§4.4) | A sole-trader ABN is free/instant and ABNs are public — ungated, a candidate could mint the platform's highest assurance stamp for a confederate in an afternoon |
| R7 | **Unit economics basis:** build plan/business computed margins on GST-inclusive prices and omitted candidate IDV | **Recomputed net of GST, with candidate IDV added** (§15.1): net certification $35.45; variable cost A$6.65–9.80 per certified passport; contribution A$25.65–28.80 (72–81%); CAC ceiling ≈ **A$12** per certified passport (not $13–14, not Ali's $75 from other projects) | GST registration is mandatory-in-practice from incorporation (§13.1/§15); margins must be proven on money the company actually keeps. **The model still works** — kill-line headroom ~2.5× |
| R8 | **Total cash to pilot verdict:** business ~A$16.3K vs buildops' pen-test requirement and legal's insurance stack | **One table (§15.2): ≈A$36K plan figure, range A$28–45K.** Business's $16.3K excluded the pen test entirely and budgeted insurance at $3.5K without the defamation extension; both corrected once, no double-counting (insurance line *supersedes*, pen-test line *added*) | A frozen plan cannot carry two budgets. The pen test and defamation cover are the two items a trust product cannot discover it needed after launch |
| R9 | **API timing:** spec scopes a partner API + webhooks as v1; build plan defers all integrations; integrations doc puts the core API at "the platform itself" and Zapier "early" | **Internal API v1.0; external API, webhooks, embeds and Zapier/unified-API are v1.1** (§10). Platform built API-first internally; JobAdder application still filed Week 1 | Approval queues and per-partner dev would consume the pilot window; the pilot's 25 known agencies use the web flow + share link. The internal-API-first build preserves the v1.1 path at near-zero extra cost |
| R10 | **Passport caps:** build plan "up to 3 standing references" per passport; buildops v1.0 scope "up to 3 employment records"; product hardening: per-employment cap, unlimited employments; business pricing: $39 includes 3 references, extra record $9 | **Unlimited Employment Records; ≤3 referees per employment; $39 certification includes up to 3 standing references; additional employment record (with references) $9 each** (§§5.5, 9) | A per-passport cap dies the moment a casual care worker — the exact wedge user, often holding 2–3 concurrent jobs — outgrows it |
| R11 | **Candidate paywall vs evaluative delivery:** spec §12 implies $39 activation unlocks sharing; business §1.2 lists "evaluative layer shareable" as a certification unlock; product hardening §B8 says evaluative delivery is never tier-gated | **§B8 wins** (§9): free tier = build, collect, share (two-layer link), ≤5 employer requests/month; certification = ID badge, verified link, unlimited requests, correction/response centre, sharing kit, pack transfer. **Evaluative delivery flows through the employer's paid pull in both tiers**; uncertified passports are labelled "candidate identity not platform-verified" | The pilot's executioner metric (employer acceptance) must not be confounded by a candidate paywall; each side pays for what it values |
| R12 | **Public page & verify endpoint:** spec §10.2 shows factual layers on the public page; business free tier promises a "factual summary link" | **Red-team split wins (D-12/D-24)** (§7.1): anonymous layer = status chips only; factual detail behind work-email OTP + audited view; verify endpoint accepts candidate-issued tokens only, uniform negatives, no dates | The link *will* be public in practice (CVs, LinkedIn). As specced it was a scrapable database of care workers' job histories, and the verify endpoint an existence oracle for who is job-hunting |
| R13 | **Two different "$6" products:** product hardening's instant shortlist **Check** ($6: factual + E11 + E12) vs business's **factual-only pull** ($6: a Full Request that delivers degraded) | **Both kept, distinctly named and metered** (§§6.8, 9): Check = $6 instant shortlist product; Full Request = $12, or $6 when it delivers factual-only. Both count as 0.5 pull in agency plans | They serve different moments (screening many vs probing one) and different failure modes; collapsing them would either overcharge shortlisting or undercharge degraded full pulls |
| R14 | **Question mapping:** spec §5.2 specifies semantic classification (embeddings + LLM) at v1 | **Deterministic only in v1.0** (codes, synonym table, employer-confirmed preview); semantic mapping is v1.1 behind a **≥98% precision gate**, de-identified before leaving AU infrastructure (§6.10) | A wrong silent mapping misrepresents a referee's answer — an accuracy *and* legal risk — and pilot employers are onboarded onto the sector template anyway |
| R15 | **Collect-at-exit:** spec includes employer self-serve in v1; build plan defers entirely; business prices a $59/mo standalone | **Concierge/admin-triggered in v1.0; self-serve v1.1; automation v2.** Free during pilot and in Scale; standalone $59/mo launches only on the §16 trigger (≥5 non-Scale employers asking) (§6.3) | Exit collection is the supply engine and 2–3 founding employers will use it in the pilot — but self-serve tooling before the pilot proves anything is waste, and charging for supply acquisition taxes our own moat |
| R16 | **Agency plans:** build plan defers subscriptions post-pilot; business fixes tiers now; buildops puts plans in v1.1 | **Tiers and prices frozen now (§9); billing automation is v1.1.** Pilot agencies are free founding verifiers (§14.2); monthly Stripe Invoicing can run manually if a conversion lands early | Pricing is a promise founding agencies sign against; the automation is plumbing that can follow the promise |
| R17 | **Referee completion — denominator and bar:** build-plan target ≥70% (invited → standing, 7 days) vs business funnel assumptions (55% of invited verify; ~47% reach standing) | **Metric definition frozen** (§14.3): completion = standing within 7 days ÷ **all invited referees, all channels**; target ≥70%, kill <40%. The funnel's ~47% stands as the *conservative planning assumption* for volumes/cash — if the pilot lands there, that is the reshape zone, judged honestly | The two files measured different things (a success bar vs a planning model). Freezing one denominator prevents the pilot result being spun either way after the fact |
| R18 | **Candidate conversion:** build plan "≥35% of completions"; business funnel ~33% of accounts / ~79% of standing-reference holders | **Frozen:** headline target = **≥35% of accounts → certified** (§14.5); the funnel's ~79% standing→certified rate is the planning assumption under charge-at-standing sequencing (§15/§16) | One headline number, defined once; the funnel explains how it is reached |
| R19 | **"Tier 2 IDV completion ≥60%"** (build plan metric) | **Restated** (§14.3): IDV *step* completion = referees completing document + liveness ÷ referees who start it; target ≥60% | Under D-01, IDV completion among *delivering* referees is 100% by construction — the old metric measured nothing. The funnel step is where friction actually shows |
| R20 | **Retention schedule:** product hardening §D7 (IDV tokens active + 1 yr; evaluative 7 yrs after last activity) vs legal §8.2 (IDV tokens life of account + 7 yrs; versions life of passport + 7 yrs) | **Legal wins wholesale** (§13.7) | The legal schedule sits on three statutory floors (defamation limitation + extension, Corporations Act s 286, tax records) balanced against APP 11.2; the product figures were estimates without those floors |
| R21 | **Credentials panel:** product hardening §E2 adopts display-only police/WWCC/NDIS status on the passport vs legal §3.2 (v1 collects/displays no WWCC status) | **Legal wins: NO credentials panel in v1.0** (§13.5). Any future credentials feature requires fresh legal review. Credential *bundling* (§16) survives as a referral partnership — the partner performs the check and receives a click, never content or status | Displaying screening status drifts into screening-adjacent territory and APP 3 problems, and risks implying the passport intersects mandated checks — the exact misrepresentation §13.5 bans |
| R22 | **Language:** buildops assumes "English only"; product hardening §D5 requires translated templates for five high-stakes flows | **Merged** (§11.1): English UI in v1.0; **professionally translated templates** (invitation, consent summary, window notifications + action page, reconfirmation ask, authorisation page) in Mandarin, Nepali, Tagalog, Hindi, Punjabi ship in v1.0; full UI i18n is v2 | In this workforce, comprehension *is* completion rate and consent validity — but only the flows where misunderstanding is dangerous or fatal justify translation spend at v1 |
| R23 | **Inbound referee email:** build plan files inbound mail into the referee dashboard as correspondence | **Kept, with red-team D-17 as a hard rule** (§7.2): inbound email is **never a request**; unauthenticated mail quarantined; no clickable links from external mail in the dashboard; external mail never carries platform action buttons | A spoofed email rendered as a platform request would launder phishing through the trusted UI — the referee's inbox is an attack surface, not just a feature |
| R24 | **Insurance budget:** business A$3,500 vs legal A$4–8K | **Legal wins: budget A$4–8K/yr, plan A$6K**, PI + cyber + express defamation/media extension (§§13.6, 15.2) | Standard PI commonly *excludes* defamation — our single most probable large claim. The business figure priced generic medians for a business that is not generic |
| R25 | **Penetration test:** build plan defers it to post-pilot revenue (self-review only at launch) | **Buildops wins: pen test is a launch gate** (§11.3), budgeted §15.2. Sole fallback: capped invite-only pilot + Ali's written risk acceptance; pen test then gates any public launch | This product holds third-party opinions about named workers plus IDV outcomes. A "self-review only" open launch is the one corner this plan refuses to cut |
| R26 | **Ali's referee verification ladder** (Ali input, corrected version: the ladder verifies the **referee**, not the candidate) vs the drafts' tier design, which had work-email attestation and employer confirmation but no LinkedIn rung | **Integrated as Axis 2 (affiliation) of the verification architecture** (§4.2): rung 1 LinkedIn corroboration (ops-reviewed, labelled "Profile-corroborated") → rung 2 company-email attestation → rung 3 employer/HR confirmation. It corroborates affiliation; it never substitutes for Axis 1 (IDV + liveness) and never by itself lifts a reference above Tier 1 | Ali's direction strengthens the platform's core layer — it verifies the referee's employment at the claimed organisation, which also indirectly corroborates the candidate's claim. The honest-labelling constraint stands: LinkedIn is self-reported, so it corroborates rather than proves, and overstating "verified" is the ACL/moat risk R2 guards |
| R27 | **Name & domain:** domain-names.md recommended "RefereeCheck" on refereecheck.com.au (singular .com parked for sale, price unlisted) | **Ali's decision (2026-11-18 ~00:51 ACST) wins: RefereeChecks, primary domain refereechecks.com** (Ali-checked; independently confirmed unregistered via Verisign RDAP 404). refereecheck.com.au becomes a defensive registration. Referee email subdomain: **`refs.refereechecks.com`** (build plan's `refs.` shape over the spec's `ref.`). SMS sender ID: shortened corresponding form (e.g. "RefChecks") per §1/§12.7 (§1) | "Referee checks" is the exact plural phrase in AU job ads ("referee checks will be undertaken"); the plural .com avoids the parked singular entirely (no published price; Sedo: not for sale; broker-only route at a A$145.41 fee) and keeps NZ/expansion open |
| R28 | **Notification cadence:** spec fixes two reminders (+1 business day, −4h) | **Merged cadence frozen** (§6.9): open (email+SMS) → +1bd (email) → −24h (email+SMS) → −4h (SMS if unacted), plus quiet hours, digest mode, pull-notification batching, and the referee snooze (+1 business day, once per task) from product hardening §D2 | The spec's two reminders are a subset of the hardened cadence; the additions protect the SMS channel's credibility (every message specific, none in quiet hours) and convert the commonest default-cause (days off) into a labelled one-day delay |
| R29 | **Default release vs undelivered notification:** spec's UNREACHABLE state delivers the standing version at window close; red-team D-19 says a reference should never default-release on an email nobody received | **Split by delivery evidence** (§6.8): where at least one channel confirmed delivery, UNREACHABLE handling applies (Label C + flag); where **no** channel confirmed delivery, evaluative content does **not** default-release — factual layer only, labelled | Silence after *seeing* the choice is meaningful consent; silence from an unopened email is weaker. The consent's legitimacy depends on the notification actually arriving |

**Count: 29 conflicts reconciled.** Everything else in the source files stands as written and is incorporated by the section references throughout this plan.

---

## 18. Change control — Ali's "no changes later" rule, made operational

This plan is **frozen as of 18 November 2026**. No honest plan can promise that reality will never force a change — vendors change prices, lawyers find wording problems, pen tests find holes. What the freeze does is make every change *visible, priced, and approved*:

1. **The frozen baseline** is this document. It is versioned; any edit after freeze is a new version with a changelog entry. The source drafts are evidence, not authority — where they disagree with this plan, this plan wins (§17).
2. **Only three routes in:**
   - **(a) Defects** — the build doesn't match this plan. Fix to the plan; log the same day.
   - **(b) Legal/security requirements** — a lawyer answer (Appendix A), a pen-test finding, or a regulator/vendor rule that makes a frozen item unlawful or unsafe. Fix the minimum necessary; log the same day; Ali is notified, not asked to re-design.
   - **(c) A written change request (CR)** — stating: **what** changes, **why**, **build days**, **timeline impact**, **risk impact**, and **what it displaces** from the §11.2 slip list. **Ali approves or rejects in writing.** No verbal scope additions. No quiet additions — if a pilot agency demands external API access, that is a CR, not a favour.
3. **After feature freeze (Week 12):** P0/P1 fixes only. Everything else is v1.1 by definition.
4. **What a CR can never change without re-opening the whole freeze:** the §1 design principles (application-specific disclosure; no browsing/talent pool; never sell data), the §6.5 consent triangle, the §7 labelling honesty rules, and the §14.5 kill criteria. Those are the product's constitution and its pilot's integrity — changing them mid-flight invalidates the experiment the pilot exists to run.
5. **Decisions already delegated:** label wording experiments in pilot weeks 1–3 (§14.4) are pre-authorised *within* the honesty rules; vendor substitutions that follow §12.6's interface rule and don't change labels, tiers, or prices are operational, not CRs.

---

## 19. Launch-gate checklist — all boxes green, or no pilot

Owners: **Ali** (owner decisions & external actions) · **Build** (deliverables) · **Joint** (Ali + build + external sign-off). This merges the legal gate list and the buildops gate list, deduplicated.

**Ali**
- [ ] Legal entity incorporated (Pty Ltd); ABN active; **GST registered**; ABR authorised-contact email current (blocks ACMA confirmation, §12.7)
- [ ] **Domains registered: refereechecks.com** (primary) **+ refereecheck.com.au** (defensive)
- [ ] Formal IP Australia trademark search (classes 9, 35, 42, 45) + ASIC business-name check completed; brand committed on the results
- [ ] Pricing confirmed as frozen in §9 ($39 / $12 / $6 / Check $6; agency tiers; founding terms)
- [ ] Stripe account activated in the company's name (KYC complete, bank account, GST treatment confirmed with accountant)
- [ ] ACMA sender-ID confirmation completed in ACMA Assist (myID) for **both** SMS providers (ClickSend + Sinch/MessageMedia)
- [ ] **Insurance bound, certificates in hand:** PI + cyber + **defamation/media extension**; broker advised the business holds employment references + IDV outcomes
- [ ] Privacy/technology lawyer engaged; Appendix A answers received in writing (or explicitly scheduled with launch-blocking items answered); pen-test firm booked (Week 8) and deposit paid
- [ ] DVS access category confirmed in writing with the IDV provider (§13.8)
- [ ] Backup operator contracted, trained, access provisioned (least-privilege)
- [ ] Pilot agency agreements **signed with committed volumes**: target 25 orgs (minimum viable pilot: 15), each with named contact + start date
- [ ] Founder support roster published internally (Sydney hours, §12.1) for pilot weeks
- [ ] Budget funded per §15.2 (≈A$36K staged: ~$5K to build midpoint; legal/insurance weeks 6–7; pen test booked Week 8) — **or** the capped-pilot fork elected in writing (§15.2)

**Build**
- [ ] Stack spike passed or Cloud Run fallback invoked (§11.1) — decision recorded
- [ ] All §11.4 v1.0 scope items complete; feature freeze declared (Week 12)
- [ ] §11.3 state-machine suite green incl. property, race, fake-clock and soak tests; authz matrix tests green; security self-checklist green; storage audit proves no ID documents held (§8.3)
- [ ] **Pen test complete; critical/high findings remediated + retested;** mediums triaged with dates
- [ ] Accessibility: axe zero critical/serious on core flows; manual keyboard + screen-reader passes signed off; consent copy comprehension-tested on 3 non-technical readers
- [ ] Load test at 10× pilot volume passed; scheduler stress case (1,000 windows closing in one simulated hour) passed
- [ ] Backups running; **restore drill passed** with RPO/RTO measured, not assumed
- [ ] Kill switch tested end-to-end; incident runbook (§12.4) tabletop completed with the backup operator; NDB templates pre-drafted; breach register created
- [ ] Event ledger + feedback capture (§14.3) verified against synthetic packs; weekly dashboard generating correctly
- [ ] Data export (candidate/referee/employer) tested; account-deletion flow tested; retention deletion jobs (§13.7) implemented, not just scheduled
- [ ] Support inbox live; all §12.3 templates loaded as macros; status page live; trust centre + methodology page + crisis playbook published (§§7.1, 8.4)
- [ ] Six APP 5 collection notices live with version logging (§13.2); transactional/marketing streams separated (§7.3); "verified" copy everywhere matches the actual verification basis (§4.1); banned-claims list (§13.5) applied to all copy; pack disclaimer live

**Joint**
- [ ] Legal sign-off: privacy policy (incl. ADM section), collection notices, collection consent incl. default-release wording, all three ToS (UCT-reviewed), employer terms incl. the "does not replace NDIS Worker Screening / police checks" wording, question set + labels reviewed for defamation risk, E8 "prefer to discuss" retain/remove call made by defamation counsel (Q5)
- [ ] PIA reviewed by the privacy lawyer; IDV offshore-processing disclosure confirmed in the referee notice; vendor/APP 8 register complete with DPAs
- [ ] Complaints mechanism live to s 31A spec; suppression SLA ≤7 days operational; concerns-notice playbook written
- [ ] Dry-run pilot passed: 5 candidates / 5 referees / 2 employers end-to-end incl. one default, one revoke, one correction case, one IDV exception — all handled via the real queues
- [ ] Agency onboarding pack + referee help sheet + candidate FAQ published
- [ ] Go/no-go review held against this checklist; §14.5 criteria understood and re-accepted by Ali; pilot start date set

---

## 20. Ali's remaining gates — the only things left undecided

Everything else in this plan is decided. These are the items only Ali can do or decide; the build cannot start (Freeze Day 0, §11.2) until gates 1–4 are done.

1. **Approve this frozen plan** — including the name **RefereeChecks** and the §18 change-control rule that binds future changes (his own included) to a written CR.
2. **Register the domains:** refereechecks.com (primary; confirmed available 18 Nov 2026) + refereecheck.com.au (defensive). Availability is a snapshot — these are the kind of exact-phrase names that disappear.
3. **Incorporate the Pty Ltd** (the company is the APP entity, DVS applicant, contracting party and insured — §13.1), with ABN + **GST registration from day one**, and confirm the ABR authorised-contact email is current (it gates the ACMA sender-ID confirmation).
4. **Commission the formal trademark search** (IP Australia, classes 9/35/42/45) + ASIC business-name check — the US "REFEREE®" registration in this industry (§1) is the one flag the search must clear before brand commitment.
5. **Fund the budget:** ≈**A$36K** to pilot verdict (range A$28–45K, §15.2), staged so a kill decision before weeks 6–7 sinks only ~$5K — **or** elect in writing the capped invite-only pilot without the pen test (§15.2 fork; not recommended, and it hard-gates any public launch behind the pen test).
6. **Engage the solicitor** with Appendix A's 18 questions — written answers pre-launch; Q5 (E8 "prefer to discuss") and Q18 (DVS access category) are launch-blocking.
7. **Sign the pilot agencies:** 25 founding agreements (15 minimum) with committed request volumes, named contacts and start dates (§14.2) — signatures without volume don't count.
8. **Complete the ACMA sender-ID confirmation** in ACMA Assist via myID, for both SMS providers (§12.7) — a two-minute step only the ABR authorised contact can do, on a 15-business-day clock started in Week 1.
9. **Activate Stripe** in the company's name (KYC) and confirm GST treatment with the accountant.
10. **Contract the backup operator** before pilot start (§12.1) — the pilot's ops load (10–14 hrs/week steady, 16–22 at peak) is not survivable solo-plus-illness.

---

## Appendix A — The 18 lawyer questions (to be answered in writing pre-launch)

*For an Australian solicitor (privacy + defamation + employment). Grouped as in the legal hardening (§10 of `harden-legal.md`).*

**Privacy & data**
1. On our facts (fee-per-disclosure of consented references), are we an APP entity from day one via the s 6D "trades in personal information" carve-out, or does the consent-based-trading exception preserve the small-business exemption — and does the answer change any launch obligation given we intend full compliance regardless?
2. Consent validity: given candidate/referee power imbalances (job-seeking; former-employee requests), is our pre-authorisation + per-pull notification + one-tap revoke model sufficient to keep APP 3/6 consent "voluntary and informed"? What additional indicia (cooling-off, independent confirmation, plain-language testing) would you require?
3. Does E8 (substantiated complaint/investigation/disciplinary outcome) involve collecting *sensitive information* requiring APP 3.3 consent in the form we've drafted, and is our candidate consent copy specific enough?
4. APP 12: is our redaction line (referee private contact details redacted; all content about the candidate disclosed) correct, and are there circumstances where referee identity itself could be withheld?
5. *(Defamation counsel)* E8's "Prefer to discuss with the employer directly" option: retain with our fences (§13.4), or remove? Please advise on the imputation-by-selection risk specifically.
6. ADM transparency (APP 1.7, from 10 Dec 2026): do our fraud-signal holds and question-mapping classifier trigger the disclosure duty on OAIC's current guidance, and is our draft privacy-policy wording sufficient?
7. Cross-border: is our APP 8 position sound for Veriff (Estonia) processing of ID documents/biometrics, and do we need express APP 8 consent as well as contractual safeguards for that flow?

**Defamation**
8. Qualified privilege: does the platform, as a commercial intermediary charging per disclosure, hold its own qualified privilege under s 30 (NSW) and equivalents on our exact flow (pre-authorised default release included), or should the ToS restructure the disclosure as the referee's act via the platform as agent? What wording achieves the stronger position?
9. Given WA has no serious-harm element and no s 31A defence, and SA declined s 31A: is our "strictest-jurisdiction" control set (7-day suppression nationally, concerns-notice playbook) the right risk posture, and should WA/SA employer deliveries carry any additional step?
10. *(Also employment)* "Employment agency" boundary: do we require any licence, registration, or code compliance as an employment agent/private employment agent in WA (Employment Agents Act 1976) or QLD (Private Employment Agents Act 2005) — including because candidates pay the $39 activation — and does the agency-plan tier change the answer?
11. Labour-hire boundary confirmation: on our facts (no supply of workers, no payment of workers, fees for information only), confirm we are outside the QLD/VIC/SA/ACT labour-hire licensing schemes, and review our four boundary markers (§13.1) for completeness.

**Consumer, contracts & structure**
12. Review all three ToS (candidate, referee, employer/agency) against the UCT regime; confirm current maximum penalties (including the reported March 2026 doubling) and advise the defensible liability-cap figure given our insurance limits.
13. Marketing sign-off: review the banned-claims list and approved claim forms ("verified", "facts instantly…") against ACL ss 18/29, and the collect-at-exit employer pitch ("never field a reference call again") for any representation we cannot substantiate.
14. Fair Work: does any element of our employer marketing or agency-plan terms risk accessorial liability (s 550) if an employer uses passport status as a hiring filter, and is our ToS allocation + marketing rule sufficient mitigation?
15. Retention schedule (§13.7): confirm the 7-year snapshot/audit retention is defensible under APP 11.2 (i.e. that legal-defence purpose justifies it), and advise the correct destruction trigger for evaluative content where a candidate closes their account mid-schedule.
16. Structure & tax (with accountant): Pty Ltd + voluntary GST registration from day one; confirm $39/$12 GST-inclusive modelling and any payroll/contractor implications of the collect-at-exit employer relationships.
17. Insurance adequacy (with broker, counsel to review): are A$1–2M defamation/media limits adequate for a national republication model, and should referee-facing terms include a contractual cap on referee liability to encourage referee participation?
18. DVS: confirm our IVS access category (business user with own participation agreement vs identity-service-provider model), who must sign, and whether our planned consent wording satisfies the IVS participation terms.

---

## Appendix B — Source map

| Master plan section | Primary sources |
|---|---|
| §1 Name & domain | `domain-names.md` (§§1, 5) + **Ali's domain decision, 2026-11-18 ~00:51 ACST** (§17 R27) |
| §2 Validation basis | `VERDICT.md`; `incumbents.md`; `portability.md`; `demand-economics.md` |
| §3 Roles & identity | `product-spec.md` §1; `harden-product.md` §A4, §C2 |
| §4 Verification | `product-spec.md` §2; `harden-legal.md` §§0.3, 6.4; `harden-redteam.md` D-01/05/07/09/15; `ali-input-verification-ladder.md` (corrected version) |
| §5 Reference & question set | `product-spec.md` §§3, 11; `harden-product.md` §B5; `harden-legal.md` §§1.2, 2.5, 3.4 |
| §6 Core flows | `product-spec.md` §§4–9; `harden-product.md` §§A1–A3, B1–B9, C1–C6, D1–D2, E1, E5; `harden-redteam.md` D-16/19/35; `harden-buildops.md` §1 |
| §7 Labelling & public surfaces | `product-spec.md` §§4.4, 5.3, 10.2; `harden-redteam.md` D-12/13/24; `harden-product.md` §D7 |
| §8 Anti-gaming & security | `product-spec.md` §9; `harden-redteam.md` D-02–D-39 (decision register) |
| §9 Pricing | `harden-business.md` §1; `product-spec.md` §12; `harden-product.md` §§B8, C1, D3–D4 |
| §10 Integrations | `integrations.md` (all); `product-spec.md` §10.1; `harden-buildops.md` §1 #5/#7 |
| §11 Build plan | `harden-buildops.md` §§1–3, 7; `build-plan.md` §§2–3 (as re-estimated) |
| §12 Operations | `harden-buildops.md` §§5–6; `harden-product.md` §D6; `build-plan.md` §2.4–2.5 |
| §13 Legal | `harden-legal.md` (all); `portability.md` §3 |
| §14 Pilot | `build-plan.md` §3; `harden-buildops.md` §4; `harden-business.md` §2.3 |
| §15 Financial model | `harden-business.md` §§1, 5; `build-plan.md` §4 (recomputed per §17 R7/R8) |
| §16 GTM & expansion | `harden-business.md` §§2–4; `integrations.md` §4 |
| §17 Reconciliations | All files, cross-checked |
| §18 Change control | `harden-buildops.md` §§0, 3.4 + Ali's "no changes later" instruction |
| §19 Launch gates | `harden-legal.md` §9; `harden-buildops.md` §9 (merged, deduplicated) |
| §20 Ali's gates | `harden-buildops.md` §§1, 9; `domain-names.md` §5; `harden-legal.md` §§0.2, 9 |
| Appendix A | `harden-legal.md` §10 (verbatim questions) |

*End of frozen plan v1.0 — 18 November 2026.*
