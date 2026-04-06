---
title: 'Ihre Daten sind verschlüsselt: Warum das wichtig ist'
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Jede Haiku.lt-Benutzerdatenbank ist im Ruhezustand verschlüsselt. Hier erfahren Sie, was das bedeutet und warum Sie das wissen sollten.

## Was Verschlüsselung bedeutet (einfach)

Stellen Sie sich Ihre Rechnungen und Kundendaten wie ein Tagebuch vor. Die Verschlüsselung sperrt dieses Tagebuch und verwandelt jedes Wort in ein zufälliges Kauderwelsch. Ohne den Schlüssel sieht jemand, der das Tagebuch in der Hand hält, nichts als Rauschen — `X7k#mQ2$pL9@vR4...` — völlig unlesbar.

Die Datenbank eines jeden Benutzers erhält einen eindeutigen Schlüssel, und Haiku.lt speichert diesen Schlüssel niemals im Klartext.

## Das Backup-Szenario

Haiku.lt macht regelmäßig Backups, um sich vor Datenverlust zu schützen. Stellen Sie sich nun ein Worst-Case-Szenario vor: Ein Hacker gelangt irgendwie in den Besitz einer dieser Sicherungsdateien.

Und was haben sie? Eine Datei voller verschlüsseltem Kauderwelsch. Ohne den Verschlüsselungsschlüssel ist die Sicherung für den Hacker wertlos. Sie können weder Ihre Kundennamen noch Rechnungsbeträge oder andere Daten lesen.

## Wie stark ist „verschlüsselt"?

Haiku.lt verwendet eine AES-256-Verschlüsselung — der gleiche Standard, der weltweit von Banken und Regierungen verwendet wird. Um einen AES-256-Schlüssel zu erzwingen, müsste ein Angreifer 2²⁵⁶ mögliche Kombinationen ausprobieren.

Zur Veranschaulichung: Selbst wenn alle Computer auf der Erde mit voller Geschwindigkeit laufen würden, würde das Knacken eines einzigen AES-256-Schlüssels länger dauern als das derzeitige Alter des Universums. Es ist kein praktischer Angriff.

## Die Quintessenz

Sollten die Backups von Haiku.lt jemals gestohlen werden, wären Ihre Daten weiterhin geschützt. Die Verschlüsselung sorgt dafür, dass der physische Besitz einer Sicherungsdatei ohne den Verschlüsselungsschlüssel bedeutungslos ist.

Ihre Rechnungen sind Ihr Geschäft. Sie sollten Ihre bleiben.
