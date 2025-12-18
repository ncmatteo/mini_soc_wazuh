# Wazuh Server

## Rôle du Wazuh Server

Le Wazuh Server est le composant central de l’architecture.
Il reçoit les événements collectés par les agents, applique les règles de détection,
corrèle les logs et génère des alertes de sécurité.

Dans ce projet, le serveur joue le rôle d’outil d’analyse SOC :
sans lui, les agents ne feraient que collecter des données
et l’indexer ne servirait qu’au stockage.



## Architecture
Le lab est volontairement déployé sur une seule machine Linux.
Ce choix permet de se concentrer sur la compréhension du moteur d’analyse, la détection d’attaques et l’analyse des alertes.

Les composants suivants sont utilisés :
- Wazuh Manager
- Analysis Engine
- Wazuh API
- Filebeat (envoi vers l’indexer)

Aucune architecture cluster ou haute disponibilité n’est mise en place,
car elle n’est pas nécessaire dans un contexte de lab.



## Fonctionnement global

Le fonctionnement du Wazuh Server dans ce projet suit les étapes suivantes :

1. Les agents collectent les événements sur les endpoints (Windows, Linux)
2. Les logs sont transmis au Wazuh Server
3. Les décodeurs interprètent les événements
4. Les règles de détection sont appliquées
5. Les alertes générées sont envoyées vers l’indexer
6. Les alertes sont visualisées dans le dashboard



## Utilisation dans les scénarios d’attaque

Le Wazuh Server est utilisé pour :
- détecter l’exécution de processus suspects
- identifier des mécanismes de persistance
- analyser les comportements observés lors des scénarios d’attaque
- corréler les événements avec les techniques MITRE ATT&CK

Les alertes générées sont ensuite analysées comme dans un contexte SOC
afin de distinguer les vrais positifs des faux positifs.
