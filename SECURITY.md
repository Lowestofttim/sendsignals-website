# Security Policy

This repository (`sendsignals-website`) is the **public marketing site** for
Send Signals (`sendsignals.co.uk`) — a static site served via GitHub Pages. It
contains no student data and no application logic; the product itself lives at
`app.sendsignals.co.uk` (see the `sendsignals-app` repository).

## Reporting a vulnerability

**Please do not open a public issue for security problems.**

Report suspected vulnerabilities privately to **security@sendsignals.co.uk**
(or hello@sendsignals.co.uk if that is unavailable). Include:

- a description of the issue and its potential impact,
- steps to reproduce (a proof of concept if you have one),
- any affected URLs or pages.

We aim to acknowledge reports within **2 working days**. Please give us a
reasonable opportunity to fix the issue before any public disclosure. We will
not pursue researchers who act in good faith and avoid privacy violations, data
destruction, or service degradation.

## Supported versions

This is a continuously-deployed static site; security fixes are applied to
`main` and published immediately. Only the live site is supported.

## What this site does (and doesn't)

- **No personal data of children** is processed here. The site is informational
  plus a demo-request form and a cookie notice.
- **No tracking/analytics/advertising cookies** — only essential cookies for the
  product (documented in the on-site Cookie Policy).
- Legal copy (Privacy/Terms/Cookies) is shown on the site; fuller **draft**
  versions for solicitor/DPO review live in `docs/legal/` and are **not** the
  published legal text.

## Scope

In scope: this repository's static content and configuration. Out of scope: the
web application (`sendsignals-app`) and third-party services (GitHub Pages,
Resend, etc.) — report those to the main app repo or the respective vendor.
