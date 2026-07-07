---
title: 'Google Drive-Integration'
date: '2026-05-24'
modified: '2026-05-24'
---

Haiku speichert Rechnungs-PDFs und Ausgabendateien direkt in Ihrem Google Drive — in einer einheitlichen Ordnerstruktur und mit klaren Dateinamen, damit alles ohne manuelles Sortieren geordnet bleibt.

## Drive autorisieren

1. Gehen Sie zu **Einstellungen → Google Drive**.
2. Klicken Sie auf **Google Drive verbinden** und schließen Sie die Google-Autorisierung ab.
3. Eine Bestätigung erscheint, sobald Haiku berechtigt ist, Dateien in einem eigenen Haiku-Ordner anzulegen.

Haiku schreibt ausschließlich in seinen eigenen Ordnerbaum. Andere Ordner Ihres Drive werden nicht gelesen oder aufgelistet.

## Ordnerstruktur

Dateien werden unter einem obersten Ordner `Haiku.lt` abgelegt, getrennt nach Typ und Jahr:

```
Haiku.lt
  ├── Invoices
  │     └── 2026
  │           └── INV-2026-045.pdf
  └── Expenses
        └── 2026
              └── 2026-05-12-acme-supplies.pdf
```

Der Jahresordner entsteht automatisch beim ersten Upload für dieses Jahr.

## Dateibenennung

**Rechnungen** — der Dateiname enthält Serie und Nummer (z. B. `INV-2026-045.pdf`). Erneutes Speichern nach Sperren überschreibt die vorhandene Datei, statt ein Duplikat anzulegen.

**Ausgaben** — Dateien werden mit dem Ausgabendatum und einem Kurzform-Slug von Verkäufer oder Beschreibung benannt (z. B. `2026-05-12-acme-supplies.pdf`) und sind so ohne Öffnen auffindbar.

## Wann Dateien wohin gehen

| Aktion | Datei in Drive gespeichert? |
|---|---|
| Rechnung erstellen | Nein — manuell über **PDF in Drive speichern** oder als Stapel in Multi-Edit |
| Rechnung sperren | Nein — Sperren ist unabhängig von Drive |
| Rechnung per E-Mail senden | Nein — Drive-Speicherung ist eine separate Aktion |
| Ausgabe mit „In Drive hochladen“ hinzufügen | Ja — Upload erfolgt in Schritt 3 |
| Multi-Edit → PDFs in Drive speichern | Ja — markierte Rechnungen werden im Bulk hochgeladen |
| Ausgabe löschen | Nein — Datei bleibt in Drive; **Aus Drive löschen** auf der Karte verwenden |

Diese Trennung ist Absicht: Sperren und Versenden betreffen den Buchhaltungsstatus, Drive-Speicherung dient der Archivierung. Beide können zu unterschiedlichen Zeiten geschehen.

## Bulk-Operationen

Um eine ganze Monatsmenge Rechnungen auf einmal in Drive zu speichern, nutzen Sie den [Multi-Edit-Assistenten](/de/batch-edit-invoices) — er bietet sowohl **PDFs in Google Drive speichern** als auch **Aus Google Drive löschen** als Operationen.

## Zugriff entziehen

Drive trennen: **Einstellungen → Google Drive → Trennen**. Bereits in Drive vorhandene Dateien bleiben erhalten — die Trennung verhindert nur weitere Uploads durch Haiku.

Sie können den Zugriff auch direkt bei Google entziehen: [myaccount.google.com/permissions](https://myaccount.google.com/permissions). Haiku erkennt den Entzug beim nächsten Upload-Versuch und fordert zur erneuten Verbindung auf.
