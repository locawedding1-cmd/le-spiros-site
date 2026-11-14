# Géraldine Coiffure — site vitrine

Site one-page statique (HTML/CSS/JS, aucun build), pensé mobile-first, déployé sur GitHub Pages dans le sous-dossier `/geraldine/`.

## À compléter avant d'envoyer au salon

Cherchez `<!-- À COMPLÉTER -->` dans `index.html` pour chaque emplacement exact.

- **Horaires** — aucune horaire n'est affichée, le site dit "Appelez-nous". À remplacer par les vraies horaires dans la section Infos pratiques (`#infos`) et dans le `<dl class="info-list">`.
- **Services et tarifs** — les 6 cartes (`#services`) sont marquées "À confirmer", sans aucun prix inventé. À compléter avec la vraie liste de prestations et les tarifs réels.
- **Photos** — la galerie (`#galerie`) a 2 vraies photos de substitution (salon et bac de lavage, libres de droits, voir crédits ci-dessous) et 2 cases "Photo à venir". À remplacer les 4 par de vraies photos du salon, des coupes et des réalisations.
- **Avis** — les 3 avis sont réels (fournis tels quels) mais sans nom d'auteur attribué (aucun prénom n'a été donné) : affichés comme "Avis Google vérifié". Si vous avez les prénoms ou initiales réels, les ajouter dans chaque `<cite>`.

## Ce qui est déjà réel (ne pas modifier sans vérifier)

- Nom, adresse (Rue de Beaumont 117, 6030 Charleroi), téléphone (0488 66 88 03), lien Facebook, note Google (4,4/5, 27 avis) : fournis directement, repris tels quels dans le HTML et le JSON-LD `HairSalon`.
- La carte Google Maps dans `#infos` est une vraie carte intégrée sur l'adresse réelle (pas une image).

## Outils utilisés

- **ui-ux-pro-max** : palette (sable, bordeaux profond, accent doré) et pairing typographique (Playfair Display + Inter, preset "Classic Elegant", recommandé pour spa/beauté).
- **21st.dev (recherche de composants, portés en vanilla JS/CSS, pas de React)** :
  - carrousel d'avis : inspiré de "Reviews Carousel" (cartes empilées, dots, clavier, autoplay).
  - bouton d'appel flottant mobile : inspiré de "Book A Call Button" / "Glossy Slider Call Button".
  - galerie hover : effet de zoom léger au survol.

## Accessibilité et performance

- Contraste vérifié (clair et sombre) sur tous les textes, y compris l'accent doré (plus foncé en clair, plus clair en sombre pour rester lisible dans les deux cas).
- `prefers-reduced-motion` respecté : le carrousel ne joue pas tout seul, les animations d'apparition sont désactivées.
- Images en `loading="lazy"` sauf la photo du hero (chargée en priorité).
- Focus visibles sur tous les boutons et liens interactifs.
- Markup sémantique (`header`, `main`, `footer`, `dl`, `blockquote`/`cite`).

## Publier sur GitHub Pages

Ce site vit dans `livrables/application/geraldine-coiffure-site/` du projet, et est synchronisé vers le dépôt GitHub Pages existant `locawedding1-cmd/le-spiros-site`, sous-dossier `/geraldine/` :

```bash
# 1. copier la page et ses assets dans le dossier de déploiement
cp index.html /chemin/vers/le-spiros-deploy/geraldine/index.html
cp -R assets/img/*.webp /chemin/vers/le-spiros-deploy/geraldine/assets/img/

# 2. committer et pousser
cd /chemin/vers/le-spiros-deploy
git add geraldine/
git commit -m "Mets à jour le site Géraldine Coiffure"
git push origin main
```

Le site est alors visible à **https://locawedding1-cmd.github.io/le-spiros-site/geraldine/** après quelques dizaines de secondes (délai normal de GitHub Pages).

Pour un dépôt GitHub Pages indépendant (pas dans `/geraldine/` mais à la racine d'un nouveau dépôt), il suffit de copier `index.html` et le dossier `assets/img/` à la racine de ce nouveau dépôt et d'activer GitHub Pages dans ses réglages (Settings → Pages → Source: `main` branch, dossier `/`).

## Crédits photo (substitution, à remplacer)

- Salon de coiffure : Daderot, CC0 — commons.wikimedia.org/wiki/File:Hair_salon_-_Arlington,_MA.jpg
- Bac de lavage : johnrosman, CC BY 2.0 — commons.wikimedia.org/wiki/File:Inside_the_Hair_Salon_(5577833869).jpg
