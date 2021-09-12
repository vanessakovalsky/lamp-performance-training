# Exercice 5 - Profiler et optimiser php

## Objectifs

Cet exercice a pour objectifs : 
* d'utiliser xdebug pour obtenir des informations sur l'execution du code PHP
* d'optimiser le code PHP et sa configuration

## Profiler une application PHP avec xdebug

* Commencer par installer xdebug : 
```
sudo apt-get install php-xdebug
```
* Ou sur un autre environnement : https://xdebug.org/docs/install 
* Pour activer le profiler et récupérer les informations de profiling voir ici : https://xdebug.org/docs/profiler 
* Vous pouvez aussi consulter cette vidéo en français : https://www.youtube.com/watch?v=mahIIF0c8Zo 
* Ou celle-ci poru le profiling : https://www.youtube.com/watch?v=mNc_tcomrVs 

* Une fois xdebug configurer, lancer votre application et naviguer dans celle-ci en suivant un scénario classique.
* Aller voir dans les resultats du profiling, quelles sont les fonctions qui prennent du temps à s'executer dans votre code 

## Optimiser son code PHP et sa config

* A l'aide du profiling effectuée, quelles sont les fonctions PHP qui sont très lente dans votre code ?
* Peuvent elle être simplifiée ? 
* Quels types de boucles utilisez vous ?
* Y'a t'il des boucles dans des boucles ?

* Dans le fichier php.ini certaines configuration peuvent ralentir l'execution de votre code. 
* Vous pouvez par exemple commenter l'ensemble des valeurs qui sont dans votre fichier pour forcer php a utilise ses valeur par défaut. 
* Puis voir ensuite en les decommantant une par une lesquelles accélère ou ralentissent l'execution de votre code? (pour vous aguiller, il peut être utile de regarder en // ce qu'il se passe sur la machine pour voir si la RAM, le CPU, le disque sont utilisés correctement)

-> L'optimisation est un travail plutôt empirique sur la partie code et configuration.

* Une fois les correctifs de code et de configuration effectuées, le profiling est t'il toujours le même ? Combien de temps avez vous gagné ?

* Une fois les optimisations apportées, relancer un test de charge avec le script ab puis avec votre scénario jmeter pour voir la différence. 

## Pour aller plus loin 

Il existe de nombreux autres outils pour profiler du code php 
* le framework phpbench: https://github.com/phpbench/phpbench
* un plugin pour le faire depuis datadog : https://github.com/DataDog/dd-trace-php 
* blackfire : https://blackfire.io/docs/introduction
