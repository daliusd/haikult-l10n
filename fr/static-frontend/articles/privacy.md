---
title: 'Politique de confidentialité'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Cette politique de confidentialité décrit comment Haiku.lt collecte et utilise les données.

## Données que nous collectons

- Adresse IP, date et heure, informations sur le navigateur.

- Adresse email.

- Données que vous saisissez dans le système lors de son utilisation.

## Cookies et stockage du navigateur

Nous utilisons des cookies et le stockage du navigateur pour fournir des fonctionnalités essentielles :

### Cookies

- **Cookie d'authentification (auth_token)** : Un cookie sécurisé, HTTP-only utilisé pour maintenir votre session de connexion. Ce cookie est essentiel pour que le service fonctionne et expire après environ 2 mois. Sans ce cookie, vous ne pouvez pas utiliser Haiku.lt.

### Stockage local du navigateur

Nous stockons les données suivantes dans le stockage local de votre navigateur :

- **Préférence de langue** : Votre langue d'interface sélectionnée (anglais ou lituanien) pour fournir un rendu immédiat de l'interface utilisateur.

- **Masquage de notification** : Enregistre si vous avez masqué certaines notifications pour éviter de les afficher de manière répétée.

- **Synchronisation du changement de compte** : Données temporaires (supprimées après 1 seconde) utilisées pour synchroniser le changement de compte entre plusieurs onglets du navigateur.

### Stockage de session du navigateur

- **Suivi de visite** : Un indicateur de session uniquement pour éviter les boucles de redirection sur la page d'accueil. Ces données sont supprimées lorsque vous fermez votre navigateur.

### Aucun suivi tiers

Nous n'utilisons aucun cookie d'analyse, de publicité ou de suivi tiers. Tous les cookies et le stockage sont strictement nécessaires au fonctionnement du service.

## Services tiers

- **Services Google** : Nous nous intégrons aux services Google lorsque vous vous connectez via OAuth Google :

  - **Google Drive** (optionnel) : Si vous accordez l'autorisation Google Drive, nous accédons à :
    - **Ce à quoi nous accédons** : Fichiers créés par Haiku.lt dans votre Google Drive. Nous utilisons la portée `drive.file` qui donne accès uniquement aux fichiers créés par notre application - nous ne pouvons pas voir ni accéder à d'autres fichiers dans votre Drive.
    - **Comment nous l'utilisons** : Pour enregistrer les PDF de factures sur votre Google Drive dans une structure de dossiers organisée (Haiku.lt/Invoices/Année). Lorsque vous utilisez la fonctionnalité "Enregistrer sur Drive", nous créons ou mettons à jour des fichiers PDF.
    - **Comment nous le stockons** : Nous stockons l'ID du fichier Google Drive dans notre base de données pour suivre quelles factures ont été enregistrées et pour permettre les mises à jour des fichiers existants. Le contenu réel du PDF n'est pas stocké sur nos serveurs - il existe uniquement dans votre Google Drive.
    - **Comment nous le partageons** : Les ID de fichiers Google Drive ne sont jamais partagés avec des tiers, jamais vendus à des courtiers de données, et jamais utilisés pour la publicité, le marketing, la formation d'IA ou tout autre usage que la gestion de vos PDF de factures dans votre Drive.
    - **Comment le contrôler** : Vous pouvez gérer les autorisations Drive via vos [autorisations de compte Google](https://myaccount.google.com/permissions). Les fichiers restent dans votre Drive sous votre contrôle. Vous pouvez les supprimer à tout moment. La révocation de l'accès empêche notre capacité à créer de nouveaux fichiers ou à mettre à jour les fichiers existants.
  
  - **Gmail** (optionnel) : Si vous accordez l'autorisation Gmail, nous accédons à :
    - **Ce à quoi nous accédons** : Autorisation d'envoyer des emails via votre compte Gmail. Nous utilisons la portée `gmail.send` qui permet d'envoyer des emails en votre nom. Nous ne lisons pas vos emails existants ni n'accédons à votre boîte de réception.
    - **Comment nous l'utilisons** : Pour envoyer des emails de factures à vos acheteurs lorsque vous utilisez la fonctionnalité "Envoyer la facture". Les emails incluent le PDF de facture en pièce jointe et des pièces jointes supplémentaires optionnelles (comme le XML CII pour la facturation électronique).
    - **Comment nous le stockons** : Nous ne stockons pas le contenu des emails ni les données de messages envoyés. Les emails envoyés apparaissent dans votre dossier "Envoyés" Gmail sous votre contrôle.
    - **Comment nous le partageons** : La capacité d'envoi d'email n'est jamais partagée avec des tiers, jamais vendue, et jamais utilisée pour la publicité, le marketing, le spam ou tout autre usage que l'envoi de factures que vous choisissez explicitement d'envoyer.
    - **Comment le contrôler** : Vous pouvez gérer les autorisations Gmail via vos [autorisations de compte Google](https://myaccount.google.com/permissions). Les emails envoyés restent dans votre compte Gmail. La révocation de l'accès empêche notre capacité à envoyer des emails en votre nom.
  
  - **Google Calendar** (optionnel, lecture seule) : Si vous accordez l'autorisation du calendrier, nous accédons à :
    - **Ce à quoi nous accédons** : Noms de vos calendriers, titres d'événements, dates/heures d'événements et statut de participation (pour filtrer les événements refusés). Nous utilisons la portée de l'API Google Calendar `calendar.readonly` qui fournit un accès en lecture seule.
    - **Comment nous l'utilisons** : Exclusivement pour vous aider à créer des factures basées sur des événements du calendrier via la fonctionnalité "Créer à partir du calendrier". Les titres d'événements deviennent des descriptions de lignes d'articles de facture, et les dates d'événements aident à définir les plages de dates de facture.
    - **Comment nous le stockons** : Les données du calendrier **ne sont pas stockées de manière permanente** dans nos bases de données. Elles sont récupérées à la demande uniquement lorsque vous utilisez la fonctionnalité de facture du calendrier et existent temporairement dans la mémoire de votre navigateur pendant le processus de création de facture.
    - **Comment nous le partageons** : Les données du calendrier ne sont **jamais partagées** avec des tiers, **jamais vendues** à des courtiers de données, et **jamais utilisées** pour la publicité, le marketing, la formation d'IA ou tout autre usage que la création de factures pour vous.
    - **Comment le contrôler** : Vous pouvez gérer les autorisations du calendrier de manière indépendante via vos [autorisations de compte Google](https://myaccount.google.com/permissions). La révocation de l'accès arrête immédiatement l'accès aux données. Vous pouvez également déconnecter l'intégralité de votre compte Google via les paramètres Haiku.lt.
    
  Toutes les autorisations OAuth Google nécessitent votre autorisation explicite. Vous contrôlez quelles autorisations accorder et pouvez les révoquer à tout moment.

- **Stripe** : Nous utilisons Stripe pour le traitement des paiements des abonnements premium. Stripe traite toutes les informations de paiement en toute sécurité selon leur politique de confidentialité. Nous recevons uniquement la confirmation des paiements réussis.

- **Brevo (Sendinblue)** : Nous utilisons Brevo pour envoyer des emails transactionnels, y compris les emails de connexion par lien magique et les emails de factures. Brevo reçoit l'adresse email du destinataire et le contenu de l'email nécessaire pour envoyer ces messages. Brevo est situé dans l'UE (France). Voir leur [Politique de confidentialité](https://www.brevo.com/legal/privacypolicy/).

## Protection des données

Pour protéger les données collectées, nous prenons les mesures suivantes :

- Mettre à jour les logiciels serveur aussi fréquemment que possible.

- Mettre à jour les logiciels Haiku.lt aussi fréquemment que possible.

- Configurer correctement les serveurs.

## Vos droits

Pour des informations détaillées sur vos droits relatifs aux données en vertu du RGPD, y compris le droit d'accès, de suppression et d'exportation de vos données, veuillez consulter notre [page RGPD](/fr/gdpr).
