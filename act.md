# Heuristiques — problème d’ordonnancement

### Tp de Dufloer Rémi 

## Travail préliminaire

### Q1)

Afin de calculer la qualité d'ordonancement j'ai créé un algo qui va tout d'abord recuperer les données d'un fichier afin de récuperer les taches avec leur temps d'exécution, leur poids ainsi que leur temps limite,

Une fois cela, je fais le calcul de qualité de l'ordonancement en reprenant la formule donnée dans le tp, cela se traduit dans le code par :

```py
for i in (ordonancement):
        time_total += int(liste_des_objet[i][0])
        Tj = max(time_total - int(liste_des_objet[i][2]),0)
        quality += int(liste_des_objet[i][1])*Tj
```

**avec quality et time_total initialisé a 0**

### Q2)

Génerer une solution aléatoire reviens à choisir aléatoirement une tache dans une liste de tache, de retirer cette tache dans cette liste et de recommencer cette opératon jusqu'à ce qu'il nest plus de tache dans la liste .


## Heuristiques constructives et recherche locale simple

### Q3)

Ici on cherche a comment pourrons nous créé un ordonancement juste avec ce que l'on connait sur les taches.

J'ai ainsi codé 3 Heuristiques , une qui est on prend les taches dans l'ordre qu'elles sont écrites dans le fichier, la seconde est on prend les taches qui ont un temps d'éxécution le plus court, la dernière est celles qui ont un plus court temps de retard.

Nous ferons une analyse à la question 7 sur les résultats

### Q4)

J'ai implémenter un seul voisinage, c'est un voisinage de permutation .
J'ai cependant implémenter en dur 4 recherche locale simple, toute de type Hill Climing :

    - hillClimbingBestNeighbour :
            initialisation : solution random
            type de mouvement : meilleur voisin 
    - hillClimbingWorstNeighbour :
            initialisation : solution random
            type de mouvement : pire voisin 
    - hillClimbingFirstNeighbour :
            initialisation : solution random
            type de mouvement : premier voisin 
    - hillClimbingGeneral :
            initialisation : vous avez le choix parmis :
                        - solution random
                        - les heuristique de la question 3
            type de mouvement : vous avez le choix parmis :
                        - ceux cité au dessus et un voisin random

## Recherche locale itérée

### Q5)

Implémenter une recherche locale itérée de type ils est assez simple une fois que l'on a fait un Hill Climbing,
on doit tout d'abord crée une solution initial, ensuite on cherhce les voisin de cette solution et on va en choisir un celon un critére, mais a partir de maintenant on va modifier les instances de la solution avec une perturbation, ici en inversant k valeur.
 
suite au résultat observer precedement j'ai fait un iterated local search avec une initialisation avec une heuristique de plus court retard, un pivot de bestNeighbour et une condition d'arret qui est un n itération

### Q6)

#### annalyse Heuristiques constructives et recherche locale simple, meilleur sollution objective :

    ici mettre l'image 

Voici un graphique montrant le score sur 5 fichier avec tout les Heuristiques constructives et recherche locale simple citées au dessus.
    
L'échel sur ce graphique est une échelle arbitraire car les score en fonction des fichier varient beaucoup.

On remarque que l'algorithme Hill Climbing avec un mouvement ou on choisis le bestNeighbour et une initialisation avec l'heuristique du plus court retard, nous renvoie toujours les meilleur solution 

#### annalyse Ils, meilleur sollution objective  :
 
L'algorithme Ils permet d'obtenir de meilleur résultat cependant ce dernier met bien trop de temps, j'ai trouvé mes meilleurs résultat avec un n= 50 et un k = 6

#### analyse en temps :

Ce qui est le plus viable en temps sont les heuristique implémenter a la question 3 car la compléxité des heuristique est en moyenne en O(n).

Cependant entre ILS et Hill Climbing, le temps est bien plus long, tout d'abord hill climbing est plus rapide que Ils car Ils appel Hill Climbing, de plus Ils appel au minimimum n * Hill Climbing avec n = n_itération .

### Choix du meilleur algorithme :

Avec toute l'analyse fait auparavant mon choix se porte sur l'algorithme Hill Climbing avec un mouvement ou on choisis le bestNeighbour et une initialisation avec l'heuristique du plus court retard car il a de très bon résultat et il est bien plus rapide qu'un ILS ainsi si on doit avoir une bonne solution dans un petit temps je choisis ce dernier .


### Q7) 

les résultats sont directement sur le site contest 

## Problèmes rencontrer

- J'ai eu du mal a réaliser un bencmark qui réalise exactement ce que je voulais 
- J'ai eu des problèmes liées au temps que mets ils a tourner 