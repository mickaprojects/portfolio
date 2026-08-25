# Portfolio — Micka Andriamiadanarivo

Site one-page bilingue (FR/EN), statique, sans build. Le contenu complet est dans `index.html`.

## Déployer sur Cloudflare Pages

Deux façons de faire, au choix.

### Option A — Upload direct via Wrangler (le plus rapide)

Pas besoin de GitHub. Depuis ce dossier :

```
npm install
npx wrangler login       # ouvre le navigateur pour connecter ton compte Cloudflare
npm run deploy
```

La première fois, Wrangler crée le projet `micka-portfolio` sur Cloudflare Pages et te donne une URL du type `https://micka-portfolio.pages.dev`. Pour republier après une modif, relance juste `npm run deploy`.

### Option B — Intégration Git (déploiement auto à chaque push)

1. Pousse ce dossier sur un repo GitHub.
2. Sur [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Sélectionne le repo. Build settings : **Framework preset = None**, **Build command = (vide)**, **Output directory = /**.
4. Déploie. Chaque futur `git push` republie automatiquement le site.

## Domaine personnalisé

Une fois le projet créé sur Cloudflare Pages, un domaine perso peut être rattaché depuis l'onglet **Custom domains** du projet (achat du nom de domaine à faire séparément, ex. via Cloudflare Registrar).

## Structure

- `index.html` — page unique, tout le contenu (HTML/CSS/JS inline, pas de dépendances de build)
- Polices chargées depuis Google Fonts (Fraunces, IBM Plex Sans, IBM Plex Mono)
