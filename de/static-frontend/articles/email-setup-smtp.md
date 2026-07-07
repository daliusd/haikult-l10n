---
title: 'E-Mail-Einrichtung: SMTP'
date: '2026-05-23'
modified: '2026-05-23'
---

SMTP (Simple Mail Transfer Protocol) ist der universelle Standard für den E-Mail-Versand. Verwenden Sie SMTP, wenn Sie sich bei Haikult nicht mit Google anmelden oder wenn Rechnungen über einen bestimmten Server gehen sollen — den Mailhost Ihrer Domain, Outlook, SendGrid, Mailgun oder einen beliebigen anderen Anbieter. Falls Sie Gmail OAuth nutzen, ist [E-Mail-Einrichtung: Gmail (OAuth)](/de/email-setup-gmail) die einfachere und sicherere Wahl für Google-Konten.

## SMTP-Server konfigurieren

![SMTP-Formular auf der Seite „E-Mail-Anbieter"](/screenshots/email-setup-smtp/de/step-1-smtp-form.png)

Öffnen Sie **Einstellungen → E-Mail-Anbieter**. Die Seite zeigt das SMTP-Formular direkt an. Wenn Sie sich ursprünglich mit Google angemeldet haben, wechseln Sie zunächst zur Option **SMTP**.

Beginnen Sie mit der **Anbieter-Vorlage** — die Auswahl von Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid oder Mailgun füllt Serveradresse, Port und Sicherheitseinstellungen für Sie aus. Wählen Sie **Custom**, falls Ihr Anbieter nicht aufgeführt ist.

Füllen Sie anschließend die übrigen Felder aus:

- **Host** — die SMTP-Serveradresse (zum Beispiel `smtp.gmail.com`).
- **Port** — üblicherweise 587 (STARTTLS) oder 465 (SSL/TLS). Die Vorlage trifft das meist richtig.
- **Security** — wählen Sie zwischen STARTTLS, das eine offene Verbindung verschlüsselt nachrüstet, und SSL/TLS, das vom ersten Byte an verschlüsselt ist. Verwenden Sie die von Ihrem Anbieter angegebene Einstellung.
- **Username** — meist Ihre vollständige E-Mail-Adresse.
- **Password** — Ihr Kontopasswort oder ein anwendungsspezifisches Passwort, falls Ihr Anbieter eines verlangt (Gmail und Yahoo verlangen es).
- **From address** — der für Empfänger sichtbare Absender, zum Beispiel `Company Name <you@example.com>`.

## Verbindung testen

Klicken Sie vor dem Speichern auf **Test Connection**. Haikult versucht, den Server zu erreichen, sich zu authentifizieren und meldet das Ergebnis. Schlägt der Test fehl, weist die Fehlermeldung meist auf die wahrscheinliche Ursache hin — falscher Port, ungültige Anmeldedaten oder eine Sicherheitsabweichung.

## Speichern und Versand starten

Sobald der Test erfolgreich ist, klicken Sie auf **Save SMTP Settings**. Ab diesem Moment wird jede versendete Rechnung über Ihren SMTP-Server verschickt.

Siehe auch: [E-Mail-Einrichtung: Gmail (OAuth)](/de/email-setup-gmail).
