# Exercice 6 - Reponse HTTP, assets et mise en cache

## Objectifs 
Cet exercice a pour objectifs : 
* De définir les bonnes réponses HTTP
* De gérer au mieux les assets
* D'utiliser la mise en cache

## Reponses HTTP et leur entête

* Dans les réponses renvoyées par notre application, quelles sont les entêtes liées à la mise en cache qui sont définies ?
* Peut on les optimiser / ajouter ?
* Comment définir les valeurs de chacune des entêtes ? 
* Comment invalider en PHP le cache HTTP (pour forcer une MAJ depuis le serveur par exemple) ?

## Gérer les assets

* Comment les feuilles de styles et script js sont envoyées au navigateur ?
* Y'a t'il un ou plusieurs scripts ?
* Sont t'il envoyé au début ou à la fin de la page ?
* Sont t'il compressés ?
* Côté symfony ont t'il bien été publié ? 
* Est ce que les assets sont bien mise en cache par le navigateur ? 

## Mise en cache des données côté serveur

* Il est possible de mettre en cache les données dans notre application. Cela permet d'éviter à PHP de recalculer des données pour un certain temps ou tant qu'on ne lui a pas demander de le faire.
* Cela est fait dans l'application exemple, quelle service est utilisé pour cela ?
* Quelles sont les conditions d'invalidation du cache ?
* Y'a t'il d'autres parties de l'application qui pourraient être mise en cache ?

## Pour aller plus loin 
* Varnish et les ESI sont également des solutions de caches exploitables pour des sites à fort trafic : https://blog.link-value.fr/varnish-concr%C3%A8tement-comment-%C3%A7a-marche-33be251ce46f
* Utiliser Redis pour mettre en cache l'execution de son code : http://www.w3big.com/fr/redis/redis-php.html 
* Utiliser un CDN : https://blog.site-web-creation.net/cdn/ 