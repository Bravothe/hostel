# Good Turn Hostel — Hostel Management Platform

**Prepared for:** Good Turn Hostel
**Prepared by:** Thembo Allan
**Date:** September 19, 2025

---

## 1) Executive Summary

We propose a modern Hostel Management Platform tailored to Good Turn Hostel’s operations. The system digitizes student reporting each term, captures bio & guardian details (including simple medical profile), enforces term-based registration after payment, and integrates mobile money and bank payments. The implementation requires a target of **UGX 3,500,000** with a 6‑week delivery plan and optional ongoing maintenance.

---

## 2) Objectives

* Replace paper-based reporting with a secure web system.
* Allow students/guardians to **register for a term only after payment** is confirmed.
* Support payments via **mobile number (MoMo)** and **bank/aggregator**.
* Provide receipts, statements, and clear reports (occupancy, arrears, revenue).
* Improve communication with SMS/email notifications.

---

## 3) Scope & Key Modules

1. **Student Profiles**

   * Bio data, photo, simple medical info, emergency contacts.
   * Parent/guardian records (multiple guardians supported).

2. **Term Management & Reporting**

   * Define terms (e.g., Term I/II/III) with open/close dates & fees.
   * Student **term registration** flows (new and returning).
   * “Report on arrival” checklist; attach receipts & notes.

3. **Payments & Receipts**

   * **Mobile Money** (MTN/Airtel) via collections; initiate/verify by phone number.
   * **Bank/Payment Aggregator** option (e.g., Flutterwave/Pesapal/Equity/…); card/bank transfer.
   * Auto‑reconciliation, instant receipt generation, downloadable PDF.
   * Arrears tracking, penalties (optional), refunds workflow (manual approval).

4. **Room/Bed & Occupancy (Basic)**

   * Rooms, beds, occupancy status; quick assign/unassign.

5. **Dashboards & Reports**

   * Occupancy overview, payments today/this term, pending registrations.
   * Exportable CSV/PDF: student lists, arrears, revenue summaries.

6. **Notifications**

   * SMS/email alerts for successful payments, registration status, fee reminders.

7. **Self‑Service Portal (Students/Guardians)**

   * View invoices, pay dues, download receipts, see room assignment and term status.

8. **Admin & Security**

   * Roles: Admin, Warden/Clerk, Accountant (extendable).
   * Audit logs for key actions; data export & encrypted backups.

---

## 4) Deliverables

* Production-ready web application + Admin dashboard.
* Integrated payments (1 MoMo provider + 1 bank/aggregator in scope).
* Reporting pack (PDF/CSV exports).
* Deployment (cloud) with SSL, domain wiring, and nightly backups.
* Technical handover: source code repo, environment docs, API docs, admin manual.
* Training: 2 sessions (admin).

---

## 5) Technology Stack

* **Frontend:** React + Next.js, Tailwind CSS.
* **Backend:** Node.js (Express/NestJS) + Prisma ORM.
* **Database:** MySQL (managed cloud DB).
* **Integrations:** Mobile Money Collections (MTN/Airtel) + one bank/aggregator (e.g., Flutterwave/Pesapal).
* **Hosting:** Vercel/Render/Railway or VPS on DigitalOcean/Linode.
* **Observability:** Request logs, error monitoring, basic analytics.

---

## 6) Data Model (High-Level)

* `students` (bio, medical, contacts)
* `guardians` (phone/email, relationship)
* `student_guardian` (links)
* `terms` (label, dates, fees)
* `enrollments` (student, term, status, balance)
* `payments` (amount, method, reference, status)
* `rooms`, `beds`, `allocations`
* `invoices`, `receipts`
* `users`, `roles`, `audit_logs`

---

## 7) Implementation Plan & Timeline (6 Weeks)

**Week 1 — Discovery & Design**

* Confirm detailed workflows, UX wireframes, data model finalization.

**Week 2 — Backend Foundations**

* DB schema, auth, roles, core CRUD; payments sandbox setup.

**Week 3 — Core Modules**

* Students & guardians; terms; enrollments; receipts; exports.

**Week 4 — Payments & Reconciliation**

* MoMo + bank/aggregator integration; receipts & arrears automation.

**Week 5 — Portal, Notifications & Reports**

* Self‑service portal; SMS/email flows; dashboards & PDFs.

**Week 6 — UAT, Training & Go‑Live**

* Data import (CSV), bug fixes, deployment, cutover plan.

> **Go‑Live Support:** 1 month hyper‑care included after launch.

---

## 8) Pricing (One‑Time Build)

**Total Fixed Price:** **UGX 3,500,000** *(exclusive of taxes & third‑party/provider fees)*

**Breakdown**

| Work Package                                    |    Cost (UGX) |
| ----------------------------------------------- | ------------: |
| Discovery, UX & Data Modeling                   |       350,000 |
| Backend (API, DB, Auth, Roles)                  |       900,000 |
| Frontend Admin (students, terms, enrollments)   |       950,000 |
| Payments Integration (MoMo + 1 bank/aggregator) |       600,000 |
| Dashboards & Reports (CSV/PDF)                  |       450,000 |
| Notifications (SMS/email)                       |       200,000 |
| Self‑Service Portal (students/guardians)        |       300,000 |
| Deployment, SSL, Domain wiring, Backups         |       200,000 |
| UAT, Training, Handover                         |       300,000 |
| **TOTAL**                                       | **3,500,000** |

> **Note:** Regular sum of components is valued higher; a bundle discount is applied to meet the UGX 3.5M budget target.

---

## 9) Payment Milestones

* **40% (UGX 1,400,000)** — Project kickoff (contract + design start).
* **30% (UGX 1,050,000)** — MVP delivered (payments + enrollments working).
* **30% (UGX 1,050,000)** — Final acceptance & handover.

---

## 10) Recurring / Third‑Party Costs (Not Included)

* **Hosting:** \~ UGX 60,000 – 120,000 / month (cloud/app + DB), depending on choice & usage.
* **Domain & SSL:** \~ UGX 80,000 – 120,000 / year.
* **SMS:** provider‑based per‑SMS fees.
* **Payment Fees:** charged by MoMo/bank/aggregator per transaction (collections/settlement).

We will shortlist providers and optimize cost during setup.

---

## 11) Assumptions

* Good Turn Hostel provides branding (logo, colors) and fee schedules.
* One MoMo provider (MTN or Airtel) **and** one bank/aggregator are in scope; additional providers can be added as an enhancement.
* Historical data will be supplied in CSV/Excel for import (if available).
* Up to 3 admin roles; more roles/complex approvals can be scoped later.
* English as the primary UI language (additional languages optional).

---

## 12) Optional Add‑Ons (Priced Separately)

* **Advanced Bed Management** (inventory KPIs, maintenance): from UGX 400,000
* **Biometric check‑in/out**: device & integration TBD
* **Multi‑branch / multi‑hostel** support: from UGX 1,200,000

---

## 13) Quality, Security & Backups

* Secure authentication & role‑based access control.
* Encrypted in transit (HTTPS) and at rest (managed DB).
* Daily automated backups, 7–30 day retention.
* Audit logs for payment & enrollment events.
* Documentation & admin manual provided.

---

## 14) Next Steps

1. Approve scope & budget (UGX 3,500,000).
2. Sign work order & pay 40% to initiate.
3. Provider accounts (MoMo + aggregator), domain, and branding assets.
4. Kickoff workshop (2 hours(Online Discussion/Meeting)) to finalize workflows & timelines.

---

**Prepared by:**
*Thembo Allan*
Software Developer
Phone: 0765384261 / 0747313467
Email: [themboallan9@gmail.com](mailto:themboallan9@gmail.com)
