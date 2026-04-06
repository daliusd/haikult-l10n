---
title: 'Sending Invoices'
date: '2021-04-15'
modified: '2026-03-28'
---

After creating an invoice, you need to deliver it to the buyer.
One convenient method is to send the PDF via email, and Haiku.lt
can help with this.

Haiku.lt supports two ways to send emails:

## 1. Choose an Email Sending Method

### Gmail (OAuth)

If you signed in with Google, Haiku.lt can send emails directly
from your Gmail account using secure OAuth — no password sharing required.
When signing in, you must grant permission to send emails on your behalf.
If you didn't do this initially, sign out and sign in again.

### SMTP

You can also send emails via any SMTP server. This works with any
email provider and is the only option for non-Gmail users.

To configure SMTP, go to [Settings → Email Provider Settings](/app/settings/email-provider):

1. If you use Gmail login, select **SMTP** as your sending method.
2. Choose a **provider preset** to auto-fill the server settings:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun, or Custom
3. Fill in the SMTP details:
   - **Host** — SMTP server address (e.g., `smtp.gmail.com`)
   - **Port** — typically 587 (STARTTLS) or 465 (SSL/TLS)
   - **Security** — STARTTLS upgrades a plain connection to encrypted; SSL/TLS is encrypted from the start
   - **Username** — your email address
   - **Password** — your email password or app-specific password
   - **From address** — the sender address shown to recipients (e.g., `Company Name <you@example.com>`)
4. Click **Test Connection** to verify your settings before saving.
5. Click **Save SMTP Settings**.

## 2. Email Settings

In [Settings](/app/settings) you can configure:

### Email Subject

Customize the email subject line to fit your needs. You can use these variables:
- `{{invoiceNo}}` - invoice number (e.g., INV/001)
- `{{buyer}}` - buyer name
- `{{seller}}` - seller name
- `{{price}}` - invoice amount with currency
- `{{invoiceDate}}` - invoice date

### Email Templates

Choose from these templates:

**Plain text** - simple text format that works perfectly in all email clients.

**Simple HTML** - beautifully formatted HTML email using [MJML](https://mjml.io/) technology.

**With logo** - HTML template with your company logo at the top.

**With logo and price** - additionally displays the invoice amount in the email.

**With logo, price and additional info** - also displays additional information.

**With logo, price and email note** - includes an optional per-send note you can type before sending.

**With line items** - displays a full table of invoice line items (name, quantity, unit price, total) along with the grand total.

HTML templates use the [MJML](https://mjml.io/) format, which ensures emails
look great across all email clients. If you want to create your own template
or modify an existing one, you can ask AI for help - just describe how you
want your email to look, and AI can generate the MJML code for you.

### Template Variables

In all templates you can use these values:

**Basic information:**
- `{{issuer}}` - person who created the invoice
- `{{invoiceNo}}` - invoice number
- `{{buyer}}` - buyer
- `{{seller}}` - seller
- `{{price}}` - invoice amount
- `{{extra}}` - additional information
- `{{userNote}}` - your note
- `{{emailNote}}` - note in the email (entered during sending)
- `{{email}}` - buyer's email

**Dates:**
- `{{invoiceDate}}` - invoice date
- `{{created}}` - invoice creation date (same as invoiceDate)

**Invoice details:**
- `{{seriesName}}` - invoice series name (e.g., "INV")
- `{{seriesId}}` - number in series (e.g., "001")
- `{{language}}` - invoice language ("lt" or "en")

**Logo:**
- `{{logoUrl}}` - logo URL

**Brand colors:**
- `{{brandPrimary}}` - primary color
- `{{brandSecondary}}` - secondary color
- `{{brandText}}` - text color
- `{{brandTextSecondary}}` - secondary text color
- `{{brandBackground}}` - background color
- `{{bodyBackground}}` - page background color
- `{{backgroundSecondary}}` - secondary background color

### Line Items

You can loop over invoice line items using Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Each line item exposes:
- `{{name}}` - item name
- `{{amount}}` - quantity
- `{{unit}}` - raw UN/ECE unit code (e.g., `H87`)
- `{{unitName}}` - unit long form, localized (e.g., "piece", "kilogram")
- `{{unitSymbol}}` - unit short form, localized (e.g., "pc", "kg")
- `{{unitPrice}}` - formatted price per unit (e.g., "€10.00")
- `{{formattedPrice}}` - formatted line total — amount × unit price (e.g., "€30.00")
- `{{vat}}` - VAT percentage (if set)
- `{{vatcode}}` - VAT code (if set)

### Conditional Templates

You can use Handlebars conditions to show content only when a value exists:

```
{{#if extra}}
  <mj-text>Additional information: {{extra}}</mj-text>
{{/if}}
```

This is especially useful when you want to display an additional information
block only when it's actually filled in.

### Brand Colors and Logo

In settings you can also:
- Upload your logo
- Change brand colors

## 3. Sending the Invoice

1. Specify the buyer's email address in the invoice
2. Click the "Send invoice" button
3. The invoice will be marked as locked and sent

The invoice will be sent from your Gmail account using the selected template.
