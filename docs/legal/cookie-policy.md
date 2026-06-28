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

| Name / type | Purpose | Category | Duration |
|-------------|---------|----------|----------|
| Supabase authentication / session cookies (`sb-…`) | Keeps a signed-in user (staff or pupil) securely logged in; refreshed on each request | Strictly necessary | Session / until sign-out or token expiry (managed by Supabase) |
| HQ idle-timeout cookie (`hq_active`) | Times out an idle Send Signals **staff/admin** console session; **not used on pupil devices** | Strictly necessary | Up to 8 hours (refreshed on activity) |
| Cloudflare Turnstile challenge cookie | Set by Cloudflare on the **public sign-up / demo** pages only, to tell humans from bots when an account or demo is requested; not set on the pupil check-in flow | Strictly necessary (anti-abuse) | Short-lived (set by Cloudflare) |
| Service-worker / PWA cache (browser storage, not a cookie) | Caches app assets so the installable app loads and works offline | Strictly necessary | Until the app is updated or browser storage is cleared |
| Local app state (browser `localStorage`/`sessionStorage`, not a cookie) | Remembers in-app settings (e.g. last-used view) to make the app usable; held on the device, not sent for tracking | Functional | Until cleared by the user |

The Supabase session cookies are **HTTP-only** where set as cookies (not readable
by page scripts) and are marked **Secure** in production. We do not sell or share
the contents of any of these items, and none of them are used for advertising.

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

The items in section 1 are **strictly necessary or functional** for the service
to work, so under the Privacy and Electronic Communications Regulations (PECR)
they do not require prior consent. Because we set **no** analytics, advertising
or other non-essential cookies, the app does not need a cookie-consent banner for
its own functioning.

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

Send Signals' data subjects are **children**, so we apply the ICO's Age
Appropriate Design Code ("Children's Code"):

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
tests), HTTP-only session cookies and a Content-Security-Policy, two-factor
authentication (2FA) available for admin accounts `[LEGAL REVIEW: confirm 2FA is
enforced for all admin accounts at launch]`, audit logging of configuration and
permission changes, encryption in transit (TLS), and point-in-time-recovery (PITR)
database backups `[LEGAL REVIEW: confirm PITR is enabled on the production plan at
launch]`. More detail is in the **Privacy Policy**.

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

## 11. Contact

privacy@sendsignals.co.uk

**Send Signals Limited**, a company registered in England & Wales (company no. **17147174**), registered office **7 Paradise Grove, Walsall, England, WS3 4NN**. ICO registration number **ZC138681**.
