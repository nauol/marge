---
name: sherlock
description: Trouver où un pseudo (nom d'utilisateur) est utilisé sur les réseaux sociaux et sites web, avec l'outil open source Sherlock. À utiliser pour chercher ses propres pseudos ou ceux d'une personne qui a donné son accord.
---

# Sherlock : trouver ses pseudos sur le web

Sherlock vérifie si un même pseudo existe sur des centaines de sites (réseaux sociaux, forums, plateformes de jeux, etc.).
C'est un outil open source (dépôt : https://github.com/sherlock-project/sherlock), installé ici depuis ce dépôt GitHub.

## Règle à respecter

Utiliser Sherlock uniquement :
- pour chercher **ses propres pseudos** ;
- ou pour une personne qui a **donné son accord** ;
- ou dans un cadre professionnel autorisé (par exemple un audit de sa propre marque).

Ne jamais s'en servir pour suivre, surveiller ou retrouver une personne privée sans son accord.

## Étapes

1. **Vérifier l'installation** :
   ```bash
   /home/user/.venvs/sherlock/bin/sherlock --version
   ```
   Si la commande n'existe pas (l'environnement a été réinitialisé), la réinstaller :
   ```bash
   python3 -m venv /home/user/.venvs/sherlock && /home/user/.venvs/sherlock/bin/pip install sherlock-project
   ```
   (Si l'installation échoue, cloner le dépôt puis `pip install .` à l'intérieur.)

2. **Demander le ou les pseudos** à chercher à l'utilisateur (un ou plusieurs, séparés par des espaces).

3. **Lancer la recherche** (résultats positifs seulement) :
   ```bash
   /home/user/.venvs/sherlock/bin/sherlock --print-found --timeout 15 PSEUDO
   ```

   Options utiles :
   - `--site NomDuSite` : tester un seul site (peut être répété).
   - `--csv` ou `--xlsx` : enregistrer les résultats dans un fichier.
   - `--folderoutput DOSSIER` : choisir où ranger les fichiers.
   - `--nsfw` : inclure les sites pour adultes (désactivés par défaut).

4. **Présenter les résultats simplement** : une liste des sites où le pseudo a été trouvé, avec le lien.
   Préciser qu'une présence trouvée ne prouve pas que c'est la même personne : un pseudo courant peut appartenir à plusieurs personnes. Il faut vérifier chaque profil à la main.

5. **Ne pas garder de données inutiles** : supprimer les fichiers de résultats si l'utilisateur ne les veut plus.

## Ce que l'outil ne fait pas

- Il ne cherche pas d'adresses e-mail, de numéros de téléphone ni de noms réels.
- Il ne voit pas les profils privés ou les comptes supprimés de manière fiable.
- Les sites changent souvent : un résultat peut être faux (faux positifs) ou manquer (faux négatifs).
