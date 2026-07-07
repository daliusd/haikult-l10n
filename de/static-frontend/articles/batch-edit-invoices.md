---
title: 'Mehrere Rechnungen im Bulk bearbeiten'
date: '2026-05-24'
modified: '2026-05-24'
---

Wenn Sie viele Rechnungen auf einmal bearbeiten möchten — versenden, PDFs in Google Drive speichern, einen Stapel als bezahlt markieren, Beträge ändern — führt der **Multi-Edit**-Assistent die Operation im Bulk mit einem einzigen Prüfschritt aus.

## Assistenten öffnen

![Multi-Edit-Seite](/screenshots/batch-edit-invoices/de/step-1-multi-edit.png)

Klicken Sie auf der Rechnungsseite auf **Multi-Edit**. Der Assistent öffnet sich unter **/invoices/multi-edit**.

## Schritt 1 — Operation und Filter wählen

Der erste Schritt zeigt Übersichtswerte (Gesamt, nicht versendet, unbezahlt usw.) und erlaubt das Filtern der Liste nach Zeitraum und Rechnungstyp. Wählen Sie die Operation:

- **Neue Rechnungen im Bulk erstellen** — öffnet den Ablauf zum Erstellen aus dem Kalender.
- **Nicht versendete Rechnungen versenden** — verschickt PDF und Links per E-Mail an die Kunden.
- **Als bezahlt markieren** — setzt das Bezahlt-Flag und (optional) ein Zahlungsdatum.
- **PDFs in Google Drive speichern** — lädt in Ihren Drive-Ordner hoch.
- **Aus Google Drive löschen** — entfernt die PDF-Kopie (die Rechnung bleibt in Haiku).
- **Betrag ändern** — wendet eine prozentuale oder feste Anpassung auf Positionen an.
- **Aus System löschen** — entfernt die ausgewählten Rechnungen endgültig.

## Schritt 2 — Rechnungen auswählen

Die gefilterte Liste erscheint mit Kontrollkästchen. Markieren Sie die gewünschten Zeilen oder nutzen Sie das Kopfzeilen-Kontrollkästchen, um alle auszuwählen. Gesperrte Rechnungen können nicht bearbeitet oder im Betrag geändert werden und werden für diese Operationen automatisch ausgeschlossen.

## Schritt 3 — Operation konfigurieren

Jede Operation hat ihr eigenes Konfigurationsformular:

- **Versenden**: E-Mail-Vorlage wählen, bei Bedarf Betreff/Text überschreiben.
- **Als bezahlt markieren**: Zahlungsdatum wählen.
- **In Drive speichern**: den Zielordner bestätigen (standardmäßig `Haiku.lt/Invoices/YYYY/`).
- **Betrag ändern**: Prozentsatz oder festen Differenzbetrag eingeben und entscheiden, ob MwSt. einbezogen wird.
- **Löschen**: bestätigen.

Klicken Sie auf **Anwenden**, um die Operation auszuführen. Ein Fortschrittsbalken zeigt jede Rechnung während der Verarbeitung an.

## Schritt 4 — Ergebnisse

Eine Zusammenfassung listet erfolgreiche und fehlgeschlagene Zeilen auf. Bei Fehlern wird der Grund angezeigt (gesperrte Rechnung, fehlende E-Mail, abgelaufene Drive-Autorisierung usw.), sodass Sie sie korrigieren und erneut ausführen können.

## Was nicht im Bulk geändert werden kann

- **Gesperrte Rechnungen** — die Sperre ist ein bewusstes Signal, dass eine Rechnung final ist. Einzeln entsperren.
- **Käufer- oder Verkäuferdaten** — sind je Rechnung individuell und werden im Bulk nicht angeboten, um versehentliches Überschreiben zu vermeiden.
- **Rechnungsnummern und -serien** — werden über [Rechnungsserien und Nummerierung](/de/invoice-series-and-numbering) verwaltet.

## Zusammenspiel mit Auto-Programmen

Wenn Sie die [Zusatzinfo-Programmierung](/de/extra-info-programming) nutzen, wird jedes Programm mit `// AUTO` ganz oben beim Bulk-Bearbeiten erneut ausgeführt und das Zusatzinfo-Feld für jede Rechnung im Stapel neu berechnet. Das ist der richtige Ort, um dynamische Inhalte (z. B. aktualisierte Zahlungsbedingungen) für einen ganzen Monat an Rechnungen in einem Rutsch neu auszuwerten.
