# Wazuh Agent

## Rôle du Wazuh Agent

Le Wazuh Agent est déployé sur les endpoints à surveiller.
Son rôle est de **collecter des événements locaux** et de les transmettre
au Wazuh Server via un canal chiffré et authentifié.

L’agent ne réalise **aucune corrélation ni détection avancée**.
Il agit comme une source de données pour l’analyse SOC effectuée côté serveur.



## Endpoints surveillés dans le projet

Dans ce lab Mini-SOC, des agents Wazuh sont déployés sur :
- une machine Windows 
- une machine Linux 

Ces endpoints permettent de simuler différents scénarios d’attaque
et d’observer les comportements systèmes associés.



## Données collectées

Les agents collectent notamment les logs systèmes (Windows Event Logs, journaux Linux), les événements liés aux processus, les connexions réseau et les modifications de fichiers et de configuration

Ces données servent de base à la détection des activités suspectes
lors des scénarios d’attaque.



## Déploiement des agents

Les agents sont déployés à l’aide du Wazuh Dashboard,
via la fonctionnalité Deploy new agent.

Cette méthode permet de générer automatiquement les clés d’enrôlement, de configurer l’adresse du serveur et d’assurer une installation cohérente entre les endpoints

Une fois installés, les agents apparaissent dans le dashboard
avec leur statut (actif, déconnecté, en attente).



## Fonctionnalités utilisées dans le projet

Toutes les fonctionnalités de l’agent ne sont pas exploitées.
Dans ce projet, la collecte de logs, la surveillance des événements système et le support à la détection d’attaques seront utilisé.

Les modules comme la sécurité cloud ou les conteneurs
ne sont pas utilisés dans ce contexte.



## Importance dans l’analyse SOC

Sans agent, aucun événement local ne peut être observé.
Le Wazuh Agent est donc un composant essentiel pour détecter des comportements malveillants, comprendre le contexte d’une alerte et pouvoir analyser la chronologie des événements sur un endpoint
