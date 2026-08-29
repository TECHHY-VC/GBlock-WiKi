# 8. Glossary

Plain-language definitions of the terms used across GBlock. Terms are grouped
by theme to make them easier to scan.

---

## Membership and identity

**Registered**
The base status of anyone who arrives via magic link, invitation, or a
member's Data Room link. Starts with the welcome grant (30 reputation, or 40
plus a vouch gift via invitation). Can apply for other statuses. Cannot see
dealflow or place blocks on its own.

**Welcome Grant**
The starting reputation every new member receives: 30, or 40 plus one vouch
gift when the registration came through an invitation. The inviter's stake is
restored on activation.

**Ambassador**
The default starting role, also available by open self-application. Grants the
right to send invitations and earn referral rewards. Does **not** grant
dealflow access.

**Resident**
A status for market participants. Reached only through the **waitlist**, by
collecting two vouches from KYC-verified members (at least one from a
Resident). Grants dealflow access, the right to place blocks, mediated
introductions, and the right to vouch others into Resident. Does **not** grant
referral rewards by itself.

**Ambassador-Resident**
A member who holds both Ambassador and Resident. Has the full combined rights of
both. Not a separate application.

**Founder Functions**
A silent, lifelong extension of your account — payment account (top-ups,
scoring purchases) and Data Rooms. Activated automatically when you create
your first Data Room. No badge, no application. _Rolling out._

**Waitlist**
The only path to Resident status, open to every registered member who has
completed KYC, including Ambassadors.

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
A Trust Tier reached by collecting at least two active guarantees from Verified
members (a minimum threshold, not a cap — guarantors are unlimited). Grants
full secondary-market access, including sale block creation.

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
Verified, Core, Principal, Partner, Vanguard (750+, no ceiling). Determines
reward rate and Power recharge speed.

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

## Guarantees, vouches, and probation

**Guarantee**
An act where a Verified member vouches for another member on the Vouched trust
path. Reserves 10 Power as collateral. Starts a probation period.

**Guarantor**
The member who issues a guarantee. Shares accountability for the ward's
conduct during probation.

**Ward**
The member who receives a guarantee and enters probation.

**Vouch**
A backing on the Resident path, delivered through the waitlist. Credits +10
reputation to the candidate and +5 to the voucher, and stakes 10 of the
voucher's Volume capacity. The first vouch of a candidate can come from any
KYC-approved member; the decisive second vouch must come from a KYC-verified
Resident. A member's vouch limit is their Volume capacity divided by ten
(rounded down).

**Rework**
The withdrawal of a vouch or guarantee because the backed member violated
trust. The staked capacity is not returned; reputation is clawed back with an
additional penalty; repeated reworks trigger operator review.

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
report. A Data Room belongs to the **company**: if company ownership changes,
the room follows the company.

**Archive (Data Room)**
A soft close. Investors keep read access; the room does **not** free its slot.
Only "delete permanently" removes documents, revokes grants, and frees the
room's slot.

**Listing State**
A Data Room's publication status in the public project catalog. Listed only
with a valid scoring and a completed company profile; an expired scoring moves
the room out of the catalog (with an "expired" placeholder) while the room
keeps working for existing grantees.

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
Documents never leave the provider. Grants the Verified Trust Tier. One
identity verifies exactly one active account; a duplicate identity is
declined, not merged.

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

## Balances and payouts

**Reward Balance**
The balance where referral rewards land, credited in a monthly batch on the
1st of the month. Withdrawals happen through payout requests only.

**Payment Balance**
The balance used for platform purchases (such as project scoring), funded by
card top-ups. Rewards can be moved into it (a 3% fee applies); moving it back
to rewards is an operator-reviewed request.

**Payout Request**
The only way to withdraw rewards: a reviewed request to the operator.
Minimum $50, USDT (BEP-20) destination, $150 per-request cap without KYC.
See [Payouts and rewards](10-payouts-and-rewards.md).

**Business-Day SLA**
Payout clocks measured in working days: the operator responds to a payout
request within 1 business day, and approved payouts are sent within 3
business days.

**Transaction Hash (tx-hash)**
The on-chain identifier of a sent payout, delivered to you in the completion
notification so you can verify the transfer.

**Reconcile**
The daily automated check that reward balances on accounts never exceed
accrued-minus-withdrawn rewards. A discrepancy alerts the operator before any
payout moves.

---

## Deal communication

**Contact Verification Check**
The automated check on deal-thread messages for direct contact data (emails,
phones, messenger handles, external messenger links).

**Quarantine**
The state of a message held by the contact verification check: the recipient
sees a neutral cover, the sender sees their own text and its status, and the
operator can review everything. Quarantine applies until the deal contract is
signed; afterwards, exchanging contacts is legitimate. _Rolling out._

**Silent Referral**
A member who registered after clicking a link to your Data Room. Attributed
to you like any other referral (last touch, all channels), with no reputation,
vouch, or accountability obligations for either side. See
[Silent Data Room referrals](11-silent-dr-referral.md).

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
Verified 24h, Vouched 48h, Anonymous 72h. Payout requests use a separate
business-day SLA (see above).

---

## Where to go next

- **The full role and access model:** [User roles and statuses](02-user-roles-and-statuses.md)
- **Every flow that uses these terms:** [User journeys](04-user-journeys.md)
- **The numbers behind Volume and Power:** [Reputation economy](05-reputation-economy.md)
- **Balances and payouts in detail:** [Payouts and rewards](10-payouts-and-rewards.md)
