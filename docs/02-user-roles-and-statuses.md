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

### The welcome grant

Every new member starts with the same welcome grant:

- **30** starting reputation (Volume and Power) when you register directly.
- **40** starting reputation plus **1 vouch gift** when you register through a
  member's invitation. The member who invited you gets their staked Power back
  and restores the reputation they staked.

Reputation only grows from there. See [Reputation economy](05-reputation-economy.md).

### The statuses

| Status | How you get it | What it grants |
|---|---|---|
| **Registered** | Arrive via magic link, invitation, or a member's Data Room link | Basic access with the welcome grant. Can apply for other statuses. Cannot see dealflow or place blocks. |
| **Ambassador** | The default starting role, or open self-application + accepting the Ambassador Terms | The right to send invitations and earn referral rewards. **Does not grant dealflow.** |
| **Resident** | The waitlist: collect **two vouches from KYC-verified members, at least one from a Resident** | Access to dealflow, placing blocks, mediated introductions, and the right to vouch others into Resident. Does not grant referral rewards. |
| **Ambassador-Resident** | Hold both Ambassador and Resident | The full combined rights of both. |

### Reading the table

- **Ambassador is the default starting role.** Every new member starts as an
  Ambassador; you can also apply openly from the public site. Ambassador status
  is about community growth (invites, referral rewards).
- **Resident is about market participation** (dealflow, blocks, vouching).
  Neither status implies the other, and Resident is reachable **only through
  the waitlist** — the waitlist is open to every registered member who has
  completed KYC, including Ambassadors.
- **Ambassador-Resident** is not a separate application. It is what happens when
  one member qualifies for and holds both.
- **Founder functions** are not a status. They are a silent extension of your
  account, described below.

---

## Axis 2 — Trust Tier

Trust Tier is an **independent axis from Status**. It exists to let members
participate at the level of identity assurance they are comfortable with, from
fully anonymous to KYC-verified.

| Trust Tier | How you reach it | What it unlocks |
|---|---|---|
| **Anonymous** | Default for everyone | View dealflow, act as a buyer (requires one guarantor, any tier). **Cannot create sale blocks.** |
| **Vouched** | At least two active guarantees where **both** guarantors are Verified | Full secondary-market access: create sale blocks, participate in deal threads. |
| **Verified** | Pass KYC | Full access with no guarantor requirement, plus primary-listing eligibility and faster operator service levels. |

Guarantors are **not limited to two people**. Two Verified guarantees is the
minimum threshold for the Vouched path, not a cap — you can collect more.

### Why Trust Tier matters even if you are a Resident

A Resident who is still Anonymous **cannot place sale blocks**. They can browse
dealflow and act as a buyer (with one guarantor), but to become a seller they
must either:

- reach **Vouched** by collecting guarantees from Verified members (two is the
  minimum), or
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
- The ability to give vouches on the Resident path (see below).
- A 1.2x reputation accrual rate (1.3x with 2FA enabled).
- The faster 24-hour operator review SLA.

You are never forced to reveal your identity to the network. Anonymous members
can accumulate Volume and act as buyers indefinitely.

One identity can be verified only once: if the same person is already an
active verified member, a new KYC attempt with that identity is declined
rather than merged. See
[Trust and safety - KYC and identity](07-trust-and-safety.md#kyc-and-identity).

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
| Give a vouch (Resident path) | No | First vouch only (KYC-approved members) | First vouch, plus the decisive vouch if you are a Resident |
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
- On the Resident path, **any KYC-approved member can give a first vouch**, but
  the decisive second vouch — the one that completes a waitlist candidate's
  Resident status — must come from a **KYC-verified Resident**.
- How many vouches you can give is derived from your Volume, not from a fixed
  per-tier cap: your limit is your Volume capacity divided by ten (rounded
  down). See [Reputation economy](05-reputation-economy.md#vouches).
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
| **Core** | 50 - 149 | 13% | 120 hours |
| **Principal** | 150 - 349 | 17% | 72 hours |
| **Partner** | 350 - 749 | 20% | 24 hours |
| **Vanguard** | 750+ | 25% | 12 hours |

The Vanguard tier has **no Volume ceiling**: the ladder keeps climbing, and
25% is the maximum direct reward rate.

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

## Founder functions (rolling out)

Founder is **not a role you apply for** and not a badge you wear. It is a
silent extension of your account that unlocks the selling side of the platform:
a payment account (top-ups and scoring purchases) and Data Rooms for your
company.

How it works:

- **Activation is automatic and silent.** Creating your first Data Room
  switches the functions on. There is no application, no fee, and no waiting
  period. The Data Room creation flow and the scoring form share one dataset,
  so creating a room also prepares a scoring draft for the same company.
- **It is lifelong.** The functions never expire and are not removed for
  inactivity.
- **It is invisible.** You will not see the word "Founder" anywhere in the
  cabinet. The functions simply appear.
- **It only unlocks the input side.** You can top up your payment balance and
  purchase project scoring. It does not by itself unlock withdrawals — payouts
  follow the model in [Payouts and rewards](10-payouts-and-rewards.md).
- **It does not change your reputation.** Activating the functions neither
  adds nor removes reputation, and your welcome grant is unaffected.

In the cabinet, the wallet's payment block is visible to everyone; if the
founder functions are not active yet, the top-up button explains what
activates them (create a Data Room).

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

- **Status:** Registered, with the invite welcome grant — 40 reputation and
  1 vouch gift (a direct registration would start at 30).
- **Trust Tier:** Anonymous (no KYC, no guarantees).
- **Reputation Tier:** Verified (0-49 Volume).

What can you do? Browse dealflow, no (that needs Resident). Place a sale block,
no. Send invitations, yes — every member starts in the Ambassador role, and
your invitations carry referral rewards.

To unlock more, you would pursue one or more of:

1. **Become a Resident** by joining the waitlist and collecting two vouches
   from KYC-verified members, at least one from a Resident. Your invitation
   vouch gift counts as a real vouch. This opens dealflow rights, block
   placement, and vouching.
2. **Reach Vouched** by collecting guarantees from Verified members (two is the
   minimum). This lets you place sale blocks.
3. **Reach Verified** by completing KYC. This removes the guarantor requirement
   for blocks, lets you vouch others, raises your accrual rate to 1.2x, and
   puts you in the 24-hour operator SLA queue.
4. **Activate founder functions** by creating a Data Room for your company.
   This switches on top-ups and scoring purchases.

Each of these is independent. You can sequence them in whatever order matches
your goals.

---

## Where to go next

- **How to actually get invited or admitted:** [Getting access](03-getting-access.md)
- **The end-to-end flows:** [User journeys](04-user-journeys.md)
- **The numbers behind Volume and Power:** [Reputation economy](05-reputation-economy.md)
- **Every term used on this page, defined:** [Glossary](08-glossary.md)
