# etat de l'ide multi fenêtre

## ordre a integrer

1 - opening_native_Window

2 - fix/taskbarmanager3

3 - fix/desktop


## branche importante

### opening_native_Window

Dans cette branche on retrouve le code pour l'ouverture de fenêtre native avec des spec applications.
Cette branche n'utilise pas MiniWorld comme world de fenêtre native car on peut faire une pr de cette branche dans un premier temps 
pour fonctionner avec l'existant.

![](https://github.com/pharo-project/pharo/assets/92677219/fab5ae6b-7a94-4ecb-aa8f-aca163401f94)
![](https://github.com/pharo-project/pharo/assets/92677219/032134de-f9f7-41df-85c5-c062c91b284c)
![](https://github.com/pharo-project/pharo/assets/92677219/0d11f007-2e95-4f0f-b781-60561e5d11f8)


#### code pour lancer

il suffit de cliquer sur le window menu puis sur open in external Window


#### glitch mineur

les growlMorph ne se mette pas en bas a gauche mais en plein millieux : surement un problème de layout 
Lorsque l'on fait une sauvegarde de l'image les fenêtre native se ferme et se réouvre ( ceci est normal car l'on recommence une session est du coup on relance le startup) mais cela n'est pas très jolie 

#### ce qui reste a faire

celon moi on peut faire une pr dans l'état pour pharo 12. Les utilisateurs pourrait comme cela donner leur avis dessus et cela permetterait d'avoir plus de personne relevant des bugs ou non

### fix/desktop

Dans cette branche on retrouve le code pour avoir un desktop qui s'appuye sur miniWorld, cette branche a deja eu ça pr : https://github.com/pharo-project/pharo/pull/13740
Mais `astares` ma partagé sont desktop fait au par avant qui a l'air plus aboutit, il faudrait peut être sans inspirer pour l'avenir, ainsi j'ai laisser cette pr de coté en attendant 

<img width="1280" alt="Capture d’écran 2023-05-16 à 15 51 09" src="https://github.com/pharo-project/pharo/assets/92677219/c3941506-6094-42cb-afbd-2ac0efccd707">



#### code pour lancer

```st
	wm := MorphicWindowManager new.
	wm openNewWindowWithRoot: DesktopMorph new .
```

#### glitch mineur

le cursor ne correspond pas au bon en fonction de si la fenetre originale se trouve en dessous de celle du desktop.
Tout les outils de pharo ne sont pas disponible avec ce desktop.

#### ce qui reste a faire

si on garde le desktop comme ici il faut :
	- corriger les problèmes de la pr ( c'est principalement des problèmes de dépendance)
	- ajouter une menu bar 
	- ajouter le plus possible les outils de pharo ( pour cela supprimer les fameux **curentWorld**)

sinon reprendre le code de `astares` fait sur pharo 9 et le passer sur pharo 12

### fix/taskbarmanager3

Dans cette branche j'introduis le principe de MiniWorld, une pr est fait mais je ne pense pas que c'est integrable maintenant.
En effect si on veut que les utilisateurs utilise les nativeWindow maintenant il vaut mieux laisser le **OSWindowWorldMorph**
car il hérite de WorldMorph est dans l'instanct T cela fonctionne. Le MiniWorld est bien car il a le moins de méthode possible mais avec lui on ne peut pas encore ouvrir des spec Application ( surement pas grand chose mais cela necessite un peux plus de travail) 

<img width="1280" alt="Capture d’écran 2023-04-27 à 11 45 09" src="https://github.com/pharo-project/pharo/assets/92677219/d2beeab7-10b9-43ae-b45a-437ca11a0c62">


#### code pour lancer

```st
	wm := MorphicWindowManager new.
	wm openNewWindowWithRoot: ClyFullBrowserMorph onDefaultEnvironment .
```

#### glitch mineur

	le clic droit ne s'ouvre pas au bonne endroit ( merci currentWorld)
	la sauvegarde dans une fenêtre native fait tout planter
	

#### ce qui reste a faire

améliorer le code en le factorisant peut être avec des traits ( pour le code partagé entre worldMorph et MiniWorld)
supprimer le plus de currentWorld possible
appliquer les changement de la branche opening_native_Window pour que cela fonctionne avec miniWorld

### fix/taskbarmanager (integré)

Dans cette branche j'ai introduit le concept de WindowNative, une pr est faite est elle est intégré. Les Natives Window fonctionne avec le **OSWindowWorldMorph**

#### code pour lancer

```st
	wm := MorphicWindowManager new.
	wm openNewWindowWithRoot: ClyFullBrowserMorph onDefaultEnvironment .
```

#### glitch mineur (decouvert après)

	le clic droit ne s'ouvre pas au bonne endroit ( merci currentWorld)
	la sauvegarde dans une fenêtre native fait tout planter
    pour corriger cela intégrer : opening_native_Window


#### ce qui reste a faire

	appliquer les changement de la branche opening_native_Window


