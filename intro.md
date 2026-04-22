# Prise en main de TIC-80

TIC-80 est une fantasy retro console open source conçu pour créer, jouer et partager de petits jeux. Prenez quelques instants pour la découvrir en testant un jeu : [https://tic80.com/play](https://tic80.com/play)

Tous les outils sont intégrés pour vous permettre de créer facilement un jeu : éditeurs de code, de sprites, de cartes, de sons, ainsi qu'un terminal.

Pour réaliser cet atelier, vous pouvez utiliser directement TIC-80 dans votre navigateur : https://tic80.com/create.

## Initialiser TIC-80 pour pouvoir utiliser le langage Python

il vous suffit de taper la commande suivante

```bash
new python
```

## Reset “hello world”

Le plus simple pour bien comprendre le fonctionnement de TIC-80 consiste de partir d’un environnement vierge, nous allons donc supprimer tous les éléments de la démo.

- Utilisez la touche  **`ESC`** de votre clavier pour vous rendre dans l’éditeur de code
- Vous pouvez sélectionner tout texte avec **`CTRL`+`A`** et ensuite supprimer le code existant

> QUIZ.A1.1 Commande d'initialisation
> Quelle commande initialise un projet Python dans TIC-80 ?

- A. init python
- B. new python
- C. start python

## Affichage du pad et de l’écran de jeu

Rendez vous dans  l’éditeur, normalement vous y êtes déjà, et écrivez le code suivant : 

```python
# script:  python

def TIC():
 cls()
 rect(0,0,120,120,10)
 rect(45, 110, 30, 3, 12)
```

Vous pouvez maintenant retourner sur le terminal avec la touche **`ESC`** de votre clavier et taper la commande **`run`** pour lancer votre jeu

> QUIZ.A1.2 La fonction `cls()`
> À quoi sert la fonction cls() dans notre programme TIC-80 ?

- A. À calculer le score du joueur
- B. À dessiner un rectangle
- C. À effacer l'écran
- D. À changer la couleur du fond


### Quelques explications

Chaque environnement et chaque langage de programmation possède ses spécificités. Pour cet atelier, nous utilisons le langage Python et l’environnement TIC-80 : 

- Il faut  expliquer à TIC-80 que le code sera écrit en langage Python en écrivant à la première ligne  de l’éditeur `# script:  python`
- La partie principale du programme se déclare de la façon suivante `def TIC():`
- Le code en dessous de la partie principale du programme doit respecter une indentation propre au python : il faut un espace au début de chaque ligne comme dans l’exemple
- Nous pouvons utiliser des instructions prédéfinies comme `cls()` pour effacer l’écran (CLear Screen) et `rect()` pour dessiner des rectangles.