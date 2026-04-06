---
title: 'DSGVO - Ihre Datenrechte'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt verpflichtet sich, Ihre personenbezogenen Daten zu schützen und Ihre Datenschutzrechte gemäß der Datenschutz-Grundverordnung (DSGVO) zu respektieren. Diese Seite erklärt Ihre Rechte und wie wir mit Ihren Daten umgehen.

## Ihre Datenrechte

Gemäß DSGVO haben Sie folgende Rechte bezüglich Ihrer personenbezogenen Daten:

### Auskunftsrecht

Sie haben das Recht, auf alle personenbezogenen Daten zuzugreifen, die wir über Sie speichern. Sie können Ihre Daten jederzeit exportieren:

- **Vollständiger Datenbankexport**: Laden Sie Ihre vollständige Datenbank einschließlich aller Rechnungen, Einstellungen und Audit-Logs aus Ihren Kontoeinstellungen herunter.
- **Rechnungsexport**: Exportieren Sie Ihre Rechnungen im CSV-Format, gefiltert nach Datumsbereich und Serienname.

### Recht auf Löschung (Recht auf Vergessenwerden)

Sie haben das Recht, die Löschung Ihrer personenbezogenen Daten zu beantragen. Sie können Ihr gesamtes Konto und alle zugehörigen Daten jederzeit über Ihre Kontoeinstellungen löschen. Diese Aktion ist dauerhaft und kann nicht rückgängig gemacht werden.

### Recht auf Datenübertragbarkeit

Sie können Ihre Daten in maschinenlesbaren Formaten exportieren:

- SQLite-Datenbankformat (vollständiger Datenexport)
- CSV-Format (Rechnungsdatenexport)

Dies ermöglicht es Ihnen, Ihre Daten auf einen anderen Dienst zu übertragen, wenn Sie dies wünschen.

### Recht auf Berichtigung

Sie haben das Recht, ungenaue oder unvollständige personenbezogene Daten zu korrigieren. Sie können alle Ihre Daten direkt in der Anwendung bearbeiten, einschließlich:

- Rechnungsdetails
- Käufer- und Verkäuferinformationen
- Ihre persönlichen Präferenzen und Einstellungen

### Recht auf Einschränkung der Verarbeitung

Sie haben das Recht, unter bestimmten Umständen die Einschränkung der Verarbeitung Ihrer personenbezogenen Daten zu verlangen. Kontaktieren Sie uns über die unten stehende E-Mail, um dieses Recht auszuüben.

### Widerspruchsrecht

Sie haben das Recht, der Verarbeitung Ihrer personenbezogenen Daten für bestimmte Zwecke zu widersprechen. Da Haiku.lt Ihre Daten ausschließlich zur Bereitstellung des von Ihnen angeforderten Rechnungsdienstes verarbeitet, würde ein Widerspruch gegen die Verarbeitung uns daran hindern, den Dienst bereitzustellen.

## Datenspeicherung

Ihre Daten werden aufbewahrt, **bis Sie Ihr Konto löschen**. Wir löschen inaktive Konten nicht automatisch. Sie haben die volle Kontrolle darüber, wann Ihre Daten entfernt werden.

Wenn Sie Ihr Konto löschen, werden alle Ihre Daten dauerhaft aus unseren Systemen entfernt.

## Verantwortlicher

Der Verantwortliche für Haiku.lt ist:

**Dalius Dobravolskas**

Für datenschutzbezogene Fragen oder zur Ausübung Ihrer Datenrechte kontaktieren Sie:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Serverstandort

Alle Haiku.lt-Server und Datenspeicher befinden sich in der **Europäischen Union, speziell in Deutschland**. Ihre Daten verlassen die EU nicht, es sei denn, Sie autorisieren ausdrücklich Drittanbieter-Integrationen (siehe Auftragsverarbeiter unten).

## Rechtsgrundlage für die Verarbeitung

Wir verarbeiten Ihre personenbezogenen Daten auf Grundlage von:

- **Vertragserfüllung**: Zur Bereitstellung des Rechnungsdienstes, für den Sie sich angemeldet haben
- **Berechtigtes Interesse**: Zur Aufrechterhaltung der Dienstsicherheit, Betrugsprävention und Verbesserung des Dienstes
- **Einwilligung**: Für optionale Funktionen wie Google Drive- und Gmail-Integration

## Auftragsverarbeiter

Haiku.lt nutzt folgende Drittanbieterdienste, um unsere Funktionalität bereitzustellen:

### Google LLC

**Genutzte Dienste**: OAuth 2.0-Authentifizierung, Google Drive API, Gmail API, Google Calendar API

**Geteilte Daten**: E-Mail-Adresse, Name, OAuth-Tokens (nur wenn Sie die Google-Integration autorisieren)

**Zweck**: Um Ihnen Folgendes zu ermöglichen:
- **Authentifizierung** mit Ihrem Google-Konto über OAuth 2.0
- **Google Drive** (Bereich: `drive.file`): Rechnungs-PDFs in Ihrem Drive in organisierten Ordnern (Haiku.lt/Invoices/Year) speichern. Wir können nur auf Dateien zugreifen, die von unserer Anwendung erstellt wurden, nicht auf Ihre anderen Drive-Dateien. Wir speichern Drive-Datei-IDs, um gespeicherte Rechnungen zu verfolgen.
- **Gmail** (Bereich: `gmail.send`): Rechnungs-E-Mails in Ihrem Namen an Käufer senden. Wir lesen Ihren Posteingang oder vorhandene E-Mails nicht. Gesendete E-Mails erscheinen in Ihrem Gmail-Ordner "Gesendet".
- **Google Calendar** (Bereich: `calendar.readonly`, optional): Kalenderereignistitel, -daten, -zeiten und Teilnahmestatus lesen, um beim Erstellen von Rechnungen zu helfen. Diese Daten werden vorübergehend abgerufen und nicht dauerhaft gespeichert.

**Datenspeicherung**: 
- Drive-Datei-IDs: In unserer Datenbank gespeichert, bis Sie die Rechnung löschen oder Ihr Google-Konto trennen
- Kalenderdaten: Nicht gespeichert (nur bei Bedarf abgerufen)
- Gmail-Daten: Nicht gespeichert (E-Mails verbleiben in Ihrem Gmail-Konto)
- OAuth-Tokens: Verschlüsselt und gespeichert, bis Sie Ihr Konto trennen

**Datenschutzrichtlinie**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Standort**: Vereinigte Staaten (mit EU-US Data Privacy Framework-Konformität)

### Stripe, Inc.

**Genutzte Dienste**: Zahlungsabwicklung für Abonnements

**Geteilte Daten**: E-Mail-Adresse, Zahlungsinformationen (direkt von Stripe verarbeitet)

**Zweck**: Verarbeitung von Abonnementzahlungen für Premium-Funktionen

**Datenschutzrichtlinie**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Standort**: Vereinigte Staaten (mit EU-US Data Privacy Framework-Konformität)

### Brevo (Sendinblue)

**Genutzte Dienste**: Transaktionaler E-Mail-Versand

**Geteilte Daten**: E-Mail-Adresse des Empfängers, E-Mail-Inhalt (Magic-Link-Tokens für die Anmeldung; Rechnungsdetails beim Versenden von Rechnungen über Brevo)

**Zweck**: Zur Zustellung von Authentifizierungs-E-Mails (Magic-Link-Anmeldung) und Rechnungs-E-Mails an Käufer

**Datenspeicherung**: Brevo kann gesendete E-Mail-Protokolle für einen begrenzten Zeitraum gemäß ihrer Richtlinie aufbewahren. Wir speichern E-Mail-Inhalte nicht länger auf unseren Servern als nötig, um sie zu versenden.

**Datenschutzrichtlinie**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Standort**: Europäische Union (Frankreich)

## Datensicherheit

Wir ergreifen geeignete technische und organisatorische Maßnahmen zum Schutz Ihrer personenbezogenen Daten:

- Verschlüsselung sensibler Daten (OAuth-Tokens, Refresh-Tokens)
- Sichere HTTPS-Verbindungen
- HTTP-only, sichere Authentifizierungs-Cookies
- Regelmäßige Software-Updates
- Benutzerbezogene Datenbankisolierung
- Audit-Protokollierung zur Verfolgung von Kontozugriffen

## Benachrichtigung bei Datenschutzverletzungen

Im unwahrscheinlichen Fall einer Datenschutzverletzung, die ein Risiko für Ihre Rechte und Freiheiten darstellt, werden wir Sie und die zuständige Aufsichtsbehörde innerhalb von 72 Stunden benachrichtigen, wie von der DSGVO gefordert.

## Aufsichtsbehörde

Wenn Sie Bedenken hinsichtlich der Handhabung Ihrer personenbezogenen Daten haben, haben Sie das Recht, bei Ihrer lokalen Datenschutz-Aufsichtsbehörde Beschwerde einzulegen.

Für Benutzer in Deutschland ist die Aufsichtsbehörde:

**Bundesbeauftragter für den Datenschutz und die Informationsfreiheit**  
Website: [https://www.bfdi.bund.de](https://www.bfdi.bund.de)

## Aktualisierungen dieser Richtlinie

Wir können diese DSGVO-Informationsseite von Zeit zu Zeit aktualisieren. Das Datum "geändert" oben auf dieser Seite gibt an, wann sie zuletzt aktualisiert wurde.

Für allgemeine Datenschutzinformationen siehe unsere [Datenschutzrichtlinie](/de/privacy).
