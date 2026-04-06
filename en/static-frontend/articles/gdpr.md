---
title: 'GDPR - Your Data Rights'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt is committed to protecting your personal data and respecting your privacy rights under the General Data Protection Regulation (GDPR). This page explains your rights and how we handle your data.

## Your Data Rights

Under GDPR, you have the following rights regarding your personal data:

### Right to Access

You have the right to access all personal data we hold about you. You can export your data at any time:

- **Full database export**: Download your complete database including all invoices, settings, and audit logs from your account settings.
- **Invoice export**: Export your invoices as CSV format, filtered by date range and series name.

### Right to Erasure (Right to be Forgotten)

You have the right to request deletion of your personal data. You can delete your entire account and all associated data at any time through your account settings. This action is permanent and cannot be undone.

### Right to Data Portability

You can export your data in machine-readable formats:

- SQLite database format (complete data export)
- CSV format (invoice data export)

This allows you to transfer your data to another service if you choose.

### Right to Rectification

You have the right to correct inaccurate or incomplete personal data. You can edit all your data directly in the application, including:

- Invoice details
- Buyer and seller information
- Your personal preferences and settings

### Right to Restriction of Processing

You have the right to request restriction of processing your personal data in certain circumstances. Contact us using the email below to exercise this right.

### Right to Object

You have the right to object to processing of your personal data for specific purposes. Since Haiku.lt processes your data solely to provide the invoicing service you requested, objecting to processing would prevent us from providing the service.

## Data Retention

Your data is kept **until you delete your account**. We do not automatically delete inactive accounts. You are in full control of when your data is removed.

When you delete your account, all your data is permanently removed from our systems.

## Data Controller

The data controller for Haiku.lt is:

**Dalius Dobravolskas**

For privacy-related questions or to exercise your data rights, contact:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Server Location

All Haiku.lt servers and data storage are located in the **European Union, specifically in Germany**. Your data does not leave the EU unless you explicitly authorize third-party integrations (see Subprocessors below).

## Legal Basis for Processing

We process your personal data based on:

- **Contract performance**: To provide the invoicing service you signed up for
- **Legitimate interest**: To maintain service security, prevent fraud, and improve the service
- **Consent**: For optional features like Google Drive and Gmail integration

## Subprocessors

Haiku.lt uses the following third-party services to provide our functionality:

### Google LLC

**Services used**: OAuth 2.0 Authentication, Google Drive API, Gmail API, Google Calendar API

**Data shared**: Email address, name, OAuth tokens (only when you authorize Google integration)

**Purpose**: To enable you to:
- **Authenticate** with your Google account using OAuth 2.0
- **Google Drive** (scope: `drive.file`): Save invoice PDFs to your Drive in organized folders (Haiku.lt/Invoices/Year). We can only access files created by our application, not your other Drive files. We store Drive file IDs to track saved invoices.
- **Gmail** (scope: `gmail.send`): Send invoice emails to buyers on your behalf. We do not read your inbox or existing emails. Sent emails appear in your Gmail "Sent" folder.
- **Google Calendar** (scope: `calendar.readonly`, optional): Read calendar event titles, dates, times, and attendance status to help create invoices. This data is fetched temporarily and not stored permanently.

**Data Retention**: 
- Drive file IDs: Stored in our database until you delete the invoice or disconnect your Google account
- Calendar data: Not stored (fetched on-demand only)
- Gmail data: Not stored (emails remain in your Gmail account)
- OAuth tokens: Encrypted and stored until you disconnect your account

**Privacy Policy**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Location**: United States (with EU-US Data Privacy Framework compliance)

### Stripe, Inc.

**Services used**: Payment processing for subscriptions

**Data shared**: Email address, payment information (handled directly by Stripe)

**Purpose**: To process subscription payments for premium features

**Privacy Policy**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Location**: United States (with EU-US Data Privacy Framework compliance)

### Brevo (Sendinblue)

**Services used**: Transactional email delivery

**Data shared**: Recipient email address, email content (magic link tokens for login; invoice details when sending invoices via Brevo)

**Purpose**: To deliver authentication emails (magic link login) and invoice emails to buyers

**Data Retention**: Brevo may retain sent email logs for a limited period per their policy. We do not store email content on our servers beyond what is needed to send it.

**Privacy Policy**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Location**: European Union (France)

## Data Security

We take appropriate technical and organizational measures to protect your personal data:

- Encryption of sensitive data (OAuth tokens, refresh tokens)
- Secure HTTPS connections
- HTTP-only, secure authentication cookies
- Regular software updates
- Per-user database isolation
- Audit logging for account access tracking

## Data Breach Notification

In the unlikely event of a data breach that poses a risk to your rights and freedoms, we will notify you and the relevant supervisory authority within 72 hours as required by GDPR.

## Supervisory Authority

If you have concerns about how we handle your personal data, you have the right to lodge a complaint with your local data protection supervisory authority.

For users in Lithuania, the supervisory authority is:

**State Data Protection Inspectorate**  
Website: [https://vdai.lrv.lt](https://vdai.lrv.lt)

## Updates to This Policy

We may update this GDPR information page from time to time. The "modified" date at the top of this page indicates when it was last updated.

For general privacy information, see our [Privacy Policy](/en/privacy).
