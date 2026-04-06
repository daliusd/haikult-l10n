---
title: 'Envoyer des factures'
date: '2021-04-15'
modified: '2026-03-28'
---

Après avoir créé une facture, vous devez la remettre à l'acheteur.
Une méthode pratique consiste à envoyer le PDF par email, et Haiku.lt peut vous aider avec cela.

Haiku.lt prend en charge deux méthodes d'envoi d'emails :

## 1. Choisir une méthode d'envoi d'email

### Gmail (OAuth)

Si vous vous êtes connecté avec Google, Haiku.lt peut envoyer des emails directement
depuis votre compte Gmail via OAuth sécurisé — aucun partage de mot de passe requis.
Lors de la connexion, vous devez accorder l'autorisation d'envoyer des emails en votre nom.
Si vous ne l'avez pas fait initialement, déconnectez-vous et reconnectez-vous.

### SMTP

Vous pouvez également envoyer des emails via n'importe quel serveur SMTP. Cela fonctionne avec
n'importe quel fournisseur d'email et est la seule option pour les utilisateurs non-Gmail.

Pour configurer SMTP, accédez à [Paramètres → Paramètres du fournisseur d'email](/app/settings/email-provider) :

1. Si vous utilisez la connexion Gmail, sélectionnez **SMTP** comme méthode d'envoi.
2. Choisissez un **préréglage de fournisseur** pour remplir automatiquement les paramètres du serveur :
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun ou Personnalisé
3. Renseignez les détails SMTP :
   - **Hôte** — adresse du serveur SMTP (par ex. `smtp.gmail.com`)
   - **Port** — généralement 587 (STARTTLS) ou 465 (SSL/TLS)
   - **Sécurité** — STARTTLS met à niveau une connexion non chiffrée vers chiffrée ; SSL/TLS est chiffré dès le départ
   - **Nom d'utilisateur** — votre adresse email
   - **Mot de passe** — votre mot de passe email ou un mot de passe spécifique à l'application
   - **Adresse d'expéditeur** — l'adresse expéditeur affichée aux destinataires (par ex. `Nom de l'entreprise <vous@example.com>`)
4. Cliquez sur **Tester la connexion** pour vérifier vos paramètres avant de sauvegarder.
5. Cliquez sur **Enregistrer les paramètres SMTP**.

## 2. Paramètres d'email

Dans les [Paramètres](/app/settings), vous pouvez configurer :

### Objet de l'email

Personnalisez la ligne d'objet de l'email selon vos besoins. Vous pouvez utiliser ces variables :
- `{{invoiceNo}}` - numéro de facture (par exemple, INV/001)
- `{{buyer}}` - nom de l'acheteur
- `{{seller}}` - nom du vendeur
- `{{price}}` - montant de la facture avec devise
- `{{invoiceDate}}` - date de facture

### Modèles d'email

Choisissez parmi ces modèles :

**Texte brut** - format de texte simple qui fonctionne parfaitement dans tous les clients de messagerie.

**HTML simple** - email HTML magnifiquement formaté utilisant la technologie [MJML](https://mjml.io/).

**Avec logo** - modèle HTML avec le logo de votre entreprise en haut.

**Avec logo et prix** - affiche en plus le montant de la facture dans l'email.

**Avec logo, prix et informations supplémentaires** - affiche également des informations supplémentaires.

**Avec logo, prix et note email** - inclut une note facultative que vous pouvez saisir avant l'envoi.

**Avec lignes de facturation** - affiche un tableau complet des lignes de la facture (nom, quantité, prix unitaire, total) ainsi que le total général.

Les modèles HTML utilisent le format [MJML](https://mjml.io/), qui garantit que les emails sont superbes sur tous les clients de messagerie. Si vous souhaitez créer votre propre modèle ou modifier un modèle existant, vous pouvez demander de l'aide à l'IA - décrivez simplement comment vous voulez que votre email apparaisse, et l'IA peut générer le code MJML pour vous.

### Variables de modèle

Dans tous les modèles, vous pouvez utiliser ces valeurs :

**Informations de base :**
- `{{issuer}}` - personne qui a créé la facture
- `{{invoiceNo}}` - numéro de facture
- `{{buyer}}` - acheteur
- `{{seller}}` - vendeur
- `{{price}}` - montant de la facture
- `{{extra}}` - informations supplémentaires
- `{{userNote}}` - votre note
- `{{emailNote}}` - note dans l'email (saisie lors de l'envoi)
- `{{email}}` - email de l'acheteur

**Dates :**
- `{{invoiceDate}}` - date de facture
- `{{created}}` - date de création de la facture (identique à invoiceDate)

**Détails de la facture :**
- `{{seriesName}}` - nom de série de la facture (par exemple, "INV")
- `{{seriesId}}` - numéro dans la série (par exemple, "001")
- `{{language}}` - langue de la facture ("lt" ou "en")

**Logo :**
- `{{logoUrl}}` - URL du logo

**Couleurs de marque :**
- `{{brandPrimary}}` - couleur primaire
- `{{brandSecondary}}` - couleur secondaire
- `{{brandText}}` - couleur du texte
- `{{brandTextSecondary}}` - couleur du texte secondaire
- `{{brandBackground}}` - couleur d'arrière-plan
- `{{bodyBackground}}` - couleur d'arrière-plan de la page
- `{{backgroundSecondary}}` - couleur d'arrière-plan secondaire

### Lignes de Facturation

Vous pouvez parcourir les lignes de facturation à l'aide de Handlebars `{{#each lineItems}}` :

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Chaque ligne de facturation expose :
- `{{name}}` - nom de l'article
- `{{amount}}` - quantité
- `{{unit}}` - code d'unité UN/ECE brut (par ex. `H87`)
- `{{unitName}}` - forme longue de l'unité, localisée (par ex. "pièce", "kilogramme")
- `{{unitSymbol}}` - forme courte de l'unité, localisée (par ex. "pce", "kg")
- `{{unitPrice}}` - prix formaté par unité (par ex. "€10,00")
- `{{formattedPrice}}` - total de ligne formaté — quantité × prix unitaire (par ex. "€30,00")
- `{{vat}}` - pourcentage de TVA (si défini)
- `{{vatcode}}` - code TVA (si défini)

### Modèles conditionnels

Vous pouvez utiliser les conditions Handlebars pour afficher du contenu uniquement lorsqu'une valeur existe :

```
{{#if extra}}
  <mj-text>Informations supplémentaires : {{extra}}</mj-text>
{{/if}}
```

Ceci est particulièrement utile lorsque vous souhaitez afficher un bloc d'informations supplémentaires uniquement lorsqu'il est réellement rempli.

### Couleurs de marque et logo

Dans les paramètres, vous pouvez également :
- Télécharger votre logo
- Modifier les couleurs de marque

## 3. Envoyer la facture

1. Spécifiez l'adresse email de l'acheteur dans la facture
2. Cliquez sur le bouton "Envoyer la facture"
3. La facture sera marquée comme verrouillée et envoyée

La facture sera envoyée depuis votre compte Gmail en utilisant le modèle sélectionné.
