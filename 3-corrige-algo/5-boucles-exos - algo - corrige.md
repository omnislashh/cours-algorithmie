# Exercice 5.1
Ecrire un algorithme qui demande à l’utilisateur un nombre compris entre 1 et 3 jusqu’à ce que la réponse convienne.
```C#
Variable N en Entier   // Déclaration de la variable N qui stockera le nombre saisi par l'utilisateur

Debut
  N ← 0   // Initialisation de N à une valeur en dehors de l'intervalle attendu pour forcer l'entrée dans la boucle

  Ecrire "Entrez un nombre entre 1 et 3"   // Message demandant à l'utilisateur d'entrer un nombre valide

  TantQue N < 1 ou N > 3   // Boucle qui s'exécute tant que N n'est pas dans l'intervalle [1,3]
    Lire N   // Lecture de l'entrée utilisateur

    Si N < 1 ou N > 3 Alors   // Vérification si le nombre est hors de l'intervalle
      Ecrire "Saisie erronée. Recommencez”   // Message d'erreur pour informer l'utilisateur qu'il doit entrer une valeur correcte
    FinSi

  FinTantQue   // Fin de la boucle, on sort uniquement si N est compris entre 1 et 3

Fin

```

# Exercice 5.2
Ecrire un algorithme qui demande un nombre compris entre 10 et 20, jusqu’à ce que la réponse convienne. En cas de réponse supérieure à 20, on fera apparaître un message : « Plus petit ! », et inversement, « Plus grand ! » si le nombre est inférieur à 10.
```C#
Variable N en Entier   // Déclaration de la variable N qui stockera le nombre saisi par l'utilisateur

Debut
  N ← 0   // Initialisation de N à une valeur en dehors de l'intervalle [10, 20] pour s'assurer que la boucle se lance

  Ecrire "Entrez un nombre entre 10 et 20"   // Affichage du message invitant l'utilisateur à entrer un nombre valide

  TantQue N < 10 ou N > 20   // Boucle qui s'exécute tant que N est en dehors de l'intervalle [10, 20]
    Lire N   // Lecture de la saisie de l'utilisateur

    Si N < 10 Alors   // Si le nombre saisi est inférieur à 10
      Ecrire "Plus grand !"   // Message indiquant à l'utilisateur que le nombre doit être plus grand que 10
    SinonSi N > 20 Alors   // Si le nombre saisi est supérieur à 20
      Ecrire "Plus petit !"   // Message indiquant à l'utilisateur que le nombre doit être plus petit que 20
    FinSi

  FinTantQue   // Fin de la boucle, l'utilisateur ne peut sortir de la boucle que si le nombre est entre 10 et 20

Fin

```

# Exercice 5.3
Ecrire un algorithme qui demande un nombre de départ, et qui ensuite affiche les dix nombres suivants. Par exemple, si l'utilisateur entre le nombre 17, le programme affichera les nombres de 18 à 27.

On peut imaginer deux variantes, strictement équivalentes :  
```C#
Variables N, i en Entier   // Déclaration des variables N (le nombre de départ) et i (utilisée pour la boucle)

Debut
  Ecrire "Entrez un nombre : "   // Demande à l'utilisateur de saisir un nombre de départ
  Lire N   // Lecture du nombre saisi par l'utilisateur

  Stop ← N+10   // Définition de la variable "Stop" qui correspond à la limite supérieure (N + 10)

  Ecrire "Les 10 nombres suivants sont : "   // Affichage d'un message pour annoncer les nombres suivants

  TantQue N < Stop   // Boucle qui continue tant que N est inférieur à la limite "Stop"
    N ← N+1   // Incrémentation de N pour obtenir le nombre suivant
    Ecrire N   // Affichage du nombre suivant
  FinTantQue   // Fin de la boucle qui affiche les nombres jusqu'à "Stop"

Fin

```
Ou bien :

```C#
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
i ← 0
Ecrire "Les 10 nombres suivants sont : "
TantQue i < 10
   i ← i + 1
   Ecrire N + i
FinTantQue
Fin
```
# Exercice 5.4
Réécrire l'algorithme précédent, en utilisant cette fois l'instruction Pour

Là encore, deux variantes, correspondant trait pour trait à celles du corrigé précédent :
```C#
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Ecrire "Les 10 nombres suivants sont : "
Pour i ← N + 1 à N + 10
  Ecrire i
i Suivant
Fin
```
Ou bien :
```C#
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Ecrire "Les 10 nombres suivants sont : "
Pour i ← 1 à 10
  Ecrire N + i
i Suivant
Fin
```
# Exercice 5.5
Ecrire un algorithme qui demande un nombre de départ, et qui ensuite écrit la table de multiplication de ce nombre, présentée comme suit (cas où l'utilisateur entre le nombre 7) :
Table de 7 :  
7 x 1 = 7  
7 x 2 = 14  
7 x 3 = 21  
…  
7 x 10 = 70  
```C#
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Ecrire "La table de multiplication de ce nombre est : "
Pour i ← 1 à 10
  Ecrire N, " x ", i, " = ", n*i
i Suivant
Fin
```


# Exercice 5.6
Ecrire un algorithme qui demande un nombre de départ, et qui calcule la somme des entiers jusqu’à ce nombre. Par exemple, si l’on entre 5, le programme doit calculer :  
1 + 2 + 3 + 4 + 5 = 15  
NB : on souhaite afficher uniquement le résultat, pas la décomposition du calcul.  

```C#
Variables N, i, Som en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Som ← 0
Pour i ← 1 à N
  Som ← Som + i
i Suivant
Ecrire "La somme est : ", Som
Fin
```


# Exercice 5.7
Ecrire un algorithme qui demande un nombre de départ, et qui calcule sa factorielle.
NB : la factorielle de 8, notée 8 !, vaut  
1 x 2 x 3 x 4 x 5 x 6 x 7 x 8  

```C#
Variables N, i, F en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
F ← 1
Pour i ← 2 à N
  F ← F * i
i Suivant
Ecrire "La factorielle est : ", F
Fin
```

# Exercice 5.8
Ecrire un algorithme qui demande successivement 20 nombres à l’utilisateur, et qui lui dise ensuite quel était le plus grand parmi ces 20 nombres :  
Entrez le nombre numéro 1 : 12  
Entrez le nombre numéro 2 : 14  
etc.  
Entrez le nombre numéro 20 : 6  
Le plus grand de ces nombres est  : 14  
Modifiez ensuite l’algorithme pour que le programme affiche de surcroît en quelle position avait été saisie ce nombre :  
C’était le nombre numéro 2  

```C#
Variables N, i, PG en Entier   // Déclaration des variables N (le nombre saisi), i (index de la boucle), PG (le plus grand nombre)

Debut
  PG ← 0   // Initialisation de PG à 0, car on suppose que les nombres saisis seront tous supérieurs ou égaux à 0

  Pour i ← 1 à 20   // Boucle qui répète 20 fois, une fois pour chaque nombre à entrer
    Ecrire "Entrez un nombre : "   // Demande à l'utilisateur d'entrer un nombre
    Lire N   // Lecture du nombre saisi par l'utilisateur

    Si i = 1 ou N > PG Alors   // Si c'est le premier nombre ou si le nombre saisi est plus grand que le précédent plus grand
      PG ← N   // Le nombre saisi devient le nouveau plus grand nombre
    FinSi

  i Suivant   // Passage à l'itération suivante (augmentation de i pour saisir le nombre suivant)

  Ecrire "Le nombre le plus grand était : ", PG   // Affichage du plus grand nombre saisi
Fin

```
En ligne 3, on peut mettre n’importe quoi dans PG, il suffit que cette variable soit affectée pour que le premier passage en ligne 7 ne provoque pas d'erreur.

Pour la version améliorée, cela donne :

```C#
Variables N, i, PG, IPG en Entier
Debut
PG ← 0
Pour i ← 1 à 20
  Ecrire "Entrez un nombre : "
  Lire N
  Si i = 1 ou N > PG Alors
    PG ← N
    IPG ← i
  FinSi
i Suivant
Ecrire "Le nombre le plus grand était : ", PG
Ecrire "Il a été saisi en position numéro ", IPG
Fin
```
# Exercice 5.9
Réécrire l’algorithme précédent, mais cette fois-ci on ne connaît pas d’avance combien l’utilisateur souhaite saisir de nombres. La saisie des nombres s’arrête lorsque l’utilisateur entre un zéro.  
```C#
Variables N, i, PG, IPG en Entier
Debut
N ← 1
i ← 0
PG ← 0
TantQue N <> 0
  Ecrire "Entrez un nombre : "
  Lire N
  i ← i + 1
  Si i = 1 ou N > PG Alors
    PG ← N
    IPG ← i
  FinSi
FinTantQue
Ecrire "Le nombre le plus grand était : ", PG
Ecrire "Il a été saisi en position numéro ", IPG
Fin
```

# Exercice 5.10
Lire la suite des prix (en euros entiers et terminée par zéro) des achats d’un client. Calculer la somme qu’il doit, lire la somme qu’il paye, et simuler la remise de la monnaie en affichant les textes "10 Euros", "5 Euros" et "1 Euro" autant de fois qu’il y a de coupures de chaque sorte à rendre.
```C#
Variables E, somdue, M, Reste, Nb10E, Nb5E En Entier   // Déclaration des variables nécessaires : E pour un montant, somdue pour la somme totale due, M pour le montant payé, Reste pour le reste à rendre, Nb10E et Nb5E pour compter le nombre de billets de 10 et 5 euros à rendre.

Debut
  E ← 1   // Initialisation de E à 1 pour démarrer la boucle, en attendant le premier montant

  somdue ← 0   // Initialisation de la somme due à 0

  TantQue E <> 0   // Boucle pour saisir les montants des achats jusqu'à ce que l'utilisateur entre 0
    Ecrire "Entrez le montant : "   // Demande à l'utilisateur d'entrer le montant d'un achat
    Lire E   // Lecture du montant saisi
    somdue ← somdue + E   // Ajoute le montant saisi à la somme totale due
  FinTantQue   // Fin de la boucle, arrêtée lorsque E est égal à 0 (fin de la saisie des achats)

  Ecrire "Vous devez :", somdue, " euros"   // Affiche la somme totale due

  Ecrire "Montant versé :"   // Demande à l'utilisateur combien il a payé
  Lire M   // Lecture du montant payé

  Reste ← M - somdue   // Calcule le reste à rendre en soustrayant la somme due de la somme payée

  Nb10E ← 0   // Initialisation du compteur de billets de 10 euros à 0

  TantQue Reste >= 10   // Tant qu'il reste au moins 10 euros à rendre
    Nb10E ← Nb10E + 1   // Augmente le nombre de billets de 10 euros
    Reste ← Reste – 10   // Déduit 10 euros du reste à rendre
  FinTantQue   // Fin de la boucle pour les billets de 10 euros

  Nb5E ← 0   // Initialisation du compteur de billets de 5 euros à 0

  Si Reste >= 5   // Si le reste à rendre est supérieur ou égal à 5 euros
    Nb5E ← 1   // Un billet de 5 euros doit être rendu
    Reste ← Reste – 5   // Déduit 5 euros du reste à rendre
  FinSi   // Fin de la condition pour les billets de 5 euros

  Ecrire "Rendu de la monnaie :"   // Affiche la section du rendu de la monnaie

  Ecrire "Billets de 10 E : ", Nb10E   // Affiche le nombre de billets de 10 euros à rendre
  Ecrire "Billets de 5 E : ", Nb5E   // Affiche le nombre de billets de 5 euros à rendre
  Ecrire "Pièces de 1 E : ", Reste   // Affiche le reste, qui représente le nombre de pièces de 1 euro à rendre

Fin   // Fin de l'algorithme

```

# Exercice 5.11
Écrire un algorithme qui permette de connaître ses chances de gagner au tiercé, quarté, quinté et autres impôts volontaires.  
On demande à l’utilisateur le nombre de chevaux partants, et le nombre de chevaux joués. Les deux messages affichés devront être :  
Dans l’ordre : une chance sur X de gagner
Dans le désordre : une chance sur Y de gagner
X et Y nous sont donnés par la formule suivante, si n est le nombre de chevaux partants et p le nombre de chevaux joués (on rappelle que le signe ! signifie "factorielle", comme dans l'exercice 5.7 ci-dessus) : 
``` C#
X = n ! / (n - p) !
Y = n ! / (p ! * (n – p) !)
```
NB : cet algorithme peut être écrit d’une manière simple, mais relativement peu performante. Ses performances peuvent être singulièrement augmentées par une petite astuce. Vous commencerez par écrire la manière la plus simple, puis vous identifierez le problème, et écrirez une deuxième version permettant de le résoudre.

<hr>

Spontanément, on est tenté d'écrire l'algorithme suivant :
```C#
Variables N, P, i, Numé, Déno1, Déno2 en Entier   // Déclaration des variables nécessaires

Debut
  Ecrire "Entrez le nombre de chevaux partants : "   // Demander le nombre total de chevaux partants
  Lire N   // Lire le nombre de chevaux partants
  Ecrire "Entrez le nombre de chevaux joués : "   // Demander le nombre de chevaux choisis par l'utilisateur
  Lire P   // Lire le nombre de chevaux joués
  
  Numé ← 1   // Initialiser le numérateur pour le calcul de X (factorielle de N)
  
  Pour i ← 2 à N   // Commence une boucle de 2 à N pour calculer N!
    Numé ← Numé * i   // Multiplie le numérateur par i pour calculer la factorielle de N
  i Suivant   // Fin de la boucle pour calculer N!
  
  Déno1 ← 1   // Initialiser le dénominateur 1 pour le calcul de X (factorielle de N - P)
  
  Pour i ← 2 à N - P   // Commence une boucle de 2 à (N - P) pour calculer (N - P)!
    Déno1 ← Déno1 * i   // Multiplie le dénominateur par i pour calculer (N - P)!
  i Suivant   // Fin de la boucle pour calculer (N - P)!
  
  Déno2 ← 1   // Initialiser le dénominateur 2 pour le calcul de Y (factorielle de P)
  
  Pour i ← 2 à P   // Commence une boucle de 2 à P pour calculer P!
    Déno2 ← Déno2 * i   // Multiplie le dénominateur par i pour calculer P!
  i Suivant   // Fin de la boucle pour calculer P!
  
  Ecrire "Dans l’ordre, une chance sur ", Numé / Déno1   // Affiche la chance dans l’ordre (X)
  Ecrire "Dans le désordre, une sur ", Numé / (Déno1 * Déno2)   // Affiche la chance dans le désordre (Y)
  
Fin   // Fin de l'algorithme

```

Cette version, formellement juste, comporte tout de même deux faiblesses.

La première, et la plus grave, concerne la manière dont elle calcule le résultat final. Celui-ci est le quotient d'un nombre par un autre ; or, ces nombres auront rapidement tendance à être très grands. En calculant, comme on le fait ici, d'abord le numérateur, puis ensuite le dénominateur, on prend le risque de demander à la machine de stocker des nombres trop grands pour qu'elle soit capable de les coder (cf. le préambule). C'est d'autant plus bête que rien ne nous oblige à procéder ainsi : on n'est pas obligé de passer par la division de deux très grands nombres pour obtenir le résultat voulu.

La deuxième remarque est qu'on a programmé ici trois boucles successives. Or, en y regardant bien, on peut voir qu'après simplification de la formule, ces trois boucles comportent le même nombre de tours ! (si vous ne me croyez pas, écrivez un exemple de calcul et biffez les nombres identiques au numérateur et au dénominateur). Ce triple calcul (ces trois boucles) peut donc être ramené(es) à un(e) seul(e). Et voilà le travail, qui est non seulement bien plus court, mais aussi plus performant :
```C#
Variables N, P, i, A, B en Numérique
Debut
Ecrire "Entrez le nombre de chevaux partants : "
Lire N
Ecrire "Entrez le nombre de chevaux joués : "
Lire P
A ← 1
B ← 1
Pour i ← 1 à P
  A ← A * (i + N - P)
  B ← B * i
i Suivant
Ecrire "Dans l’ordre, une chance sur ", A
Ecrire "Dans le désordre, une chance sur ", A / B
Fin
```