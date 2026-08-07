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

- Invitation-based onboarding via magic link.
- Member cabinet: home, profile, interests, reputation, notifications.
- Statuses: Registered, Ambassador, Resident, Ambassador-Resident.
- Trust Tiers: Anonymous, Vouched, Verified (via KYC).
- Canonical Tier Catalog and the reputation economy (Volume and Power).
- Guarantees and probation, including the Trust Gate for sale blocks.
- Sale blocks: draft, submit, review, active, stale, expired, removed,
  rejected, archived.
- Dealflow browsing, access requests, buyer interest.
- Mediated deal threads.
- Data Room: owner-controlled document storage, access grants, scoring report.
- Complaints (safe reporting flow).
- 2FA (voluntary TOTP, with accrual bonus).
- Device alerts for unrecognized logins.
- Read-only API (v1).

---

## What is planned

The following are in active development or design and are **not** yet live.
They are described here so members know what is coming, but they should not be
relied on today.

- **Self-service Data Room to Primary Market listing.** A flow where a member
  creates a data room from the cabinet, the project is scored automatically,
  and it is listed as a primary-market draft that enters operator eligibility
  review. Investors would then view the public room, express interest, and
  request access. This is the most significant in-flight change to the project
  axis.
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
