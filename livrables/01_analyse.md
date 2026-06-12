# Analyse initiale

Repo analysé : `eco-training-starters/heavy-ops`

Catégorie : dashboard / outil métier / SaaS interne.

## Baseline EcoIndex

Mesure réalisée sur le tableau de bord, la page principale de l'application.

- Score : 77 / 100 (note B)
- Poids de page : 0.314 Mo
- Éléments DOM : 366
- Requêtes : 26
- Empreinte pour 1000 visites par mois : 1.46 kgCO2e et 21.9 l d'eau

## Baseline Lighthouse

- Performance : 88
- Accessibilité : 100
- Bonnes pratiques : 100
- SEO : 82

Lighthouse signale surtout du JavaScript non minifié (environ 737 Ko d'économies possibles) et du code JavaScript inutilisé (environ 685 Ko). Ces deux points se corrigent avec un build de production, qui minifie le code et retire l'inutile.

Données : 180 dossiers, fichiers data autour de 196 Ko.

## Observation principale

Le poids de la page est déjà faible. Ce qui tire le score EcoIndex vers le bas, c'est surtout le nombre d'éléments affichés (366), puis le nombre de requêtes (26).

Dans le calcul EcoIndex, le nombre d'éléments du DOM pèse plus que les requêtes, qui pèsent elles-mêmes plus que le poids. Le levier principal est donc d'alléger l'interface du tableau de bord, puis de réduire les appels réseau. Côté Lighthouse, le gain le plus simple est de servir un build de production minifié.
