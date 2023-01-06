# Table of contents

1. [Introduction](#introduction)
   1. [Software summary](#software-summary)
   2. [Authors mail addresses](#authors-mail-addresses)
   3. [Software version](#software-version)
2. [User installation manual](#user-installation-manual)
3. [User manual](#user-manual)
   1. [Implemented functionalities](#implemented-functionalities)
   2. [Unimplemented functionalities](#unimplemented-functionalities)
   3. [Tutorial](#tutorial)
   4. [Known bugs and how to avoid them](#known-bugs-and-how-to-avoid-them)
4. [Maintenance manual](#maintenance-manual)
   1. [Metamodel](#metamodel)
   2. [Templates](#templates)
5. [Development history](#development-history)
6. [Review and prospects](#review-and-prospects)
7. [Conclusion](#conclusion)

## Introduction

Our software lets you build Android applications using a model with a high abstraction level. Using this model, our software generate the entire source code of the designed application, which can afterwards be compiled and installed on an Android device (or emulator).

#### Software summary

This software is composed of 3 different components. The first one being the metamodel, defining the available concepts for our application.
The second component is the models editor, allowing the user to create and edit models using a graphic editor or a tree editor. The user can this way choose their favourite editor, or the most appropriate one for the desired application.
The final component is the source code generator, creating the finished product.

#### Authors mail addresses

- Romain Degrave :  romain.degrave.etu@univ-lille.fr
- Rémi Dufloer : remi.dufloer.etu@univ-lille.fr

#### Software version

Version 1.0

## User installation manual

To be able to generate Android source code, you must first install `Android Studio`. To do so, follow this tutorial : https://developer.android.com/studio/install

For the remaining components of the software, `Eclipse Papyrus` is needed. Here is a tutorial to install it : https://www.fil.univ-lille.fr/~dumoulin/docs/blogs/installerPapyrusPourIDMetPJE.html

Once those are installed, you must clone our repository to proceed. To do so, we start by opening `Eclipse Papyrus`.
Using the Git perspective, click on **Clone a Git repository**.

![Screenshot from 2023-01-04 10-35-38](https://user-images.githubusercontent.com/92677219/210791026-880ba3ff-6aba-41fa-8a46-e74a2c68d760.png)


And fill the form as shown in the screenshot :

![Screenshot from 2023-01-04 10-37-42](https://user-images.githubusercontent.com/92677219/210791090-c512ddef-188d-44d4-b9c3-c12d25e7bd2e.png)

Once the repository cloned, the following project must be imported : **multiActivity** , **multiActivity.edit** , **multiActivity.editor**
To do so, right-click on the working tree then choose `Import`.

![Screenshot from 2023-01-04 10-40-06](https://user-images.githubusercontent.com/92677219/210791186-f92f3a8d-c3f1-4ae2-a2d6-940da12467b5.png)

Using the modeling perspective, open the metamodel, located on the path **multiActivity** -> **model** -> **multiActivty.aird**. Right-click anywhere on the graph, and choose the **Generate all** option, as pictured :
![image](https://user-images.githubusercontent.com/92677219/209837805-f898fa43-c5c3-4ed5-aec5-2e9d1ea0b1b7.png)

Then, click on the green arrow, and launch an **Eclipse Application** :
![image](https://user-images.githubusercontent.com/92677219/209837747-7fd4d3e4-3e56-42f7-a41e-755d78da42ba.png)

A new **Eclipse** window will open, in which you need to clone the software (this time using the local repository, previously cloned), and import every project, excepted the three already imported in the first **Eclipse**.

![Screenshot from 2023-01-04 10-42-45](https://user-images.githubusercontent.com/92677219/210791319-894bb8f7-6ae7-40a8-b760-bc134585f0cf.png)
**Attention ici c'est le git de sr1 donc peut être devoir changer le screen**


## User manual

#### Implemented functionalities

Here are the implemented and usable Android functionalities :

- Activities, and their layout
- Buttons displaying a popup when pressed (of a defined message, or of the current date)
- TextView (a displayable string)
- Buttons used to open another Activity
- Displayable lists (and displayable list elements), linked to a Datasource and an Entity
- List elements can be editable and / or deletable
- Entities are built using primitives types (String, int, boolean, Double)
- Datasource is a Java list

#### Unimplemented functionalities

The unimplemented functionalities are :

- Entities using complex proprieties (typed using another dedicated entity)
- Fragments
- Datasource using a DB, Rest, Room

#### Tutorial

```
Note :

When creating a model, there is no need to fill the **id** fields, as they will later be automatically filled by the software.
```

This tutorial is designed to help you build your first application using our software.

We will begin by creating a model using the tree editor, then we shall see how to make the same model using the graphic editor.

The first step is to create the file storing our model, in the **Eclipse Application**. The file we want to create is known by **Eclipse** as an **multiActivity Model**.

Our first application will be simple and contain no lists. After that tutorial, you should be able to create models like the one you can find in the file **Mymultiactivity**.

![image](https://user-images.githubusercontent.com/92677219/209840719-3d7928dc-0328-433c-b1a9-19eb252ff207.png)

Lets do it step by step :

First, by clicking on **Application**, you will be able to set the name of your application, using the **Properties** tab.

Then, right-clicking on your application will offer you three choices :

![image](https://user-images.githubusercontent.com/92677219/209841465-26c2aa6b-d920-48ba-8268-6438c7778d2d.png)

We want to start by creating an **Activity**. In the **Properties** you can here set the name of your activity, et choose if it will be the activity launched at the start of your app (one and only one must be declared as the launcher activity for the app to work). We must then add a **Layout** to this activity, once again by right-clicking said activity.

![image](https://user-images.githubusercontent.com/92677219/209841713-a9ad01cd-97b6-4291-a7e0-c1d2041d7c82.png)

Once our layout created, we have the possibility to add view elements to our activity, as always by right-clicking.

![image](https://user-images.githubusercontent.com/92677219/209841999-e73845da-8e25-4ac7-b1a8-2dab7961875c.png)

Now, you can create a few other activities and add different views to them until you are satisfied with your application!

Here is an example of what it could look like :

![image](https://user-images.githubusercontent.com/92677219/209842324-40a4501f-fcec-4133-a3b7-f8975202af8f.png)

Let's now see how we can create an app using lists.

This is another application, therefore we start by creating a new file, and once again we name our application.

We then right-click on our **Application**, but this time to add an **Entity**.

![image](https://user-images.githubusercontent.com/92677219/209842665-82a9780d-7858-4284-9709-30855b5ca1be.png)

This entity must also be named, so that is the first thing to do. Afterwards, we need to add some properties to our entity, as always by right-clicking and selecting **Property**.

![image](https://user-images.githubusercontent.com/92677219/209842853-89ef6e54-c7ab-4b68-8cb8-bd043768e52e.png)

The properties tab now offers us the possibility to give a name and a type to our property.

Once our **Entity** is completed, going back to our **Application** allows us by right-clicking to add a **ListComponent**.

![image](https://user-images.githubusercontent.com/92677219/209843066-651f96c8-3526-4ac8-90b6-21d5de4fa208.png)

There is several properties that we must set in the properties tab this time, as shown on the screenshot :

![image](https://user-images.githubusercontent.com/92677219/209843238-50b57ec6-3422-4e8b-8d9e-a325e10e7b14.png)

The next step is to create a **Java List**, the datasource of our list. We can do so by right-click on our list component and choose **ListJava**.

The properties tab shows us once again new properties to fill, in order to complete our datasource.

Our list component is almost done! The final step is now to add a view element able to display our list. To do so, create an activity and its layout as previously shown, and add a **ListView** to the layout.

![image](https://user-images.githubusercontent.com/92677219/209843498-af8c0faf-e5b5-4180-965b-fa0909057aed.png)

Finally, complete the list by setting the properties of its **ListView**.

![image](https://user-images.githubusercontent.com/92677219/209844829-5c56f755-a8ee-4dac-ba63-64e1a49de9c3.png)

Now that we now how to use this tool to create a model, all that remains is creating the application we are dreaming about!

Of course, to do so we can also use the graphic editor :

**ici faire des screens et expliquer comment on fait pour visualiser avec representation.aird**

Pour visualiser nos instance et les utiliser tout d'abord il faut créer un nouveaux fichier de représentation sirius, pour cela il faut :

faire un click droit sur le fichier **test_sirius** puis `New` et `Other` :

![creation_aird](https://user-images.githubusercontent.com/92677219/211039703-d6f02c36-a232-4988-b189-2afabdadc10a.png)

Une fois cela fais il faut se rendre dans le dossier sirius et cliquer sur **Representations File** :

![representation_file](https://user-images.githubusercontent.com/92677219/211039780-13346f48-3f73-4d66-a66a-c1a253787b9b.png)

Ensuite il faut choisir l'option **Empty file** :

![empti_file](https://user-images.githubusercontent.com/92677219/211039903-0d4db670-f89a-48d7-a44f-c68a87074eb6.png)

Puis lui donner un nom et choisir ou mettre le fichier de représentation : 

![choose_name_and_where_do_you_want](https://user-images.githubusercontent.com/92677219/211039948-d6986b20-98fe-4db8-9dea-d96a8b17ac5e.png)

Une fois cela fais il faut ouvrir le fichier pour cela faite un double click vous devez obtenir une fenêtre comme ceci :

![open_the_file](https://user-images.githubusercontent.com/92677219/211040081-ab11e667-ed46-4297-a374-745d10e30311.png)

Ici il y a deux possibilitées, créé une nouvelle instande de modèle ou éditer/visualiser une instance existante.

- Ici nous allons commencer par une instance existante, ainsi pour cela il vous faut ajouter le modèle :
![add_model](https://user-images.githubusercontent.com/92677219/211040150-a295cf0b-bd48-4d95-8ab2-0adb5d0a4743.png)


Ici il faut regarder dans le workspace et choisir l'instance que vous voulez visualiser, ici se sera **first.multiactivity** :

![browse_workspace](https://user-images.githubusercontent.com/92677219/211040294-02ea219e-9127-4e42-b410-abcc96e15f5f.png)

Une fois cela fait il faut choisir quelle type de représentation vous voulez, avec un seul ou plusieurs layout : 

![good_choice](https://user-images.githubusercontent.com/92677219/211040396-79a64c5f-d78f-4705-a6db-86cfe2b2258b.png)

Lorsque vous avez choisie il faut savoir quelle aplication dans votre modèle vous voulez représenter :

![after_good_choice](https://user-images.githubusercontent.com/92677219/211040446-3453379f-391b-4e85-a442-0f5692758d8f.png)

Donnez un nom a votre représentation :

![set_name](https://user-images.githubusercontent.com/92677219/211040499-f42d2875-b1ef-4cf2-a6e8-a3ecf7cf8f47.png)

Une fois cela fait, `Eclypse Papyrus` ouvre automatiquement la représentation graphique :

![file_open_automatically](https://user-images.githubusercontent.com/92677219/211040544-964d0b69-f60e-4aaf-bcb2-826b7597d3c0.png)

Nous verrons par la suite comment éditer cette visualisation.

- Voyons maintenant comment créer une instance grâçe à sirius.

Reparton sur notre fichier **Representation.aird** et cliquer sur `New...` puis selectionner `multiactivity`:
![tout_dabord_new_model](https://user-images.githubusercontent.com/92677219/211040655-e5762b14-23a8-4d8c-88c3-e38e5c4f1c12.png)

Choisiser le point d'entrée de votre instance ici `Application`:
![choose_yhe_start](https://user-images.githubusercontent.com/92677219/211040683-a077d8de-2113-4ce9-84fc-bb3d14b67f72.png)


metter votre instance ou vous le souhaiter et comment vous vouler l'appeler :

![set_the_name_and_the_destination](https://user-images.githubusercontent.com/92677219/211040809-be6d9704-24ae-4109-aef0-558300461676.png)

Maintenant choisisons le type de représentation pour cela cliquer sur `New...` dans la partie représenation puis choisisez celle qui vous convient, ici `multiactivityDiagramWithOneLayout` :

![new_representation_for_new_model](https://user-images.githubusercontent.com/92677219/211040870-d6a7155e-b92b-4a34-a6e8-135eea3c9e61.png)


Ici il faut choisir votre instance, prenons celle que nous venons de créé :

![choose_the_modele_do_you_want](https://user-images.githubusercontent.com/92677219/211040963-0b346d90-90cd-4e90-925c-615ca3edae24.png)


Donnons un nom a notre visualization :

![set_name_new](https://user-images.githubusercontent.com/92677219/211040992-96814df4-8d31-4a92-8d09-b033a406fcdd.png)


La visualisation est a l'image de l'instance, vide.

Maintenant nous allons voir comment éditer des visualization 

** ici voir comment imbriquer avec la partie en dessous**

Tout d'abord nous allons créer deux nouvelles **Activity** pour cela cliquer sur **ActivityCreationTool** :
![first_create_an_activty](https://user-images.githubusercontent.com/92677219/211041165-f677b4d3-4bd1-44b2-bf73-a0a89679d0d6.png)


Puis cliquer dans le grand espace blanc, votre activité est créé :
![activity_create](https://user-images.githubusercontent.com/92677219/211041195-32dd3b47-4933-430a-9a0b-e98b9644f9d4.png)


Répéter ce que l'on viens de faire au dessus pour avoir une autre **Activity**, puis cliquer sur cette dernière puis **f2** pour la renommer ici ce sera `Activity2` :

![for_exemple_create_an_other_activity](https://user-images.githubusercontent.com/92677219/211041263-999e6ea2-bbf6-43e9-ac05-fdfb81c39d90.png)


Nous allons maintenant crééer un **PopUpTime** pour cela cliquer sur **PopUpTimeCreationTool** :

![create_po_up_time](https://user-images.githubusercontent.com/92677219/211041353-bda6293b-9de8-400d-bc4d-9382af842d01.png)


Puis cliquer dans une des activity ici ce sera **Activity** :

![pop_up_time_create](https://user-images.githubusercontent.com/92677219/211041420-eb0db71e-90b1-4b42-b40b-0488214c8ba8.png)


Maintenant nous allons créer un bouton pour lier **Activity** à **Activity2**, ainsi cliquer sur **NewAwtivityCreationTool** :

![create_a_lien_envers_deux_activity](https://user-images.githubusercontent.com/92677219/211041486-2f7a23c3-9c95-41aa-a106-267e2297d397.png)


Puis cliquer dans **Activity** :

![button_create](https://user-images.githubusercontent.com/92677219/211041605-627f544d-48e8-4f45-8578-7a118b5c6be8.png)


Pour lier ce bouton a **Activity2** cliquer sur **NewActivityEdgeCreation** :

![edge_creation](https://user-images.githubusercontent.com/92677219/211041669-f00c36b5-3187-4bdf-903c-9a78700e3e6d.png)


Puis cliquer une première fois sur le bouton créer puis une seconde fois sur **Activity2**, vous obtiendrez ceci :
![edge_create](https://user-images.githubusercontent.com/92677219/211041693-b2464733-baaa-4bf5-9088-4b4187ab8250.png)

On peut vérifier que cela est un impact sur notre modèle :

![instance_automatiquement_éditer](https://user-images.githubusercontent.com/92677219/211041717-53728cba-bc82-429c-ba62-843c22784d93.png)


Il existe d'autre outils de crétion que voici : ** cette phrase est une phrase a changé c'est pour faire le lien avec en dessous **



Here are some examples of models made using this graphic editor. First, one with a list and a single activity :

![image](https://user-images.githubusercontent.com/92677219/209844927-a0cb7c70-f079-4764-b6ad-9dc748d105c2.png)

And secondly, one using several activities :

![image](https://user-images.githubusercontent.com/92677219/209845003-41c7669d-e211-4bba-ba0e-d67cbd5c8a44.png)

By clicking on their name, we are able to rename several things : an **Activity**, a **TextView**, an **Entity**, a **ListComponent** or a **Property**.

Here are every usable creation tool in the graphic editor :

![image](https://user-images.githubusercontent.com/92677219/209845785-fdc40ce6-ad2f-47c3-a4a4-245842e345b7.png)

Once a model is completed, we must launch the model transformation to add an **id** to every element that needs one. To do so we launch this configuration, using the **QVTo** perspective and clicking on the green arrow to create a new configuration :

![image](https://user-images.githubusercontent.com/92677219/209845902-8e5ee30a-9fc7-4f50-aa2f-da5211d2a6b9.png)

Here this is done on the model *test_list*, but any model can be used in this configuration.

Now that we have a completed model, we just need to generate its code in an **Android** project and compile it to be able to use the app we designed.

To do so, we must turn to **Android Studio**, and create a new project named like our application.

(bref chopper le chemin relatif, importer dans eclipse faut faire des screens)

Once we imported our project, we need to launch a new configuration, this time using the **Acceleo** perspective. Here is the configuration to use, using the model we want to generate :

![image](https://user-images.githubusercontent.com/92677219/209846231-1544c0cb-96b5-4e60-b1d1-259f6ff3f054.png)

The code of our application is now generated! Now all that remains is going back on Android Studio, where we can test the app on a physical device or an emulator.

#### Known bugs and how to avoid them

- An **Activity** cannot have several layout (this will create a bug when generating the code). To avoid this, only use one layout per activity

- Every **id** must be unique across the model, or the app might not launch. To avoid this, let the model transformation deal with the ids, as it will save you some time and ensure that every id is properly set

## Maintenance manual

#### Metamodel

Here is the metamodel used to design our application models :

![image](https://user-images.githubusercontent.com/92677219/209937497-8e40f4e1-1958-46c9-aa08-7fe64912c88d.png)

Its starting point is the **Application** concept. It can contain activities (**Activity**), list components (**ListComponent**) and entities (**Entity**). To function, every application must have at least an activity.

The activities, represented by the **Activity** concept, have a name and can be flagged as the launcher activity (using inheritance from **LaunchableEntity**). Every entity must have a **Layout** (and can have more than one) and each **Layout** is composed of views (**View**).

A **View** is a graphical element with which the user can interact or not. Each view has an identifier, from the inherited **IdentifiableEntity**.

Here is the list of available views :
- **TextView** : shows the defined *textOperation* in the activity
- **PopUpTime** : a button prompting a popup displaying the date and time when pressed
- **PopUpMessage** : a button (titled using the *title* property) prompting a popup displaying *a message* when pressed (it also has a *name*, used to differentiate different PopUpMessages within the same activity)
- **NewActivity** : a button used to switch a another activity (defined by the *activity* relation) when pressed
- **ListView** : displays a list (defined by the *listcomponent* relation)

Going back to our starting point, we have a composition for the **Entity** concept. An entity is composed of properties **Property** which has a *name* and a *type* (defined in the **PropertyType** enum). For example, a Contact could be an entity composed of a first name, last name, age and phone number.

From the same starting point we can find our lists (**ListComponent**). They have a relation to an **Entity**, and are composed with a **DataSource** (our only implemented **DataSource** being the **ListJava**) that must also be linked to the same entity. We can also choose if a **ListComponent** has a create button and/or a delete button for entities.

Note : every concept of the metamodel who has a name inherits from the abstract class **NamedEntity**.

#### Templates

Here is the architecture of the templates used to generate Android source code.

![le_main_generate (2)](https://user-images.githubusercontent.com/92677219/209941800-36e4c7c6-4c30-4dcd-ad1a-7b3902505010.png)

Our templates are divided in two packages, one containing every template used for the generation of lists, and the other one for every other aspect of an application.

The main template is in the file **generate.mtl**, and here is how it basically works :

![le_main_generate (3)](https://user-images.githubusercontent.com/92677219/209942297-c4f665f4-3cea-42c3-91af-3a5a5a17ec5c.png)

This template imports generating functions from every other templates, and launch them in a certain order to generate the entire code of an application.

For an example of the templates used by the main template, here is how the template **generateActivity.mtl** is composed :

![utilisation_du_polymorphisme (2)](https://user-images.githubusercontent.com/92677219/209942726-cc7d4b91-5431-4860-8532-b739a5bd62bf.png)

First, the template creates a file for each **Activity**, using the name of said activity in the name of the generated file. Then, once the correct imports are done, a function for every **View** is generated using polymorphism.

## Development history



All our work, and the commit history can be found here : https://gitlab-etu.fil.univ-lille.fr/remi.dufloer.etu/degrave_dufloer_pje-a_idm

Here are some key points of the development of this software :

- September 26 : Creation of a basic version of our metamodel

- October 10 : Creation of the generation templates for our metamodel

- October 17 : Creation of the graphic editor

- November 8 : Changes in the metamodel, to correct some cardinalities and relation names

- November 17 : Adding the concept of **IdentifiableEntity** and according changes in the templates

- November 21 : Creation of the model transformation using **QVTo**, and adding the lists in the metamodel

- November 28 : Changes in the metamodel to add the **LauncherEntity** concept

- December 5 : Work on the generation of lists

- December 8 : Changes in the graphic editor to include lists

- December 12 : Work on the generation of lists + changes in metamodel and generation to be able to include several **PopUpMessage** in an activity



|              Tasks              | Romain Degrave | Rémi Dufloer |
| :------------------------------: | :------------: | :----------: |
|          Metamodel           |       X        |      X       |
|       Graphic Editor        |       X        |      X       |
|      Generation templates       |       X        |      X       |
|           Models            |       X        |      X       |
| Generation templates for lists |       X        |              |
|  Graphic editor for lists  |                |      X       |



## Review and prospects

The provided software is in a completed state, with a final product made to be easy to use and practical for an user, the most notable example of that being the model transformation setting the identifiers automatically for the user.

However things can always be improved, a few examples of improvements being :

- Support several layouts per activity
- Complex entities, using property definable in a model
- Creating other implementations of datasources

## Conclusion

To create this software, we had to discover and learn how to develop Android applications, something we had never done previously.

Model-driven development also taught us a lot about conception, being a totally different approach to development.
The scale of this project was also for us a way to gain some insight on how to work as a team and split tasks, going from a blank state to a full and usable software.

Creating every component needed for the software also enabled us to think more about the user experience and was the occasion to work on specific tools that we had not previously worked on like graphic editors.

All of those reasons made the *PJE* course a fulfilling and rewarding experience.
