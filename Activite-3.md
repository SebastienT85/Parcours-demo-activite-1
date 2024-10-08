# Activite-3
## Objectif @showdialog
Dans cette activité, nous allons programmer un mini-jeu d'esquive d'astéroïdes.
Tu vas pouvoir contrôler un vaisseau spatiale et esquiver des astéroïdes.
Coder par tes propres mains.

## Étape 1
Nous allons commencer par créer notre joueur.
1. Dans la section ``||variables:variables||`` cliquer sur créer une variable et nommé la **joueur**.
2. Glisser ``||variables:définir joueur à 0 ||`` dans le crochet ``||basic:au démarrage||``.
3. Dans la section  ``||game:jeu||``, glisser ``||game:créer un sprite à x:2 y:2||`` à la place de 0 dans ``||variables:définir joueur à 0 ||``.
4. Changer les valeurs **X** pour **2** et **Y** pour **4**.
(Cliquer sur avancé pour afficher la section ``||game:jeu||`` et ``||functions:fonctions||``)

```blocks
let Joueur: game.LedSprite = null
Joueur = game.createSprite(2, 4)
```

## Étape 2
Maintenant nous allons faire les déplacements du joueur.
1. Pour ça, glisser ``||Input:lorsque de le bouton A est pressé||`` trouvable dans la section ``||Input:entrée||`` dans l'espace de programmation
2. Trouver dans la section ``||game:jeu||`` le bloc ``||game:sprite modifie de x : 1||`` et glisser le dans le crochet ``||Input:lorsque de le bouton A est pressé||``.
3. Changer ``||variables:sprite||`` pour ``||variables:joueur||``.
4. Changer la valeur **1** par **-1**
5. Cliquer droit sur ``||Input:lorsque de le bouton A est pressé||`` et dupliquer le.
6. Changer ``||Input:A||`` pour ``||Input:B||`` et **-1** pour **1**.
7. Tester avec le simulateur, en pressant ``||Input:A||`` la led allumée se déplace vers la gauche et inversement pour ``||Input:B||``.

```blocks
let Joueur: game.LedSprite = null
Joueur = game.createSprite(2, 4)
input.onButtonPressed(Button.A, function () {
   Joueur.change(LedSpriteProperty.X, -1)
})
input.onButtonPressed(Button.B, function () {
   Joueur.change(LedSpriteProperty.X, 1)
})
```

## Étape 3
Maintenant que nous avons le joueur fonctionnel, nous allons programmer les astéroïdes.
1. Le mur d'astéroïdes sera initialisé en haut du microbit avec un espace pour que le vaisseau puisse passer.
2. Pour ce faire, commençons par déclarer 4 nouvelles variables nommées ``||variables:wall1||``, ``||variables:wall2||``, ``||variables:wall3||`` et ``||variables:wall4||``.
3. Créé une autre ``||variables:variables||`` nommée ``||variables:random||``.
4. Ensuite, créons une fonction en cliquant sur la section ``||functions:fonction||`` puis créer une fonction, nommée la **defineWall** et cliquer sur terminer.
> Une fonction te permet d'écrire un groupe de lignes de code une seule fois, et ensuite tu peux les utiliser encore et encore en appelant simplement le nom de la fonction.
> Dans notre cas nous allons appeler la fonction quand nous voudrons faire apparaitre un nouveau mur d'astéroïdes.

## Étape 4
Nous voulons un trou dans le mur mais nous ne voulons pas qu'il soit tout le temps au même endroit.
1. Glisser ``||variables:définir random à 0||`` dans la fonction ``||functions:defineWall||``.
2. Dans la section ``||math:maths||`` selectionnées ``||math:choisir au hasard de 0 à 10||`` et glisser le à la place du 0 dans ``||variables:définir random à 0||``.
3. Changer **10** pour **4**.
4. Dans la section ``||logic:logique||`` selectionnées ``||logic:si <vrai> alors sinon||`` et glisser le sous ``||variables:définir random à ...||``.
5. Cliquer **4** fois sur le **+** et cliquer sur le **-** du ``||logic:sinon||``.
6. Remplacer le ``||logic:<vrai>||`` de ``||logic:si <vrai> alors||``  par ``||logic:0 = 0||`` trouvable dans la section ``||logic:logic||``
7. Faite la meme chose pour les **4** autres vide de ``||logic:sinon si < > alors||``.
8. Dans la section ``||variables:variables||`` trouver le bloc ``||variables:random||`` et glisser le dans tous les 0 de gauche des blocs ``||logic:0 = 0||`` que vous venez d'ajouter.
9. Dans le premier, ``||logic:sinon si random = 0 alors||`` remplacer le **0** par **1**.
10. Dans le deuxième, ``||logic:sinon si random = 0 alors||`` remplacer le **0** par **2**.
11. Dans le troisième, ``||logic:sinon si random = 0 alors||`` remplacer le **0** par **3**.
12. Dans le quatrième, ``||logic:sinon si random = 0 alors||`` remplacer le **0** par **4**.

```blocks
function defineWall () {
   random = randint(0, 4)
   if (random == 0) {
      
   } else if (random == 1) {
      
   } else if (random == 2) {
      
   } else if (random == 3) {
      
   } else if (random == 4) {
      
   }
}
```

## Étape 5
1. Dans la section ``||variables:variables||``, glisser ``||variables:definir wall1 à 0||`` **4** fois dans le premier crochet ``||logic:si <vrai> alors||``
2. changer les variables définie pour ``||variables:wall1||``, ``||variables:wall2||``, ``||variables:wall3||``, ``||variables:wall4||``.
3. Répéter l'opération pour chaque crochet ``||logic:sinon si <vrai> alors||``.
4. Vous devez avoir **4** fois le bloc ``||variables:définir wall à 0||`` dans chaque crochets ``||logic:si <vrai> alors||`` et ``||logic:sinon si <vrai> alors||``.
5. Dans la section ``||game:jeu||``, trouver ``||game:créer un sprite à x:2 y:2||`` et remplacer chaque **0** de ``||variables:definir wall à 0||`` par ce bloc.
6. Répéter l'opération pour les **4** crochet ``||logic:sinon si <vrai> alors||``.

```blocks
function defineWall () {
   random = randint(0, 4)
   if (random == 0) {
       wall1 = game.createSprite(2, 2)
       wall2 = game.createSprite(2, 2)
       wall3 = game.createSprite(2, 2)
       wall4 = game.createSprite(2, 2)
   } else if (random == 1) {
       wall1 = game.createSprite(2, 2)
       wall2 = game.createSprite(2, 2)
       wall3 = game.createSprite(2, 2)
       wall4 = game.createSprite(2, 2)
   } else if (random == 2) {
       wall1 = game.createSprite(2, 2)
       wall2 = game.createSprite(2, 2)
       wall3 = game.createSprite(2, 2)
       wall4 = game.createSprite(2, 2)
   } else if (random == 3) {
       wall1 = game.createSprite(2, 2)
       wall2 = game.createSprite(2, 2)
       wall3 = game.createSprite(2, 2)
       wall4 = game.createSprite(2, 2)
   } else if (random == 4) {
       wall1 = game.createSprite(2, 2)
       wall2 = game.createSprite(2, 2)
       wall3 = game.createSprite(2, 2)
       wall4 = game.createSprite(2, 2)
   }
}
```

## Étape 6
Nous allons initialiser les coordonnées des astéroïdes. l'axe X est l'axe horizontal, sa position peut allé de **0** à **4**, **0** étant la led la plus a gauche du microbit et **4** la plus à droite.
L'axe Y est l'axe vertical, sa position peut allé de **0** à **4**, **0** étant la led la plus haute du microbit et **4** en bas du microbit.
1. La variable ``||variables:random||`` permet de définir la position du trou de manière aléatoire.
2. Comme nous voulons que les astéroïdes apparaissent en haut du microbit, changer la valeur **Y** de tout les ``||game:créer un sprite à x:2 y:2||`` de la fonction ``||functions:defineWall||`` à **0**.
3. Dans le crochet ``||logic:si random = 0||``, remplacer le premier **X : 0** par **1**, le deuxième par **2**, le troisième par **3** et le quatrième par **4**.
4. Dans le crochet ``||logic:si random = 1||``, remplacer le premier **X : 0** par **0**, le deuxième par **2**, le troisième par **3** et le quatrième par **4**.
5. Dans le crochet ``||logic:si random = 2||``, remplacer le premier **X : 0** par **0**, le deuxième par **1**, le troisième par **3** et le quatrième par **4**.
6. Dans le crochet ``||logic:si random = 3||``, remplacer le premier **X : 0** par **0**, le deuxième par **1**, le troisième par **2** et le quatrième par **4**.
7. Dans le crochet ``||logic:si random = 4||``, remplacer le premier **X : 0** par **0**, le deuxième par **1**, le troisième par **2** et le quatrième par **3**.
8. Le mur d'astéroïdes est maintenant pres, il ne reste plus qu'à l'afficher.

```blocks
function defineWall () {
   random = randint(0, 4)
   if (random == 0) {
       wall1 = game.createSprite(1, 0)
       wall2 = game.createSprite(2, 0)
       wall3 = game.createSprite(3, 0)
       wall4 = game.createSprite(4, 0)
   } else if (random == 1) {
       wall1 = game.createSprite(0, 0)
       wall2 = game.createSprite(2, 0)
       wall3 = game.createSprite(3, 0)
       wall4 = game.createSprite(4, 0)
   } else if (random == 2) {
       wall1 = game.createSprite(0, 0)
       wall2 = game.createSprite(1, 0)
       wall3 = game.createSprite(3, 0)
       wall4 = game.createSprite(4, 0)
   } else if (random == 3) {
       wall1 = game.createSprite(0, 0)
       wall2 = game.createSprite(1, 0)
       wall3 = game.createSprite(2, 0)
       wall4 = game.createSprite(4, 0)
   } else if (random == 4) {
       wall1 = game.createSprite(0, 0)
       wall2 = game.createSprite(1, 0)
       wall3 = game.createSprite(2, 0)
       wall4 = game.createSprite(3, 0)
   }
}
}
```

## Étape 7
Il faut maintenant exécuter la fonction ``||functions:defineWall||`` au démarrage pour que les astéroïdes s'affiche.
1. Dans la section ``||functions:fonctions||``, glisser ``||functions:appel defineWall||`` dans le crochet ``||basic:au démarrage||``.
2. Les astéroïdes apparaissent mais ne descendent pas vers le joueur.
3. Dans la section ``||functions:fonctions||``, cliquer sur **créer une fonction** et nommer la **deplacement**
4. Dans la section ``||game:jeu||``, glisser et déposer ``||game:sprite modifie X de 1||`` dans le crochet de la fonction ``||functions:deplacement||``
5. Dupliquer le bloc ``||game:sprite modifie X de 1||`` pour l'avoir 4 fois dans la fonction ``||functions:deplacement||``.
6. Glisser la variable ``||variables:wall1||`` à la place de sprite dans le premier bloc de la fonction ``||functions:deplacement||``.
7. Glisser la variable ``||variables:wall2||`` à la place de sprite dans le deuxième bloc de la fonction ``||functions:deplacement||``.
8. Glisser la variable ``||variables:wall3||`` à la place de sprite dans le troisième bloc de la fonction ``||functions:deplacement||``.
9. Glisser la variable ``||variables:wall4||`` à la place de sprite dans le quatrième bloc de la fonction ``||functions:deplacement||``.
10. Changer les ``||game:X||`` pour ``||game:Y||``.
> À chaque appel de la fonction ``||functions:deplacement||`` les astéroïdes descendront de 1 vers le joueur.

```blocks
let wall1: game.LedSprite = null
let wall2: game.LedSprite = null
let wall3: game.LedSprite = null
let wall4: game.LedSprite = null
function Deplacement () {
   wall1.change(LedSpriteProperty.Y, 1)
   wall2.change(LedSpriteProperty.Y, 1)
   wall3.change(LedSpriteProperty.Y, 1)
   wall4.change(LedSpriteProperty.Y, 1)
}
```

## Étape 8
1. Créer une variable ``||variables:temps||``, glisser et déposer ``||variables:définir temps à 0||`` dans le crochet ``||basic:au démarrage||``.
2. Changer **0** par **500**.
3. Dans la section ``||basic:bases||`` glisser et déposer ``||basic:pause(ms)100||`` tout en haut du crochet ``||basic:toujours||``.
4. Glisser la variable ``||variables:temps||`` dans le bloc ``||basic:pause||``.
5. Dans la section ``||functions:fonctions||``, glisser ``||functions:appel deplacement||`` dans le crochet ``||basic:toujours||``.

```blocks
Joueur = game.createSprite(2, 4)
defineWall()
let temps = 500
function defineWall () {}
function deplacement () {}
basic.forever(function () {
   basic.pause(temps)
   deplacement()
})
```

## Étape 9
Nous allons maintenant créer la troisième et dernière fonction pour supprimer les astéroïdes quand ils seront arrivés au niveau du joueur.
1. Créer une fonction et nommer la ``||functions:deleteWall||``.
2. Glisser ``||game:supprimer this||`` **4** fois dans la fonction ``||functions:deleteWall||``.
3. Remplacer le premier ``||variables:this||`` par ``||variables:wall1||`` .
4. Remplacer le deuxième ``||variables:this||`` par ``||variables:wall2||``.
5. Remplacer le troisième ``||variables:this||`` par ``||variables:wall3||``.
6. Remplacer le quatrième ``||variables:this||`` par ``||variables:wall4||``.

```blocks
let wall1: game.LedSprite = null
let wall2: game.LedSprite = null
let wall3: game.LedSprite = null
let wall4: game.LedSprite = null
function deleteWall () {
   wall1.delete()
   wall2.delete()
   wall3.delete()
   wall4.delete()
}
```

## Étape 10
Nous allons maintenant commencer la boucle de jeu.
1. Glisser le bloc ``||logic:si <vrai> alors sinon||`` dans le crochet ``||basic:toujours||`` sous ``||functions:appel deplacement||``.
2. Dans la section ``||logic:logique||``, trouver ``||logic:< > ou < >||`` et glisser le à la place de ``||logic:<vrai>||``.
3. Glisser à nouveau un bloc ``||logic:< > ou < >||`` dans chaque espace ``||logic:< >||`` du bloc ``||logic:< > ou < >||``.
4. Trouver dans la section ``||game:jeu||`` le bloc ``||game:sprite touche < >||`` et glisser le dans les **4** espaces ``||logic:< >||`` du bloc ``||logic:< < > ou < > > ou < < > ou < > >||``.
5. Changer ``||variables:sprite||`` dans les blocs ``||game:sprite touche < >||`` respectivement pour ``||variables:wall1||``, ``||variables:wall2||``, ``||variables:wall3||`` et ``||variables:wall4||``.
6. Ajouter la variable ``||variables:joueur||`` dans ``||game:< >||`` des **4** blocs ``||game:sprite touche < >||``.
7. Trouver le bloc ``||game:fin du jeu||`` dans la section ``||game:jeu||`` et glisser le dans le premier crochet ``||logic:si <vrai> alors||``
> Explication du code : si les astéroïdes ``||variables:wall1||``, ``||variables:wall2||``, ``||variables:wall3||`` et ``||variables:wall4||`` touche le joueur ``||variables:joueur||``, alors c'est la fin du jeu et le score est affiché. score que nous implémenterons à la fin.

```blocks
function deplacement () {}
let wall1: game.LedSprite = null
let wall2: game.LedSprite = null
let wall3: game.LedSprite = null
let wall4: game.LedSprite = null
let Joueur: game.LedSprite = null
basic.forever(function () {
    deplacement()
    basic.pause(temps)
    if (wall1.isTouching(Joueur) || wall2.isTouching(Joueur) || (wall3.isTouching(Joueur) || wall4.isTouching(Joueur))) {
        game.gameOver()
    } else if (true) {
        
    }
})
```

## Étape 11
Nous allons faire boucler les astéroïdes si le joueur passe à travers.
1. Cliquer sur le **+** du bloc ``||logic:si <vrai> alors||`` du crochet ``||basic:toujours||`` et sur le **-** du ``||logic:sinon||``
2. Trouver dans la section ``||logic:logique||`` le bloc ``||logic:0 = 0||`` et glisser le dans l'espace vide ``||logic:sinon si < > alors||``.
3. Dans la section ``||game:jeu||``, trouver le bloc ``||game:sprite x||`` et glisser dans le **0** de gauche de ``||logic:0 = 0||``.
4. Changer ``||game:X||`` pour ``||game:Y||`` et le **0** de droite par 4.
5. Changer ``||variables:sprite||`` pour ``||variables:wall1||``.
> Explication du code : si l'astéroïde 1 arrive en bas du microbit et n'a pas touché le joueur, alors le code dans le crochet ``||logic:sinon si wall1 y = 4 alors||`` sera exécuté.
> L'astéroïde 1 étant alligné avec les autres, il n'est pas necessaire de verifier la coordonnée en **Y** de tous.

```blocks
function deplacement () {}
let wall1: game.LedSprite = null
let wall2: game.LedSprite = null
let wall3: game.LedSprite = null
let wall4: game.LedSprite = null
let Joueur: game.LedSprite = null
basic.forever(function () {
    deplacement()
    basic.pause(timing)
    if (wall1.isTouching(Joueur) || wall2.isTouching(Joueur) || (wall3.isTouching(Joueur) || wall4.isTouching(Joueur))) {
        game.gameOver()
    } else if (wall1.get(LedSpriteProperty.Y) == 4) {
        
    }
})
```

## Étape 12
1. Dans la section ``||functions:fonctions||``, trouver le bloc ``||functions:appel deleteWall||`` et ajouter le dans le crochet ``||logic:sinon si wall1 y = 4 alors||``.
2. Dans la section ``||functions:fonctions||``, trouver le bloc ``||functions:appel defineWall||`` et ajouter le dans le crochet ``||logic:sinon si wall1 y = 4 alors||``.
3. Dans la section ``||game:jeu||``, trouver le bloc ``||game:incrémenter le score de 1||`` et ajouter le dans le crochet ``||logic:sinon si wall1 y = 4 alors||``.
4. Dans la section ``||game:jeu||``, trouver le bloc ``||game:définir le scrore à 0||`` et ajouter le dans le crochet ``||basic:au démarrage||``.

```blocks
function deplacement () {}
function deleteWall () {}
function defineWall () {}
let wall1: game.LedSprite = null
let wall2: game.LedSprite = null
let wall3: game.LedSprite = null
let wall4: game.LedSprite = null
let Joueur: game.LedSprite = null
Joueur = game.createSprite(2, 4)
defineWall()
let temps = 500
game.setScore(0)
basic.forever(function () {
    deplacement()
    basic.pause(timing)
    if (wall1.isTouching(Joueur) || wall2.isTouching(Joueur) || (wall3.isTouching(Joueur) || wall4.isTouching(Joueur))) {
        game.gameOver()
    } else if (wall1.get(LedSpriteProperty.Y) == 4) {
        deleteWall()
        defineWall()
        game.addScore(1)
    }
})
```

## Étape 13
Nous allons ajouter un peu de difficulté avec le temps pour avoir un peu de défi.
1. Dans la section ``||logic:logique||``, trouver ``||logic:si <vrai> alors sinon||`` et glisser le dans le crochet ``||logic:sinon si wall1 y = 4 alors||``.
2. Dans la section ``||logic:logique||``, trouver ``||logic:0 < 0||`` et glisser le dans l'espace vide du bloc ``||logic:si <vrai> alors||``.
3. Dans la section ``||variables:variables||``, glisser ``||variables:temps||`` dans le **0** de gauche du bloc ``||logic:0 < 0||``.
4. Changer le **0** de droite par **100**.
5. Dans la section ``||variables:variables||``, glisser ``||variables:définir temps à 0||`` dans le crochet  ``||logic:si temps < 100 alors||`` et changer **0** par **100**.
6. Dans la section ``||variables:variables||``, glisser ``||variables:modifier temps de 1||`` dans le crochet ``||logic:sinon||``, changer **1** par **-10**.
> À chaque fois que les astéroïdes arrivent en bas du microbit, le temps entre chaque avancé des astéroïdes est réduit.

```blocks
function deplacement () {}
function deleteWall () {}
function defineWall () {}
let wall1: game.LedSprite = null
let wall2: game.LedSprite = null
let wall3: game.LedSprite = null
let wall4: game.LedSprite = null
let Joueur: game.LedSprite = null
basic.forever(function () {
    deplacement()
    basic.pause(timing)
    if (wall1.isTouching(Joueur) || wall2.isTouching(Joueur) || (wall3.isTouching(Joueur) || wall4.isTouching(Joueur))) {
        game.gameOver()
    } else if (wall1.get(LedSpriteProperty.Y) == 4) {
        deleteWall()
        defineWall()
        game.addScore(1)
        if (temps < 100) {
            temps = 100
        } else {
            temps += -10
        }
    }
})
```

## Étape 14
Voici le code en entier, compares avec le tiens pour voir si tu n'as pas fait d'erreurs. 

Les problèmes les plus récurents sont l'inversion d'un **X** pour un **Y**,

erreur lors de la saisi de valeur,

mauvaise variable selectionné.

```blocks
function deleteWall () {
    wall1.delete()
    wall2.delete()
    wall3.delete()
    wall4.delete()
}
function defineWall () {
    random = randint(0, 4)
    if (random == 0) {
        wall1 = game.createSprite(2, 0)
        wall2 = game.createSprite(1, 0)
        wall3 = game.createSprite(3, 0)
        wall4 = game.createSprite(4, 0)
    } else if (random == 1) {
        wall1 = game.createSprite(0, 0)
        wall2 = game.createSprite(2, 0)
        wall3 = game.createSprite(3, 0)
        wall4 = game.createSprite(4, 0)
    } else if (random == 2) {
        wall1 = game.createSprite(0, 0)
        wall2 = game.createSprite(1, 0)
        wall3 = game.createSprite(3, 0)
        wall4 = game.createSprite(4, 0)
    } else if (random == 3) {
        wall1 = game.createSprite(0, 0)
        wall2 = game.createSprite(1, 0)
        wall3 = game.createSprite(2, 0)
        wall4 = game.createSprite(4, 0)
    } else if (random == 4) {
        wall1 = game.createSprite(0, 0)
        wall2 = game.createSprite(1, 0)
        wall3 = game.createSprite(3, 0)
        wall4 = game.createSprite(2, 0)
    }
}
input.onButtonPressed(Button.A, function () {
    Joueur.change(LedSpriteProperty.X, -1)
})
input.onButtonPressed(Button.B, function () {
    Joueur.change(LedSpriteProperty.X, 1)
})
function deplacement () {
    wall1.change(LedSpriteProperty.Y, 1)
    wall2.change(LedSpriteProperty.Y, 1)
    wall3.change(LedSpriteProperty.Y, 1)
    wall4.change(LedSpriteProperty.Y, 1)
}
let random = 0
let wall4: game.LedSprite = null
let wall3: game.LedSprite = null
let wall2: game.LedSprite = null
let wall1: game.LedSprite = null
let Joueur: game.LedSprite = null
game.setScore(0)
let temps = 500
Joueur = game.createSprite(2, 4)
defineWall()
basic.forever(function () {
    deplacement()
    basic.pause(temps)
    if (wall1.isTouching(Joueur) || wall2.isTouching(Joueur) || (wall3.isTouching(Joueur) || wall4.isTouching(Joueur))) {
        game.gameOver()
    } else if (wall1.get(LedSpriteProperty.Y) == 4) {
        deleteWall()
        defineWall()
        game.addScore(1)
        if (temps < 100) {
            temps = 100
        } else {
            temps += -10
        }
    }
})
```