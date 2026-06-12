# Plan d'action

Le point de départ est la mesure EcoIndex actuelle du tableau de bord : score de 77.

Les actions sont traitées une par une, dans l'ordre de la priorisation et du backlog. Après chaque action, une nouvelle mesure est comparée à la précédente pour voir le gain réel.

## Étapes

1. **Baseline initiale**

   Conserver les preuves de mesure dans `mesures/00_baseline_initiale/`.

2. **US01 - Alléger l'interface**

   Réduire le nombre d'éléments affichés sur le tableau de bord : journal plus court, graphiques simplifiés, blocs et indicateurs en double retirés.

   Mesure dans `mesures/us01_alleger_interface/`.

3. **US02 - Réduction du rafraîchissement automatique**

   Couper le rafraîchissement automatique toutes les 5 secondes, ou le remplacer par un rafraîchissement manuel.

   Mesure dans `mesures/us02_reduire_rafraichissement/`.

4. **US03 - Chargement initial léger**

   Ne charger au démarrage que les données utiles à la première vue, au lieu de tout charger d'un coup.

   Mesure dans `mesures/us03_chargement_initial_leger/`.

5. **US04 - Pagination et détail à la demande**

   Paginer la liste des dossiers et charger les notes et l'historique seulement à l'ouverture d'un dossier.

   Mesure dans `mesures/us04_pagination_detail_demande/`.

6. **US05 - Minification du JS et du CSS**

   Activer la minification au build dans `vite.config.ts` (JS via esbuild, CSS), puis servir le build de production (`npm run build` puis `npm run preview`). À mesurer sur le build, pas sur le serveur de dev.

   Mesure dans `mesures/us05_minification/`.

## Roadmap sur 6 mois

- **Mois 1** : US01 et US02, les deux actions à plus fort impact (interface allégée et fin du rafraîchissement automatique). Mesure après chaque action.
- **Mois 2 et 3** : US03 et US04 (chargement initial ciblé, pagination et détail à la demande).
- **Mois 4** : US05 (minification et build de production) et remise en place d'un cache simple, puis mesure complète (EcoIndex et Lighthouse).
- **Mois 5 et 6** : suivi dans le temps. Garder un budget d'éléments et de requêtes, et vérifier à chaque évolution que le score reste au-dessus de 90.

## Méthode

Une seule user story est traitée à la fois. Chaque mesure est faite de la même façon que la baseline, pour que la comparaison avant / après reste fiable. L'objectif est de passer de 77 à 90 ou plus.
