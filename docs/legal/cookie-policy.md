# Cookie Policy — DRAFT (requires legal review)

**Last updated:** [LEGAL REVIEW: publication date] · **Version:** draft

Send Signals is designed to use the **minimum** browser storage needed to run the
service. We use **no** analytics, advertising or cross-site tracking, and we set
no cookies that profile or track children.

This policy explains the small number of cookies and similar browser-storage
items Send Signals relies on. It sits alongside our **Privacy Policy** (which
explains how pupil data is handled) and our **Terms & Conditions**.

> **About our role.** Send Signals helps a school *flag* low wellbeing so its
> staff can act; it is **not** a clinical, crisis or safeguarding service — the
> school's staff do the actual safeguarding. For pupil data, the **school is the
> data controller** and Send Signals acts as its **data processor** under a Data
> Processing Agreement. Questions about a specific child's data are answered by
> the school (see "How to exercise your rights", below).

## 1. What we use

| Name / Pattern | Type | Purpose | Duration | Category |
|----------------|------|---------|----------|----------|
| `sb-*` | Cookie | Supabase authentication/session (keeps a signed-in user logged in) | Session / until sign-out (provider-managed) | Strictly necessary. (Secure + SameSite=Lax; readable by the app's JavaScript, not httpOnly.) |
| `hq_active` | Cookie | staff/admin idle-timeout timestamp (auto sign-out) | 8 hours | Strictly necessary (security). |
| `ss_kiosk_token` | Cookie (httpOnly) | device authentication on school-supplied kiosk tablets only | per kiosk session | Strictly necessary. |
| Cloudflare Turnstile challenge cookie (`cf_*`/`__cf*`, set by Cloudflare) | Cookie (third-party) | bot/abuse protection on the PUBLIC sign-up and demo forms only (never the pupil app) | short-lived | Strictly necessary. |
| Demo/sandbox session cookies | Cookie (httpOnly) | public demo mode only | demo session | Strictly necessary. |
| Telemetry/error client id | Browser storage (localStorage) | a random pseudonymous id for first-party crash/error telemetry (NOT advertising/tracking; no third party) | until cleared | Functional. |
| Remember-me (email + flag) | Browser storage (localStorage) | pre-fills your email on the sign-in screen IF you tick "remember me" | until cleared | Functional (user-initiated). |
| Kiosk state (mode / token / student name / fleet token) | Browser storage (localStorage) | supplied-tablet kiosk mode only | until cleared | Strictly necessary (kiosk). |
| UI/app state (school-logo cache, demo viewing date, welcome-seen, PWA-install-dismissed, progress-celebrated flags, deep-link-handled, session heartbeat) | Browser storage (local/session) | remember UI preferences and app state | until cleared / session | Functional. |

Browser local/session storage are not cookies but are listed here for
transparency; none are used for advertising or cross-site tracking.

The Supabase session cookies are marked **Secure** in production. Authentication
uses secure, same-site Supabase session cookies. In the current browser client
these cookies are readable by the application's JavaScript, so we also rely on
TLS, the SameSite attribute, a Content-Security-Policy, database tenant isolation
(RLS), least-privilege access and audit logging. We do not sell or share the
contents of any of these items, and none of them are used for advertising.

`[LEGAL REVIEW: confirm the exact cookie names and durations shown to users
match the live deployment at publication — the Supabase session-cookie names and
TTLs are controlled by Supabase and the project's session settings.]`

## 2. What we do **not** use

- **No analytics** — no Google Analytics, Vercel Analytics, Plausible, PostHog,
  Meta Pixel or any other analytics or product-telemetry cookie. *(Send Signals
  does collect anonymous crash/error reports to keep the app working; these carry
  no pupil data, set no tracking cookie, and strip any token or query string from
  URLs before storing.)*
- **No advertising or marketing cookies.**
- **No third-party cross-site tracking.** Pupils' or staff browsing is not
  profiled across sites, and we do not build advertising profiles of anyone —
  least of all children.

## 3. Consent (PECR)

We only store or access information on a device where it is strictly necessary (a
PECR exception) or where we have obtained the required consent / provided the
required objection mechanism. Because we set **no** analytics, advertising or
other cross-site tracking cookies, the app does not need a cookie-consent banner
for its own functioning.

`[LEGAL REVIEW: confirm the marketing website's own cookie banner/wording matches
this "essential only" position, and that no non-essential storage is set before
any consent on the public site.]`

## 4. International transfers and where data is stored

The cookies above are stored in the user's own browser. The data they help carry
(for example, an authenticated session) relates to information that Send Signals
handles as follows: pupil data is stored at rest in the UK (Supabase, London
region). The application is served over Vercel's global edge network, which is not
pinned to a single region and processes data only in transit. Some sub-processors
(email, push notifications, billing, bot-protection) operate outside the UK — see
the sub-processor list and the International transfers section.

Where a strictly-necessary provider operates internationally (for example,
Cloudflare's global anti-abuse network serving the Turnstile challenge), that
provider's processing is governed by the school's Data Processing Agreement and
the appropriate UK transfer safeguards. See the **Privacy Policy** for the full
list of sub-processors and transfer detail.

`[LEGAL REVIEW: confirm the international-transfer mechanism (e.g. UK IDTA / UK
Addendum to the EU SCCs) used for any sub-processor that processes data outside
the UK, and that it is reflected consistently here and in the Privacy Policy.]`

## 5. Children

Send Signals' data subjects are **children**, so the service is **designed around
the principles of the ICO Age Appropriate Design Code (Children's Code)**: `[LEGAL
REVIEW: confirm whether the Children's Code applies in full given Send Signals'
processor role, or only its principles — ICO edtech guidance is role-dependent]`

- We do **not** use cookies or any browser storage to track, profile or target
  children, or to build advertising or behavioural profiles.
- Pupil-facing pages set only the strictly-necessary login session items needed
  to let a child sign in and submit a check-in. The Cloudflare anti-abuse
  challenge and the staff idle-timeout cookie are **not** used in the pupil
  check-in flow.
- The lawful basis for processing pupil wellbeing information (which is
  **special-category** data under UK GDPR) is the **school's**, as data
  controller — typically the school's public task and its safeguarding duties —
  **not** consent obtained through a cookie banner.

`[LEGAL REVIEW: confirm the wording of the school's Article 6 lawful basis and
Article 9 special-category condition (e.g. public task / substantial public
interest / safeguarding) as set out in the school's own privacy information.]`

## 6. How long the underlying data is kept

The cookies themselves expire as set out in section 1. The pupil data they help
access is kept under the school's retention settings: by default, pupil check-in
and message history is retained for **365 days** and then automatically deleted
by a nightly purge. A school can change this window (the minimum the purge will
honour is 30 days). Welfare-flag disclosure records are **retained beyond the
window** — the scheduled purge keeps them rather than auto-deleting them, so a
school's safeguarding record isn't lost to routine purging. A defined
disclosure-retention period (e.g. a leave-date + N years rule) `[LEGAL REVIEW:
define + implement]` is not yet implemented. When a school stops using Send
Signals, its data is deleted or returned to it in line with the Data Processing
Agreement. Full detail is in the **Privacy Policy**.

## 7. Managing cookies and clearing storage

You can clear or block cookies and clear site storage in your browser settings,
and clearing storage will sign you out and remove any cached app data. Because
the items we use are strictly necessary, **the platform may not function
correctly** without them — in particular, blocking the session cookie will stop
you signing in.

## 8. Security

The session our cookies maintain is protected by, among other measures:
per-school database isolation (Postgres Row-Level Security, so one school cannot
read another's data and a pupil can only see their own — covered by automated
tests), secure session cookies and a Content-Security-Policy, two-factor
authentication (2FA) available for admin accounts `[LEGAL REVIEW: confirm 2FA is
enforced for all admin accounts at launch]`, audit logging of configuration and
permission changes, encryption in transit (TLS), and point-in-time-recovery (PITR)
database backups `[LEGAL REVIEW: confirm PITR is enabled on the production plan at
launch]`. Authentication uses secure, same-site Supabase session cookies. In the
current browser client these cookies are readable by the application's JavaScript,
so we also rely on TLS, the SameSite attribute, a Content-Security-Policy,
database tenant isolation (RLS), least-privilege access and audit logging. More
detail is in the **Privacy Policy**.

## 9. Your rights and how to exercise them

Pupils, parents and staff have rights over personal data under UK GDPR —
including access, rectification, erasure, restriction, objection and (where
applicable) portability.

Because the **school is the data controller**, requests about a specific child's
data — including subject access requests and requests to delete a child's data —
should be made **to the school**, which will action them (Send Signals supports
the school with a built-in pupil-erasure tool that permanently removes a pupil's
data on the school's instruction). If you are unsure who to contact at the
school, or you have a question about cookies specifically, you can also reach
Send Signals using the details below and we will help route your request.

## 10. Complaints and the ICO

If you are concerned about how your (or your child's) personal data is handled,
please raise it with the **school** in the first instance. You also have the
right to complain to the UK Information Commissioner's Office (ICO) at
**ico.org.uk** or by calling its helpline.

You can make a data-protection complaint to us at privacy@sendsignals.co.uk. We
will acknowledge your complaint within 30 days, investigate it and keep you
updated without undue delay, and tell you the outcome. You also have the right to
complain to the Information Commissioner's Office (ICO) at ico.org.uk.

## 11. Contact

privacy@sendsignals.co.uk

**Send Signals Limited**, a company registered in England & Wales (company no. **17147174**), registered office **7 Paradise Grove, Walsall, England, WS3 4NN**. ICO registration number **ZC138681**.
