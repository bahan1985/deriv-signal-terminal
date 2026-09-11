# Deriv Signal Terminal

Terminal web de signaux **manuel uniquement** pour les indices synthétiques Deriv.

## Fonctionnement

- Connexion au WebSocket public de Deriv pour les données de marché.
- Détection dynamique des actifs synthétiques via `active_symbols`.
- Historique initial via `ticks_history`.
- Flux temps réel via `ticks`.
- Un contexte indépendant par actif : buffer de ticks, analyse, cooldown et état.
- Indicateurs : EMA 9/21/50, RSI 14, momentum/ROC, volatilité tick, accélération, structure HH/HL ou LH/LL, confirmation récente.
- Score de confluence sur 100.
- `NO TRADE` par défaut lorsque la confluence est insuffisante.
- Expiration dynamique recommandée entre 2 et 10 ticks lorsqu'un signal dépasse le seuil.
- Protection contre les ticks dupliqués.
- Aucun ordre Deriv n'est envoyé. Le terminal produit seulement des indications CALL/PUT destinées à une entrée manuelle.

## Publication GitHub Pages

1. Créez/ouvrez votre dépôt GitHub.
2. Ajoutez `index.html` à la racine du dépôt.
3. Allez dans **Settings → Pages**.
4. Dans **Build and deployment**, choisissez **Deploy from a branch**.
5. Sélectionnez la branche `main` et le dossier `/ (root)`.
6. Cliquez **Save**.
7. Après le déploiement, GitHub affichera l'URL Pages.

## Important

Ce terminal est un outil d'analyse expérimentale. Un score élevé n'est pas une garantie de gain. Testez d'abord en démo et conservez le mode manuel.
