---
title: 'Rechnungsserien und Nummerierung'
date: '2026-05-23'
modified: '2026-05-23'
---

Jede Rechnung in Haikult wird durch einen **Seriennamen** und eine **Seriennummer** eindeutig gekennzeichnet. Zusammen bilden sie die eindeutige Referenz der Rechnung. In diesem Artikel erfahren Sie, wie beide zusammenspielen und welche Regeln Haikult durchsetzt, damit Ihre Nummerierung gültig bleibt.

## Serienname, Nummer und Datum

![Serienfelder im Formular für neue Rechnungen](/screenshots/invoice-series-and-numbering/de/step-1-series.png)

Der **Serienname** ist meist ein kurzes Präfix — wenige Buchstaben wie Ihre Initialen oder eine Abkürzung Ihres Firmennamens. Verwenden Sie ihn für alle Rechnungen derselben Geschäftstätigkeit konsistent, damit sie eine zusammenhängende Folge bilden.

Die **Seriennummer** wird automatisch erzeugt. Beim Anlegen einer neuen Rechnung sucht Haikult die höchste vorhandene Nummer dieses Seriennamens und schlägt die nächste freie vor. Sie können den Wert bei Bedarf überschreiben, doch zwei Rechnungen mit demselben Seriennamen und derselben Nummer lassen sich nicht speichern — doppelte Nummern werden blockiert.

Das **Rechnungsdatum** hängt eng mit der Seriennummer zusammen. Die Nummern müssen nicht nur dem Wert nach, sondern auch zeitlich aufeinanderfolgen: Rechnung Nr. 5 darf nicht früher datiert sein als Rechnung Nr. 4 derselben Serie. Verletzt das gewählte Datum diese Reihenfolge, verweigert Haikult das Speichern und fordert Sie zur Korrektur auf.

Führen Sie mehrere parallele Sequenzen — etwa eine für Beratungsleistungen und eine weitere für Produktverkäufe —, vergeben Sie für jede einen eigenen Seriennamen. Jede Serie führt ihre Nummerierung unabhängig weiter.
