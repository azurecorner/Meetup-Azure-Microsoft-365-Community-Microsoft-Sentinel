# Meetup-Azure-Microsoft-365-Community-Microsoft-Sentinelt 


 **Qu'est-ce que Microsoft Sentinel ?**
Azure Sentinel est une solution de gestion des informations et des événements de sécurité (SIEM) et de réponse d'automatisation de l'orchestration de la sécurité (SOAR) de Microsoft

Dans cette session, je vais configurer un espace de travail Microsoft Sentinel et en apprendre davantage sur les éléments suivants
* Connecteurs de données
* Cahiers
* Alertes analytiques
* Chasse aux menaces
* Incidents et enquêtes
* Playbooks d'automatisation


**Security Information and event management (SIEM)**
**1. Qu'est-ce que la gestion des informations et des événements de sécurité (SIEM) ?**

Un SIEM est un outil qu'une organisation utilise pour collecter, analyser et effectuer des opérations de sécurité sur ses systèmes informatiques. 

Dans sa forme la plus simple, un système SIEM vous permet de :

Collectez et interrogez les journaux (ou logs).
Effectuez une forme de détection de corrélation ou d'anomalie.
Créez des alertes et des incidents en fonction de vos découvertes des failles de securité.
Un système SIEM peut offrir des fonctionnalités telles que :

* Gestion des journaux : capacité à collecter, stocker et interroger les données des journaux à partir des ressources de votre environnement.
* Alerte : un regard proactif dans les données du journal pour les incidents de sécurité potentiels et les anomalies.
* Visualisation : graphiques et tableaux de bord qui fournissent des informations visuelles sur vos données de journal.
* Gestion des incidents : capacité à créer, mettre à jour, attribuer et enquêter sur les incidents qui ont été identifiés.
* Interrogation des données : un langage de requête riche, similaire à celui de la gestion des journaux, que vous pouvez utiliser pour interroger et comprendre vos données.


**Security Orchestration, Automation and Response (SOAR)**
Un SOAR est Security Orchestration, Automation and Response : un ensemble de logiciels pour collecter les menaces de sécurité à partir de sources et répondre aux événements de sécurité


**Microsoft Sentinel workspace**

**Single-tenant single Log Analytics workspaces**
![espace de travail à tenant unique](https://user-images.githubusercontent.com/108787059/205441652-79dbed21-48a0-4faa-876c-d16ba12ea2cc.png)

Ce Log Analytics workspaces (ou  espace de travail ) reçoit les journaux des ressources provenant d'autres régions sur le  même tenant. Étant donné que les données de journal (lorsqu'elles sont collectées) voyageront d'une région à l'autre et seront stockées dans une autre région, cela crée deux problèmes possibles. Tout d'abord, cela peut entraîner un coût de bande passante. Deuxièmement, s'il existe une exigence de gouvernance des données pour conserver les données dans une région spécifique, l'option d'utiliser un espace de travail unique ne serait pas une option de mise en œuvre.

**tenant unique avec des Log Analytics workspaces (espaces de travail) Microsoft Sentinel régionaux**
![espace de travail régional à tenant unique](https://user-images.githubusercontent.com/108787059/205441664-cd1652b4-0a5e-4b79-b2c0-53474e2621c2.png)

Le tenant unique avec des Log Analytics workspaces Microsoft Sentinel régionaux disposera de plusieurs Log Analytics workspaces Sentinel nécessitant la création et la configuration de plusieurs Log Analytics workspaces Microsoft Sentinel.
* Pas de de gestion centrale. Vous ne cherchez pas au même endroit pour voir toutes les données
* Analytics, Workbooks, etc. doivent être déployés plusieurs fois.
**Multi-tenant Log Analytics workspaces**
![espaces-de-travail-multi-tenants](https://user-images.githubusercontent.com/108787059/205441668-f2482989-ac0b-474d-92d2-3d5579479a64.png)

pour gérer des Log Analytics workspaces  Microsoft Sentinel, qui n'est pas dans un seul tenant, il faudra  gerer des Log Analytics workspaces multi-tenants à l'aide d'Azure Lighthouse.

Créer un espace de travail Microsoft Sentinel
Pour activer Microsoft Sentinel, vous avez besoin d'autorisations de contributeur pour l'abonnement dans lequel réside l'espace de travail Microsoft Sentinel. Pour utiliser Microsoft Sentinel, vous avez besoin d'autorisations de contributeur ou de lecteur sur le groupe de ressources auquel appartient l'espace de travail.
Rôles spécifiques à Microsoft Sentinel
Tous les rôles intégrés Microsoft Sentinel accordent un accès en lecture aux données de votre espace de travail Microsoft Sentinel :

Microsoft Sentinel Reader : peut afficher des données, des incidents, des classeurs et d'autres ressources Microsoft Sentinel.

Microsoft Sentinel Responder : peut, en plus de ce qui précède, gérer les incidents (assigner, rejeter, etc.)

Contributeur Microsoft Sentinel : peut, en plus de ce qui précède, créer et modifier des classeurs, des règles d'analyse et d'autres ressources Microsoft Sentinel.

Microsoft Sentinel Automation Contributor : permet à Microsoft Sentinel d'ajouter des playbooks aux règles d'automatisation. Il n'est pas destiné aux comptes d'utilisateurs.

Pour de meilleurs résultats, ces rôles doivent être attribués au groupe de ressources qui contient l'espace de travail Microsoft Sentinel. Les rôles s'appliquent ensuite à toutes les ressources déployées pour prendre en charge Microsoft Sentinel, si ces ressources se trouvent dans le même groupe de ressources.
![image](https://user-images.githubusercontent.com/108787059/205442362-979c288a-74b9-47bd-8d06-42176ab6274c.png)

**3. Activer Microsoft Sentinelle**
Créer un espace de travail Log Analytics, un compte de stockage, un coffre de clés et une machine virtuelle

**Connecteurs de données**

**Classeur Sentinelle Azure**

**Alertes analytiques**

**Chasse de fil**

La chasse aux menaces est le processus de recherche itérative dans une variété de données dans le but d'identifier les menaces dans les systèmes.
**Incidents et enquêtes**

**Livres de jeu d'automatisation**



https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Qu
