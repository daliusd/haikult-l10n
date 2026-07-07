---
title: 'Fälligkeitsdaten und Zahlungsbedingungen'
date: '2026-05-23'
modified: '2026-05-23'
---

Auf den meisten Rechnungen muss angegeben sein, bis wann die Zahlung erwartet wird. Haikult speichert für jede Rechnung ein Fälligkeitsdatum und lässt Sie festlegen, wie dieses standardmäßig berechnet wird. Dieser Artikel beschreibt das Fälligkeitsfeld im Rechnungsformular, die Standardberechnung und wie sich die Zahlungsbedingungen auf der erzeugten PDF anzeigen lassen.

## Das Fälligkeitsfeld

![Fälligkeitsfeld im Bereich „Zusätzlich“ des Formulars für neue Rechnungen](/screenshots/due-dates-and-payment-terms/de/step-1-due-date-field.png)

Das **Fälligkeitsdatum** befindet sich im Bereich „Zusätzlich“ des Rechnungsformulars, direkt neben dem Aussteller und den Notizen. Beim Anlegen einer neuen Rechnung füllt Haikult dieses Feld anhand Ihrer Standardvorgabe (siehe unten) vor. Den Wert können Sie jederzeit für eine einzelne Rechnung anpassen — etwa um einem bestimmten Kunden eine längere Zahlungsfrist einzuräumen oder das Datum komplett zu entfernen, wenn kein Termin gilt.

Intern wird das Fälligkeitsdatum als gewöhnliches Kalenderdatum gespeichert. Haikult markiert überfällige Rechnungen in der Rechnungsliste anhand dieses Werts — ein korrekter Eintrag hilft also, verspätete Zahlungen auf einen Blick zu erkennen.

## Standardvorgabe festlegen

![Standardfälligkeit auf der Seite mit den Rechnungseinstellungen](/screenshots/due-dates-and-payment-terms/de/step-2-due-date-default.png)

Die Standardfälligkeit wird auf der Seite **Rechnungseinstellungen** konfiguriert. Vier Modi stehen zur Auswahl:

- **Keine** — es wird kein Fälligkeitsdatum automatisch gesetzt; Sie tragen es jedes Mal selbst ein.
- **Tage ab Rechnungsdatum** — fügt dem Rechnungsdatum eine feste Anzahl Tage hinzu (standardmäßig 30). Das ist die häufigste Wahl für Zahlungsziele wie 14 oder 30 Tage.
- **Tag des Monats** — wählt einen bestimmten Tag im Monat, beispielsweise den 10. Liegt das Rechnungsdatum hinter diesem Tag, springt die Fälligkeit auf denselben Tag im Folgemonat.
- **Monatsende** — der letzte Tag des Rechnungsmonats.

Welcher Modus auch gewählt wird — das Ergebnis ist nur ein Vorschlag, den Sie auf jeder Rechnung weiterhin anpassen können.

## Zahlungsbedingungen auf der Rechnungs-PDF anzeigen

Das Fälligkeitsdatum wird mit der Rechnung gespeichert, erscheint aber nicht automatisch auf der PDF. Um eine Zeile wie „Bitte zahlen Sie bis 2026-06-22“ auf dem Dokument selbst auszugeben, nutzen Sie das Feld **Zusätzliche Informationen** auf der Rechnung. Sie können dort beliebigen Text manuell eintragen oder das Feld von Haikult mithilfe des Zusatzinformationsprogramms automatisch befüllen lassen.

Das Programm hat Zugriff auf eine Variable `dueDate`, sodass ein kleines Snippet wie:

```js
// AUTO
if (dueDate) {
  globalThis.result = `Bitte zahlen Sie bis ${formatDate(dueDate)}`;
}
```

die Zahlungszeile auf jeder Rechnung mit dem Fälligkeitsdatum synchronisiert. Eine ausführliche Anleitung — inklusive sprachabhängiger Texte und Kombinationen mit Zahlungsarten — finden Sie im Artikel [Zusätzliche Informationsprogrammierung](/de/extra-info-programming).
