---
title: "Vos données sont chiffrées : Pourquoi c'est important"
date: '2026-03-15'
modified: '2026-03-15'
showDate: true
---

Chaque base de données utilisateur de Haiku.lt est chiffrée au repos. Voici ce que cela signifie et pourquoi vous devriez vous en préoccuper.

## Ce que le chiffrement signifie (simplement)

Imaginez vos factures et vos données clients comme un journal intime. Le chiffrement verrouille ce journal et brouille chaque mot en un charabia aléatoire. Sans la clé, la personne qui tient le journal ne voit rien d'autre que du bruit — `X7k#mQ2$pL9@vR4...` — complètement illisible.

La base de données de chaque utilisateur reçoit une clé unique, et Haiku.lt ne stocke jamais cette clé en texte clair.

## Le scénario de sauvegarde

Haiku.lt effectue des sauvegardes régulières pour se protéger contre la perte de données. Imaginons maintenant le pire des scénarios : un pirate informatique met la main sur l'un de ces fichiers de sauvegarde.

Qu'obtient-il ? Un fichier rempli d'un charabia brouillé. Sans la clé de chiffrement, la sauvegarde n'a aucune valeur pour lui. Il ne peut pas lire les noms de vos clients, les montants de vos factures ou toute autre donnée.

## Quelle est la force du « chiffrement » ?

Haiku.lt utilise le chiffrement AES-256 — le même standard utilisé par les banques et les gouvernements dans le monde entier. Pour forcer brutalement une clé AES-256, un attaquant devrait essayer 2²⁵⁶ combinaisons possibles.

À titre de comparaison, même en utilisant tous les ordinateurs de la planète à pleine vitesse, il faudrait plus de temps que l'âge actuel de l'univers pour déchiffrer une seule clé AES-256. Il ne s'agit pas d'une attaque pratique.

## En conclusion

Si les sauvegardes de Haiku.lt étaient volées, vos données resteraient protégées. Le chiffrement garantit que la possession physique d'un fichier de sauvegarde n'a pas de sens sans la clé de chiffrement.

Vos factures sont votre affaire. Elles doivent rester les vôtres.
