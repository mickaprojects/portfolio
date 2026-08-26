# Portfolio — Micka Andriamiadanarivo

Site one-page bilingue (FR/EN), statique, sans build. Le contenu complet est dans `index.html`.

## Déployer sur Cloudflare Pages

**Statut actuel (depuis le 2026-08-26) : déploiement automatique via GitHub, actif.**

Le code est sauvegardé sur https://github.com/mickaprojects/portfolio (branche `master`), et le projet Cloudflare Pages `micka-portfolio` est connecté à ce repo (Settings → Build → Git repository). Build settings : Framework preset = None, Build command = (vide), Root directory = (vide) — site statique, pas d'étape de build.

**Workflow habituel pour publier une modif :**

```
git add .
git commit -m "ton message"
git push
```

Cloudflare détecte le push et republie automatiquement sur https://micka-portfolio.pages.dev en quelques secondes — aucune commande de déploiement à lancer.

### Solution de secours — Upload direct via Wrangler

Si jamais le lien Git casse ou que tu veux publier sans passer par GitHub :

```
npm install
npx wrangler login       # ouvre le navigateur pour connecter ton compte Cloudflare
npm run deploy
```

## Domaine personnalisé

Une fois le projet créé sur Cloudflare Pages, un domaine perso peut être rattaché depuis l'onglet **Custom domains** du projet (achat du nom de domaine à faire séparément, ex. via Cloudflare Registrar).

## Structure

- `index.html` — page unique, tout le contenu (HTML/CSS/JS inline, pas de dépendances de build)
- Polices chargées depuis Google Fonts (Fraunces, IBM Plex Sans, IBM Plex Mono)
