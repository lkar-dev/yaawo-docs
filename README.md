# YAAWO API — Static Documentation

Swagger UI statique pour l'API YAAWO, hébergé sur GitHub Pages.

**URL** : https://lkar-dev.github.io/yaawo-docs/

## Structure

```
index.html       — Swagger UI (charge swagger-ui-dist via CDN)
openapi.json     — Spécification OpenAPI 3.1.0 (générée par Scramble)
```

## Mise à jour

Après chaque évolution de l'API, régénérer la spec et copier le fichier :

```bash
# Depuis le repo yaawo-api
DB_CONNECTION=sqlite DB_DATABASE=:memory: php artisan scramble:export
cp api.json ../yaawo-docs/openapi.json
rm api.json

# Pousher vers GitHub Pages
cd ../yaawo-docs
git add openapi.json
git commit -m "docs: update openapi.json"
git push origin main
```
