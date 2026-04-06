---
title: 'Rechnungen versenden'
date: '2021-04-15'
modified: '2026-03-28'
---

Nachdem Sie eine Rechnung erstellt haben, müssen Sie sie an den Käufer liefern.
Eine bequeme Methode ist das Versenden der PDF per E-Mail, und Haiku.lt
kann dabei helfen.

Haiku.lt unterstützt zwei Methoden zum E-Mail-Versand:

## 1. Versandmethode wählen

### Gmail (OAuth)

Wenn Sie sich mit Google angemeldet haben, kann Haiku.lt E-Mails direkt
von Ihrem Gmail-Konto über sicheres OAuth senden — keine Passwortfreigabe erforderlich.
Bei der Anmeldung müssen Sie die Berechtigung erteilen, E-Mails in Ihrem Namen zu senden.
Wenn Sie dies anfangs nicht getan haben, melden Sie sich ab und wieder an.

### SMTP

Sie können E-Mails auch über einen beliebigen SMTP-Server senden. Dies funktioniert mit jedem
E-Mail-Anbieter und ist die einzige Option für Nicht-Gmail-Nutzer.

Um SMTP zu konfigurieren, gehen Sie zu [Einstellungen → E-Mail-Anbieter-Einstellungen](/app/settings/email-provider):

1. Wenn Sie Gmail-Login verwenden, wählen Sie **SMTP** als Versandmethode.
2. Wählen Sie eine **Anbieter-Voreinstellung**, um die Servereinstellungen automatisch auszufüllen:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun oder Benutzerdefiniert
3. Füllen Sie die SMTP-Daten aus:
   - **Host** — SMTP-Serveradresse (z. B. `smtp.gmail.com`)
   - **Port** — typischerweise 587 (STARTTLS) oder 465 (SSL/TLS)
   - **Sicherheit** — STARTTLS aktualisiert eine unverschlüsselte Verbindung auf verschlüsselt; SSL/TLS ist von Anfang an verschlüsselt
   - **Benutzername** — Ihre E-Mail-Adresse
   - **Passwort** — Ihr E-Mail-Passwort oder ein app-spezifisches Passwort
   - **Absenderadresse** — die den Empfängern angezeigte Absenderadresse (z. B. `Firmenname <sie@example.com>`)
4. Klicken Sie auf **Verbindung testen**, um Ihre Einstellungen vor dem Speichern zu überprüfen.
5. Klicken Sie auf **SMTP-Einstellungen speichern**.

## 2. E-Mail-Einstellungen

In den [Einstellungen](/app/settings) können Sie Folgendes konfigurieren:

### E-Mail-Betreff

Passen Sie die E-Mail-Betreffzeile an Ihre Bedürfnisse an. Sie können diese Variablen verwenden:
- `{{invoiceNo}}` - Rechnungsnummer (z. B. INV/001)
- `{{buyer}}` - Käufername
- `{{seller}}` - Verkäufername
- `{{price}}` - Rechnungsbetrag mit Währung
- `{{invoiceDate}}` - Rechnungsdatum

### E-Mail-Vorlagen

Wählen Sie aus diesen Vorlagen:

**Einfacher Text** - einfaches Textformat, das perfekt in allen E-Mail-Clients funktioniert.

**Einfaches HTML** - schön formatierte HTML-E-Mail mit [MJML](https://mjml.io/)-Technologie.

**Mit Logo** - HTML-Vorlage mit Ihrem Firmenlogo oben.

**Mit Logo und Preis** - zeigt zusätzlich den Rechnungsbetrag in der E-Mail an.

**Mit Logo, Preis und zusätzlichen Informationen** - zeigt auch zusätzliche Informationen an.

**Mit Logo, Preis und E-Mail-Notiz** - enthält eine optionale Notiz, die Sie vor dem Versand eingeben können.

**Mit Positionen** - zeigt eine vollständige Tabelle der Rechnungspositionen (Name, Menge, Stückpreis, Gesamt) sowie den Gesamtbetrag an.

HTML-Vorlagen verwenden das [MJML](https://mjml.io/)-Format, das sicherstellt, dass E-Mails
in allen E-Mail-Clients großartig aussehen. Wenn Sie Ihre eigene Vorlage erstellen
oder eine vorhandene ändern möchten, können Sie KI um Hilfe bitten - beschreiben Sie einfach, wie Sie
möchten, dass Ihre E-Mail aussieht, und KI kann den MJML-Code für Sie generieren.

### Vorlagenvariablen

In allen Vorlagen können Sie diese Werte verwenden:

**Grundinformationen:**
- `{{issuer}}` - Person, die die Rechnung erstellt hat
- `{{invoiceNo}}` - Rechnungsnummer
- `{{buyer}}` - Käufer
- `{{seller}}` - Verkäufer
- `{{price}}` - Rechnungsbetrag
- `{{extra}}` - zusätzliche Informationen
- `{{userNote}}` - Ihre Notiz
- `{{emailNote}}` - Notiz in der E-Mail (während des Versands eingegeben)
- `{{email}}` - E-Mail des Käufers

**Daten:**
- `{{invoiceDate}}` - Rechnungsdatum
- `{{created}}` - Rechnungserstellungsdatum (gleich wie invoiceDate)

**Rechnungsdetails:**
- `{{seriesName}}` - Rechnungsserienname (z. B. "INV")
- `{{seriesId}}` - Nummer in der Serie (z. B. "001")
- `{{language}}` - Rechnungssprache (z. B. "de")

**Logo:**
- `{{logoUrl}}` - Logo-URL

**Markenfarben:**
- `{{brandPrimary}}` - Primärfarbe
- `{{brandSecondary}}` - Sekundärfarbe
- `{{brandText}}` - Textfarbe
- `{{brandTextSecondary}}` - Sekundäre Textfarbe
- `{{brandBackground}}` - Hintergrundfarbe
- `{{bodyBackground}}` - Seitenhintergrundfarbe
- `{{backgroundSecondary}}` - Sekundäre Hintergrundfarbe

### Positionen

Sie können Rechnungspositionen mit Handlebars `{{#each lineItems}}` durchlaufen:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Jede Position stellt folgende Felder bereit:
- `{{name}}` - Artikelname
- `{{amount}}` - Menge
- `{{unit}}` - roher UN/ECE-Einheitscode (z. B. `H87`)
- `{{unitName}}` - Einheit in Langform, lokalisiert (z. B. "Stück", "Kilogramm")
- `{{unitSymbol}}` - Einheit in Kurzform, lokalisiert (z. B. "Stk", "kg")
- `{{unitPrice}}` - formatierter Preis pro Einheit (z. B. "€10,00")
- `{{formattedPrice}}` - formatierter Zeilenbetrag — Menge × Stückpreis (z. B. "€30,00")
- `{{vat}}` - Mehrwertsteuersatz (falls angegeben)
- `{{vatcode}}` - Mehrwertsteuercode (falls angegeben)

### Bedingte Vorlagen

Sie können Handlebars-Bedingungen verwenden, um Inhalte nur anzuzeigen, wenn ein Wert vorhanden ist:

```
{{#if extra}}
  <mj-text>Zusätzliche Informationen: {{extra}}</mj-text>
{{/if}}
```

Dies ist besonders nützlich, wenn Sie einen zusätzlichen Informationsblock
nur anzeigen möchten, wenn er tatsächlich ausgefüllt ist.

### Markenfarben und Logo

In den Einstellungen können Sie auch:
- Ihr Logo hochladen
- Markenfarben ändern

## 3. Rechnung versenden

1. Geben Sie die E-Mail-Adresse des Käufers in der Rechnung an
2. Klicken Sie auf die Schaltfläche "Rechnung senden"
3. Die Rechnung wird als gesperrt markiert und versendet

Die Rechnung wird von Ihrem Gmail-Konto mit der ausgewählten Vorlage versendet.
