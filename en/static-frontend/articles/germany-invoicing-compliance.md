---
title: 'Invoicing in Germany: Complete 2026 Compliance Guide for Small Businesses'
date: '2026-02-08'
modified: '2026-03-28'
showDate: true
---

Germany has some of the most rigorous invoicing requirements in Europe. Between GoBD regulations, e-invoicing mandates, and strict audit trail requirements, it's easy to feel overwhelmed. This guide breaks down what you actually need to know about invoicing in Germany in 2026—from VAT registration and mandatory fields to e-invoicing timelines and GoBD compliance.

## VAT Registration and Rates

Germany offers a **Kleinunternehmerregelung** (small business exemption): if your annual turnover is below €22,000, you can operate VAT-free. Registration becomes mandatory if you exceeded €22,000 last year or expect to exceed €50,000 this year. Cross-border EU sales have a €10,000 threshold.

**VAT number format**: `DE` + 9 digits (e.g., `DE123456789`)
**Processing time**: 2-4 weeks from Bundeszentralamt für Steuern (BZSt)

**VAT rates:**
- **19%** - Standard rate (most goods and services)
- **7%** - Reduced rate (food, books, newspapers, public transport, cultural events)
- **0%** - Exports and intra-EU supplies (with valid VAT number)

## Mandatory Invoice Fields

Every **full invoice** (over €250) must include:

- Seller name, address, and VAT number (DE + 9 digits)
- Buyer name, address, and VAT number (if B2B and registered)
- Unique sequential invoice number (no gaps allowed)
- Invoice date and delivery/performance date
- Clear description of goods/services
- Quantity, unit price (net), VAT rate, VAT amount, total (gross)

> **Small-amount invoices (Kleinbetragsrechnungen)** under €250 have lighter requirements — buyer name and address are not required; only seller details, date, description, VAT rate, and total amount.

**Special text requirements:**
- **Reverse charge**: "Steuerschuldnerschaft des Leistungsempfängers"
- **Intra-EU supply**: "Innergemeinschaftliche Lieferung"
- **Small business exemption**: "Kein Ausweis von Umsatzsteuer, da Kleinunternehmer gemäß § 19 UStG"

## Invoice Numbering

Numbers must be **sequential and unique** with no gaps. Alphanumeric formats are fine:
- `2026-0001, 2026-0002...`
- `INV-DE-2026-00001`
- `R-2026/001` (R = Rechnung)

You can reset annually as long as the year is included in the number.

## Language and Currency

**Language**: Any of the 24 EU official languages are accepted. German is recommended for domestic clients, English for international. Tax authorities may request translations during audits.

**Currency**: Any currency accepted on invoices, but VAT reporting must be in EUR using ECB exchange rates from the invoice date.

## E-Invoicing Requirements (2025-2028)

E-invoicing means **structured electronic invoices** with machine-readable XML data, not just PDF emails. Germany accepts **ZUGFeRD** (hybrid PDF with embedded CII XML) and **XRechnung** (pure XML), both EN 16931-compliant.

**Timeline:**
- **January 1, 2025**: All B2B businesses must be able to **receive** e-invoices (email inbox is sufficient; no dedicated system required)
- **January 1, 2027**: Large companies (€800K+ turnover) must **issue** e-invoices
- **January 1, 2028**: All businesses must **issue** e-invoices

**B2C exemption**: If you invoice consumers, traditional PDF invoices remain valid. E-invoicing only applies to B2B transactions between VAT-registered businesses.

## Do You Need Double-Entry Bookkeeping?

Germany's bookkeeping requirements depend on your business type — and this matters for understanding what Haiku covers.

**German law distinguishes two methods:**

| Business Type | Required Method | Haiku Sufficient? |
|---|---|---|
| Freelancer, Kleinunternehmer, GbR (below HGB thresholds) | Einnahmen-Überschuss-Rechnung (EUR) — simple income/expense recording per §4 Abs. 3 EStG | ✅ Yes |
| GmbH, AG, larger traders (above €600K revenue or €60K profit) | Doppelte Buchführung — double-entry bookkeeping per §238 HGB | ⚠️ Separate accounting software required |

**If you're a freelancer or small business** below the HGB thresholds, the simpler EUR method applies. Haiku's invoice and expense tracking — combined with the journal CSV export — fully satisfies this requirement.

**If your business is subject to §238 HGB** (typically GmbH, AG, or larger sole traders), German law requires a general ledger, chart of accounts, and formal balance sheet under the double-entry system. Haiku is an invoicing tool, not an accounting system — you will need dedicated bookkeeping software (e.g., DATEV, Lexware, Sevdesk) alongside Haiku.

**GoBD compliance** (audit trail, immutability, 10-year retention) applies to **all** German taxpayers regardless of bookkeeping method, and Haiku implements this fully for all users.

## GoBD: Digital Bookkeeping Requirements

Germany's GoBD regulations require comprehensive audit trails and immutable storage for digital financial records.

**Audit trail requirements:**
- Log all invoice access, creation, modification, and deletion
- Track user identification and precise timestamps
- Retain audit logs for 10 years
- Ensure logs are tamper-resistant

**Invoice immutability:**
- Invoices cannot be changed after issuance
- Store in original format (XML for e-invoices)
- Any corrections require credit notes or amended invoices
- Storage must be tamper-proof

**Access control:**
- User authentication required
- All access must be logged
- Role-based access recommended

For e-invoices (ZUGFeRD/XRechnung), the XML component is the legally binding document.

## Archiving, Reporting, and Penalties

**Retention**: Keep invoices for **10 years** from the end of the calendar year. Store in original format (XML for e-invoices), ensure accessibility for tax inspections, and maintain backups.

**VAT reporting:**
- Monthly/quarterly VAT returns due by the 10th of the following month
- Annual VAT return due May 31
- EC Sales List (ZM) monthly/quarterly by the 25th
- **All filing must be electronic** via the ELSTER portal

**Penalties**: GoBD non-compliance can result in fines up to €25,000, tax estimation (usually overestimated), and back payments with interest. Penalties depend on whether deficiencies distort your financial position—minor errors are usually correctable.

## What Haiku.lt Supports for Germany

Haiku.lt includes strong support for German invoicing requirements:

### Core Features ✅

- **ZUGFeRD/Factur-X format**: Every invoice includes embedded CII XML (EN 16931-compliant)
- **Sequential numbering**: Configurable formats with gap prevention
- **All mandatory fields**: Complete coverage of German invoice requirements
- **German language**: Native support for all invoice text
- **Multi-currency with EUR conversion**: International invoicing support
- **VAT rates**: 19%, 7%, and 0% calculations

### GoBD Compliance ✅ (Updated February 2026)

Haiku.lt now includes comprehensive GoBD compliance features:

- **Audit trail logging**: Tracks all invoice operations (create, update, delete, view, download) with user identification and precise timestamps
- **Immutable storage**: Original invoice data preserved in database with full documentation of any changes through audit logs
- **Access control**: User authentication and action tracking for all operations
- **Audit panel**: Review audit logs at `/app/settings/invoice-audit`
- **10-year retention**: Complete audit trail meets GoBD retention requirements

### Compliance Status: 🟢 Compliant

| Category | Status | Gap |
|----------|--------|-----|
| **B2C** | ✅ Compliant | PDF invoices with all required fields |
| **B2B Issuing** | ✅ Compliant | ZUGFeRD/EN 16931 format meets all B2B requirements |
| **B2B Receiving** | ✅ Compliant | Email inbox sufficient per BMF (mandatory since Jan 2025) |
| **GoBD** | ✅ Compliant | Audit logging and immutable storage implemented |

**E-Invoice Receiving**: Since January 2025, all German businesses must be able to receive structured e-invoices. Per the German Federal Ministry of Finance (BMF), providing an email inbox is sufficient to meet this requirement — no dedicated e-invoicing system or app feature is needed.

## Practical Takeaways

**B2C businesses**: Standard PDF invoices with all mandatory fields are sufficient. No e-invoicing required.

**B2B businesses**: Must receive e-invoices now (since Jan 2025) and issue them by 2027/2028. Haiku.lt's ZUGFeRD/EN 16931 format covers B2B issuing, and an email inbox is sufficient for receiving per BMF.

**Invoice numbering**: Use simple formats like `2026-0001` and increment sequentially. Document any gaps.

**Retention**: Keep invoices for 10 years. Cloud storage is fine if integrity and accessibility are maintained.

**VAT filing**: Set reminders for the 10th of each month (or quarterly). Late filing is a common compliance issue.

## The Bottom Line

Germany's invoicing requirements are detailed but manageable:

- **Mandatory fields**: Haiku.lt covers all required fields
- **E-invoicing**: ZUGFeRD/EN 16931 format (which Haiku.lt generates) meets all B2B issuing requirements
- **B2B receiving**: Email inbox is sufficient per BMF — no dedicated system needed
- **B2C**: PDF invoices remain valid—no e-invoicing required
- **GoBD**: Haiku.lt includes comprehensive audit logging and immutable storage (updated February 2026)
- **Retention**: Plan for 10-year archiving

Haiku.lt provides full B2B and B2C invoicing compliance for Germany, with EN 16931-compliant ZUGFeRD format, GoBD audit trail capabilities, and email-based e-invoice receiving that meets BMF requirements.

Ready to create professional, Germany-compliant invoices? Get started at [haiku.lt](https://haiku.lt).
