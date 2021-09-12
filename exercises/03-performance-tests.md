# Exercice 3 - mesurer pour performer

## Objectifs
Cet exercice a pour objectifs : 
* de vous permettre d'identifier les étapes pour savoir d'où un problème de performance peut venir
* de préparer des scénarios répetable avec des outils pour simuler une montée en charge et mesurer les performances de votre applications

## Identifier un problème de performance
* Suite à un reportage à la TV sur l'entreprise, le site web s'est écroulé et ne répondait plus. Il a été nécessaire de redémarrer le serveur pour pouvoir de nouveau accéder au site.
* Identifier les causes de ce problème, pour cela :
    * Décrire les étapes à effectuer
    * Identifier les causes possibles
    * Comment avez vous été informé de ce problème ? Au bout de combien de temps ?
* Vous devriez maintenant avoir un plan d'action pour identifier le problème.

## Mesurer ses performances avec des benchmarls
* ab est un outil fourni par apache qui permet de simuler de la charge sur son serveur : https://httpd.apache.org/docs/2.4/fr/programs/ab.html 
* Préparer un script de tests de charge avec l'utilitaire ab pour simuler une charge qui augmentera progressivement pour savoir à partir de quand le serveur ne répond plus.
* L'objectif ici est d'identifier à partir de combien d'utilisateur le site ne repond plus.

## Définir un scénario de test de charge avec Jmeter
* Jmeter permet de définir un scénario et de répeter son utilisation afin de simuler une montée en charge avec le comportement d'un utilisateur.
* Définir sur notre application le parcours le plus utilisé (par exemple, je me connecte, je liste les match et je place un pari) et le transformer en scénario Jmeter pour pouvoir simuler celui-ci de nombreuses fois : 
https://www.loadview-testing.com/fr/the-ultimate-guide-to-jmeter-load-performance-testing-tutorial/ 

--> Nous sommes maintenant prêt a voir quel charge notre serveur peut supporter sans optimisation.

* Lancer successivement le script ab puis noter les résultats.
* Redémarrer le serveur et lancer le scénario jmeter, la aussi noter les résultats.
* Ces résultats nous servirons de point de départ pour les améliorations que nous allons apporter.


## Pour aller plus loin - d'autres outils

* k6 permet aussi de faire du benchmark : https://k6.io/ 
* Siege est un autre utilitaire de test de charge : https://fr.linux-console.net/?p=75 