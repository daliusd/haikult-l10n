---
title: 'Email Templates and Variables'
date: '2026-05-24'
modified: '2026-05-24'
---

When Haikult sends an invoice email, both the subject line and the email body are rendered from templates you control. This article covers every part of that templating system: subject customization, the built-in body templates, the full variable reference, and how to use loops and conditionals to build a custom MJML template.

If you haven't configured email delivery yet, start with [Email Setup: Gmail (OAuth)](/en/email-setup-gmail) or [Email Setup: SMTP](/en/email-setup-smtp).

## Where to configure

All template settings live on the [Email settings page](/app/settings/email). You'll find the subject line, the template picker, optional per-template body editing, and the logo and brand-color controls (covered in [Brand customization](/en/brand-customization)).

## Email subject

The subject line can be a fixed string or a Handlebars-style template using these variables:

- `{{invoiceNo}}` — invoice number (e.g. `INV/001`)
- `{{buyer}}` — buyer name
- `{{seller}}` — seller name
- `{{price}}` — invoice amount with currency
- `{{invoiceDate}}` — invoice date

For example: `Invoice {{invoiceNo}} from {{seller}} — {{price}}`.

## Built-in body templates

Pick a template based on how rich you want the email to look:

- **Plain text** — simple text format that displays perfectly in every email client.
- **Simple HTML** — formatted HTML email built with [MJML](https://mjml.io/).
- **With logo** — HTML template with your company logo at the top.
- **With logo and price** — also displays the invoice amount.
- **With logo, price and additional info** — also displays the extra-info field.
- **With logo, price and email note** — includes an optional per-send note you can type before sending.
- **With line items** — includes a full table of line items (name, quantity, unit price, total) plus the grand total.

All HTML templates use the MJML format, which renders well across Gmail, Outlook, Apple Mail, mobile clients, and more. If you'd like a custom template, you can write your own MJML or ask an AI tool to generate one based on a description.

## Template variables

Every template — built-in or custom — has access to the same set of variables.

**Basic information:**

- `{{issuer}}` — person who created the invoice
- `{{invoiceNo}}` — invoice number
- `{{buyer}}` — buyer
- `{{seller}}` — seller
- `{{price}}` — invoice amount
- `{{extra}}` — additional information field
- `{{userNote}}` — internal note from the invoice
- `{{emailNote}}` — note typed at send time
- `{{email}}` — buyer's email

**Dates:**

- `{{invoiceDate}}` — invoice date
- `{{created}}` — invoice creation date (same value as `invoiceDate`)

**Invoice details:**

- `{{seriesName}}` — series name (e.g. `INV`)
- `{{seriesId}}` — number within the series (e.g. `001`)
- `{{language}}` — invoice language (`lt`, `en`, etc.)

**Logo:**

- `{{logoUrl}}` — URL of your uploaded logo

**Brand colors:**

- `{{brandPrimary}}`, `{{brandSecondary}}` — primary and secondary brand colors
- `{{brandText}}`, `{{brandTextSecondary}}` — text and secondary text colors
- `{{brandBackground}}`, `{{bodyBackground}}`, `{{backgroundSecondary}}` — background colors

See [Brand customization](/en/brand-customization) for how to set these.

## Line items loop

To list invoice line items in the email body, loop over them with Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Each iteration exposes:

- `{{name}}` — item name
- `{{amount}}` — quantity
- `{{unit}}` — raw UN/ECE unit code (e.g. `H87`)
- `{{unitName}}` — unit long form, localized (e.g. "piece", "kilogram")
- `{{unitSymbol}}` — unit short form, localized (e.g. "pc", "kg")
- `{{unitPrice}}` — formatted price per unit (e.g. `€10.00`)
- `{{formattedPrice}}` — formatted line total (amount × unit price)
- `{{vat}}` — VAT percentage, if set
- `{{vatcode}}` — VAT code, if set

## Conditional sections

Use Handlebars `{{#if}}` to render a block only when the value is set:

```
{{#if extra}}
  <mj-text>Additional information: {{extra}}</mj-text>
{{/if}}
```

This is especially useful for optional fields like `extra`, `userNote`, and `emailNote` so the email looks tidy regardless of which fields are filled in.

See also: [Email Setup: Gmail (OAuth)](/en/email-setup-gmail), [Email Setup: SMTP](/en/email-setup-smtp), [Brand customization](/en/brand-customization).
