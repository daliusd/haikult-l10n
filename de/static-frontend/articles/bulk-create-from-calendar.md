---
title: 'Rechnungen massenhaft aus Google Kalender erstellen'
date: '2026-05-24'
modified: '2026-05-24'
---

Der Assistent „Aus Kalender erstellen" verwandelt Google-Kalender-Termine in vier Schritten in Rechnungen. Jeder eindeutige Termintitel wird zu einer Rechnung, und die Anzahl der Termine ergibt die Menge.

## Wie Termine zu Rechnungen werden

Der Assistent gruppiert Termine nach Titel und wendet diese Logik an:

- Alle Termine mit demselben Titel werden zu einer Rechnung zusammengefasst.
- Die Anzahl der Termine ergibt die Menge.
- Termine ohne Titel und von Ihnen abgelehnte Termine werden übersprungen.
- Wiederkehrende Termine werden aufgelöst — jeder Termin zählt einzeln.
- Käuferdaten (E-Mail, Land, USt-IdNr., Sprache, letzter Preis) werden aus früheren Rechnungen mit demselben Namen vorausgefüllt.

## Voraussetzungen

- Ein Haiku.lt-Konto (kostenlos bis 500 Rechnungen).
- Ein Google Kalender mit Terminen, deren Titel konsistent vergeben sind — meist der Kundenname.
- Google-Kalender-Berechtigung, die bei der Anmeldung mit Google erteilt wird.

Der Kalenderinhalt wird nur temporär während des Assistenten gelesen und nicht gespeichert.

## Schritt 1 — Assistent öffnen

![Aus-Kalender-Assistent](/screenshots/bulk-create-from-calendar/de/step-1-wizard.png)

Klicken Sie im Dashboard auf **Aus Kalender erstellen**. Der vierstufige Assistent öffnet sich.

## Schritt 2 — Import konfigurieren

| Feld | Was eingeben |
|---|---|
| Kalender | Welcher Google Kalender ausgelesen wird. Der Hauptkalender ist mit „(Hauptkalender)" markiert. |
| Zeitraum | Der abzurechnende Zeitraum. Standard: aktueller Monat. Der Assistent zeigt live an, wie viele Termine im Zeitraum liegen. |
| Rechnungsserie | Der Seriencode (z. B. `THERAPIE`, `COACHING`). Vorschläge aus Ihren letzten Serien. |
| Verkäufer | Ihr Verkäuferblock — wird aus der letzten Rechnung dieser Serie übernommen. |
| Aussteller | Die unterzeichnende Person oder Rolle — wird ebenfalls vorausgefüllt. |
| Positionsname | Was abgerechnet wird (z. B. „Therapiesitzung"). Beim Tippen erscheinen Vorschläge aus Ihrer Historie. |
| Standardpreis | Der reguläre Satz. Wird für Kunden ohne hinterlegten Preis verwendet. |
| MwSt. % | Nur sichtbar, wenn MwSt. in den Einstellungen aktiviert ist. |
| Einheit | Standard „Stück"; aus der Auswahl auch „Stunden" oder andere. |

Sobald die Pflichtfelder ausgefüllt sind und der Assistent mindestens einen Termin findet, wird **Weiter** aktiv.

## Schritt 3 — Prüfen und bearbeiten

Es erscheint eine Tabelle mit einer Zeile pro eindeutigem Termintitel. Jede Spalte ist editierbar:

- **Käufername** — der Termintitel; anpassen, falls Ihr Kalender informelle Namen verwendet.
- **Menge** — Anzahl der gefundenen Termine.
- **E-Mail**, **Land**, **USt-IdNr.** — aus der Rechnungshistorie vorausgefüllt, sofern vorhanden.
- **Rechnungssprache** — 39 Optionen; voreingestellt mit der zuletzt für den Käufer verwendeten Sprache.
- **Preis** — aus der letzten Rechnung dieser Käufer-/Positionskombination; sonst der Standardpreis.

Sie können:

- Eine Zeile entfernen, um einen Kunden in diesem Lauf zu überspringen.
- Einen Käufer manuell mit **+ Käufer hinzufügen** ergänzen (z. B. eine Sitzung außerhalb des Kalenders).
- Jede Zelle anpassen, um Einzelfälle zu korrigieren.

Wenn die Tabelle stimmt, klicken Sie auf **N Rechnungen erstellen**.

## Schritt 4 — Erstellung und Ergebnisse

Ein Fortschrittsbalken zeigt „Rechnung X von Y wird erstellt…" während jede Rechnung generiert wird. Die meisten Stapel dauern deutlich unter zwei Minuten.

Der Ergebnisbildschirm meldet:

- **Erfolgreich** — erstellte Rechnungen mit Serie, Nummer und Link „Ansehen".
- **Fehlgeschlagen** — Zeilen, die nicht erstellt werden konnten, mit dem Grund (Validierung, Plan-Limit erreicht usw.).

Von hier können Sie zum Dashboard zurückkehren, den Assistenten erneut starten oder zu **Multi-Edit** wechseln, um Rechnungen gesammelt zu versenden, PDFs in Google Drive zu speichern, zu sperren oder als bezahlt zu markieren — siehe [Rechnungen versenden und PDFs in Google Drive speichern](/de/google-drive-integration).

## Tipps

- **Konsistente Termintitel sind wichtig** — „Marie Dubois" und „marie dubois" gelten als unterschiedliche Kunden.
- **Eigener Abrechnungskalender** verhindert, dass private Termine mit hineinrutschen.
- **Termine ablehnen, die nicht abgerechnet werden sollen** — abgelehnte Termine werden automatisch ausgeschlossen.
- **Assistenten je Leistungstyp einzeln ausführen**, wenn Sie unterschiedliche Leistungen zu unterschiedlichen Sätzen abrechnen (z. B. Einzel- vs. Gruppensitzungen).
