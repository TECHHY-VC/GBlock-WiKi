# 7. Trust and safety

GBlock's entire design assumes that members behave responsibly because their
reputation is at stake. This page explains the safety mechanisms that make that
assumption enforceable: KYC, re-authentication, probation, complaints,
two-factor authentication, and device alerts.

---

## KYC and identity

KYC (Know Your Customer) is the path to the **Verified** trust tier. It is
performed by an external provider.

- Your documents **never leave the provider**. GBlock does not see or store
  your identity documents.
- A single KYC session can cover both member participation and project listing
  purposes, so you do not repeat the process for each use case.
- Completing KYC grants the Verified trust tier, which unlocks full market
  access without a guarantor, primary-listing eligibility, faster operator
  review, and a higher reputation accrual rate.

You are never forced to complete KYC. Anonymous members can accumulate Volume
and act as buyers indefinitely. KYC is a choice to unlock fuller access and
faster service, not a condition of membership.

For projects, KYB (Know Your Business) and project-level KYC are required for
primary-market listings.

---

## Re-authentication

Some actions are sensitive enough that a recent login is required, even if you
are already in the cabinet. This is **re-authentication**: a fresh magic-link
confirmation within the last 10 minutes.

Actions that require re-authentication:

- Creating a sale block.
- Accepting a guarantee.
- Publishing a primary listing.
- Granting or revoking Data Room access.
- Withdrawing from a deal thread.
- Enabling, verifying, or disabling 2FA.

If you try one of these actions without a recent re-authentication, the
platform prompts you to confirm via a new magic link. This keeps a stolen
session from being enough to take consequential actions on your behalf.

---

## Probation

Probation is the supervised observation period that starts when a guarantee is
activated.

| Type | Duration | Applies to |
|---|---|---|
| Standard | 30 days | A normal guarantee. |
| Founding | 14 days | Founding-grant Residents. |
| Extended | Set by operator | Members under conduct review. |

**During probation:**

- The guarantor's 10 Power is held as collateral.
- The ward is under supervised observation.
- Trust violations by the ward penalize both the ward and the guarantor.

**Outcomes:**

- **Success:** the ward completes probation in good standing. The guarantor's
  Power returns. A Volume bonus may be awarded to the guarantor.
- **Violation:** three or more violations lead to revocation of the guarantee
  and reputation impact for the guarantor.

Probation is why a guarantee is more than a formality. When you vouch for
someone, you are genuinely staking your reputation on their conduct for the
duration of the probation window.

---

## Complaints

The complaint flow lets any member report misconduct or quality issues
securely.

**Complaint types:**

- Abusive behavior.
- Suspicious activity.
- Block quality issue.
- Referral abuse.
- Reputation dispute.
- Marketplace abuse.
- Manual report.

**How it works:**

1. You open **Report** from the cabinet and pick a type.
2. You submit what you can. Evidence and operator notes are stored internally.
3. The operator reviews and may act: warn, restrict, revoke a guarantee, remove
   a block, or adjust reputation.
4. You may receive status updates through notifications.

**What is protected:**

- Evidence and internal operator notes are **never visible to other members**.
- Your identity as the reporter is **not exposed** to the subject of the
  complaint.

The complaint flow is the safety valve for the reputation system. If you see
something wrong, report it. The system is designed to protect you for doing so.

---

## Two-factor authentication

2FA is voluntary at every tier. It protects your account and adds a 0.1x
reputation accrual bonus.

- **Method:** TOTP (Time-based One-Time Password), compatible with standard
  authenticator apps.
- **Enabling:** open Settings → 2FA, scan the QR code, verify a code. Requires
  re-authentication.
- **Effect:** your reputation accrual rate rises by 0.1x. A Verified member
  goes from 1.2x to 1.3x; Anonymous and Vouched members go from 1.0x to 1.1x.
- **Disabling:** also requires re-authentication. You lose the accrual bonus.

Because 2FA sits on top of magic-link authentication, an attacker would need
both your email access and your authenticator device to compromise your
account. Enable it.

---

## Device alerts

When GBlock detects a login from an unrecognized device fingerprint, it sends
an email alert. The alert lets you catch unauthorized access early. If you
receive a device alert you do not recognize, treat it as a signal to review
your account and, if needed, file a complaint.

---

## Standing and restrictions

Your **standing** reflects whether you are in good standing or under any
restriction. Restrictions can result from:

- A failed probation (yours or one you guaranteed).
- Operator action following a sustained complaint.
- Repeated trust violations.

Standing is visible on your cabinet home. If you are restricted, the cabinet
explains the nature of the restriction and what it affects. Restrictions are
not secret; the goal is for you to always know where you stand and what to do
to recover.

---

## What GBlock does not do

For completeness, the things GBlock deliberately does not do, even though a
member might expect them from other platforms:

- GBlock does **not** custody assets or funds.
- GBlock does **not** settle transactions.
- GBlock does **not** advise on the merits of any opportunity.
- GBlock does **not** guarantee the accuracy of seller-provided information.
  Members must perform their own diligence.
- GBlock does **not** reveal member identities to counterparties outside of a
  mediated introduction.

These boundaries exist by design. They keep GBlock in a narrow, defensible
role: discovery, verification, mediated introductions, and governed access.

---

## Where to go next

- **The rules behind probation and guarantors:** [User roles and statuses](02-user-roles-and-statuses.md)
- **The numbers behind reputation and the 2FA bonus:** [Reputation economy](05-reputation-economy.md)
- **The flows that use re-authentication:** [User journeys](04-user-journeys.md)
