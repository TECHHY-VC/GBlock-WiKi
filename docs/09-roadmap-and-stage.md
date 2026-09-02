# 9. Roadmap and stage

GBlock is a staged product. This page describes the current stage, the
roadmap, what is live today, what is planned, and what is explicitly out of
scope. It exists so members and applicants can calibrate their expectations.

---

## Current stage: PRE_MARKET_INTERNAL_UAT

GBlock is in **PRE_MARKET_INTERNAL_UAT** (pre-market internal user acceptance
testing). This is a controlled, invitation-only, pre-market phase.

What this means in practice:

- The platform is **invitation-only**. There is no open public registration.
- The product is being validated against its specification with a controlled
  group of members.
- Some functionality described in this wiki is live; some is planned and
  marked as such.
- Deployment to this stage does **not** imply market release, open onboarding,
  or live commercial traffic.

If you are reading about GBlock from outside, treat the live experience as
real but evolving. Features marked as _planned_ or _roadmap_ in this wiki are
not yet available to members.

---

## Roadmap phases

The GBlock roadmap is organized into five phases.

| Phase | Focus |
|---|---|
| **P0 - Core Platform** | The foundation: identity, magic-link auth, member cabinet, reputation, statuses, guarantees, complaints, 2FA. |
| **P1 - Primary Market Readiness** | KYC/KYB flows, project scoring, data room, primary-market listing eligibility. |
| **P2 - Dealflow and Market Operations** | Sale blocks, dealflow, access requests, deal threads, operator review tooling. |
| **P3 - Growth and Trust Economy** | Referral rewards, tier catalog maturity, ambassador growth, reputation economy tuning. |
| **P4 - Regulated Integrations** | Integrations with regulated counterparties where applicable, subject to jurisdictional limits. |

Phases are sequential in intent but overlapping in execution. P0, P1, and P2
are largely in place today; P3 is maturing; P4 is future work contingent on
external partnerships and regulatory positioning.

---

## What is live

The following are part of the current live experience for members:

- Invitation-based onboarding via magic link, with the welcome grant (30
  starting reputation; 40 plus a vouch gift via invitation).
- Member cabinet: home, profile, interests, reputation, notifications.
- Statuses: Registered, Ambassador, Resident, Ambassador-Resident. Ambassador
  as the default starting role.
- Trust Tiers: Anonymous, Vouched, Verified (via KYC).
- Canonical Tier Catalog and the reputation economy (Volume and Power), with
  the final tier ladder Verified → Core → Principal → Partner → Vanguard at
  rates 10 / 13 / 17 / 20 / 25%.
- Guarantees and probation, including the Trust Gate for sale blocks.
- Sale blocks: draft, submit, review, active, stale, expired, removed,
  rejected, archived.
- Dealflow browsing, access requests, buyer interest.
- Mediated deal threads with automated contact checks on messages.
- Data Room: owner-controlled document storage, access grants, scoring report,
  scoring-expiry placeholders in the project catalog.
- Wallet: reward and payment balances, card top-ups, reward-to-payment
  transfers, monthly reward crediting on the 1st, and daily balance
  reconciliation against the reward ledger.
- **Payouts through operator-reviewed requests.** Self-service withdrawal has
  been removed: payout requests go through the support pipeline (minimum $50,
  USDT BEP-20, $150 per-request cap without KYC) with transaction-hash
  notifications.
- Support tickets to the operator.
- Complaints (safe reporting flow).
- 2FA (TOTP, with accrual bonus).
- Device alerts for unrecognized logins.
- Read-only API (v1).
- **Founder functions as a silent flag.** Automatic activation on first Data
  Room creation or scoring submission, lifelong, no badge — unlocking top-ups
  and scoring purchases, with the locked-wallet hint for everyone else.
- **Data Room limits and the catalog gate.** One reusable free primary-market
  room per member; unlimited rooms with valid scoring (one scoring = one
  room); unlimited secondary-market rooms for KYC-verified Residents; catalog
  listing requires valid scoring plus a completed company profile; the
  permanent-delete vs archive choice with its slot semantics.
- **KYC revocation handling.** A revoked verification archives excess rooms
  while preserving existing grants (grandfathering); new grants stay closed.
- **Silent Data Room referral engine.** Last-touch attribution across Data
  Room links and invites, the ambassador-ladder economics, and the
  founder-facing link metrics in the cabinet.
- **Contact-check quarantine and covers.** Quarantine ends at contract
  signing; recipients see neutral covers, senders see status, the operator
  sees everything.

---

## Rolling out

These are confirmed parts of the product model that are being switched on in
stages. Some members may already see them; not everyone does yet. They are
described throughout this wiki with a _rolling out_ marker.

- **Payout SLA clocks.** The 1-business-day response / 3-business-day payout
  targets as enforced queue metrics.
- **2FA enforcement for all members.**
- **Contact-check extensions.** Broader language matching in the detector
  (transliteration, mixed scripts, slang, obfuscations).
- **Layered document watermarking** (visible + forensic) in Data Rooms.
- **Referral tree and reward history** in the cabinet (the tree itself is
  live; history views are being expanded).

---

## What is planned

The following are in active development or design and are **not** yet live.
They are described here so members know what is coming, but they should not be
relied on today.

- **Silent Data Room referral analytics.** The engine is live (see
  [Silent Data Room referrals](11-silent-dr-referral.md)); deeper analytics
  and reporting continue to expand.
- **Unified Data Room + scoring flow.** One dataset for both: creating a room
  produces a scoring draft for the same company, with shared company fields
  feeding the public catalog card.
- **Self-service Data Room to Primary Market listing.** A flow where a member
  creates a data room from the cabinet, the project is scored automatically,
  and it is listed as a primary-market draft that enters operator eligibility
  review. Investors would then view the public room, express interest, and
  request access.
- **KYC deduplication** as an enforced platform check (duplicate identities
  declined at verification). Revocation handling is already live.
- **Account sleep lifecycle enforcement.** The inactivity model described in
  [Trust and safety](07-trust-and-safety.md) — a warning phase, deactivation
  with unpublishing of public artifacts, then deletion after 30 days of
  inactivity, with founder functions frozen while an account sleeps — is in
  final development and independent verification.
- **API expansion.** The current API is read-only. Broader surface area is
  under consideration, with re-authentication and operator review applied to
  any mutating action.
- **Reputation economy tuning.** As the network grows, accrual events, reward
  rates, and recharge schedules may be adjusted. Changes follow operator
  policy and are versioned (the current catalog is `tier-catalog-2026-07-v1`).

Anything in this section is directional, not committed. Do not make decisions
that depend on these features being available by a specific date.

---

## What is out of scope

These are things GBlock explicitly does not do and does not plan to do. They
are listed to remove ambiguity.

- **On-platform transactional settlement.** GBlock arranges introductions; it
  does not move money or assets.
- **Custody.** GBlock does not hold assets, funds, or securities.
- **Investment advice.** GBlock does not advise on the merits of any
  opportunity. Members do their own diligence.
- **Public marketplace.** GBlock is invitation-only and reputation-governed.
  There is no plan for open public registration into market surfaces.
- **Crypto or token products.** A _block_ is a private package of assets or an
  opportunity, nothing more.
- **Guaranteed returns.** No promise of profit, ever. Any communication
  claiming otherwise is not from GBlock.

---

## Stage-aware reading of this wiki

Because GBlock is in a pre-market stage, treat this wiki as a description of
the member experience at the current stage, not a fixed product contract. When
a feature is described as live, it reflects the current behavior. When a
feature is described as planned, it reflects the direction of travel.

For the canonical product specification, the authoritative source inside TECH
HY is the Unified PRD (v2.0). This wiki is the public-facing companion, not the
internal system of record.

---

## Where to go next

- **Start from the top:** [What is GBlock](01-what-is-gblock.md)
- **Who can do what, today:** [User roles and statuses](02-user-roles-and-statuses.md)
- **The definitions behind every term above:** [Glossary](08-glossary.md)
- **Balances and payouts:** [Payouts and rewards](10-payouts-and-rewards.md)
