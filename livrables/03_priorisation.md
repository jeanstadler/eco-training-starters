# Priorisation

La priorisation part des constats : l'interface affiche beaucoup d'éléments, la page se rafraîchit automatiquement, trop de données sont chargées à l'ouverture et la liste des dossiers est complète dès le départ.

Le poids de la page est déjà faible. Pour gagner des points, il faut agir d'abord sur ce qui pèse le plus dans le calcul EcoIndex : le nombre d'éléments affichés, puis le nombre de requêtes.

## Ordre retenu

1. **US01 - Alléger l'interface**

   C'est l'action la plus prioritaire. Le nombre d'éléments du DOM est ce qui pèse le plus sur le score. Réduire les blocs affichés au premier plan agit donc directement dessus.

2. **US02 - Réduction du rafraîchissement automatique**

   La page se recharge toute seule toutes les 5 secondes et relance plusieurs appels à chaque fois. Couper ce rafraîchissement est un gain rapide sur le nombre de requêtes et sur l'usage en session longue.

3. **US03 - Chargement initial léger**

   À l'ouverture, l'application charge en une fois des données dont la première vue n'a pas besoin. Ne charger que l'utile réduit le poids et les requêtes au démarrage.

4. **US04 - Pagination et détail à la demande**

   La liste complète des dossiers et leurs détails sont chargés trop tôt. Paginer la liste et charger les notes et l'historique au clic réduit les données envoyées sans intérêt immédiat.

5. **US05 - Minification du JS et du CSS**

   Lighthouse signale du JavaScript non minifié et du code inutilisé. Servir un build de production, où le JS et le CSS sont minifiés et le code inutile retiré, corrige ce point et réduit le nombre de requêtes. Cette action vient en dernier car elle fait passer la mesure du serveur de dev au build de production.

## Logique générale

Les deux premières actions visent ce qui compte le plus pour le score : moins d'éléments à l'écran et moins d'appels réseau. Les deux suivantes améliorent la sobriété en usage réel : moins de données chargées d'un coup, moins de détails inutiles. La dernière, la minification, s'appuie sur le build de production et règle le point soulevé par Lighthouse.

Après chaque user story, une nouvelle mesure EcoIndex est faite dans le dossier de mesure correspondant.
