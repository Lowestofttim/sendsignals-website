# Legal drafts — open items for sign-off

_Status (2026-06-28): the three policies had a **factual-completeness pass**, then a **readiness-review amendment pass** (responding to the Codex legal-readiness review). Every system-grounded fact was verified against the codebase, code/document mismatches were corrected (several were confirmed real and fixed — see below), the three are mutually consistent, and over-claims were removed. They remain **drafts for solicitor sign-off — not published.** Everything below is flagged in-line as `[LEGAL REVIEW: …]`._

## Must resolve before publishing (priority order)

1. ~~**Corporate identity**~~ ✅ **FILLED (verified vs Companies House + Play org account):** Send Signals Limited · company no. **17147174** (England & Wales) · registered office **7 Paradise Grove, Walsall, England, WS3 4NN** · ICO registration **ZC138681** · contact privacy@sendsignals.co.uk. _Only remaining:_ name a DPO / data-protection lead **if one is appointed** — and note the Codex review flags that, because the service processes children's special-category data at scale, the DPO question needs a **formal documented assessment** (don't just record "small company, none needed").
2. **Publication date** on each document.
3. **Controller/processor + DPA**: confirm school = controller for pupil data; confirm the **Article 28 DPA** exists + is referenced, and its sub-processor + transfer schedule matches these docs. ⭐ **The DPA must explicitly cover children's special-category data** — and specifically confirm the **Resend DPA covers children's personal data** (Resend now processes pupil email addresses + sign-in links; see resolved item below).
4. **Lawful basis** (school's to confirm): UK GDPR Art 6 (public task) + Art 9(2)(g) + DPA 2018 Sch 1. **Also confirm Send Signals' OWN controller lawful bases** for the new "Where Send Signals is itself the controller" section (website enquiries, demos, support, billing, ops/security logs, telemetry).
5. **International transfers**: confirm the **UK IDTA / UK Addendum to the SCCs** safeguard for each non-UK sub-processor — Resend (US), Google FCM (US/global), Stripe (US/global), Cloudflare Turnstile (US/global), Anthropic (US, optional), Vercel (global edge).
6. **Welfare-flag / disclosure retention** ⚠ _substantive_: define a concrete retention period for welfare disclosures **and implement it** (today the purge retains them with no defined "+N years from leave-date" rule). Highest-risk gap.
7. **Security claims to confirm before they can stand**: 2FA **enforced** (not just available) for admins at launch; **PITR** enabled at launch; **at-rest encryption** on the Supabase plan.
8. **Children's Code applicability** ⭐ _newly flagged_: the docs now say "designed around the principles of the Children's Code" (softened). The solicitor must confirm whether the Code applies **in full** (vs principles-only) — ICO edtech guidance is role-dependent (may not apply to a pure processor; may apply where the provider influences purposes/processes for its own product). Also confirm the school holds a DPIA + whether Send Signals keeps its own product DPIA.
9. **DSAR routing**: the statutory-deadline responsibility split between the school (controller) and Send Signals (processor).
10. **Terms-only**: SLA/uptime (or explicit "none"); liability cap + carve-outs; trademark registration status; finalise the school agreement/order form the public terms cross-reference.
11. **Breach notification**: confirm the DPA covers notifying the school of a personal-data breach.
12. **Resend student-access email** _(decision taken — confirm acceptable)_: the pupil **name was removed** from the student-access/login email (code PR sendsignals-app #498) so it no longer lands in Resend's stored metadata. The email still sends to the pupil's own address with a personal sign-in link. Confirm this residual processing (pupil email + sign-in link via a US sub-processor) is acceptable + DPA-covered.

## Resolved in the 2026-06-28 readiness-review amendment pass (code/document mismatches — were real, now fixed)
- **httpOnly over-claim → corrected.** The docs said staff/admin sessions use httpOnly cookies; the code's Supabase session cookies are NOT httpOnly (the browser client reads them). Reworded to the accurate position: Secure + SameSite, readable by app JS, protected by TLS/CSP/RLS/least-privilege/audit. _(Owner decision: reword now; httpOnly hardening logged as a separate future security task.)_
- **Resend understatement → corrected (+ code change).** Docs said "staff only / no pupil data"; in fact student-access emails carried the pupil name. Pupil name **removed** from those emails (PR #498); docs now disclose Resend processes pupil email + sign-in link, with a children's-data DPA flag.
- **Push "no names" absolute claim → corrected.** Default is generic, but a per-school "Show student details on lock screen" toggle (OFF/not-recommended) can put the pupil's first name **and the disclosure message text** on a locked device. Docs now state this accurately. _(Owner decision: keep the toggle, disclose accurately.)_
- **Cookie/storage audit → done.** cookie-policy.md now has a concrete table (name/type/purpose/duration/category) of the actual cookies + browser storage (sb-*, hq_active, ss_kiosk_token, Turnstile, demo, telemetry id, remember-me, kiosk state, UI state).
- **PECR consent wording → tightened** (only store where strictly-necessary OR consented).
- **30-day complaint process → added** (privacy + cookie) with privacy@ contact + ICO escalation (DUAA-aligned).
- **"Send Signals as controller" section → added** to the privacy policy.
- **Live marketing-site overlays** (`sendsignals-website/index.html`) had older, stronger claims ("all data on UK servers", "encrypted at rest" as fact) — being corrected separately so the live site stops making unsupported claims.

## Already verified (no further factual work)
- Retention **365 days** default, per-school configurable, 30-day floor, daily purge — consistent across all three.
- Full **sub-processor list** with locations (Supabase UK/London; Vercel; Google FCM; Resend; Stripe; Cloudflare Turnstile; Anthropic optional/no-pupil-data).
- **No third-party analytics/tracking** (verified absent in code).
- **Pupil-erasure route** exists (admin-only); DSARs routed via the school.
- Positioning consistent: Send Signals **flags** low wellbeing — **not** a clinical/crisis/safeguarding service.
