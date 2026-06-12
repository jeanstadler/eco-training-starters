# Mesure - US01 Alléger l'interface

Avant (baseline) : EcoIndex 77 (note B), 366 éléments DOM, 26 requêtes, 0.314 Mo.

Après US01 :
- EcoIndex : 83 / 100 (note A)
- Poids : 0.314 Mo
- Éléments DOM : 220
- Requêtes : 26
- Empreinte (1000 visites/mois) : 1.34 kgCO2e, 20.1 l d'eau

Lighthouse : inchangé (Performance 88, Accessibilité 100, Bonnes pratiques 100, SEO 82).

Bilan : +6 points EcoIndex (77 → 83, passage en note A) et DOM -146 éléments (366 → 220).

Le poids et les requêtes ne bougent pas, c'est normal : l'US01 réduit ce qui est *affiché* (le nombre d'éléments du DOM), pas les *données chargées*. La réduction des requêtes et du poids viendra avec les US suivantes.

Preuve : `ecoindex-us1.pdf`
