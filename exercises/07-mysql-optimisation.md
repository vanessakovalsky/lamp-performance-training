# Exercice 7 - Optimisation de la base de données et de ses requêtes

## Objectifs
Cet exercice a pour objectifs : 
* De verifier la structure de la base de données et de l'optimiser
* D'optimiser les requêtes et la configuration de la BDD

## Optimiser la structure de sa BDD 
* Quels sont les index présents dans votre base de données ?
* Est ce que les types de colonnes correspondent bien aux données quelles contiennent (par exemple par de VARCHAR s'il s'agit de nombre, cela ralentit les requêtes) ?
* Est ce que certaines tables contiennent plusieurs dizaine de colonnes ? Est t'il possible de séparer cela en différentes tables ? 
* Quels sont les clés étrangères utilisées ? Les options de cascade sont t'elles bien activées ? 
* Quel est le moteur utilisé pour chaque table ?


## Optimiser les requêtes et la configuration 

* Pour les requêtes SQL, a l'aide des logs des slow query, identifier les requêtes qui prennent plus d'une seconde a s'exécuter ?
* Ces requêtes sont des requêtes que vous avez écrites ou celles produites par l'ORM ? 
* Peuvent elle etre optimiser ? (n'hésitez pas à faire des tests directement en SQL pour obtenir le temps d'execution de la requête)

* Au niveau de la configuration, combien de connexion simmultannée accepte votre BDD ?
* Quel est la taille maximum d'une requête ? Et d'une réponse ? 
* Le cache est t'il activé ?

-> Optimiser la structure et les requêtes dans votre application puis de nouveau relancer le script AB, puis le scénario jmeter et enfin un scénario manuel avec le profiling activé pour constater la différence