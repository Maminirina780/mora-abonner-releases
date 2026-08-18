# Publications Mora Abonner

Chaque version GitHub doit joindre les fichiers installables signés et un manifeste nommé `mora-abonner-update.json`. L’application mobile charge uniquement le manifeste de la dernière release et ne propose un téléchargement que si la version est plus récente et que le lien pointe vers GitHub en HTTPS.

## Android

L’APK doit être produit avec Expo Application Services ou la chaîne Android, puis signé par le même certificat de publication à chaque version. Ne changez jamais de clé de signature : Android considère une APK signée par une autre clé comme une application différente et bloque la mise à jour.

## Desktop Tauri

Le logiciel desktop doit publier ses installateurs et le manifeste de mise à jour signé par la clé Tauri. La clé privée de mise à jour ne doit jamais être placée dans le dépôt ; elle doit être enregistrée dans les secrets de publication.

## Processus

1. Augmenter la version dans l’application.
2. Construire les binaires Android et desktop avec les clés de publication.
3. Créer une release GitHub taguée `vX.Y.Z`.
4. Joindre les binaires signés et le manifeste `mora-abonner-update.json`.
5. Publier la release : les applications proposeront alors la mise à jour au prochain lancement.
