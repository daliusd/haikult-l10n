---
title: 'Privacy Policy'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

This Privacy Policy describes how Haiku.lt collects and uses data.

## Data We Collect

- IP address, date and time, browser information.

- Email address.

- Data you enter into the system while using it.

## Cookies and Browser Storage

We use cookies and browser storage to provide essential functionality:

### Cookies

- **Authentication Cookie (auth_token)**: A secure, HTTP-only cookie used to
  maintain your login session. This cookie is essential for the service to
  function and expires after approximately 2 months. Without this cookie,
  you cannot use Haiku.lt.

### Browser Local Storage

We store the following data in your browser's local storage:

- **Language Preference**: Your selected interface language (English or Lithuanian)
  to provide immediate UI rendering.

- **Notification Dismissal**: Records whether you've dismissed certain
  notifications to avoid showing them repeatedly.

- **Account Switching Sync**: Temporary data (deleted after 1 second) used to
  synchronize account switching across multiple browser tabs.

### Browser Session Storage

- **Visit Tracking**: A session-only flag to prevent redirect loops on the
  landing page. This data is deleted when you close your browser.

### No Third-Party Tracking

We do not use any analytics, advertising, or third-party tracking cookies.
All cookies and storage are strictly necessary for the service to function.

## Third-Party Services

- **Google Services**: We integrate with Google services when you connect via Google OAuth:

  - **Google Drive** (optional): If you grant Google Drive permission, we access:
    - **What we access**: Files created by Haiku.lt in your Google Drive. We use the `drive.file` scope which provides access only to files created by our application - we cannot see or access any other files in your Drive.
    - **How we use it**: To save invoice PDFs to your Google Drive in an organized folder structure (Haiku.lt/Invoices/Year). When you use the "Save to Drive" feature, we create or update PDF files.
    - **How we store it**: We store the Google Drive file ID in our database to track which invoices have been saved and to enable updates to existing files. The actual PDF content is not stored on our servers - it exists only in your Google Drive.
    - **How we share it**: Google Drive file IDs are never shared with third parties, never sold to data brokers, and never used for advertising, marketing, AI training, or any purpose other than managing your invoice PDFs in your Drive.
    - **How to control it**: You can manage Drive permissions through your [Google Account permissions](https://myaccount.google.com/permissions). Files remain in your Drive under your control. You can delete them anytime. Revoking access stops our ability to create new files or update existing ones.
  
  - **Gmail** (optional): If you grant Gmail permission, we access:
    - **What we access**: Permission to send emails through your Gmail account. We use the `gmail.send` scope which allows sending emails on your behalf. We do not read your existing emails or access your inbox.
    - **How we use it**: To send invoice emails to your buyers when you use the "Send Invoice" feature. Emails include the invoice PDF as an attachment and optional additional attachments (like CII XML for e-invoicing).
    - **How we store it**: We do not store email content or sent message data. Sent emails appear in your Gmail "Sent" folder under your control.
    - **How we share it**: Email sending capability is never shared with third parties, never sold, and never used for advertising, marketing, spam, or any purpose other than sending invoices you explicitly choose to send.
    - **How to control it**: You can manage Gmail permissions through your [Google Account permissions](https://myaccount.google.com/permissions). Sent emails remain in your Gmail account. Revoking access stops our ability to send emails on your behalf.
  
  - **Google Calendar** (optional, read-only): If you grant calendar permission, we access:
    - **What we access**: Your calendar names, event titles, event dates/times, and attendance status (to filter out declined events). We use the Google Calendar API scope `calendar.readonly` which provides read-only access.
    - **How we use it**: Exclusively to help you create invoices based on calendar events through the "Create from Calendar" feature. Event titles become invoice line item descriptions, and event dates help set invoice date ranges.
    - **How we store it**: Calendar data is **not stored permanently** in our databases. It is fetched on-demand only when you use the calendar invoice feature and exists temporarily in your browser memory during the invoice creation process.
    - **How we share it**: Calendar data is **never shared** with third parties, **never sold** to data brokers, and **never used** for advertising, marketing, AI training, or any purpose other than creating invoices for you.
    - **How to control it**: You can manage calendar permissions independently through your [Google Account permissions](https://myaccount.google.com/permissions). Revoking access stops data access immediately. You can also disconnect your entire Google account through Haiku.lt settings.
    
  All Google OAuth permissions require your explicit authorization. You control which permissions to grant and can revoke them at any time.

- **Stripe**: We use Stripe for payment processing of premium subscriptions.
  Stripe handles all payment information securely according to their privacy
  policy. We only receive confirmation of successful payments.

- **Brevo (Sendinblue)**: We use Brevo to deliver transactional emails, including magic link login emails and invoice emails. Brevo receives the recipient email address and email content necessary to deliver these messages. Brevo is located in the EU (France). See their [Privacy Policy](https://www.brevo.com/legal/privacypolicy/).

## Data Protection

To protect collected data, we take the following measures:

- Update server software as frequently as possible.

- Update Haiku.lt software as frequently as possible.

- Properly configure servers.

## Your Rights

For detailed information about your data rights under GDPR, including the right
to access, delete, and export your data, please see our [GDPR page](/en/gdpr).
