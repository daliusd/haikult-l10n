---
title: 'E-Mail-Einrichtung: Gmail (OAuth)'
date: '2026-05-23'
modified: '2026-05-23'
---

Wenn Sie sich bei Haikult mit Ihrem Google-Konto anmelden, können Sie Rechnungen direkt von Ihrer echten Gmail-Adresse über OAuth versenden. Ihre Kunden sehen die vertraute Absenderadresse im Posteingang, Antworten landen wieder im gewohnten Gmail-Verlauf, und die Gmail-Authentifizierung (SPF, DKIM, DMARC) funktioniert einwandfrei, weil die E-Mail tatsächlich aus Ihrem Konto stammt. Haikult erhält nie Ihr Passwort, und Sie können den Zugriff jederzeit widerrufen.

## Was OAuth für Sie bedeutet

OAuth ist die moderne, sichere Methode, mit der eine Anwendung im Namen einer anderen handeln darf. Statt Haikult Ihr Gmail-Passwort zu geben, erteilen Sie über den Einwilligungsdialog von Google selbst eine einzige, eng umrissene Berechtigung – *E-Mails in Ihrem Namen senden*. Haikult sieht das Passwort nie, und die Berechtigung lässt sich jederzeit zurückziehen.

## Gmail-Zugriff erteilen

Wenn Sie sich bei Haikult mit Google anmelden, zeigt Google die von Haikult angeforderten Berechtigungen an. Darunter ist die Berechtigung, E-Mails in Ihrem Namen zu senden. Klicken Sie auf **Zulassen**, um sie zu erteilen. Diese Autorisierung ist einmalig — danach kann Haikult Rechnungen aus Ihrem Gmail-Konto versenden, sobald Sie auf **Rechnung senden** klicken.

## Falls Sie die Berechtigung nicht erteilt haben

Wenn Sie sich angemeldet, die Berechtigung zum E-Mail-Versand aber übersprungen oder abgelehnt haben, kann Haikult nicht über Gmail senden. Die Lösung ist einfach: **Melden Sie sich ab und wieder an** mit Google. Achten Sie im Einwilligungsdialog darauf, dass die Berechtigung zum E-Mail-Versand angehakt bleibt, und klicken Sie auf **Zulassen**.

## Zugriff widerrufen

Die Kontrolle über die Berechtigung liegt bei Ihnen. Um Haikult den Versand aus Ihrem Gmail-Konto zu entziehen, öffnen Sie die [Sicherheitseinstellungen Ihres Google-Kontos](https://myaccount.google.com/permissions), suchen Sie Haikult in der Liste der verbundenen Apps und klicken Sie auf **Zugriff entfernen**. Sie können die Berechtigung später erneut erteilen, indem Sie sich wieder anmelden.

## Wann Sie stattdessen SMTP nutzen sollten

Gmail OAuth ist die einfachste und sicherste Option für Google-Konten. Wenn Sie kein Gmail nutzen oder lieber über einen anderen Anbieter senden (Outlook, den Mailserver Ihrer Domain, SendGrid, Mailgun usw.), verwenden Sie SMTP. Die vollständigen Konfigurationsschritte finden Sie unter [E-Mail-Einrichtung: SMTP](/de/email-setup-smtp).
