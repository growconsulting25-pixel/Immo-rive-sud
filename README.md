# Immo Rive-Sud : page « Vendre à 1% »

Page unique statique (`index.html` + `assets/`) pour les publicités Facebook. Le formulaire procède une question à la fois : adresse, délai, achat après la vente, coordonnées, puis meilleur moment pour joindre la personne.

## Sélecteur d'adresse
L'adresse est cherchée avec Photon (données OpenStreetMap). C'est gratuit et ça ne demande aucune clé API. La personne choisit son adresse dans la liste, puis ajoute son appartement ou son unité. Les champs `ville`, `code_postal`, `lat` et `lon` sont remplis automatiquement. Si l'adresse est introuvable, un lien permet de la taper à la main ; le lead porte alors `adresse_verifiee = non`.

## Recevoir les leads
- **Netlify** : déployez le dossier tel quel. Les leads arrivent dans *Forms → vendre-1-pourcent*.
- **Webhook** (Make, Zapier, GoHighLevel…) : collez l'URL dans `WEBHOOK_URL`, en haut du `<script>` dans `index.html`. Chaque lead est envoyé en JSON.

Les paramètres UTM et le `fbclid` sont enregistrés avec chaque lead. Si le Pixel Facebook est installé, l'envoi déclenche l'événement `Lead`.

## À compléter avant la mise en ligne
- Le nom du courtier et celui de l'agence dans le pied de page (exigence de l'OACIQ pour la publicité).
- Le téléphone et le courriel réels.
