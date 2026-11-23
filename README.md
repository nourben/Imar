# Invitation — Dîner caritatif IMAR

Page web qui découpe les PDF recto/verso (paysage, 2 demi-pages chacun) en 4 pages,
ajoute le nom et/ou le prénom sur la page d'invitation et exporte un PDF.
Les PDF sont générés dans le navigateur ; seul un compteur anonyme d'exports est envoyé (voir plus bas).

## Liens

- **Site** : https://nourben.github.io/Imar/
- **Statistiques** (nombre de PDF générés) : https://nourben.github.io/Imar/stats-01q12e9hes91uo.html

## Mise en ligne (déjà faite)

Le site est publié par GitHub Pages : **Settings → Pages** → *Deploy from a branch* → `main` / `/ (root)`.
Chaque modification poussée sur `main` est en ligne 1 à 2 minutes après.

> Ne pas ouvrir `index.html` en double-cliquant : le navigateur bloque le chargement des PDF.
> Pour tester sur ton PC : `python -m http.server` dans ce dossier, puis http://localhost:8000

## Utilisation

- **Ligne 1 / Ligne 2** : indépendantes, affichées en direct sur la page 1.
- **A− / A+** : taille du texte (un texte trop long rétrécit tout seul).
- **Exporter en PDF** : 4 pages, qualité d'origine (~16 Mo).
- **Version légère** : pages recalculées en 200 dpi, beaucoup plus petites (pour WhatsApp / e-mail).
- **Nom du fichier** : `Invitation_IMAR_<ligne1>_<ligne2>.pdf`, seulement ce qui est rempli.
- **Thème** : bouton en haut à droite (clair par défaut, le choix est retenu).
- **Statistiques** : petit lien en bas de page.

## Remplacer les PDF par défaut

Remplace `pdf/recto.pdf` et `pdf/verso.pdf` (mêmes noms).

## Réglages (en haut du script dans `index.html`, objet `CONFIG`)

- `pages` : ordre des pages et moitié utilisée (`half: 0` gauche, `1` droite).
- `lines` : position des 2 lignes, en fraction de la demi-page.
- `fontSize`, `maxWidth`, `color`, `filePrefix`, `lightDpi`.
- `counter` : compteur d'exports (voir ci-dessous).

## Compteur d'exports

À chaque export réussi, le site incrémente des compteurs sur le service gratuit
[Abacus](https://abacus.jasoncameron.dev) : `pdf-total`, `pdf-complet` et `pdf-leger`,
dans l'espace `imar-diner-op8dna9v`. Aucun nom n'est envoyé, uniquement +1.

- La page de stats n'a aucun lien depuis le site : il faut connaître son adresse.
- Si tu changes l'espace (`ns`), modifie-le à la fois dans `index.html` et dans la page de stats.
- Un compteur qui n'est plus utilisé pendant 6 mois est supprimé par le service.

## Bibliothèques incluses (dossier `lib/`)

pdf.js 3.11.174 (Mozilla, Apache-2.0), pdf-lib 1.17.1 (MIT), @pdf-lib/fontkit 1.1.1 (MIT).
Police : Montserrat SemiBold (SIL Open Font License).
