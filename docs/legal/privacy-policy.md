# Privacy Policy — DRAFT (requires legal review)

**Last updated:** [DATE] · **Version:** draft

> **[DECISION] Controller/processor:** If schools are the data controllers and
> Send Signals is the processor, reframe this document accordingly and point
> schools to the Data Processing Agreement. See `README.md`.

## 1. Who we are

Send Signals is a student wellbeing and SEND-support platform used by UK schools.
It is operated by **Send Signals Ltd**, a company registered in England & Wales
(company no. **[CONFIRM]**), registered office **[CONFIRM]**.

- Privacy / data protection contact: **[CONFIRM — DPO or privacy lead]**,
  privacy@sendsignals.co.uk
- ICO registration number: **[CONFIRM]**

## 2. Our role

Send Signals is provided to schools. Where a school decides how and why pupil
data is used, the **school is the data controller** and **Send Signals Ltd acts
as a data processor** on the school's documented instructions under a Data
Processing Agreement (UK GDPR Article 28). `[CONFIRM with legal]` This policy
explains, transparently, how data is handled within the service.

## 3. The data we process

- **Pupil identity:** name and a school-assigned identifier (typically from the
  school's Microsoft/Google account).
- **SEND/wellbeing information (special category data):** check-in ratings
  (green/amber/red), pre-set signal/message selections, optional short notes a
  pupil attaches, and SEND profile fields the school maintains.
- **Staff accounts:** name, role, work email, authentication identifiers.
- **Technical data:** timestamps of interactions, device/session identifiers
  needed to keep the service secure.

We practise **data minimisation** — we collect only what the service needs.

## 4. Lawful basis

- **Personal data (Art 6):** **[CONFIRM — e.g. public task (school) / legitimate
  interests / contract]**.
- **Special category data (Art 9):** wellbeing/SEND data is special category
  data and additionally relies on **[CONFIRM — e.g. Art 9(2)(g) substantial
  public interest (safeguarding/education) / explicit consent]**.

The school determines and documents the lawful basis; Send Signals supports it.

## 5. How the data is used

Solely to support pupil wellbeing and SEND provision within the pupil's own
school: to let pupils check in, to surface concerns to the school's SEND/pastoral
team, to trigger safeguarding alerts the school has configured, and to produce
the school's own provision/progress records. **We never sell data, use it for
advertising, or share it outside the pupil's school team.**

## 6. Children's data

We follow the ICO **Age Appropriate Design Code**. Data minimisation and the
**best interests of the child** are core principles. Pupils can only ever see
their **own** data — never another pupil's. We do not profile children for
marketing and run no third-party tracking.

## 7. Who we share data with (sub-processors)

We use a small number of carefully chosen providers to run the service:

| Provider | Purpose | Location | Notes |
|----------|---------|----------|-------|
| Supabase | Database & authentication | London / UK (eu-west-2) | Row-Level Security enforces school isolation |
| Vercel   | Application hosting / CDN | [CONFIRM region/routing] | |
| Resend   | Transactional email (e.g. alerts) | [CONFIRM — US-based; confirm transfer safeguard] | alert emails are data-minimised (no pupil name) |

We do not share data with any other third parties except where required by law
or to protect a child's safety. `[CONFIRM final list + transfer safeguards]`

## 8. International transfers

The primary database is hosted in the **UK (London, eu-west-2)**. Where any
sub-processor processes data outside the UK, we rely on an appropriate transfer
safeguard (e.g. the UK International Data Transfer Agreement / Addendum to the
EU SCCs). `[CONFIRM which providers + mechanism]`

## 9. Retention

We keep data only as long as necessary for the school's SEND/wellbeing purposes.
Indicative periods (**[CONFIRM with the school + legal]**):

- Check-ins / messages / alerts: **[e.g. current + N academic years]**
- Pupil & staff accounts: removed/anonymised **[e.g. N months]** after a pupil
  leaves or a school offboards.

On a school offboarding, its data is deleted or returned per the DPA. `[CONFIRM]`

## 10. How we protect data

- **Tenant isolation** in the database via Postgres Row-Level Security — one
  school can never read another's data; a pupil can only see their own. This is
  tested automatically in our build pipeline.
- **UK data residency** for the database (London, eu-west-2).
- **Encryption** in transit (HTTPS/HSTS) and at rest.
- **Least-privilege** access and audited use of privileged keys.
- **Data minimisation in notifications** — alert emails contain no pupil name;
  staff sign in to view details.

## 11. Your rights

Under UK GDPR, data subjects have the right to access, rectification, erasure,
restriction, portability and to object. Because the **school is usually the
controller**, requests are normally made to the school, which we support as
processor. To raise a request or concern, contact your school's SEND/data team,
or email privacy@sendsignals.co.uk. `[CONFIRM routing]`

## 12. Complaints

If you are unhappy with how your data has been handled you can complain to the
**Information Commissioner's Office (ICO)**, ico.org.uk, though we'd welcome the
chance to resolve it first.

## 13. Changes

We may update this policy; the "last updated" date will change and material
changes will be communicated to schools.

## 14. Contact

privacy@sendsignals.co.uk · hello@sendsignals.co.uk
