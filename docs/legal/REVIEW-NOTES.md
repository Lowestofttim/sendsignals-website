# Legal drafts — open items for sign-off

_Status (2026-06-28): privacy-policy.md, terms-and-conditions.md and cookie-policy.md have had a **factual-completeness pass** — every system-grounded fact (retention, sub-processors, hosting/region, security, pupil-erasure route, cookies) was filled in and verified against the codebase, the three are now mutually consistent, and over-claims were removed. They are **drafts for solicitor sign-off — not published.** Everything below is flagged in-line as `[LEGAL REVIEW: …]`._

## Must resolve before publishing (priority order)

1. ~~**Corporate identity**~~ ✅ **FILLED (2026-06-28, verified vs Companies House + Play org account):** Send Signals Limited · company no. **17147174** (England & Wales) · registered office **7 Paradise Grove, Walsall, England, WS3 4NN** · ICO registration **ZC138681** · contact privacy@sendsignals.co.uk. _Only remaining sub-item:_ name a DPO / data-protection lead **if one is appointed** (a small company may not need a named DPO — solicitor to confirm).
2. **Publication date** on each document.
3. **Controller/processor + DPA**: confirm the **school = controller** for all in-scope data; confirm the **Article 28 DPA** exists, is referenced, and its sub-processor + international-transfer schedule matches these three docs.
4. **Lawful basis** (the school's to confirm): UK GDPR Art 6 (public task) + Art 9(2)(g) special-category condition + DPA 2018 Schedule 1.
5. **International transfers**: confirm Vercel's edge/region position, and the **UK IDTA / UK Addendum to the SCCs** safeguard for each non-UK sub-processor — Resend (US), Google FCM (US/global), Stripe (US/global), Cloudflare Turnstile (US/global), Anthropic (US, optional).
6. **Welfare-flag / disclosure retention** ⚠ _substantive_: define a concrete retention period for welfare disclosures **and implement it**. Today the scheduled 365-day purge *retains* welfare-flag records rather than deleting them, but there is **no defined "+N years from leave-date" rule in code** — for a children's safeguarding-adjacent dataset this is the highest-risk gap.
7. **Security claims to confirm before they can stand**: 2FA **enforced** (not just available) for all admin accounts at launch; **PITR** enabled on the production Supabase plan at launch; at-rest encryption on the Supabase plan.
8. **Children's Code / DPIA**: confirm the school holds a DPIA; confirm age-appropriate-design alignment.
9. **DSAR routing**: the statutory-deadline responsibility split between the school (controller) and SendSignals (processor).
10. **Terms-only**: SLA/uptime commitment (or explicit "none"); liability cap + carve-outs; trademark registration status.
11. **Breach notification**: confirm the DPA covers notifying the school of a personal-data breach.

## What is already done + verified (no further factual work needed)
- Retention default **365 days**, per-school configurable, 30-day floor, daily purge — consistent across all three.
- Full **sub-processor list** with locations: Supabase (UK/London), Vercel (global edge, US-HQ), Google FCM (US/global), Resend (US), Stripe (US/global, UK entity for UK billing), Cloudflare Turnstile (US/global), Anthropic (US — optional, **no pupil data**).
- **No third-party analytics/tracking** (verified absent in code); cookies are strictly-necessary auth (Supabase) + the Turnstile challenge cookie on public sign-up only.
- **Pupil-erasure route** exists (admin-only); DSARs routed via the school.
- Positioning is correct and consistent: SendSignals **flags** low wellbeing for staff — **not** a clinical/crisis/safeguarding service.
