---
title: 'Email Setup: Gmail (OAuth)'
date: '2026-05-23'
modified: '2026-05-23'
---

If you sign in to Haikult with your Google account, you can send invoices directly from your real Gmail address using OAuth. Your clients see your familiar email in their inbox, replies land back in your normal Gmail thread, and Gmail's authentication (SPF, DKIM, DMARC) works correctly because the email genuinely comes from your account. No password is ever shared with Haikult, and you can revoke access at any time.

## What OAuth Means for You

OAuth is the modern, secure way for one application to act on behalf of another. Instead of giving Haikult your Gmail password, you grant a single, narrow permission — *send email on your behalf* — through Google's own consent screen. Haikult never sees your password, and the permission can be withdrawn whenever you choose.

## Authorize Gmail Access

When you sign in to Haikult with Google, Google shows you the list of permissions Haikult is requesting. Among them is the permission to send emails on your behalf. Click **Allow** to grant it. This is a one-time authorization — once granted, Haikult can send invoices from your Gmail account whenever you press **Send invoice**.

## If You Did Not Grant the Permission

If you signed in but skipped or denied the email-sending permission, Haikult will not be able to send through Gmail. The fix is straightforward: **sign out and sign in again** with Google. On the consent screen, make sure the email-sending permission stays checked, then click **Allow**.

## Revoking Access

You stay in control of the permission. To remove Haikult's ability to send from your Gmail account, open your [Google Account security settings](https://myaccount.google.com/permissions), find Haikult in the list of connected apps, and click **Remove access**. You can re-authorize later by signing in again.

## When to Use SMTP Instead

Gmail OAuth is the simplest and most secure option for Google accounts. If you do not use Gmail, or you prefer to send through another provider (Outlook, your domain's mail server, SendGrid, Mailgun, and so on), use SMTP instead. See [Email Setup: SMTP](/en/email-setup-smtp) for the full configuration steps.
