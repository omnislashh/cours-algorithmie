# Exercice 7.1
Ecrivez un algorithme qui permette de saisir un nombre quelconque de valeurs, et qui les range au fur et à mesure dans un tableau. Le programme, une fois la saisie terminée, doit dire si les éléments du tableau sont tous consécutifs ou non.
Par exemple, si le tableau est :  
 
12	13	14	15	16	17	18  

ses éléments sont tous consécutifs. En revanche, si le tableau est :  
 
9	10	11	15	16	17	18  

ses éléments ne sont pas tous consécutifs.  
```C#
Variables Nb, i en Entier         // Déclaration des variables Nb pour le nombre de valeurs et i pour l'index des boucles
Variable Flag en Booléen         // Déclaration de la variable Flag qui va permettre de vérifier si les nombres sont consécutifs
Tableau T[] en Entier            // Déclaration du tableau T qui va stocker les valeurs saisies

Debut
  // Demander à l'utilisateur combien de valeurs il souhaite saisir
  Ecrire "Entrez le nombre de valeurs :"
  Lire Nb                    // Lire la taille du tableau (nombre de valeurs à saisir)
  
  // Redimensionner le tableau T avec la taille appropriée
  Redim T[Nb-1]

  // Boucle pour saisir les valeurs
  Pour i ← 0 à Nb - 1
    Ecrire "Entrez le nombre n° ", i + 1  // Afficher l'instruction de saisie
    Lire T[i]                            // Lire la valeur saisie par l'utilisateur et la stocker dans le tableau T
  i Suivant                               // Passer à l'élément suivant du tableau

  Flag ← Vrai                             // Initialiser la variable Flag à "Vrai", en supposant que les nombres sont consécutifs

  // Boucle pour vérifier si les nombres sont consécutifs
  Pour i ← 1 à Nb - 1
    Si T[i] <> T[i – 1] + 1 Alors         // Si l'élément actuel n'est pas égal au précédent + 1 (c'est-à-dire qu'ils ne sont pas consécutifs)
      Flag ← Faux                          // On change Flag à "Faux" si les nombres ne sont pas consécutifs
    FinSi
  i Suivant                                 // Passer à l'élément suivant du tableau

  // Vérification du résultat et affichage du message approprié
  Si Flag Alors
    Ecrire "Les nombres sont consécutifs"  // Si Flag est toujours "Vrai", afficher que les nombres sont consécutifs
  Sinon
    Ecrire "Les nombres ne sont pas consécutifs"  // Sinon, afficher que les nombres ne sont pas consécutifs
  FinSi

Fin    // Fin de l'algorithme

```
Cette programmation est sans doute la plus spontanée, mais elle présente le défaut d'examiner la totalité du tableau, même lorsqu'on découvre dès le départ deux éléments non consécutifs. Aussi, dans le cas d'un grand tableau, est-elle dispendieuse en temps de traitement. Une autre manière de procéder serait de sortir de la boucle dès que deux éléments non consécutifs sont détectés. La deuxième partie de l'algorithme deviendrait donc :  
```C#
i ← 1
TantQue T[i] = T[i – 1] + 1 et i < Nb - 1
  i ← i + 1
FinTantQue
Si T[i] = T[i – 1] + 1 Alors
  Ecrire "Les nombres sont consécutifs"
Sinon
  Ecrire "Les nombres ne sont pas consécutifs"
FinSi
```
# Exercice 7.2
Ecrivez un algorithme qui trie un tableau dans l’ordre décroissant.
Vous écrirez bien entendu deux versions de cet algorithme, l'une employant le tri par sélection, l'autre le tri à bulles.

On suppose que N est le nombre d’éléments du tableau. Tri par insertion :
```C#
…
Variables i, j, posmaxi, temp en Entier
Tableau t[] en Entier
Debut
  Pour i ← 0 à N - 2
    posmaxi ← i  // Initialiser la position de l'élément maximal à la position actuelle
    Pour j ← i + 1 à N - 1
      Si t[j] > t[posmaxi] Alors   // Si l'élément à la position j est plus grand que l'élément à la position posmaxi
        posmaxi ← j                // Mettre à jour la position de l'élément maximal
      FinSi
    j Suivant
    temp ← t[posmaxi]               // Stocker temporairement l'élément maximal
    t[posmaxi] ← t[i]               // Échanger l'élément maximal avec l'élément à la position i
    t[i] ← temp
  i Suivant
Fin


Tri à bulles :

…
Variables i, temp en Entier
Tableau t[] en Entier
Variable Yapermut en Booléen
Debut
  Yapermut ← Vrai  // Initialiser la variable de contrôle de permutation
  TantQue Yapermut
    Yapermut ← Faux   // Réinitialiser la variable à Faux, ce qui arrêtera la boucle si aucun échange n'est effectué
    Pour i ← 0 à N - 2
      Si t[i] < t[i + 1] Alors   // Si l'élément à la position i est plus petit que l'élément suivant
        temp ← t[i]               // Stocker temporairement l'élément à la position i
        t[i] ← t[i + 1]           // Échanger l'élément à la position i avec celui à la position i+1
        t[i + 1] ← temp
        Yapermut ← Vrai           // Indiquer qu'un échange a été effectué, donc continuer à trier
      FinSi
    i Suivant
  FinTantQue
Fin

```
# Exercice 7.3
Ecrivez un algorithme qui inverse l’ordre des éléments d’un tableau dont on suppose qu'il a été préalablement saisi (« les premiers seront les derniers… »)

On suppose que n est le nombre d’éléments du tableau préalablement saisi

```C#
…
Pour i ← 0 à (N-1)/2
  Temp ← T[i]
  T[i] ← T[N-1-i]
  T[N-1-i] ← Temp
i suivant
Fin
```

# Exercice 7.4
Ecrivez un algorithme qui permette à l’utilisateur de supprimer une valeur d’un tableau préalablement saisi. L’utilisateur donnera l’indice de la valeur qu’il souhaite supprimer. Attention, il ne s’agit pas de remettre une valeur à zéro, mais bel et bien de la supprimer du tableau lui-même ! Si le tableau de départ était :  
 
12	8	4	45	64	9	2  

Et que l’utilisateur souhaite supprimer la valeur d’indice 4, le nouveau tableau sera :  
 
12	8	4	45	9	2  

```C#
…
Ecrire "Rang de la valeur à supprimer ?"
Lire S
Pour i ← S à N-2
  T[i] ← T[i+1]
i suivant
Redim T[N–1]
Fin
```

# Exercice 7.5
Ecrivez l'algorithme qui recherche un mot saisi au clavier dans un dictionnaire. Le dictionnaire est supposé être codé dans un tableau préalablement rempli et trié.

```C#
N est le nombre d'éléments du tableau Dico[], contenant les mots du dictionnaire, tableau préalablement rempli.

Variables Sup, Inf, Comp en Entier
Variables Fini en Booléen
Début
Ecrire "Entrez le mot à vérifier"
Lire Mot

On définit les bornes de la partie du tableau à considérer

Sup ← N - 1
Inf ← 0
Fini ← Faux
TantQue Non Fini
Comp désigne l'indice de l'élément à comparer. En bonne rigueur, il faudra veiller à ce que Comp soit bien un nombre entier, ce qui pourra s'effectuer de différentes manières selon les langages.
  Comp ← [Sup + Inf]/2

Si le mot se situe avant le point de comparaison, alors la borne supérieure change, la borne inférieure ne bouge pas.
  Si Mot < Dico[Comp] Alors
    Sup ← Comp - 1

Sinon, c'est l'inverse

  Sinon
    Inf ← Comp + 1
  FinSi
  Fini ← Mot = Dico[Comp] ou Sup < Inf
FinTantQue
Si Mot = Dico[Comp] Alors
  Ecrire "le mot existe"
Sinon
  Ecrire "Il n'existe pas"
Finsi
Fin
```
Version commentée :
```C#
N est le nombre d'éléments du tableau Dico[], contenant les mots du dictionnaire, tableau préalablement rempli.

Variables Sup, Inf, Comp en Entier
Variables Fini en Booléen
Début
  Ecrire "Entrez le mot à vérifier"
  Lire Mot

  // On définit les bornes de la partie du tableau à considérer
  Sup ← N - 1         // Borne supérieure : indice du dernier élément
  Inf ← 0             // Borne inférieure : indice du premier élément
  Fini ← Faux         // Flag indiquant si la recherche est terminée

  // Tant que la recherche n'est pas terminée (on n'a pas trouvé le mot ou on a épuisé les éléments à rechercher)
  TantQue Non Fini
    // Calcul de l'indice du milieu du sous-tableau
    Comp ← (Sup + Inf) / 2

    // Si le mot est avant l'élément de comparaison, on cherche dans la moitié gauche
    Si Mot < Dico[Comp] Alors
      Sup ← Comp - 1    // Réduire la partie supérieure de la recherche
    Sinon
      // Si le mot est après l'élément de comparaison, on cherche dans la moitié droite
      Inf ← Comp + 1    // Réduire la partie inférieure de la recherche
    FinSi

    // Vérification de si le mot a été trouvé ou si la recherche est terminée
    Fini ← (Mot = Dico[Comp]) ou (Sup < Inf)
  FinTantQue

  // Si le mot a été trouvé dans le dictionnaire
  Si Mot = Dico[Comp] Alors
    Ecrire "Le mot existe"
  Sinon
    Ecrire "Il n'existe pas"
  FinSi
Fin
```

# Exercice 7.6
Écrivez un algorithme qui fusionne deux tableaux (déjà existants) dans un troisième, qui devra être trié.
Attention ! On présume que les deux tableaux de départ sont préalablement triés : il est donc irrationnel de faire une simple concaténation des deux tableaux de départ, puis d'opérer un tri : comme quand on se trouve face à deux tas de papiers déjà triés et qu'on veut les réunir, il existe une méthode bien plus économique (et donc, bien plus rationnelle...)

Les deux tableaux de départ, A[m] et B[n], sont déjà triés : pas question donc de les empiler simplement pour se relancer dans un (long) tri. On prend simplement les deux tableaux, et on avance dans l'un puis dans l'autre selon celui des deux éléments auquel on est parvenu est le plus petit (il suffit de s'imaginer devant deux tas de papiers triés par date, et de vouloir constituer un tas unique, pour comprendre ce qu'on va faire). Le truc est qu'on ne sait pas par avance où on va en être à un moment donné dans un tableau et dans l'autre : il nous faut donc deux compteurs différents pour noter notre position dans chacun des deux tableaux. On appelle C le tableau de destination, et ic la variable qui indique où on en est dans celui-ci.

```C#
Début
(...)
Afini ← faux
Bfini ← faux
ia ← 0
ib ← 0
ic ← -1
TantQue Non Afini ou Non Bfini
   ic ← ic + 1
   Redim C[ic]
   Si Afini ou A[ia]>B[ib] Alors
      C[ic] ← B[ib]
      ib ← ib + 1
      Bfini ← ib > n
   Sinon
      C[ic] ← A[ia]
      ia ← ia + 1
      Afini ← ia > m
   FinSi
FinTantQue
Fin
```
Version commentée :
```C#
Début
  // Initialisation des variables
  Afini ← faux   // Indicateur si le tableau A est entièrement parcouru
  Bfini ← faux   // Indicateur si le tableau B est entièrement parcouru
  ia ← 0         // Indice pour le tableau A
  ib ← 0         // Indice pour le tableau B
  ic ← -1        // Indice pour le tableau C

  // Tant qu'un des tableaux n'est pas entièrement parcouru
  TantQue Non Afini ou Non Bfini
    ic ← ic + 1
    Redim C[ic]   // Redimensionner le tableau C pour y insérer un élément

    // Si le tableau A est terminé ou l'élément de A est plus grand que l'élément de B
    Si Afini ou A[ia] > B[ib] Alors
      C[ic] ← B[ib]    // Ajouter l'élément de B dans C
      ib ← ib + 1      // Avancer dans le tableau B
      Bfini ← ib > n   // Vérifier si on a parcouru tout le tableau B
    Sinon
      C[ic] ← A[ia]    // Ajouter l'élément de A dans C
      ia ← ia + 1      // Avancer dans le tableau A
      Afini ← ia > m   // Vérifier si on a parcouru tout le tableau A
    FinSi
  FinTantQue

Fin
```