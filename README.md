# Clinic Manager

**An offline-first, bilingual (Arabic / English) dental clinic system for Windows — patients, odontogram, appointments, billing and installments, with encrypted local data.**

## The problem
Small dental clinics often run on paper, spreadsheets, or cloud tools that need constant internet and send patient data off-site. They need something fast, private, and simple enough for a reception desk — that still keeps the money side exactly right.

## Key features
- **Patients & dental chart** — searchable patient list, full profile, interactive odontogram (surfaces, conditions, history).
- **Appointments** — daily schedule, status tracking, WhatsApp reminders (click-to-chat; nothing is sent automatically).
- **Billing you can trust** — integer-based ledger, invoices, payments, installments, credit notes, closed cash days, built-in self-checks that the books add up.
- **Reports & exports** — analytics dashboard, Excel / CSV / PDF exports, A4 / A5 / thermal receipts.
- **Privacy by design** — data is encrypted at rest on the clinic's own PC; works fully offline; encrypted backups.
- **Arabic (RTL) and English (LTR)**, light branding per clinic (name, logo, colours).
- **Simple / Advanced mode** — new clinics see only what they need; advanced screens (stock, lab work, advanced reports) are one switch away.
- **Licensing & optional updates** — offline activation with signed keys; opt-in, signed software updates with automatic rollback.

## Tech stack
Electron · React · TypeScript · Tailwind CSS · SQLite (sql.js) with encrypted storage · Node.js · Playwright (end-to-end tests) · property-based tests for the money engine.

## Architecture (high level)
```mermaid
flowchart LR
  UI["React UI<br/>(Arabic / English)"] -- "typed IPC" --> Core["Application core<br/>(Electron main process)"]
  Core --> DB[("Encrypted local database")]
  Core --> Files[("Encrypted attachments<br/>X-rays & documents")]
  Core --> Lic["Offline licensing<br/>(signed keys)"]
  Core -. "opt-in, signed releases" .-> Upd["Update service"]
```

## Screenshots
All data below is fake demo data.

| English | العربية |
|---|---|
| ![Dashboard](screenshots/en/01-dashboard.png) | ![لوحة التحكم](screenshots/ar/01-dashboard.png) |
| ![Patients](screenshots/en/03-patients.png) | ![المرضى](screenshots/ar/03-patients.png) |
| ![Odontogram](screenshots/en/05-odontogram.png) | ![خريطة الأسنان](screenshots/ar/05-odontogram.png) |
| ![Appointments](screenshots/en/06-appointments.png) | ![المواعيد](screenshots/ar/06-appointments.png) |
| ![Billing](screenshots/en/07-billing.png) | ![الفواتير](screenshots/ar/07-billing.png) |
| ![Installments](screenshots/en/08-installments.png) | ![الأقساط](screenshots/ar/08-installments.png) |
| ![Analytics](screenshots/en/02-analytics.png) | ![التحليلات](screenshots/ar/02-analytics.png) |
| ![Exports](screenshots/en/09-exports.png) | ![التصدير](screenshots/ar/09-exports.png) |
| ![Branding](screenshots/en/10-settings-branding.png) | ![الهوية](screenshots/ar/10-settings-branding.png) |
| ![Activation](screenshots/en/12-lock-activation.png) | ![التفعيل](screenshots/ar/12-lock-activation.png) |

## My role
Solo developer: product design, architecture, implementation, testing, packaging and licensing.

## Status
Version 0.4 — actively developed.

> Source code is private — available for a walkthrough on request.

---
© 2026 Nader Elsamahy. All rights reserved.
