---
title: 'Datenschutzerklärung'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Diese Datenschutzerklärung beschreibt, wie Haiku.lt Daten sammelt und verwendet.

## Daten, die wir sammeln

- IP-Adresse, Datum und Uhrzeit, Browserinformationen.

- E-Mail-Adresse.

- Daten, die Sie während der Nutzung in das System eingeben.

## Cookies und Browser-Speicher

Wir verwenden Cookies und Browser-Speicher, um wesentliche Funktionen bereitzustellen:

### Cookies

- **Authentifizierungs-Cookie (auth_token)**: Ein sicheres, HTTP-only Cookie, das verwendet wird, um
  Ihre Login-Sitzung aufrechtzuerhalten. Dieses Cookie ist für die Funktion des Dienstes
  unerlässlich und läuft nach etwa 2 Monaten ab. Ohne dieses Cookie
  können Sie Haiku.lt nicht verwenden.

### Browser-Lokalspeicher

Wir speichern die folgenden Daten im Lokalspeicher Ihres Browsers:

- **Sprachpräferenz**: Ihre ausgewählte Oberflächensprache (Englisch oder Litauisch)
  für sofortige UI-Darstellung.

- **Ausblenden von Benachrichtigungen**: Speichert, ob Sie bestimmte
  Benachrichtigungen ausgeblendet haben, um sie nicht wiederholt anzuzeigen.

- **Kontowechsel-Synchronisierung**: Temporäre Daten (nach 1 Sekunde gelöscht), die verwendet werden, um
  Kontowechsel über mehrere Browser-Tabs zu synchronisieren.

### Browser-Sitzungsspeicher

- **Besuchsverfolgung**: Ein nur für die Sitzung gültiges Flag, um Weiterleitungsschleifen auf der
  Landingpage zu verhindern. Diese Daten werden gelöscht, wenn Sie Ihren Browser schließen.

### Keine Drittanbieter-Verfolgung

Wir verwenden keine Analyse-, Werbe- oder Drittanbieter-Tracking-Cookies.
Alle Cookies und Speicher sind für die Funktion des Dienstes unbedingt erforderlich.

## Drittanbieter-Dienste

- **Google-Dienste**: Wir integrieren Google-Dienste, wenn Sie sich über Google OAuth verbinden:

  - **Google Drive** (optional): Wenn Sie die Google Drive-Berechtigung erteilen, greifen wir zu:
    - **Auf was wir zugreifen**: Dateien, die von Haiku.lt in Ihrem Google Drive erstellt wurden. Wir verwenden den `drive.file`-Bereich, der nur Zugriff auf Dateien bietet, die von unserer Anwendung erstellt wurden - wir können keine anderen Dateien in Ihrem Drive sehen oder darauf zugreifen.
    - **Wie wir es verwenden**: Um Rechnungs-PDFs in Ihrem Google Drive in einer organisierten Ordnerstruktur (Haiku.lt/Invoices/Year) zu speichern. Wenn Sie die Funktion „In Drive speichern" verwenden, erstellen oder aktualisieren wir PDF-Dateien.
    - **Wie wir es speichern**: Wir speichern die Google Drive-Datei-ID in unserer Datenbank, um zu verfolgen, welche Rechnungen gespeichert wurden und um Aktualisierungen bestehender Dateien zu ermöglichen. Der tatsächliche PDF-Inhalt wird nicht auf unseren Servern gespeichert - er existiert nur in Ihrem Google Drive.
    - **Wie wir es teilen**: Google Drive-Datei-IDs werden niemals mit Dritten geteilt, niemals an Datenbroker verkauft und niemals für Werbung, Marketing, KI-Training oder einen anderen Zweck als die Verwaltung Ihrer Rechnungs-PDFs in Ihrem Drive verwendet.
    - **Wie Sie es kontrollieren**: Sie können Drive-Berechtigungen über Ihre [Google-Konto-Berechtigungen](https://myaccount.google.com/permissions) verwalten. Dateien bleiben unter Ihrer Kontrolle in Ihrem Drive. Sie können sie jederzeit löschen. Das Widerrufen des Zugriffs stoppt unsere Fähigkeit, neue Dateien zu erstellen oder bestehende zu aktualisieren.
  
  - **Gmail** (optional): Wenn Sie die Gmail-Berechtigung erteilen, greifen wir zu:
    - **Auf was wir zugreifen**: Berechtigung zum Senden von E-Mails über Ihr Gmail-Konto. Wir verwenden den `gmail.send`-Bereich, der das Senden von E-Mails in Ihrem Namen ermöglicht. Wir lesen Ihre vorhandenen E-Mails nicht und greifen nicht auf Ihren Posteingang zu.
    - **Wie wir es verwenden**: Um Rechnungs-E-Mails an Ihre Käufer zu senden, wenn Sie die Funktion „Rechnung senden" verwenden. E-Mails enthalten die Rechnungs-PDF als Anhang und optionale zusätzliche Anhänge (wie CII-XML für E-Invoicing).
    - **Wie wir es speichern**: Wir speichern keine E-Mail-Inhalte oder gesendeten Nachrichtendaten. Gesendete E-Mails erscheinen in Ihrem Gmail-Ordner „Gesendet" unter Ihrer Kontrolle.
    - **Wie wir es teilen**: Die E-Mail-Versandfähigkeit wird niemals mit Dritten geteilt, niemals verkauft und niemals für Werbung, Marketing, Spam oder einen anderen Zweck als das Senden von Rechnungen verwendet, die Sie ausdrücklich senden möchten.
    - **Wie Sie es kontrollieren**: Sie können Gmail-Berechtigungen über Ihre [Google-Konto-Berechtigungen](https://myaccount.google.com/permissions) verwalten. Gesendete E-Mails bleiben in Ihrem Gmail-Konto. Das Widerrufen des Zugriffs stoppt unsere Fähigkeit, E-Mails in Ihrem Namen zu senden.
  
  - **Google Calendar** (optional, schreibgeschützt): Wenn Sie die Kalenderberechtigung erteilen, greifen wir zu:
    - **Auf was wir zugreifen**: Ihre Kalendernamen, Ereignistitel, Ereignisdaten/-zeiten und Teilnahmestatus (um abgelehnte Ereignisse herauszufiltern). Wir verwenden den Google Calendar API-Bereich `calendar.readonly`, der schreibgeschützten Zugriff bietet.
    - **Wie wir es verwenden**: Ausschließlich, um Ihnen zu helfen, Rechnungen basierend auf Kalenderereignissen über die Funktion „Aus Kalender erstellen" zu erstellen. Ereignistitel werden zu Rechnungszeilenbeschreibungen, und Ereignisdaten helfen beim Festlegen von Rechnungszeiträumen.
    - **Wie wir es speichern**: Kalenderdaten werden **nicht dauerhaft** in unseren Datenbanken gespeichert. Sie werden bei Bedarf nur abgerufen, wenn Sie die Kalenderrechnungsfunktion verwenden und existieren vorübergehend im Speicher Ihres Browsers während des Rechnungserstellungsprozesses.
    - **Wie wir es teilen**: Kalenderdaten werden **niemals** mit Dritten geteilt, **niemals** an Datenbroker verkauft und **niemals** für Werbung, Marketing, KI-Training oder einen anderen Zweck als das Erstellen von Rechnungen für Sie verwendet.
    - **Wie Sie es kontrollieren**: Sie können Kalenderberechtigungen unabhängig über Ihre [Google-Konto-Berechtigungen](https://myaccount.google.com/permissions) verwalten. Das Widerrufen des Zugriffs stoppt den Datenzugriff sofort. Sie können Ihr gesamtes Google-Konto auch über die Haiku.lt-Einstellungen trennen.
    
  Alle Google OAuth-Berechtigungen erfordern Ihre ausdrückliche Autorisierung. Sie kontrollieren, welche Berechtigungen Sie erteilen und können sie jederzeit widerrufen.

- **Stripe**: Wir verwenden Stripe für die Zahlungsabwicklung von Premium-Abonnements.
  Stripe verarbeitet alle Zahlungsinformationen sicher gemäß seiner Datenschutzerklärung.
  Wir erhalten nur Bestätigungen über erfolgreiche Zahlungen.

- **Brevo (Sendinblue)**: Wir verwenden Brevo zur Zustellung von Transaktions-E-Mails, einschließlich Magic-Link-Anmelde-E-Mails und Rechnungs-E-Mails. Brevo erhält die E-Mail-Adresse des Empfängers und den E-Mail-Inhalt, der zur Zustellung dieser Nachrichten erforderlich ist. Brevo befindet sich in der EU (Frankreich). Siehe ihre [Datenschutzerklärung](https://www.brevo.com/legal/privacypolicy/).

## Datenschutz

Um gesammelte Daten zu schützen, ergreifen wir folgende Maßnahmen:

- Aktualisierung der Server-Software so häufig wie möglich.

- Aktualisierung der Haiku.lt-Software so häufig wie möglich.

- Ordnungsgemäße Konfiguration der Server.

## Ihre Rechte

Ausführliche Informationen über Ihre Datenrechte gemäß DSGVO, einschließlich des Rechts
auf Zugriff, Löschung und Export Ihrer Daten, finden Sie auf unserer [DSGVO-Seite](/de/gdpr).
