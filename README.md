# Immo Rive-Sud : page « Vendre à 1% »

Page unique statique (`index.html` + `assets/`) pour les publicités Facebook. Le formulaire procède une question à la fois : adresse, délai, achat après la vente, coordonnées, puis meilleur moment pour joindre la personne.

## Sélecteur d'adresse
La recherche couvre toutes les adresses du Québec. La personne choisit son adresse dans la liste, puis ajoute son appartement ou son unité. Les champs `ville`, `code_postal`, `lat` et `lon` sont remplis automatiquement.

- **Recommandé : Google Places.** Collez une clé « Places API (New) » dans `GOOGLE_PLACES_KEY`, en haut du `<script>` dans `index.html`, et restreignez la clé au domaine du site. Google connaît pratiquement toutes les adresses du Québec.
- **Sans clé : Photon (OpenStreetMap).** C'est gratuit, mais certaines adresses manquent. Quand la rue est connue mais pas le numéro civique, l'adresse est quand même proposée et le lead porte `adresse_verifiee = rue seulement`.
- **Adresse introuvable :** un lien permet de la taper à la main ; le lead porte alors `adresse_verifiee = non`.

## Recevoir les leads
- **Netlify** : déployez le dossier tel quel. Les leads arrivent dans *Forms → vendre-1-pourcent*.
- **Webhook** (Make, Zapier, GoHighLevel…) : collez l'URL dans `WEBHOOK_URL`, en haut du `<script>` dans `index.html`. Chaque lead est envoyé en JSON.

Les paramètres UTM et le `fbclid` sont enregistrés avec chaque lead. Si le Pixel Facebook est installé, l'envoi déclenche l'événement `Lead`.

## À compléter avant la mise en ligne
- Le nom du courtier et celui de l'agence dans le pied de page (exigence de l'OACIQ pour la publicité).
- Le téléphone et le courriel réels.
