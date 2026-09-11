# Architecture

Le projet volontairement initial est un site statique : un seul `index.html`.
Cela évite Node, serveur et base de données pour le premier déploiement.

Le moteur est organisé conceptuellement en :

- `assets: Map<symbol, AssetContext>`
- `AssetContext.ticks`
- `analyze(context)`
- `addTick(context, quote, epoch)`
- rendu indépendant de chaque carte

Évolution recommandée après validation du MVP :
1. journal persistant côté serveur,
2. replay/backtest avec exactement la même fonction `analyze`,
3. ranking avancé,
4. statistiques par actif/direction/expiration/score/setup,
5. authentification éventuelle,
6. backend si l'on veut conserver l'historique sur plusieurs appareils.

Le flux de marché utilisé ici ne nécessite pas d'authentification selon la documentation Deriv.
