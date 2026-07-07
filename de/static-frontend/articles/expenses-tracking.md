---
title: 'Ausgabenverwaltung'
date: '2026-03-22'
modified: '2026-05-24'
---

Haiku verwaltet Geschäftsausgaben gemeinsam mit Ihren Rechnungen. Laden Sie eine Eingangsrechnung oder Quittung hoch, lassen Sie die Daten möglichst automatisch extrahieren und halten Sie Ihre Dateien in Haiku und/oder Google Drive geordnet.

## Die Ausgabenseite

![Ausgabenseite](/screenshots/expenses-tracking/de/step-1-expenses-list.png)

Die **Ausgaben**-Seite listet alle erfassten Posten und bietet Schnellzugriff zum Bearbeiten, Löschen, Öffnen der gespeicherten Datei oder Herunterladen des Originals.

Filter:

- **Zeitraum** — auf einen Monat, ein Quartal oder einen eigenen Zeitraum eingrenzen.
- **Suche nach Beschreibung** — Ausgabe per Stichwort finden.
- **Laufende Summe** — Anzahl und Summe der zum aktuellen Filter passenden Ausgaben oben auf der Seite.

Jede Karte zeigt Beschreibung, Verkäufer, Betrag, Datum und Speicherstatus (Haiku, Drive oder beides).

## Eine Ausgabe hinzufügen

Klicken Sie auf der Ausgabenseite auf **Neue Ausgabe**. Ein vierstufiger Assistent öffnet sich.

### Schritt 1 — Dokument hochladen

Datei per Drag-and-drop oder Auswahl hochladen. Unterstützte Formate: **PDF**, **JPEG**, **PNG**, **XML** — geeignet für gescannte Quittungen und elektronische Rechnungen.

### Schritt 2 — Automatisches Auslesen

Ist die Datei eine standardisierte elektronische Rechnung (Factur-X PDF, in Frankreich und Deutschland üblich; e-invoice XML), extrahiert Haiku:

- Rechnungsnummer
- Verkäufername
- Positionen
- Gesamtbetrag
- Rechnungsdatum

Bei gescannten Bildern oder unstrukturierten PDFs öffnet sich das Formular leer; die Daten geben Sie selbst ein.

### Schritt 3 — Prüfen, bearbeiten und Speicherort wählen

Ein vorausgefülltes Formular erscheint. Korrigieren Sie, was nicht stimmt, und wählen Sie, wo die Datei abgelegt wird:

- **In Haiku hochladen** — Dateien bis 2 MB, sicher in Ihrem Konto gespeichert.
- **In Google Drive hochladen** — wird in einen eigenen Ordner Ihres Drive gesendet (erfordert Autorisierung — siehe [Google Drive-Integration](/de/google-drive-integration)).

Sie können eins, beides oder nichts wählen. Der Ausgaben-Eintrag selbst wird unabhängig davon gespeichert.

### Schritt 4 — Gespeichert

Bestätigung erscheint. Von hier können Sie eine weitere Ausgabe hinzufügen oder zur Liste zurückkehren.

## Bearbeiten und Löschen

Jede Ausgabe hat einen **Bearbeiten**-Knopf, mit dem Sie jedes Feld aktualisieren können — Beschreibung, Verkäufer, Betrag, Datum, Positionen, Speicherwahl. Der **Löschen**-Knopf entfernt den Eintrag nach einer Bestätigung.

Das Löschen einer Ausgabe löscht nicht die Google-Drive-Datei. Wenn Sie auch die Cloud-Kopie entfernen möchten, nutzen Sie zuerst **Aus Drive löschen** auf der Karte.

## Intelligentes Rechnungsauslesen

Haiku liest Rechnungen in den in Europa gebräuchlichen elektronischen Formaten:

- **Factur-X / ZUGFeRD** PDFs — bei deutschen und französischen Lieferanten verbreitet.
- **UBL / Peppol / EN 16931** XML — der EU-Standard für E-Rechnungen.

Bei nicht unterstützten Formaten oder Fotos bleiben die Felder in Schritt 3 leer und werden manuell ausgefüllt.
