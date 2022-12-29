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
4. [Manuel de maintenance](#manuel-de-maintenance)
   1. [Le métamodèle](#le-métamodèle)
   2. [Les templates](#les-templates)
5. [Historique du développement](#historique-du-développement)
6. [Bilan et perspectives](#gestion-des-fichiers)
7. [Conclusion](#demandes-de-fusion)

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

![image](https://user-images.githubusercontent.com/92677219/209844829-5c56f755-a8ee-4dac-ba63-64e1a49de9c3.png)


Vous avez ainsi créer un modèle, à vous de jouer avec afin de créer votre application de vos rêves.

En ce qui concerne la représentation graphique, 

**ici faire des screens et expliquer comment on fait pour visualiser avec representation.aird**

ce qu'on peut avoir avec une liste et une seul activité : 

![image](https://user-images.githubusercontent.com/92677219/209844927-a0cb7c70-f079-4764-b6ad-9dc748d105c2.png)

ce qu'on peut avoir avec plusieurs activité :

![image](https://user-images.githubusercontent.com/92677219/209845003-41c7669d-e211-4bba-ba0e-d67cbd5c8a44.png)

vous avez la possibilité de renomer les **Activity**, les **TextView**, les **Entity**, les **ListComponent** ainsi que les **Property** en appuyant sur leur nom.

Voici toute les outils de créations qui vous sont mis à disposition.

![image](https://user-images.githubusercontent.com/92677219/209845785-fdc40ce6-ad2f-47c3-a4a4-245842e345b7.png)

Une fois que vous avez créer vos modèles il vous faudrat lancer la configuration de génération d'identifiant :

![image](https://user-images.githubusercontent.com/92677219/209845902-8e5ee30a-9fc7-4f50-aa2f-da5211d2a6b9.png)

ici on lance sur le modèle test_list

puis il faut créer le projet android de même nom et l'importer dans `Eclipse` : Romain si tu peux mettre les screen de ça vu que ta android merci bg

une fois cela fait il faut lancer la configuration de génération de code.

![image](https://user-images.githubusercontent.com/92677219/209846231-1544c0cb-96b5-4e60-b1d1-259f6ff3f054.png)

Vous venez de génerer le code android correspondant a votre application.

#### Les bugs connus et comment les contourner

problème si on change le nom des booléans dans l'edit, il faut pas changer de nom

créer des activité à plusieurs layouts ne permet pas de génerer, la solution et de crée des activité à simple layout

## Manuel de maintenance

#### Le métamodèle

Voici à quoi ressemble notre métamodèle :

![image](https://user-images.githubusercontent.com/92677219/209937497-8e40f4e1-1958-46c9-aa08-7fe64912c88d.png)

Le point de départ du métamodèle est le concept d'**Application** en effet c'est lui qui contient ces activités. Ainsi une application contient au minimum une activité.

Les **Activty** représente le concept activité, ces activité ont un nom et sont l'activités de départ ou non. Chaque **Activity** contient en Android un ou plusieurs **Layout** et chacun de ces **Layout** est composée de **View**.

Une **View** est un élément graphique avec lequel l'utilisateur peut ou non intéragir, chaque **View** ayant un identifiant, le concept de view est donc composée à un **IdentifiableEntity**. 

Parmis les **View** on retouve **TextView** qui est un text mis en dur dans le fond de l'activité. On retrouve aussi **PopUpTime** qui est un bouton qui affiche la date et l'heure, mais on retrouve aussi un autre bouton pop up, **PopUpMessage** ce bouton a un titre pour que l'utilisateur comprend ce que le bouton va afficher lorsque qu'il sera activé, et un message qui sera affiché ainsi quand il sera activé. Ce Bouton **PopUpMessage** à aussi un nom, en effet ce nom permet de le différencier des autres popUpMessage. (revoir avec Romain ici car je suis plus sur de la fin)

On retrouve aussi deux **View** un peu différente, **NewActivity** qui est un bouton qui va nous envoyer vers une autre activité, **ListView** qui va être un affichage d'une liste.

Repartons du point de départ du métamodèle, une **Application** est composée d'**Entity**, cela correspond au concept d'un élément qui à un nom et est composée de propriété, par exemple un Contact est une entity qui est composée d'un nom, d'un prénom, d'un âge, et d'un numéro de téléphone. 

Une propriété est représenté par **Property**, chaque property à un nom, comme prénom par exemple, de plus chaque **Property** est d'un type, les types disponible sont dans **PropertyType**.

Une **Entity** compose le concept de **ListComponent**, ce dernier transforme une entité en liste, est sauvegarde les information dans une ou plusieurs **DataSource**, ici les **DataSource** sont tout des **ListJava**. Les **ListComponent** donne la possibilitées ou non à l'utilisateur de crée un nouveaux contact par exemple ou bien de le supprimer.



#### Les templates

Voici l'architecture des templates

![le_main_generate (2)](https://user-images.githubusercontent.com/92677219/209941800-36e4c7c6-4c30-4dcd-ad1a-7b3902505010.png)



on remarque que les templates sont divisées en 2 packages, un qui gére tout ce qui appartient au **ListComponent** et l'autre qui gérent tout le reste de l'application.

(est ce qu'il faut dire tout ce qui se trouve dans chaque template ??)

Le main des template et **generate.mtl** voyont comment ce dernier fonctionne

![le_main_generate (3)](https://user-images.githubusercontent.com/92677219/209942297-c4f665f4-3cea-42c3-91af-3a5a5a17ec5c.png)

on voit ici comme quoi ce dernier lance uniquement les autres templates, dans un certain ordre afin de généré le code de l'application. 

Par exemple voici comment est constitué le template **generateActivity.mtl**

![utilisation_du_polymorphisme (2)](https://user-images.githubusercontent.com/92677219/209942726-cc7d4b91-5431-4860-8532-b739a5bd62bf.png)



tout d'abord on va crée le fichier correspondant à chaque activité, pour cela on va donner le nom de l'activité au fichier. Ensuite nous allons faire les bon imports puis en utilisant le polymorphisme nous allons venir crée les méthodes en fonction des **View**.



