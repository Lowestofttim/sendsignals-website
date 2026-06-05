# Legal documents — DRAFTS for review

**Status: DRAFT. Not legal advice. Do not publish until reviewed by a qualified
solicitor / your DPO.**

These are fuller drafts of the Privacy Policy, Terms & Conditions and Cookie
Policy than the short versions currently embedded in `index.html`. They expand
the existing copy to the structure UK GDPR + the ICO Children's Code expect for a
platform that processes **children's special-category (SEND/health) data**.

Once reviewed and approved, the agreed text should replace the three
`legal-overlay` blocks in `index.html` (ids `privacy`, `terms`, `cookies`).

## Decisions needed before publishing (flagged inline as `[DECISION]` / `[CONFIRM]`)

1. **Controller vs processor — most important.** The current live Privacy Policy
   states *"Data Controller: Send Signals Ltd."* For pupil data in a school
   SaaS, the **school is normally the data _controller_** and the vendor (Send
   Signals) is the **data _processor_** acting on the school's instructions
   under a Data Processing Agreement (UK GDPR Art 28). If that is the intended
   model, most of this Privacy Policy is really the school's to publish to
   parents/pupils, and Send Signals' public document should describe its role as
   a processor + point schools to the DPA. **Confirm the relationship with your
   solicitor before publishing** — it changes who is responsible for lawful
   basis, DSARs, and breach reporting.
2. **Lawful basis** (UK GDPR Art 6) and the **special-category condition**
   (Art 9) for SEND/wellbeing data — e.g. public task / substantial public
   interest / explicit consent. `[CONFIRM]`
3. **Retention periods** — how long check-ins, messages, alerts and accounts are
   kept, and what happens when a pupil leaves or a school offboards. `[CONFIRM]`
4. **Sub-processors** — confirm the list and locations (current: Supabase –
   database, London/UK; Vercel – hosting/CDN; Resend – transactional email).
   Note any that process or route data **outside the UK** and the transfer
   safeguard used (e.g. IDTA / UK Addendum to SCCs). `[CONFIRM]`
5. **ICO registration number** and **DPO / privacy contact** details. `[CONFIRM]`
6. **Company details** — registered company number + registered office for Send
   Signals Ltd. `[CONFIRM]`

## Files
- `privacy-policy.md`
- `terms-and-conditions.md`
- `cookie-policy.md`
