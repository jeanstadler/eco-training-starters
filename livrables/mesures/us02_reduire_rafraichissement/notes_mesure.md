# Mesure - US02 Réduction du rafraîchissement automatique

Avant (état post-US01) : EcoIndex 83 (note A), 220 éléments DOM, 26 requêtes, 0.314 Mo.

Après US02 :
- EcoIndex : 83 / 100 (note A)
- Poids : 0.309 Mo
- Éléments DOM : 223
- Requêtes : 22
- Empreinte (1000 visites/mois) : 1.34 kgCO2e, 20.1 l d'eau

Lighthouse : Performance 88 → 100 (TBT 0 ms). Accessibilité 100, Bonnes pratiques 100, SEO 82 (inchangés).

Bilan : requêtes 26 → 22 (-4) et Lighthouse Performance 88 → 100. Le score EcoIndex reste à 83 (note A).

Le score ne bouge pas, c'est normal : l'EcoIndex mesure un seul chargement, alors que le polling pesait surtout sur la durée d'une session (4 requêtes toutes les 5 s). Le vrai gain se voit sur le temps d'usage et sur Lighthouse, pas sur un scan ponctuel.

Preuves : `ecoindex-us2.pdf`, `lighthouse-us2-scores.png`, `lighthouse-us2-metriques.png`
