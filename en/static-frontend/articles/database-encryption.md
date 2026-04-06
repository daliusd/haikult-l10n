---
title: 'Your Data Is Encrypted: Why It Matters'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Every Haiku.lt user database is encrypted at rest. Here's what that actually means and why you should care.

## What Encryption Means (Simply)

Imagine your invoices and client data as a diary. Encryption locks that diary and scrambles every word into random gibberish. Without the key, someone holding the diary sees nothing but noise — `X7k#mQ2$pL9@vR4...` — completely unreadable.

Each user's database gets a unique key, and Haiku.lt never stores that key in plain text.

## The Backup Scenario

Haiku.lt makes regular backups to protect against data loss. Now imagine a worst-case scenario: a hacker somehow gets hold of one of those backup files.

What do they have? A file full of scrambled gibberish. Without the encryption key, the backup is worthless to them. They cannot read your client names, invoice amounts, or any other data.

## How Strong Is "Encrypted"?

Haiku.lt uses AES-256 encryption — the same standard used by banks and governments worldwide. To brute-force an AES-256 key, an attacker would need to try 2²⁵⁶ possible combinations.

For perspective: even using every computer on Earth running at full speed, cracking a single AES-256 key would take longer than the current age of the universe. It's not a practical attack.

## The Bottom Line

If Haiku.lt's backups were ever stolen, your data would remain protected. The encryption ensures that physical possession of a backup file is meaningless without the encryption key.

Your invoices are your business. They should stay yours.
