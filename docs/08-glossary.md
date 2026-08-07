# 8. Glossary

Plain-language definitions of the terms used across GBlock. Terms are grouped
by theme to make them easier to scan.

---

## Membership and identity

**Registered**
The base status of anyone who arrives via magic link or invitation. Volume 0,
Power 0. Can apply for other statuses. Cannot see dealflow or place blocks on
its own.

**Ambassador**
A status for community builders. Grants the right to send invitations and earn
referral rewards. Starting floor Volume / Power 30 / 30. Does **not** grant
dealflow access.

**Resident**
A status for market participants. Grants dealflow access, the right to place
blocks, mediated introductions, and the right to guarantee others. Starting
floor Volume / Power 10 / 10. Does **not** grant referral rewards.

**Ambassador-Resident**
A member who holds both Ambassador and Resident. Has the full combined rights of
both. Not a separate application.

**Founding Grant**
An operator-granted path to Resident status, used to bootstrap the network.
Limited to 50 grants or until 100 active Residents exist. Founding Residents
must pass KYC and serve a 14-day probation.

**Canonical Identity**
The rule that one real person maps to one `person_id`, one member account, and
one GBlock profile. Buyer and Seller are modes inside the same account, not
separate registrations.

---

## Trust Tier

**Trust Tier**
An independent axis from Status and Reputation Tier. Determines market access
based on identity assurance. Values: Anonymous, Vouched, Verified.

**Anonymous**
The default Trust Tier. Can view dealflow and act as a buyer (with one
guarantor, any tier). **Cannot create sale blocks.**

**Vouched**
A Trust Tier reached by collecting two or more active guarantees from Verified
members. Grants full secondary-market access, including sale block creation.

**Verified**
A Trust Tier reached by completing KYC. Grants full access with no guarantor
requirement, primary-listing eligibility, faster operator SLA, and a 1.2x
reputation accrual rate (1.3x with 2FA).

> Note: _Verified_ appears as both a Trust Tier (KYC passed) and a Reputation
> Tier (0-49 Volume). They are different. Always check the context.

---

## Reputation

**Volume**
Long-term reputation. An append-only ledger that only grows. Determines
Reputation Tier. Cannot be bought.

**Power**
Operational capacity. Spent on productive actions (invitations, guarantees) and
recharged over time. Ceiling is `max(Volume, status_floor)`.

**Reputation Tier**
A tier derived from Volume. Canonical catalog (`tier-catalog-2026-07-v1`):
Verified, Core, Partner, Principal, Vanguard. Determines reward rate and Power
recharge speed.

**Canonical Tier Catalog**
The authoritative mapping of Volume ranges to tiers, reward rates, and
recharge schedules. See [Reputation economy](05-reputation-economy.md).

**Reward Rate**
The share of confirmed non-transactional TECH HY revenue allocated to a member
when a rewardable event occurs. Higher Reputation Tiers earn a higher rate.
Never paid from transaction volume.

**Accrual Rate**
The multiplier applied to reputation earned from activity. Set by Trust Tier
(1.0x / 1.0x / 1.2x) and raised by 0.1x when 2FA is enabled.

---

## Guarantees and probation

**Guarantee**
An act where an active Resident (or Verified member, on the Vouched path)
vouches for another member. Reserves 10 Power as collateral. Starts a
probation period.

**Guarantor**
The member who issues a guarantee. Shares accountability for the ward's
conduct during probation.

**Ward**
The member who receives a guarantee and enters probation.

**Probation**
The supervised observation period after a guarantee activates. Standard 30
days, Founding 14 days, Extended operator-set. Violations during probation
penalize both ward and guarantor.

**Trust Gate**
The check that determines whether a member can place a sale block based on
their Trust Tier. Anonymous is blocked; Vouched is allowed with two Verified
guarantors and 24-hour freshness; Verified is allowed with no guarantors and
72-hour freshness.

---

## Market and dealflow

**Block (Sale Block)**
A private package of assets or an opportunity placed by a member. Explicitly
**not** a blockchain or crypto concept.

**Dealflow**
The set of active sale blocks visible to members who have dealflow rights.

**Buyer**
A mode inside a member account. Browses dealflow, requests access, expresses
interest, enters deal threads.

**Seller**
A mode inside a member account. Places and manages sale blocks.

**Mediated Introduction**
The governed connection between a buyer and a seller after access is approved.
GBlock never hands out direct seller contact.

**Deal Thread**
The private in-platform channel between a buyer and a seller in a mediated
introduction. Where the conversation happens. Not a transaction channel.

**Freshness**
The window during which an active block is current before it must be renewed.
Verified sellers get 72 hours; Vouched sellers get 24 hours. After the window,
the block moves through `stale_warning` to `expired`.

**Data Room (VDR)**
A member-controlled Virtual Data Room for a project. Owner uploads diligence
documents, grants and revokes access, toggles download, and views the scoring
report.

**Scoring Report**
A deterministic evaluation of a project on two axes: Potential (0-150) and
Readiness (0-150).

**Primary Market**
The surface for primary raises. Listing requires Verified Trust Tier, KYB, and
project-level KYC.

**Secondary Market**
The surface for blocks of existing assets (secondary blocks, pre-IPO, OTC,
M&A). Access depends on Trust Tier.

---

## Security

**Magic Link**
A signed, single-use authentication link sent to your email. Expires after 30
minutes. The login response is generic to prevent email enumeration.

**Re-authentication**
A fresh magic-link confirmation within the last 10 minutes, required for
sensitive actions (creating blocks, accepting guarantees, granting Data Room
access, withdrawing from deal threads, managing 2FA).

**KYC**
Know Your Customer. Identity verification performed by an external provider.
Documents never leave the provider. Grants the Verified Trust Tier.

**KYB**
Know Your Business. Business-level verification required for primary-market
listings.

**2FA (TOTP)**
Voluntary two-factor authentication using a Time-based One-Time Password app.
Adds a 0.1x reputation accrual bonus and strengthens account security.

**Device Alert**
An email sent when GBlock detects a login from an unrecognized device.

**Standing**
A member's current good-standing or restricted status, visible on the cabinet
home.

---

## Operator and governance

**Operator**
The internal role that runs GBlock: reviewing blocks, moderating complaints,
running eligibility checks, and granting founding status.

**Complaint**
A member-submitted report of misconduct or quality issues. Evidence and
operator notes stay internal; reporter identity is not exposed to the subject.

**SLA (Operator Review)**
The target time for the operator to review a submission. Set by Trust Tier:
Verified 24h, Vouched 48h, Anonymous 72h.

---

## Where to go next

- **The full role and access model:** [User roles and statuses](02-user-roles-and-statuses.md)
- **Every flow that uses these terms:** [User journeys](04-user-journeys.md)
- **The numbers behind Volume and Power:** [Reputation economy](05-reputation-economy.md)
