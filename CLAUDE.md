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

- `sites/horclean/` : LE site actuel de l'utilisateur (nettoyage de vitrines par abonnement, Genève
  et environs). Une seule page, style « Ciel doux » (blanc et bleu, police Sora), chiffon qui essuie
  la vitre au défilement (geste n° 1 « laveur pro », vitre 100 % propre à la fin). Ne jamais parler
  de robot ni de la méthode. Prix : Confort (2 passages/mois) 160 CHF/an moyenne, 220 CHF/an grande ;
  Premium (1 passage/semaine) 315 / 435 CHF/an ; passage unique dès 30 CHF, sur devis.
  Tailles : moyenne = jusqu'à 7 m² de vitres (surface totale), grande = plus de 7 m² ; vérif. au 1er passage.
  `directions.html` et `chiffon.html` sont les pages de propositions.
  En ligne : https://horclean.pages.dev (Cloudflare Pages, projet « horclean », compte 75accf69319d29822753587d540c97c4).
  Publication automatique par `.github/workflows/horclean.yml` à chaque push touchant `sites/horclean/`
  (secret GitHub CLOUDFLARE_API_TOKEN). Seuls index.html et share.jpg sont publiés.
  Formulaire : FormSubmit vers l'adresse pro de l'utilisateur (`FORM_TO` dans index.html) ; activation FormSubmit à confirmer.
- `sites/vitrabo/` : premier essai abandonné (même activité), gardé pour mémoire.
