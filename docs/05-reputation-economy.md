# 5. Reputation economy

Reputation is the backbone of GBlock. It replaces money as the thing that
unlocks access, and it is the mechanism that keeps the network honest. This
page explains how reputation is measured, how it grows, and what it unlocks.

---

## The two units: Volume and Power

GBlock reputation has two units. They do different things and you need to
understand both.

### Volume

**Volume is your long-term reputation.**

- It is an **append-only ledger**: it only grows, it never resets, and it is
  never spent on productive actions.
- Volume determines your **Reputation Tier**, which sets your reward rate and
  your Power recharge speed.
- Volume is earned through responsible conduct: successful guarantees,
  well-maintained blocks, contributions to the network, and (where applicable)
  referral outcomes.
- The single most important rule: **you cannot buy Volume.** It is only earned.

### Power

**Power is your operational capacity.**

- Power is what you spend to take productive actions that grow the network:
  sending invitations and issuing guarantees.
- Each invitation reserves 10 Power. Each guarantee reserves 10 Power.
- Reserved Power returns when the invitation activates or expires, or when the
  guarantee's probation completes.
- Your Power ceiling is `power_max = max(Volume, status_floor)`. This means
  earning Volume raises your Power ceiling, and so does qualifying for a higher
  status.

Think of it this way: Volume is your track record, Power is the working budget
that track record lets you deploy.

---

## The Canonical Tier Catalog

Reputation Tier is derived from Volume. The canonical catalog
(`tier-catalog-2026-07-v1`) is:

| Tier | Volume range | Reward rate | Power recharge time |
|---|---|---|---|
| **Verified** | 0 - 49 | 10% | 168 hours |
| **Core** | 50 - 149 | 17.5% | 120 hours |
| **Partner** | 150 - 349 | 20% | 72 hours |
| **Principal** | 350 - 999 | 25% | 24 hours |
| **Vanguard** | 1000+ | 25% | 12 hours |

### How to read the catalog

- **Reward rate** is the share of confirmed non-transactional TECH HY revenue
  allocated to the member when a rewardable event occurs. Higher tiers earn a
  larger share. Rewards are never paid from transaction volume, because GBlock
  does not settle transactions.
- **Power recharge time** is how long it takes a unit of spent Power to return.
  At Verified tier, a unit takes a week to recharge; at Vanguard, half a day.
  Higher tiers can invite and guarantee far more often.

### The two "Verified" labels

Be careful with the word _Verified_:

- A **Verified Trust Tier** means you passed KYC (identity assurance).
- A **Verified Reputation Tier** means you have 0-49 Volume (you are at the
  start of your reputation journey).

They are independent. A KYC-verified member with little activity is Verified
trust tier and Verified reputation tier. A long-tenured anonymous member could
be Vanguard reputation tier while still Anonymous trust tier. Always check the
context.

---

## How Power is spent and returned

Two productive actions reserve Power.

### Invitations

- You reserve **10 Power** when you send an invitation.
- The Power returns when the invitation **activates** (the recipient onboards)
  or **expires** (they never used the magic link).
- If the invitee misbehaves, you may face reputation impact beyond the Power
  reserve. This is why you should only invite people you can stand behind.

### Guarantees

- You reserve **10 Power** when you accept a guarantee request.
- The Power returns when the ward's **probation completes** successfully.
- If the ward violates trust during probation, both of you are penalized.
  Three or more violations lead to revocation of the guarantee.

Because Power is reserved (not destroyed), taking a productive action does not
permanently shrink your capacity. It temporarily lowers your available Power
until the action resolves. As you climb tiers, Power recharges faster, so your
effective throughput grows.

---

## How Volume grows

Volume is an append-only ledger of positive contributions. The exact accrual
events are governed by operator policy, but the categories are stable:

- **Successful guarantees.** When a ward completes probation in good standing,
  the guarantor may receive a Volume bonus.
- **Well-maintained blocks.** Active, fresh, accurately described blocks
  contribute to seller reputation.
- **Referral outcomes.** When an invitee contributes positively to the network,
  the inviter's referral attribution can translate into Volume.
- **Sustained good conduct.** Long-term participation without violations is
  recognized.

Your accrual rate is multiplied by your Trust Tier and 2FA status:

| Trust Tier | Base rate | With 2FA |
|---|---|---|
| Anonymous | 1.0x | 1.1x |
| Vouched | 1.0x | 1.1x |
| Verified | 1.2x | **1.3x** |

This is why KYC matters even for reputation growth. A Verified member earns
reputation 20% faster than an Anonymous member at the same level of activity,
and 30% faster with 2FA enabled.

---

## What reputation unlocks

Reputation is not a vanity score. It translates directly into capability.

| Capability | Driver |
|---|---|
| Higher reward rate on non-transactional revenue | Reputation Tier |
| Faster Power recharge, so more invites and guarantees per period | Reputation Tier |
| Shorter operator review SLA | Trust Tier (Verified at 24h, Vouched at 48h, Anonymous at 72h) |
| Higher reputation accrual rate | Trust Tier + 2FA |
| Eligibility to act as guarantor on the Vouched path | Trust Tier (Verified only) |
| Ability to place sale blocks without a guarantor | Trust Tier (Verified only) |
| Primary-market listing eligibility | Trust Tier (Verified) + KYB + project KYC |
| Higher simultaneous active block limit | Trust Tier (0 / 1 / 3) |

Notice that some capabilities are driven by **Trust Tier** (identity assurance)
and others by **Reputation Tier** (accumulated conduct). They work together.
A Verified member with Vanguard-tier Volume has the best of both: full market
access, the highest reward rate, the fastest recharge, and the shortest SLA.

---

## Common misconceptions

**"I can pay to skip tiers."**
No. Volume cannot be purchased. The only way to climb tiers is to accumulate
reputation through conduct over time.

**"Power is spent and gone."**
No. Power is reserved for the duration of an action and returns when the action
resolves. Your ceiling grows with Volume and status.

**"A higher Reputation Tier lets me place blocks."**
Not by itself. Block placement is gated by **Trust Tier** (Vouched or
Verified), not Reputation Tier. A Vanguard-tier Anonymous member still cannot
place a block.

**"Rewards come from deal volume."**
No. GBlock does not settle transactions. Rewards are paid only from confirmed
non-transactional TECH HY revenue.

---

## Where to go next

- **How the tiers interact with access:** [User roles and statuses](02-user-roles-and-statuses.md)
- **What the cabinet shows you about your reputation:** [Platform tour - Reputation](06-platform-tour.md#reputation)
- **KYC, 2FA, and the security behind all of this:** [Trust and safety](07-trust-and-safety.md)
