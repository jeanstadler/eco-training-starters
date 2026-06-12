# Constats avant la première action

L'application a d'abord été observée dans le navigateur, puis le code a été vérifié pour comprendre ce qui est affiché et chargé au démarrage du tableau de bord.

## Constats principaux

**Interface trop dense**

Le tableau de bord affiche beaucoup d'éléments en même temps : un journal d'une vingtaine d'événements, six graphiques détaillés, plusieurs listes et des indicateurs répétés entre la barre latérale et la vue centrale. Cela fait un nombre d'éléments élevé à l'affichage (366), et c'est le point qui pèse le plus sur le score.

**Rafraîchissement automatique trop fréquent**

La page se recharge automatiquement toutes les 5 secondes. Chaque cycle relance plusieurs appels réseau, même quand rien ne change à l'écran. Cela multiplie les requêtes et alourdit l'usage en session longue.

**Trop de données chargées d'un coup**

À l'ouverture, l'application récupère en une seule fois les données du tableau de bord, des dossiers, de l'analyse et des réglages. La première vue n'a pourtant besoin que d'une partie de ces informations.

**Liste des dossiers et détails chargés trop tôt**

La liste complète des dossiers est chargée dès le départ, avec pour chacun les notes longues et l'historique. Ces détails ne sont utiles qu'au moment où un dossier est ouvert.

**JavaScript non minifié**

Lighthouse montre que le JavaScript est servi non minifié, et qu'une partie du code n'est pas utilisée. Le code est donc plus lourd que nécessaire à charger.

## Première action retenue

La première action retenue est d'alléger l'interface du tableau de bord, en réduisant le nombre d'éléments affichés au premier plan. C'est l'action qui agit le plus directement sur le score.
