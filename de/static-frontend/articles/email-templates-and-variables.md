---
title: 'E-Mail-Vorlagen und Variablen'
date: '2026-05-24'
modified: '2026-05-24'
---

Wenn Haikult eine Rechnung per E-Mail verschickt, werden sowohl die Betreffzeile als auch der Nachrichtentext aus Vorlagen erzeugt, die Sie selbst steuern. Dieser Artikel deckt alle Teile dieses Vorlagensystems ab: Betreffanpassung, die mitgelieferten Textvorlagen, die vollständige Variablenreferenz sowie Schleifen und Bedingungen für eigene MJML-Vorlagen.

Wenn Sie den E-Mail-Versand noch nicht eingerichtet haben, beginnen Sie mit [E-Mail-Einrichtung: Gmail (OAuth)](/de/email-setup-gmail) oder [E-Mail-Einrichtung: SMTP](/de/email-setup-smtp).

## Wo konfiguriert wird

Alle Vorlageneinstellungen befinden sich auf der [E-Mail-Einstellungsseite](/app/settings/email). Dort finden Sie den Betreff, die Vorlagenauswahl, das optionale Bearbeiten der Vorlagentexte sowie Logo und Markenfarben (siehe [Markenanpassung](/de/brand-customization)).

## Betreffzeile

Die Betreffzeile kann eine feste Zeichenkette sein oder eine Handlebars-artige Vorlage mit diesen Variablen:

- `{{invoiceNo}}` — Rechnungsnummer (z. B. `INV/001`)
- `{{buyer}}` — Käufername
- `{{seller}}` — Verkäufername
- `{{price}}` — Rechnungsbetrag mit Währung
- `{{invoiceDate}}` — Rechnungsdatum

Beispiel: `Rechnung {{invoiceNo}} von {{seller}} — {{price}}`.

## Mitgelieferte Textvorlagen

Wählen Sie eine Vorlage je nachdem, wie reichhaltig die E-Mail wirken soll:

- **Einfacher Text** — schlichtes Textformat, das in jedem E-Mail-Client zuverlässig angezeigt wird.
- **Einfaches HTML** — formatierte HTML-Nachricht auf Basis von [MJML](https://mjml.io/).
- **Mit Logo** — HTML-Vorlage mit Ihrem Firmenlogo oben.
- **Mit Logo und Preis** — zeigt zusätzlich den Rechnungsbetrag.
- **Mit Logo, Preis und Zusatzinformationen** — zeigt zusätzlich das Feld mit Zusatzinformationen.
- **Mit Logo, Preis und E-Mail-Notiz** — enthält eine optionale Notiz, die Sie vor dem Versand eingeben.
- **Mit Positionen** — enthält eine vollständige Tabelle der Rechnungspositionen (Name, Menge, Stückpreis, Summe) plus Gesamtbetrag.

Alle HTML-Vorlagen verwenden das MJML-Format und werden in Gmail, Outlook, Apple Mail, mobilen Clients und weiteren E-Mail-Programmen sauber dargestellt. Wenn Sie eine eigene Vorlage möchten, können Sie MJML selbst schreiben oder ein KI-Werkzeug bitten, eine Vorlage anhand Ihrer Beschreibung zu erzeugen.

## Vorlagenvariablen

Jede Vorlage — eingebaut oder eigen — hat Zugriff auf denselben Satz an Variablen.

**Grundinformationen:**

- `{{issuer}}` — Person, die die Rechnung erstellt hat
- `{{invoiceNo}}` — Rechnungsnummer
- `{{buyer}}` — Käufer
- `{{seller}}` — Verkäufer
- `{{price}}` — Rechnungsbetrag
- `{{extra}}` — Feld mit Zusatzinformationen
- `{{userNote}}` — interne Notiz der Rechnung
- `{{emailNote}}` — beim Versenden eingegebene Notiz
- `{{email}}` — E-Mail-Adresse des Käufers

**Daten:**

- `{{invoiceDate}}` — Rechnungsdatum
- `{{created}}` — Erstellungsdatum der Rechnung (identisch mit `invoiceDate`)

**Rechnungsdetails:**

- `{{seriesName}}` — Serienname (z. B. `INV`)
- `{{seriesId}}` — Nummer innerhalb der Serie (z. B. `001`)
- `{{language}}` — Rechnungssprache (`lt`, `en` usw.)

**Logo:**

- `{{logoUrl}}` — URL Ihres hochgeladenen Logos

**Markenfarben:**

- `{{brandPrimary}}`, `{{brandSecondary}}` — Primär- und Sekundärfarbe der Marke
- `{{brandText}}`, `{{brandTextSecondary}}` — Text- und sekundäre Textfarbe
- `{{brandBackground}}`, `{{bodyBackground}}`, `{{backgroundSecondary}}` — Hintergrundfarben

Wie Sie diese setzen, steht unter [Markenanpassung](/de/brand-customization).

## Schleife über Positionen

Um Rechnungspositionen im Mailtext aufzulisten, verwenden Sie Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Pro Durchlauf stehen folgende Felder bereit:

- `{{name}}` — Artikelname
- `{{amount}}` — Menge
- `{{unit}}` — roher UN/ECE-Einheitscode (z. B. `H87`)
- `{{unitName}}` — Einheit in Langform, lokalisiert (z. B. „Stück", „Kilogramm")
- `{{unitSymbol}}` — Einheit in Kurzform, lokalisiert (z. B. „Stk", „kg")
- `{{unitPrice}}` — formatierter Preis pro Einheit (z. B. `€10,00`)
- `{{formattedPrice}}` — formatierter Zeilenbetrag (Menge × Stückpreis)
- `{{vat}}` — Mehrwertsteuersatz, falls gesetzt
- `{{vatcode}}` — Mehrwertsteuercode, falls gesetzt

## Bedingte Blöcke

Mit Handlebars `{{#if}}` zeigen Sie einen Block nur an, wenn der Wert gesetzt ist:

```
{{#if extra}}
  <mj-text>Zusätzliche Informationen: {{extra}}</mj-text>
{{/if}}
```

Besonders nützlich für optionale Felder wie `extra`, `userNote` und `emailNote` — so wirkt die E-Mail aufgeräumt, gleichgültig welche Felder ausgefüllt sind.

Siehe auch: [E-Mail-Einrichtung: Gmail (OAuth)](/de/email-setup-gmail), [E-Mail-Einrichtung: SMTP](/de/email-setup-smtp), [Markenanpassung](/de/brand-customization).
