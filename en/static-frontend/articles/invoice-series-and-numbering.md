---
title: 'Invoice Series and Numbering'
date: '2026-05-23'
modified: '2026-05-23'
---

Every invoice in Haikult is identified by a **series name** and a **series number**. Together they form the invoice's unique reference. This article explains how the two work together and what rules Haikult enforces to keep your numbering valid.

## Series Name, Number, and Date

![Series fields on the new invoice form](/screenshots/invoice-series-and-numbering/en/step-1-series.png)

The **series name** is usually a short prefix — a few letters such as your initials or an abbreviation of your business name. Keep it consistent across all invoices for the same business activity so they form a single sequence.

The **series number** is generated automatically. When you start a new invoice, Haikult looks up the highest existing number for that series name and offers the next one. You can override it if needed, but Haikult will not let you save two invoices with the same series name and number — duplicate numbers are blocked.

The **invoice date** is tied to the series number. Numbers must be sequential not only in value but also in time: invoice #5 cannot be dated earlier than invoice #4 in the same series. If the date you pick would break that order, Haikult will refuse to save the invoice and prompt you to correct it.

If you run several parallel sequences — for example one for consulting work and another for product sales — simply use a different series name for each. Each name maintains its own independent numbering.
