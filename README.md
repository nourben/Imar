# Invitation — Dîner caritatif IMAR

Page web qui découpe les PDF recto/verso (paysage, 2 demi-pages chacun) en 4 pages,
ajoute le nom et/ou le prénom sur la page d'invitation et exporte un PDF.
Tout se passe dans le navigateur, rien n'est envoyé sur un serveur.

## Mise en ligne sur GitHub Pages

1. Crée un dépôt sur GitHub (ex. `invitation-imar`).
2. Envoie tout le contenu de ce dossier à la racine du dépôt
   (bouton **Add file → Upload files**, glisse tous les fichiers et dossiers).
3. **Settings → Pages** → Source : *Deploy from a branch* → branche `main`, dossier `/ (root)` → **Save**.
4. Après 1 à 2 minutes, la page est disponible sur `https://<ton-compte>.github.io/invitation-imar/`.

> Ne pas ouvrir `index.html` en double-cliquant : le navigateur bloque le chargement des PDF.
> Pour tester sur ton PC : `python -m http.server` dans ce dossier, puis http://localhost:8000

## Utilisation

- **Ligne 1 / Ligne 2** : indépendantes, affichées en direct sur la page 1.
- **A− / A+** : taille du texte (un texte trop long rétrécit tout seul).
- **Exporter en PDF** : 4 pages, qualité d'origine (~16 Mo).
- **Version légère** : pages recalculées en 200 dpi, beaucoup plus petites (pour WhatsApp / e-mail).
- **Nom du fichier** : `Invitation_IMAR_<ligne1>_<ligne2>.pdf`, seulement ce qui est rempli.
- **Changer le recto / verso** : charge d'autres PDF sans toucher au dépôt.

## Remplacer les PDF par défaut

Remplace `pdf/recto.pdf` et `pdf/verso.pdf` (mêmes noms).

## Réglages (en haut du script dans `index.html`, objet `CONFIG`)

- `pages` : ordre des pages et moitié utilisée (`half: 0` gauche, `1` droite).
- `lines` : position des 2 lignes, en fraction de la demi-page.
- `fontSize`, `maxWidth`, `color`, `filePrefix`, `lightDpi`.

## Bibliothèques incluses (dossier `lib/`)

pdf.js 3.11.174 (Mozilla, Apache-2.0), pdf-lib 1.17.1 (MIT), @pdf-lib/fontkit 1.1.1 (MIT).
Police : Montserrat SemiBold (SIL Open Font License).
