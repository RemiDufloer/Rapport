# Sommaire 

1. [Introduction](#introduction)
    1. [Présentation du logiciel](#présentation-du-logiciel)
    2. [Comment contacter les auteurs](#comment-contacter-les-auteurs)
    3. [Version du logiciel](#version-du-logiciel)
2. [Manuel d'installation utilisateur](#manuel-d-installation-utilisateur)
3. [Manuel d'utilisation](#manuel-d-utilisation)
    1. [Les fonctionnalités implantées et leurs limitations](#les-fonctionnalités-implantées-et-leurs-limitations)
    2. [Les fonctionnalités non implantées](#les-fonctionnalités-non-implantées)
    3. [Tutoriel](#tutoriel)
    4. [Les bugs connus et comment les contourner](#les-bugs-connus-et-comment-les-contourner)
5. [Manuel de maintenance](#manuel-de-maintenance)
    1. [Le métamodèle](#le-métamodèle)
    2. [Les templates](#les-templates)
7. [Historique du développement](#historique-du-développement)
8. [Bilan et perspectives](#gestion-des-fichiers)
9. [Conclusion](#demandes-de-fusion)

## Introduction

Notre logiciel permet de concevoir des application android en modélisant cette application à un haut niveaux d'abstraction. Puis notre logiciel va générer le code complet de l'application en android. Il suffit après de le compiler et de l'installer sur un appareil android.

#### Présentation du logiciel

Notre logiciel et décomposer en 3 grande partie. La première partie est le métamodèle, ce dernier définit les principes disponibles pour notre application.
La seconde partie est la création de modèles que ce soit de façon arborescente ou de façon graphique. On met ici à disposition plusieurs possibilitées pour que l'utilisateur conçoit l'application qui désire.
La dernière partie elle sert à générer le code android.

#### Comment contacter les auteurs

- Romain Degrave :  romain.degrave.etu@univ-lille.fr
- Rémi Dufloer : remi.dufloer.etu@univ-lille.fr 

#### Version du logiciel

 Version ( ici je sais pas quoi mettre )

## Manuel d installation utilisateur

Pour installez notre logiciel vous allez devoir tout d'abbord installez `Android Studio` vous pouvez suivre le tutoriel suivant : https://developer.android.com/studio/install

Ainsi que `Eclypse Papirus` pour cela voici un tutoriel : https://www.fil.univ-lille.fr/~dumoulin/docs/blogs/installerPapyrusPourIDMetPJE.html

Une fois que cela est fait il vous faudrat cloner notre logiciel sur votre ordinateur, pour cela ouvrez `Eclypse Papirus`. 
Mettez vous en perspective git, puis cliquer sur **cloner un projet** (ici verifé que cela est le bon terme) il faudrat ensuite y mettre l'addresse suivante **https://gitlab-etu.fil.univ-lille.fr/remi.dufloer.etu/degrave_dufloer_pje-a_idm.git**

Une fois cela fait il faudrat importer les projet suivant : **multiActivity** , **multiActivity.edit** , **multiActivity.editor**
Pour cela faites un clique droit sur le working tree puis sur `Importer`.

Mettez vous ensuite en perspective modeling puis rendez vous sur le métamodèle en allant sur **multiActivity** puis **model** puis **multiActivty.aird** faite un click droit et **generate all** comme ici :
![image](https://user-images.githubusercontent.com/92677219/209837805-f898fa43-c5c3-4ed5-aec5-2e9d1ea0b1b7.png)


Cliquez sur la fleche verte et lancer une eclipse application comme ici : 
![image](https://user-images.githubusercontent.com/92677219/209837747-7fd4d3e4-3e56-42f7-a41e-755d78da42ba.png)

Un nouveau `Eclipse` va s'ouvrir, dans celui-ci il faudrat cloner comme precèdement le logiciel puis cette fois-ci importer tout le reste.

## Manuel d utilisation

#### Les fonctionnalités implantées et leurs limitations

En ce qui concerne des concepts Android implémentées et pris en charge nous avont implémentées :
- le concept d'Activity et leur layout
- différente view comme par exemple celle qui fait pop up un message ou la date, ainsi que des textView.
- le concept de Buttons (popup, newActivity)
- la navigation entre les Activity en cliquant sur un bouton
- Affichage de Listes, relié à une datasource et un type d’entité, avec possibilité de choisir les propriétés à afficher et avec possibilité de créer un nouvel élément
- Affichage d’Entity
- Déclaration d’Entity avec des types primitifs (String, int, boolean, Double)
- Déclaration de source de données qui est une liste java
    

#### Les fonctionnalités non implantées

Les fonctionnalités non implantées sont :

- Entity avec des propriétés complexes (typé par une autre entité)
- Fragments
- Datasource de type BD, Rest, Contact 

#### Tutoriel

Précision avant le tutoriel :

Lorsque vous créer un modèle vous n'avez pas besoin de remplir les champs **id**, ils seront automatiquement remplies par le logiciel. 

Passons maintenant a un petit tutoriel de ce qui est possible de faire avec notre logiciel.

Tout d'abord nous allons crééer un modéles de façon arborescente puis nous verrons comment crééer ce modèles de façon graphique.

Tout d'abord de façon arborescente, il faut pour commencer crééer un nouveaux fichier dans le fichier test de l'Eclipse d'application. Ce nouveaux fichier et un fichier de type **multiActivity Model**

Une fois ce fichier créer vous pouvez vous inspirez de ce qui vous est donnez en démo dans ce même dossier comme par exemple le fichier **Mymultiactivity**

![image](https://user-images.githubusercontent.com/92677219/209840719-3d7928dc-0328-433c-b1a9-19eb252ff207.png)

on voit ici comment crééer une Application simple, c'est a dire sans liste.

Allons y pas a pas :

Tout d'abord si vous cliquez sur **Application** vous vez la possibilité de modifier le nom de votre application.

Une fois cela fait, si vous faite un clic droit sur votre Application vous avez 3 choix qui s'offre a vous,
![image](https://user-images.githubusercontent.com/92677219/209841465-26c2aa6b-d920-48ba-8268-6438c7778d2d.png)

ici on va d'abbord créer une activity, vous avez la possibilitéer de modifier le nom de votre activité et de dire si se sera l'activité de lancement de l'application. Il faut ensuite créer un layout donc il vous faire click droit et créer un layout.

![image](https://user-images.githubusercontent.com/92677219/209841713-a9ad01cd-97b6-4291-a7e0-c1d2041d7c82.png)

Une fois votre layout créer vous avez la possibilité de rajouter des éléments a votre activité en faisant un clic droit :

![image](https://user-images.githubusercontent.com/92677219/209841999-e73845da-8e25-4ac7-b1a8-2dab7961875c.png)

maintenant vous pouvez renouvelez l'opération en créant d'autre activité.

Voila à quoi cela peut ressembler :

![image](https://user-images.githubusercontent.com/92677219/209842324-40a4501f-fcec-4133-a3b7-f8975202af8f.png)

Passont à la création de modèle avec des listes, pour cela c'est assez simple : 

Tout d'abord reprenons un nouveaux fichier comme prècedement puis donnez un nom a votre application.

Mais cette fois ci nous allons créer une Entity, pour cela faites clic droit puis cliquer sur **Entity** 
![image](https://user-images.githubusercontent.com/92677219/209842665-82a9780d-7858-4284-9709-30855b5ca1be.png)

Une fois cela fait donner lui un nom et crééer des Property, pour cela faites clic droit puis cliquer sur **Property**
![image](https://user-images.githubusercontent.com/92677219/209842853-89ef6e54-c7ab-4b68-8cb8-bd043768e52e.png)

Donnez un nom a chacune de vos property ainsi que un type.

Revenons a notre application et créons notre **ListComponent**, pour cela faites clic droit puis cliquer sur **ListComponent**

![image](https://user-images.githubusercontent.com/92677219/209843066-651f96c8-3526-4ac8-90b6-21d5de4fa208.png)

Dans votre list component vous avez plusieur champs a remplir : 

![image](https://user-images.githubusercontent.com/92677219/209843238-50b57ec6-3422-4e8b-8d9e-a325e10e7b14.png)

Puis il vous faut créer une liste java, pour cela faites clic droit puis cliquer sur **ListJava**

Puis remplir les champs demandé.

Une fois votre formulaire créer il faut mettre en place un affichage dans une activité ainsi il vous faut crééer une activité, un layout et dans ce layout ajouter une **ListView**

![image](https://user-images.githubusercontent.com/92677219/209843498-af8c0faf-e5b5-4180-965b-fa0909057aed.png)

Une fois créer compléter les champs.

Vous avez ainsi créer un modèle, à vous de jouer avec afin de créer votre application de vos rêves.

En ce qui concerne la représentation graphique

#### Les bugs connus et comment les contourner

## Manuel de maintenance

#### Le métamodèle

#### Les templates
