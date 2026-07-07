---
title: 'Google Drive Integration'
date: '2026-05-24'
modified: '2026-05-24'
---

Haiku can save invoice PDFs and expense files directly to your Google Drive, with a consistent folder structure and file naming so everything stays organised without manual filing.

## Authorizing Drive

1. Go to **Settings → Google Drive**.
2. Click **Connect Google Drive** and complete the Google authorization screen.
3. A confirmation appears once Haiku has permission to create files in a dedicated Haiku folder.

Haiku only ever writes to its own folder tree. It does not read or list other folders in your Drive.

## Folder Structure

Files are placed under a top-level `Haiku.lt` folder, split by type and year:

```
Haiku.lt
  ├── Invoices
  │     └── 2026
  │           └── INV-2026-045.pdf
  └── Expenses
        └── 2026
              └── 2026-05-12-acme-supplies.pdf
```

The year folder is created automatically the first time a file is uploaded for that year.

## File Naming

**Invoices** — the file is named with the invoice series and number (e.g. `INV-2026-045.pdf`). Locking and re-saving overwrites the existing file rather than creating a duplicate.

**Expenses** — files are named with the expense date and a slug of the seller or description (e.g. `2026-05-12-acme-supplies.pdf`), making them easy to find without opening.

## When Files Go Where

| Action | File saved to Drive? |
|---|---|
| Create invoice | No — manually save via **Save PDF to Drive** or batch-save in Multi-Edit |
| Lock invoice | No — locking is independent of Drive |
| Send invoice via email | No — Drive save is a separate action |
| Add expense with "Upload to Drive" checked | Yes — uploaded during Step 3 |
| Multi-Edit → Save PDFs to Drive | Yes — batch-uploads selected invoices |
| Delete expense | No — file stays in Drive; use **Delete from Drive** on the card |

This separation is intentional: locking and sending are about accounting state, while Drive storage is about archival. They can happen at different times.

## Bulk Operations

For sending an entire month of invoices to Drive at once, use the [batch-edit wizard](/en/batch-edit-invoices) — it includes both **Save PDFs to Google Drive** and **Delete from Google Drive** operations.

## Revoking Access

To disconnect Drive: **Settings → Google Drive → Disconnect**. Existing files in Drive remain in place — disconnecting only stops Haiku from uploading new ones.

You can also revoke access from Google directly at [myaccount.google.com/permissions](https://myaccount.google.com/permissions). Haiku will detect the revocation on the next upload attempt and prompt you to reconnect.
