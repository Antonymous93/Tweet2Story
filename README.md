# Tweet2Story (prototype V1)

Application web installable sur Android (PWA), sans backend ni API payante.

## Essayer sur Android

1. Publier les fichiers du dossier à la racine d'un dépôt GitHub public.
2. GitHub : Settings → Pages → Deploy from a branch → main / (root) → Save.
3. Ouvrir l'URL `https://PSEUDO.github.io/NOM_DU_DEPOT/` dans Chrome sur Android.
4. Menu ⋮ → Installer l'application ou Ajouter à l'écran d'accueil.

## Fonctionnement

- Importer une capture ; le bouton « Utiliser l'exemple » fournit une capture de démonstration.
- « Extraire le texte » charge Tesseract.js depuis jsDelivr et son modèle OCR anglais. Nécessite Internet au premier usage, et peut le nécessiter à nouveau selon le cache du navigateur.
- Corriger les champs et répartir manuellement le texte principal / cité.
- Choisir la cible de recadrage, puis glisser sur la capture pour sélectionner une image.
- Exporter PNG ou partager avec WhatsApp.

## Limites connues

- Le découpage automatique du texte principal et du tweet cité n'est pas implémenté : OCR brut, correction et répartition manuelles.
- Les images se sélectionnent manuellement. Un texte masqué ne peut pas être récupéré de façon fiable.
- Le service worker met en cache l'interface et l'exemple, mais pas nécessairement les ressources OCR externes.
- Le rendu s'adapte à la longueur du texte, mais les tweets exceptionnellement longs peuvent dépasser la carte. Vérifier l'aperçu.
- Pour un fonctionnement PWA complet, servir via HTTPS (GitHub Pages) ou localhost ; ouvrir index.html comme un fichier ne suffit pas.
