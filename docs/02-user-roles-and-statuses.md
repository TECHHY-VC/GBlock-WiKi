# 2. User roles and statuses

GBlock does not have a single "user role." Membership is described by **three
independent axes** that combine to determine what you can do. Confusing them is
the most common newcomer mistake, so this page is the longest in the wiki.

> **Read this page carefully.** Almost every question about "why can't I do X"
> is answered by which axis is blocking you.

---

## The three axes at a glance

| Axis | Question it answers | Possible values |
|---|---|---|
| **Status** | _How did you become a member, and what base rights do you have?_ | Registered, Ambassador, Resident, Ambassador-Resident |
| **Trust Tier** | _How proven is your identity, and what market actions does that unlock?_ | Anonymous, Vouched, Verified |
| **Reputation Tier** | _How much long-term reputation have you accumulated, and what rewards and service levels come with it?_ | Verified, Core, Partner, Principal, Vanguard |

The three axes are independent. A Resident can still be Anonymous (no KYC). A
Vanguard-tier member can be Vouched rather than Verified. Your access at any
moment is the **intersection** of all three.

---

## Axis 1 — Status

Status defines how you entered GBlock and the baseline rights you received.
Statuses are **stackable**: one person can hold several at once.

| Status | How you get it | Starting floor (Volume / Power) | What it grants |
|---|---|---|---|
| **Registered** | Arrive via magic link or invitation | 0 / 0 | Basic access. Can apply for other statuses. Cannot see dealflow or place blocks. |
| **Ambassador** | Open self-application + accept Ambassador Terms + meet eligibility | 30 / 30 | The right to send invitations and earn referral rewards. **Does not grant dealflow.** |
| **Resident** | A guarantee from an active Resident, or a founding operator grant | 10 / 10 | Access to dealflow, placing blocks, mediated introductions, and the right to guarantee others. Does not grant referral rewards. |
| **Ambassador-Resident** | Hold both Ambassador and Resident | max(current, 30) | The full combined rights of both. |

### Reading the table

- **Volume / Power floor** is the starting point, not a cap. Volume only grows
  from there through accrued reputation. See
  [Reputation economy](05-reputation-economy.md).
- **Ambassador and Resident are different doors into different rights.**
  Ambassador is about community growth (invites, referral rewards). Resident is
  about market participation (dealflow, blocks, guarantees). Neither implies the
  other.
- **Ambassador-Resident** is not a separate application. It is what happens when
  one member qualifies for and holds both.

---

## Axis 2 — Trust Tier

Trust Tier is an **independent axis from Status**. It exists to let members
participate at the level of identity assurance they are comfortable with, from
fully anonymous to KYC-verified.

| Trust Tier | How you reach it | What it unlocks |
|---|---|---|
| **Anonymous** | Default for everyone | View dealflow, act as a buyer (requires one guarantor, any tier). **Cannot create sale blocks.** |
| **Vouched** | Two or more active guarantees where **both** guarantors are Verified | Full secondary-market access: create sale blocks, participate in deal threads. |
| **Verified** | Pass KYC | Full access with no guarantor requirement, plus primary-listing eligibility and faster operator service levels. |

### Why Trust Tier matters even if you are a Resident

A Resident who is still Anonymous **cannot place sale blocks**. They can browse
dealflow and act as a buyer (with one guarantor), but to become a seller they
must either:

- reach **Vouched** by collecting two guarantees from Verified members, or
- reach **Verified** by completing KYC.

This is the most common point of friction. If you are a Resident and the
"create block" action is unavailable, check your Trust Tier first.

### KYC and anonymity

KYC is performed at an external provider. Your documents never leave the
provider, and GBlock never sees or stores them. Completing KYC upgrades you to
the **Verified** trust tier and is the cleanest path to full market access,
including:

- No guarantor requirement for sale blocks.
- A 72-hour block freshness window (vs. 24 hours for Vouched).
- The ability to serve as a guarantor on the Vouched path.
- A 1.2x reputation accrual rate (1.3x with 2FA enabled).
- The faster 24-hour operator review SLA.

You are never forced to reveal your identity to the network. Anonymous members
can accumulate Volume and act as buyers indefinitely.

---

## The full access matrix

This is the single most important table in the wiki. It shows what each Trust
Tier permits, and the conditions that apply.

| Action | Anonymous | Vouched | Verified |
|---|---|---|---|
| View dealflow | Yes | Yes | Yes |
| Express buyer interest | Yes (needs 1 guarantor, any tier) | Yes | Yes |
| Create a sale block | **No** | Yes (2 Verified guarantors, 24h freshness) | Yes (0 guarantors, 72h freshness) |
| Act as guarantor (Vouched path) | No | No | **Yes, exclusively** |
| Act as guarantor (Resident path) | No | Yes (1 max) | Yes (per tier capacity) |
| Primary-market listing | No | No | Yes (requires KYB + project KYC) |
| Maximum simultaneous blocks | 0 | 1 | 3 |
| Operator review SLA | 72h | 48h | 24h |
| Reputation accrual rate | 1.0x | 1.0x | **1.2x** |
| Reputation accrual with 2FA | 1.1x | 1.1x | **1.3x** |

Notes:

- "Freshness" is how long a block stays visible before it must be renewed or it
  goes stale. Verified sellers get a longer window because their identity is
  already proven.
- "Operator review SLA" is the target time for the GBlock operator to review
  your submission (a block, an access request, a complaint). Higher trust buys
  you a faster queue.
- 2FA is voluntary at every tier and adds a 0.1x accrual bonus on top of your
  base rate. See [Trust and safety](07-trust-and-safety.md#two-factor-authentication).

---

## Axis 3 — Reputation Tier

Reputation Tier is derived from your **Volume** (long-term reputation). It
determines reward rates and how fast your Power recharges. Volume is an
append-only ledger: it only grows, never resets, and is never "spent" on
productive actions.

The canonical tier catalog (`tier-catalog-2026-07-v1`):

| Tier | Volume range | Reward rate | Power recharge time |
|---|---|---|---|
| **Verified** | 0 - 49 | 10% | 168 hours |
| **Core** | 50 - 149 | 17.5% | 120 hours |
| **Partner** | 150 - 349 | 20% | 72 hours |
| **Principal** | 350 - 999 | 25% | 24 hours |
| **Vanguard** | 1000+ | 25% | 12 hours |

How to read this:

- **Reward rate** is the share of confirmed non-transactional TECH HY revenue
  allocated to the member when a rewardable event occurs (for example, a
  successful referral). Higher tiers earn a larger share.
- **Power recharge** is how long it takes a unit of spent Power to return.
  Higher tiers recover operational capacity faster, so they can invite and
  guarantee more often.
- The tier name **Verified** appears in both Axis 2 (Trust Tier) and Axis 3
  (Reputation Tier). They are different things. A Verified **Trust Tier** means
  you passed KYC. A Verified **Reputation Tier** means you have 0-49 Volume.
  Always check the context when you see the word.

For the mechanics behind Volume and Power, see
[Reputation economy](05-reputation-economy.md).

---

## Special admission: the founding grant

There is a third admission path alongside invitation and self-application: the
**founding operator grant**. It exists to bootstrap the network with a first
cohort of trusted Residents who can then guarantee others.

- Granted by the operator with a recorded reason and evidence.
- **Quota:** 50 founding grants, or until 100 active Residents exist.
- Founding Residents **must pass KYC**, so they enter as Verified Trust Tier.
- They serve a **14-day probation** during which they cannot issue guarantees.
- After probation they form the initial pool of Verified guarantors who can
  vouch others into Vouched status.

This path is not openly requestable. It is an operator decision tied to the
early growth phase of the club.

---

## Probation

Probation is a supervised observation period that starts when a guarantee is
activated. It exists so that a guarantor's reputation is genuinely on the line
for the person they vouched for.

| Probation type | Duration | When it applies |
|---|---|---|
| Standard | 30 days | Default for a normal guarantee. |
| Founding | 14 days | For founding-grant Residents. |
| Extended | Set by operator | Applied in response to conduct concerns. |

During probation:

- The guarantor's 10 Power is held as collateral and is not available for other
  actions.
- If the ward commits trust violations, both the ward and the guarantor are
  penalized.
- If the ward reaches the end of probation in good standing, the guarantor's
  Power returns and a Volume bonus may be awarded.
- Three or more violations by a ward lead to revocation of the guarantee and
  reputation impact for the guarantor.

Probation is one of the reasons GBlock can stay invitation-only without a
centralized gatekeeper on every action: the network polices itself through
shared accountability.

---

## Identity: one person, one account

GBlock enforces a single canonical identity per real person.

- One real person maps to one `person_id`, which maps to one member account,
  which can hold multiple compatible statuses.
- The identity chain is `BotContact → Member Account → GBlock Profile`.
- Buyer and Seller are **modes inside a single account**, not separate
  accounts. You do not register twice to do both.

This is what makes shared accountability enforceable. If a member misbehaves,
the reputation cost attaches to the real person, not a throwaway handle.

---

## Putting it together: a worked example

Suppose you are invited by a Resident, accept the magic link, and complete your
profile. At that moment:

- **Status:** Registered (Volume 0, Power 0).
- **Trust Tier:** Anonymous (no KYC, no guarantees).
- **Reputation Tier:** Verified (0-49 Volume).

What can you do? Browse dealflow, yes. Express buyer interest, yes, with one
guarantor. Place a sale block, no. Send invitations, no (you are not an
Ambassador).

To unlock more, you would pursue one or more of:

1. **Become a Resident** by getting a guarantee from an active Resident. This
   opens dealflow rights, block placement, and guarantees.
2. **Become an Ambassador** by self-applying and accepting the Ambassador Terms.
   This opens invitations and referral rewards.
3. **Reach Vouched** by collecting two guarantees from Verified members. This
   lets you place sale blocks.
4. **Reach Verified** by completing KYC. This removes the guarantor requirement
   for blocks, raises your accrual rate to 1.2x, and puts you in the 24-hour
   operator SLA queue.

Each of these is independent. You can sequence them in whatever order matches
your goals.

---

## Where to go next

- **How to actually get invited or admitted:** [Getting access](03-getting-access.md)
- **The end-to-end flows:** [User journeys](04-user-journeys.md)
- **The numbers behind Volume and Power:** [Reputation economy](05-reputation-economy.md)
- **Every term used on this page, defined:** [Glossary](08-glossary.md)
