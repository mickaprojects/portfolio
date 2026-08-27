# Lancer le site en local

Site statique one-page (`index.html`), sans étape de build. Deux façons de le prévisualiser avant de pousser sur `master`.

## Option 1 — Ouvrir le fichier directement

Le plus rapide pour un simple aperçu visuel :

```
start index.html
```

Limite : le bouton de langue FR/EN et les ancres (`#work`, `#video`, `#contact`) fonctionnent, mais tu es sur `file://` — pas représentatif de l'hébergement réel.

## Option 2 — Serveur local via Wrangler (recommandé)

Reproduit l'environnement Cloudflare Pages :

```
npm install
npx wrangler pages dev . --port 8788
```

Puis ouvrir http://localhost:8788 dans le navigateur.

`Ctrl+C` pour arrêter le serveur.

## Après vérification

Une fois satisfait du rendu local, publier avec le workflow habituel (voir `README.md` à la racine) :

```
git add .
git commit -m "ton message"
git push
```

Cloudflare republie automatiquement sur https://micka-portfolio.pages.dev en quelques secondes.

## Changer la langue par défaut

Le site est bilingue FR/EN : chaque texte existe en deux versions (`<span class="fr">` / `<span class="en">`), et un seul des deux s'affiche selon un attribut `data-lang` — le bouton EN/FR en haut à droite bascule cet attribut au clic.

Deux endroits fixent la langue affichée **au chargement** de la page, tous les deux dans `index.html` :

- **Ligne 2** — `<html lang="...">` : attribut d'accessibilité/SEO, indique la langue du document aux navigateurs et moteurs de recherche.
- **Ligne 393** — `<div data-lang="..." id="app">` : c'est celui qui décide réellement quel texte s'affiche. Le CSS associé (lignes 101-102) cache tout `.en` quand `data-lang="fr"`, et inversement.

Pour changer la langue par défaut, mettre la même valeur (`"fr"` ou `"en"`) aux deux endroits. **Actuellement réglé sur `"en"` (anglais par défaut)**, changé le 2026-08-27.
