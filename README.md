## Learning_C
- Apprendre à programmer en C / Learning C

## Les Fonctions:
Comme dans la plupart des langages, on peut en C découper un programme en plusieurs fonctions.<br> Une seule de ces fonctions existe obligatoirement;<br>
C'est la fonction principale appelée <b>main</b>.<br>
Cette fonction principale peut, éventuellement, appeler une ou plusieurs fonctions secondaires.<br>
De même, chaque fonction secondaire peut appeler d'autres fonctions secondaires ou s'appeler elle-même (dans ce dernier cas, on dit que la fonction est <b>récursive</b>).<br>
<br>
La définition d'une fonction est la donnée du texte de son algorithme, qu'on appelle corps de la fonction.<br>

```c

type nom-fonction (type-1 arg-1,...,type-n arg-n)
{[déclarations de variables locales ]
  liste d'instructions
}

```
## Les Instructions:
Comme son nom le laisse présager, le bloc d'instructions peut contenir plusieurs instructions (il peut aussi en contenir qu'une unique).<br> 
Le bloc commence par une accolade ouvrante et se termine par une accolade fermante.<br>
L'exemple ci-dessous montre un bloc d'instructions vous demandant de saisir votre nom :<br>

*ce bloc est constitué de quatre lignes de code.*

### Exemple d'instruction:
```c
{
    printf( "Veuillez renseigner votre nom : " );
    char buffer[80];
    scanf( "%s", buffer );
    printf( "Hello %s\n" );
}

```
Il faut savoir qu'un bloc d'instructions impose une durée de vie aux variables qui sont déclarées à l'intérieur de ce bloc.<br> 
En fait une telle variable (dite locale) est stockée dans un espace de mémoire particulier appelé la pile d'exécution (ou stack, en anglais).<br> 
L'état de la pile évolue au cours du temps en fonction des variables de l'on défini.<br>
<br>
Un autre point est aussi important à savoir : la taille de la pile d'exécution est limitée. Si vous saturez cette pile d'exécution, <b>une erreur FATALE sera déclenchée.</b><br> 
En réalité, un programme complexe n'a pas qu'une unique pile d'exécution.<br>
Effectivement, cette notion de pile est en fait liée à la notion de threads (aussi appelé fil d'exécution) :<br>

*il existe donc une pile d'exécution par thread.*


## Les caractères spéciaux:
- \n->retour à la ligne (= « Entrée ») ;
- \t->tabulation.

### Exemple de caractères spéciaux:

```c
printf("Hello, World\n"); //Retour Ligne
printf("Hello, World\t"); //Tabulation
```

## En résumé (À Retenir)

- Les programmes peuvent communiquer avec l'utilisateur via une console ou une fenêtre.

- Il est beaucoup plus facile pour nos premiers programmes de travailler avec la <b>console</b>, <br>bien que celle-ci soit moins attirante pour un débutant.

- Un programme est constitué d'instructions qui se terminent toutes par un point-virgule.

- Les instructions sont contenues dans des <b>fonctions</b> qui permettent de les classer, comme dans des boîtes.

- La fonction <b>main</b>(qui signifie « principale ») est la fonction par laquelle démarre votre programme.<br>
<br>

*C'est la seule qui soit obligatoire, aucun programme ne peut être compilé sans elle.*
<br>

- <b>printf</b> est une fonction toute prête qui permet d'afficher un message à l'écran dans une console.

- <b>printf</b> se trouve dans une bibliothèque où l'on retrouve de nombreuses autres fonctions prêtes à l'emploi. 

## En résumé (version Language C)

```c
/*
Ci-dessous, ce sont des directives de préprocesseur.
Ces lignes permettent d'ajouter des fichiers au projet, 
fichiers que l'on appelle bibliothèques.
Grâce à ces bibliothèques, on disposera de fonctions toutes prêtes pour afficher
par exemple un message à l'écran.
*/

#include <stdio.h>
#include <stdlib.h>

/*
Ci-dessous, vous avez la fonction principale du programme, appelée "main".
C'est par cette fonction que tous les programmes commencent.
Ici, ma fonction se contente d'afficher Bonjour à l'écran.
*/

int main()
{
  printf("Bonjour"); // Cette instruction affiche Bonjour à l'écran.
  return 0;          // Le programme renvoie le nombre 0 puis s'arrête.
}
```


## C mémoires
### Les différents types de mémoire:

voici les différents types de mémoire existant dans un ordinateur, de la plus rapide à la plus lente.<br>

- Les registres : une mémoire ultra-rapide située directement dans le processeur.

- La mémoire cache : elle fait le lien entre les registres et la mémoire vive. 

- La mémoire vive : c'est la mémoire avec laquelle nous allons travailler le plus souvent.

- Le disque dur : que vous connaissez sûrement, c'est là qu'on enregistre les fichiers. <br><br>


### *Chose très importante : Seul le disque dur retient tout le temps les informations qu'il contient. Toutes les autres mémoires (registres, mémoire cache, mémoire vive) sont des mémoires temporaires : lorsque vous éteignez votre ordinateur, ces mémoires se vident !*

## Schéma de la mémoire vive:
fonctionnement de la mémoire vive(cf photo) <br>

![Alt text](https://github.com/JeanVincentz/screen/blob/master/memories.png)
<br>

Il faut distinguer deux colonnes.

<b>Adresse</b>: 
- Une adresse est un nombre qui permet à l'ordinateur de se repérer dans la mémoire vive. On commence à l'adresse 0 (au tout début de la mémoire) et on finit à l'adresse 3 448 765 900 126 et des poussières environs (~).<br>

<b>Valeurs</b>:
- À chaque adresse, on peut stocker une valeur (un nombre) : un ordinateur stocke dans la mémoire vive ces nombres pour pouvoir s'en souvenir par la suite. On ne peut stocker qu'un nombre par adresse.<br>

*La mémoire RAM ne peut stocker que des nombres.*

## Les Variables:
En langage C, une variable est constituée de deux choses:<br>

- Une valeur: C'est le nombre qu'elle stocke, par exemple 10.<br>

- Un nom: C'est ce qui permet de la reconnaître. En programmant en C, on n'aura pas à retenir l'adresse mémoire mais à la place, on va juste indiquer des noms de variables. C'est le compilateur qui fera la conversion entre le nom et l'adresse.<br>

## Les Variables: (Contraintes)
On ne peut pas appeler une variable n'importe comment.<br>

- Il ne peut y avoir que des minuscules, majuscules et des chiffres (abcABC012).

- Le nom d'une variable doit commencer par une lettre.

- Les espaces sont interdits. À la place, on peut utiliser le caractère « <b>underscore </b>» _ (qui ressemble à un trait de soulignement). C'est le seul caractère différent des lettres et chiffres autorisé 

- Pas le droit d'utiliser des accents (<b>éàê</b>) etc.

### Très important à savoir, le langage C fait la différence entre les majuscules et les minuscules. Pour votre culture, sachez qu'on dit que c'est un langage qui « respecte la casse ».
<br>

## Les Variables: (Incorrect)
```c
largeur | LARGEUR | LArgEuR 
```
Sont trois variables différentes en langage C, même si pour nous simple humain, ça a l'air de signifier la même chose.

## Les Variables: (Correct)
```c
nombreDeVies | prenom | nom | numero_de_telephone | numeroDeTelephone
```
<br>

## Les Variables: (Types)
Lorsque l'on créer une variable, on doit lui indiquer son type:(cf photo)<br>

![Alt text](https://github.com/JeanVincentz/screen/blob/master/types.png)
<br>

signed char | int | long | :<br>
 - Permet de stocker des nombres entiers: 1, 2, 3, 4 ...<br>

float | double | :<br>
- Permet de stocker des nombres décimaux: 13.8, 16.911, 78.100 (Nombres flottants).
<br>

Pour les types entiers: 
- signed char, int, long

il existe d'autres types dits unsigned (non signés),qui eux ne peuvent stocker que des nombres positifs.<br>
Pour les utiliser, il suffit d'écrire le mot unsigned devant le type:

## Les Variables: (Types - exemple)

```c
unsigned char -> 0 à 255

unsigned int -> 0 à 65 535

unsigned long -> 0 à 4 294 967 295
```
## En résumé (À Retenir)

- Pour un nombre entier, on utilisera le plus souvent <b>int</b>
- pour un nombre flottant, on utilisera généralement <b>double</b>
- <b>char</b> toujours suivie du mot clé <b>signed</b> ou <b>unsigned</b>, 

### La raison en est toute simple : le type peut-être signé ou non signé suivant les machines.<br> Toujours veillez donc à spécifier lequel des deux ont souhaite utiliser suivant le type de valeur que l'ont désire stocker.
(cf.dossier variable)