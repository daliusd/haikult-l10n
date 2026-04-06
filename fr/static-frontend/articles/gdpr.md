---
title: 'RGPD - Vos droits relatifs aux données'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

Haiku.lt s'engage à protéger vos données personnelles et à respecter vos droits à la vie privée en vertu du Règlement Général sur la Protection des Données (RGPD). Cette page explique vos droits et comment nous traitons vos données.

## Vos droits relatifs aux données

En vertu du RGPD, vous disposez des droits suivants concernant vos données personnelles :

### Droit d'accès

Vous avez le droit d'accéder à toutes les données personnelles que nous détenons à votre sujet. Vous pouvez exporter vos données à tout moment :

- **Export complet de la base de données** : Téléchargez votre base de données complète incluant toutes les factures, paramètres et journaux d'audit depuis les paramètres de votre compte.
- **Export de factures** : Exportez vos factures au format CSV, filtrées par plage de dates et nom de série.

### Droit à l'effacement (Droit à l'oubli)

Vous avez le droit de demander la suppression de vos données personnelles. Vous pouvez supprimer l'intégralité de votre compte et toutes les données associées à tout moment via les paramètres de votre compte. Cette action est permanente et ne peut être annulée.

### Droit à la portabilité des données

Vous pouvez exporter vos données dans des formats lisibles par machine :

- Format de base de données SQLite (export complet des données)
- Format CSV (export des données de factures)

Cela vous permet de transférer vos données vers un autre service si vous le souhaitez.

### Droit de rectification

Vous avez le droit de corriger des données personnelles inexactes ou incomplètes. Vous pouvez modifier toutes vos données directement dans l'application, notamment :

- Détails des factures
- Informations sur l'acheteur et le vendeur
- Vos préférences personnelles et paramètres

### Droit à la limitation du traitement

Vous avez le droit de demander la limitation du traitement de vos données personnelles dans certaines circonstances. Contactez-nous en utilisant l'email ci-dessous pour exercer ce droit.

### Droit d'opposition

Vous avez le droit de vous opposer au traitement de vos données personnelles à des fins spécifiques. Étant donné que Haiku.lt traite vos données uniquement pour fournir le service de facturation que vous avez demandé, s'opposer au traitement empêcherait la fourniture du service.

## Conservation des données

Vos données sont conservées **jusqu'à ce que vous supprimiez votre compte**. Nous ne supprimons pas automatiquement les comptes inactifs. Vous contrôlez entièrement le moment où vos données sont supprimées.

Lorsque vous supprimez votre compte, toutes vos données sont définitivement supprimées de nos systèmes.

## Responsable du traitement

Le responsable du traitement pour Haiku.lt est :

**Dalius Dobravolskas**

Pour les questions relatives à la vie privée ou pour exercer vos droits relatifs aux données, contactez :
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Localisation des serveurs

Tous les serveurs et le stockage de données de Haiku.lt sont situés dans l'**Union Européenne, spécifiquement en Allemagne**. Vos données ne quittent pas l'UE sauf si vous autorisez explicitement des intégrations tierces (voir Sous-traitants ci-dessous).

## Base juridique du traitement

Nous traitons vos données personnelles sur la base de :

- **Exécution du contrat** : Pour fournir le service de facturation auquel vous vous êtes inscrit
- **Intérêt légitime** : Pour maintenir la sécurité du service, prévenir la fraude et améliorer le service
- **Consentement** : Pour les fonctionnalités optionnelles comme l'intégration Google Drive et Gmail

## Sous-traitants

Haiku.lt utilise les services tiers suivants pour fournir nos fonctionnalités :

### Google LLC

**Services utilisés** : Authentification OAuth 2.0, API Google Drive, API Gmail, API Google Calendar

**Données partagées** : Adresse email, nom, jetons OAuth (uniquement lorsque vous autorisez l'intégration Google)

**Objectif** : Pour vous permettre de :
- **Authentifier** avec votre compte Google en utilisant OAuth 2.0
- **Google Drive** (portée : `drive.file`) : Enregistrer les PDF de factures sur votre Drive dans des dossiers organisés (Haiku.lt/Invoices/Année). Nous pouvons uniquement accéder aux fichiers créés par notre application, pas à vos autres fichiers Drive. Nous stockons les ID de fichiers Drive pour suivre les factures enregistrées.
- **Gmail** (portée : `gmail.send`) : Envoyer des emails de factures aux acheteurs en votre nom. Nous ne lisons pas votre boîte de réception ni vos emails existants. Les emails envoyés apparaissent dans votre dossier "Envoyés" Gmail.
- **Google Calendar** (portée : `calendar.readonly`, optionnel) : Lire les titres, dates, heures d'événements du calendrier et le statut de participation pour aider à créer des factures. Ces données sont récupérées temporairement et non stockées de manière permanente.

**Conservation des données** : 
- ID de fichiers Drive : Stockés dans notre base de données jusqu'à ce que vous supprimiez la facture ou déconnectiez votre compte Google
- Données du calendrier : Non stockées (récupérées à la demande uniquement)
- Données Gmail : Non stockées (les emails restent dans votre compte Gmail)
- Jetons OAuth : Chiffrés et stockés jusqu'à ce que vous déconnectiez votre compte

**Politique de confidentialité** : [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Localisation** : États-Unis (avec conformité au cadre de confidentialité des données UE-États-Unis)

### Stripe, Inc.

**Services utilisés** : Traitement des paiements pour les abonnements

**Données partagées** : Adresse email, informations de paiement (traitées directement par Stripe)

**Objectif** : Pour traiter les paiements d'abonnement pour les fonctionnalités premium

**Politique de confidentialité** : [https://stripe.com/privacy](https://stripe.com/privacy)

**Localisation** : États-Unis (avec conformité au cadre de confidentialité des données UE-États-Unis)

### Brevo (Sendinblue)

**Services utilisés** : Envoi d'emails transactionnels

**Données partagées** : Adresse email du destinataire, contenu de l'email (jetons de lien magique pour la connexion ; détails de facture lors de l'envoi de factures via Brevo)

**Objectif** : Pour envoyer des emails d'authentification (connexion par lien magique) et des emails de factures aux acheteurs

**Conservation des données** : Brevo peut conserver les journaux d'emails envoyés pendant une période limitée conformément à leur politique. Nous ne stockons pas le contenu des emails sur nos serveurs au-delà de ce qui est nécessaire pour les envoyer.

**Politique de confidentialité** : [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Localisation** : Union Européenne (France)

## Sécurité des données

Nous prenons des mesures techniques et organisationnelles appropriées pour protéger vos données personnelles :

- Chiffrement des données sensibles (jetons OAuth, jetons de rafraîchissement)
- Connexions HTTPS sécurisées
- Cookies d'authentification HTTP-only et sécurisés
- Mises à jour logicielles régulières
- Isolation de la base de données par utilisateur
- Journalisation d'audit pour le suivi de l'accès aux comptes

## Notification de violation de données

Dans le cas improbable d'une violation de données présentant un risque pour vos droits et libertés, nous vous en informerons ainsi que l'autorité de surveillance compétente dans les 72 heures comme requis par le RGPD.

## Autorité de surveillance

Si vous avez des préoccupations concernant la façon dont nous traitons vos données personnelles, vous avez le droit de déposer une plainte auprès de votre autorité locale de protection des données.

## Mises à jour de cette politique

Nous pouvons mettre à jour cette page d'informations RGPD de temps en temps. La date "modifié" en haut de cette page indique quand elle a été mise à jour pour la dernière fois.

Pour des informations générales sur la confidentialité, consultez notre [Politique de confidentialité](/fr/privacy).
