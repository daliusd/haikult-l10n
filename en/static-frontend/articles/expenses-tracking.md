---
title: 'Expense Tracking'
date: '2026-03-22'
modified: '2026-05-24'
---

Haiku tracks business expenses alongside your invoices. Upload an invoice or receipt, have the data extracted automatically when possible, and keep files organised in Haiku and/or Google Drive.

## The Expenses Page

![Expenses page](/screenshots/expenses-tracking/en/step-1-expenses-list.png)

The **Expenses** page lists all recorded expenses with quick access to edit, delete, open the stored file, or download the original.

Filtering:

- **Date range** — focus on a specific month, quarter, or custom period.
- **Search by description** — find an expense by keyword.
- **Running total** — count and sum of expenses matching the current filter, shown at the top.

Each card shows description, seller, amount, date, and storage status (Haiku, Drive, or both).

## Adding an Expense

Click **New Expense** on the expenses page. A 4-step wizard opens.

### Step 1 — Upload the Document

Drag and drop or pick a file. Supported formats: **PDF**, **JPEG**, **PNG**, **XML** — covers scanned receipts and electronic invoices.

### Step 2 — Automatic Parsing

If the file is a standard electronic invoice (Factur-X PDF, common in France and Germany; e-invoice XML), Haiku extracts:

- Invoice number
- Seller name
- Line items
- Total amount
- Issue date

For scanned images or non-structured PDFs, the form opens empty and you fill in the details.

### Step 3 — Review, Edit, and Choose Storage

A pre-filled form appears. Correct anything that's off, then choose where the file is stored:

- **Upload to Haiku** — files up to 2 MB, stored securely in your account.
- **Upload to Google Drive** — sent to a dedicated folder in your Drive (requires authorization — see [Google Drive integration](/en/google-drive-integration)).

You can pick one, both, or neither. The expense record itself is always saved regardless of where the file goes.

### Step 4 — Saved

Confirmation appears. From here you can add another expense or return to the list.

## Editing and Deleting

Each expense has an **Edit** button to update any field — description, seller, amount, date, line items, storage choice. The **Delete** button removes the record after a confirmation step.

Deleting an expense does not delete the Google Drive file. Use the **Delete from Drive** action on the card first if you also want to remove the cloud copy.

## Smart Invoice Reading

Haiku reads invoices in standard electronic formats used across Europe:

- **Factur-X / ZUGFeRD** PDFs — common with German and French suppliers.
- **UBL / Peppol / EN 16931** XML — the EU e-invoicing standard.

For unsupported formats or photographs, fields stay empty in Step 3 and you enter them manually.
