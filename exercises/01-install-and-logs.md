# Exercice 1 - Installation du projet et découverte des logs

## Objectifs

Cet exercice a pour objectifs : 
* d'avoir un environnement complet fonctionnel avec une application PHP
* De savoir quels sont les logs difsponibles et où se trouvent t'ils
* D'être capable depuis son application d'ajouter des logs


## Pré-requis
* Nous avons besoin pour l'application de différents éléments
    * docker 
    * docker-compose
    * git
    * un navigateur (nous vous recommandons Firefox de Mozilla)
    * d'un editeur de code (comme Visual Studio Code, mais prenez celui avec lequel vous êtes le plus à l'aise)

## Installation
* Afin de réaliser l'ensemble des exercices de la formations nous vous demandons de suivre les étapes suivantes :
    * Cloner le dépôt
    * Se positionner à la racine du dossier du dépôt cloné et lancer la commande : 
    ```
    docker-compose up -d
    ```
    * Créer le fichier .env à la racine de l'application avec les informations de connexion à la BDD
    * Se connecter en ssh sur le conteneur php puis lancer les commandes suivantes :
    ```
    php bin/console doctrine:schema:create
    php bin/console doctrine:fixtures:load
    ```
    * Une fois les 3 conteneurs lancés, vous pouvez vous rendre sur l'ip de votre docker avec le port 8054 
    * Vous devriez obtenir un écran de connexion à l'application (un utilisateur tel que décrit dans la fixture User a été crée et peut être utilisé)

## Quels sont les logs disponibles et où les trouver ?

* Il existe différents logs pour votre application : 
    * Les logs systemes qui se trouvent généralement sous Linux dans le dossier /Var/log dans un fichier nommé syslog
    * Les logs du serveur web, dans notre cas nginx, ils sont accessible dans le dossier /var/log/nginx du conteneur nginx
    * Les logs de php se trouve dans le dossier /var/log par défaut
    * Les logs de la base de données qui pour mysql est précisé dans le fichier my.cnf qui est le fichier de configuration
    * Les logs des conteneurs auxquels ont peut accéder avec la commande : 
    ```
    docker logs [nomducontainer]
    ```
    * Enfin il existe egalement avec symfony comme avec de nombreux autres framework ou outils des logs applicatifs. 
* Chaque brique ayant ses propres logs, ils ont également chacun leur propre configuration.
    * Pour le serveur web, il existe une configuration générique et après chaque Virtual Host a sa propre configuration. Dans notre cas, ouvrer le fichier /nginx/default.conf pour voir la configuration utilisée par nginx et chercher les lignes correspondantes aux logs.
    * Pour php, un fichier php.ini existe et permet de configurer parmi de nombreux autres élements les logs, comme par exemple le niveau de log que l'on souhaite enregistré.
    * Pour mysql c'est le fichier my.cnf qui contient la configuration et permet notamment d'activer l'enregistrement dans les logs des requêtes lentes via le paramètre slow_query 

* Quel est le format commun des logs dans les différents fichiers ?

* Quels sont les informations qui sont utiles pour les aspects performances dans ces logs ?

## Ajouter des logs à l'application avec Monolog

* Définir dans votre applications les logs intéressants pour la performance
* A l'aide de la documentation, (https://symfony.com/doc/current/logging.html ) ajouter les logs dans le code de l'application
* Quelles fonctions de PHP peut on utiliser pour obtenir des informations liées à la performance ?

## Bonus ( a lire / faire en dehors de la formation si cela vous intéresse)
* Il est possible de centraliser ses logs pour avoir une seule interface de consultation et de recherche dans ses logs avec des outils comme la suite Elastic (anciennement ELK pour Elasticsearch Logstash Kibana): https://www.elastic.co/fr/products/  
* Voir un exemple ici avec wordpress : https://github.com/vanessakovalsky/docker-training/blob/698579956fe9fbed4cc282359ea406aba937943b/tp/tp7/tp7.md#centralisation-des-logs 