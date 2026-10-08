# Documentation SolidRocks

Site de documentation de tous les SolidRocks (une section par produit : `docs/blender/`, plus tard
`docs/max/`...), construit avec MkDocs + Material et publié par GitHub Pages.

## Mise en ligne (une seule fois, depuis GitHub Desktop)

1. Le dépôt est créé dans GitHub Desktop (File > New repository).
2. Copier dans son dossier **tout le contenu de ce zip**, y compris le dossier caché `.github`
   (sous Windows : Explorateur > Affichage > cocher « Éléments masqués » pour le voir).
3. Dans `mkdocs.yml`, ligne `site_url` : remplacer `YOUR-GITHUB-NAME` par ton pseudo GitHub et
   `REPOSITORY-NAME` par le nom exact du dépôt.
4. GitHub Desktop : écrire un résumé (ex. « Première version de la doc »), **Commit to main**.
5. **Publish repository** : **décocher « Keep this code private »** (sinon pas de site gratuit), Publish.
6. Sur github.com, dans le dépôt : **Settings > Pages > Build and deployment > Source : GitHub Actions**.
7. Onglet **Actions** : attendre la coche verte (1 à 2 minutes). Le site est à
   `https://TON-PSEUDO.github.io/NOM-DU-DEPOT/`.

Une croix rouge dans Actions = le site ne s'est pas construit (souvent une faute dans `mkdocs.yml`).
Le site précédent reste en ligne en attendant.

## Modifier une page

Éditer le fichier `.md` dans `docs/blender/`, Commit, Push : le site se republie tout seul.
Les images vont dans `docs/blender/images/` et s'insèrent avec `![Texte](images/nom.png)`.
Les encadrés « Author » signalent ce qui reste à vérifier ou compléter.

## Ajouter un produit plus tard

Créer `docs/max/` (par exemple) avec ses pages, puis ajouter sa section dans `nav:` de `mkdocs.yml`
et sa carte dans `docs/index.md`.

## Voir le site sur ta machine avant de publier (facultatif)

    pip install -r requirements.txt
    mkdocs serve

puis ouvrir http://127.0.0.1:8000

## Versions figées

`requirements.txt` fige MkDocs 1.6.1 et Material 9.7.6 : MkDocs 2.0 casse Material.
Ne pas « mettre à jour » ces versions sans vérifier.
