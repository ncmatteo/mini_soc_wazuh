# Wazuh Indexer

## Rôle du Wazuh Indexer

Le Wazuh Indexer est le composant chargé du stockage et de l’indexation
des événements et des alertes générés par le Wazuh Server.

Il ne réalise aucune détection.
Son rôle est de rendre les données persistantes, recherchables et exploitables via le dashboard.

Dans ce projet, l’indexer est indispensable pour l’analyse SOC,
car il permet d’explorer les alertes, d’appliquer des filtres
et d’analyser les événements dans le temps.


## Type de données stockées

Le Wazuh Indexer stocke les données sous forme de documents JSON, notamment les alertes de sécurité générées par les règles Wazuh, les événements bruts collectés par les agents
et les métadonnées (agent, hôte, horodatage, niveau de sévérité).

Chaque document correspond à un événement ou une alerte
et peut être recherché à l’aide de filtres (temps, hôte, règle, niveau).



## Flux de données

Le flux de données dans ce projet est le suivant :

1. Les agents envoient les événements au Wazuh Server
2. Le moteur d’analyse génère des alertes
3. Filebeat transmet les alertes au Wazuh Indexer
4. Les données sont indexées et stockées
5. Le dashboard interroge l’indexer pour l’affichage et l’analyse

L’indexer agit donc comme une **base de données orientée analyse SOC**.



## Utilisation dans le projet

Dans ce lab Mini-SOC, le Wazuh Indexer est utilisé pour :
- visualiser les alertes générées lors des scénarios d’attaque
- rechercher des événements précis (processus, IP, utilisateur)
- analyser l’évolution des alertes dans le temps
- appuyer l’analyse des vrais positifs et faux positifs



