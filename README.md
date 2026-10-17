# Immo Rive-Sud : page « Vendre à 1% »

Page d'atterrissage statique (`index.html` + `assets/`) pour les publicités Facebook. Le formulaire procède une question à la fois : adresse, délai, achat après la vente, coordonnées, puis meilleur moment pour joindre la personne.

## Recevoir les leads
- **Netlify** : déployez le dossier tel quel. Les leads arrivent dans *Forms → vendre-1-pourcent*.
- **Webhook** (Make, Zapier, GoHighLevel…) : collez l'URL dans `WEBHOOK_URL`, en haut du `<script>` dans `index.html`. Chaque lead est envoyé en JSON.

Les paramètres UTM et le `fbclid` sont enregistrés avec chaque lead. Si le Pixel Facebook est installé, l'envoi déclenche l'événement `Lead`.

## À compléter avant la mise en ligne
- Le nom du courtier et celui de l'agence dans le pied de page (exigence de l'OACIQ pour la publicité).
- Le téléphone et le courriel réels.
