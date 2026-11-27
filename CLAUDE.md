# Dépôt marge

Ce dépôt sert à deux choses :
1. ranger les skills de l'utilisateur (dans `.claude/skills/`) ;
2. créer ses sites web (un dossier par site dans `sites/<nom-du-site>/`).

## Communication

- Toujours répondre en français.
- L'utilisateur découvre Claude Code et la création de sites : expliquer simplement, sans jargon inutile.

## Règle obligatoire : proposer des directions visuelles AVANT de créer un site

Avant d'écrire la moindre page d'un nouveau site, toujours :

1. Proposer **5 à 6 directions visuelles différentes** (ambiance, palette de couleurs, typographie,
   style de photos, mise en page de l'accueil). Les montrer sous forme visuelle (une page d'aperçu
   publiée en artifact avec une vignette par direction), pas seulement en texte.
2. **Attendre que l'utilisateur choisisse** une direction (ou en mélange plusieurs).
3. Seulement ensuite, construire le site dans cette direction.

Ne jamais sauter cette étape, même si un skill (comme `design-taste-frontend`) dit de « tirer au sort »
la palette ou la mise en page : le choix de l'utilisateur passe avant.

## Skills installés

- `design-taste-frontend` (taste-skill) : concevoir des sites qui ne font pas « générés par IA ».
- `web-design-guidelines` (Vercel) : vérifier un site existant (accessibilité, formulaires, etc.).

Problème connu de `design-taste-frontend` : `photos.mjs fetch` écrit des fichiers `.webp` dont l'en-tête
RIFF a une taille à 0 ; Chrome ne les affiche pas. Après chaque téléchargement de photos, réparer
l'en-tête (taille RIFF = longueur du fichier - 8, en coupant après le bloc VP8).

## Sites

- `sites/vitrabo/` : nettoyage de vitrines par abonnement à Carouge / Genève (première version,
  modifications à venir de la part de l'utilisateur).
