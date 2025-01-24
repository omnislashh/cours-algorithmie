# Exercice 6.1
Ecrire un algorithme qui déclare et remplisse un tableau de 7 valeurs numériques en les mettant toutes à zéro.
```
Tableau Truc[6] en Numérique
Variable i en Numérique
Debut
Pour i ← 0 à 6
  Truc[i] ← 0
i Suivant
Fin
```

# Exercice 6.2
Ecrire un algorithme qui déclare et remplisse un tableau contenant les six voyelles de l’alphabet latin.
```
Tableau Truc[5] en Caractère
Debut
Truc[0] ← "a"
Truc[1] ← "e"
Truc[2] ← "i"
Truc[3] ← "o"
Truc[4] ← "u"
Truc[5] ← "y"
Fin
```

# Exercice 6.3
Ecrire un algorithme qui déclare un tableau de 9 notes, dont on fait ensuite saisir les valeurs par l’utilisateur.
```
Tableau Notes[8] en Numérique
Variable i en Numérique
Pour i ← 0 à 8
  Ecrire "Entrez la note numéro ", i + 1
  Lire Notes[i]
i Suivant
Fin
```

# Exercice 6.4
Que produit l’algorithme suivant ?  
Tableau Nb[5] en Entier  
Variable i en Entier  
```
Début
Pour i ← 0 à 5
  Nb[i] ← i * i
i suivant
Pour i ← 0 à 5
  Ecrire Nb[i]
i suivant
Fin
```
Peut-on simplifier cet algorithme avec le même résultat ?

Cet algorithme remplit un tableau avec six valeurs : 0, 1, 4, 9, 16, 25.
Il les écrit ensuite à l’écran. Simplification :

```
Tableau Nb[5] en Numérique
Variable i en Numérique
Début
Pour i ← 0 à 5
  Nb[i] ← i * i
  Ecrire Nb[i]
i Suivant
Fin
```

# Exercice 6.5
Que produit l’algorithme suivant ?
```
Tableau N[6] en Entier
Variables i, k en Entier
Début
N[0] ← 1
Pour k ← 1 à 6
  N[k] ← N[k-1] + 2
k Suivant
Pour i ← 0 à 6
  Ecrire N[i]
i suivant
Fin
```
Peut-on simplifier cet algorithme avec le même résultat ?

Cet algorithme remplit un tableau avec les sept valeurs : 1, 3, 5, 7, 9, 11, 13.
Il les écrit ensuite à l’écran. Simplification :  

```
Tableau N[6] en Numérique
Variables i, k en Numérique
Début
N[0] ← 1
Ecrire N[0]
Pour k ← 1 à 6
  N[k] ← N[k-1] + 2
  Ecrire N[k]
k Suivant
Fin
```

# Exercice 6.6
Que produit l’algorithme suivant ?
```
Tableau Suite[7] en Entier
Variable i en Entier
Début
Suite[0] ← 1
Suite[1] ← 1
Pour i ← 2 à 7
  Suite[i] ← Suite[i-1] + Suite[i-2]
i suivant
Pour i ← 0 à 7
  Ecrire Suite[i]
i suivant
Fin
```

Cet algorithme remplit un tableau de 8 valeurs : 1, 1, 2, 3, 5, 8, 13, 21
# Exercice 6.7
Ecrivez la fin de l’algorithme 6.3 afin que le calcul de la moyenne des notes soit effectué et affiché à l’écran.

```
Variable S en Numérique
Tableau Notes[8] en Numérique
Variable i en Numérique
Debut
s ← 0
Pour i ← 0 à 8
  Ecrire "Entrez la note n° ", i + 1
  Lire Notes[i]
  s ← s + Notes[i]
i Suivant
Ecrire "Moyenne :", s/9
Fin
```

# Exercice 6.8
Ecrivez un algorithme permettant à l’utilisateur de saisir un nombre quelconque de valeurs, qui devront être stockées dans un tableau. L’utilisateur doit donc commencer par entrer le nombre de valeurs qu’il compte saisir. Il effectuera ensuite cette saisie. Enfin, une fois la saisie terminée, le programme affichera le nombre de valeurs négatives et le nombre de valeurs positives.

```
Variables Nb, Nbpos, Nbneg en Numérique
Tableau T[] en Numérique
Variable i en Numérique
Debut
Ecrire "Entrez le nombre de valeurs :"
Lire Nb
Redim T[Nb-1]
Nbpos ← 0
Nbneg ← 0
Pour i ← 0 à Nb - 1
  Ecrire "Entrez le nombre n° ", i + 1
  Lire T[i]
  Si T[i] > 0 alors
    Nbpos ← Nbpos + 1
  Sinon
    Nbneg ← Nbneg + 1
  Finsi
i Suivant
Ecrire "Nombre de valeurs positives : ", Nbpos
Ecrire "Nombre de valeurs négatives : ", Nbneg
Fin
```

# Exercice 6.9
Ecrivez un algorithme calculant la somme des valeurs d’un tableau (on suppose que le tableau a été préalablement saisi).

```
Variables i, Som, N en Numérique
Tableau T[] en Numérique
Debut
… (on ne programme pas la saisie du tableau, dont on suppose qu’il compte N éléments]
Redim T[N-1]
…
Som ← 0
Pour i ← 0 à N - 1
  Som ← Som + T[i]
i Suivant
Ecrire "Somme des éléments du tableau : ", Som
Fin
```
# Exercice 6.10
Ecrivez un algorithme constituant un tableau, à partir de deux tableaux de même longueur préalablement saisis. Le nouveau tableau sera la somme des éléments des deux tableaux de départ.
Tableau 1 :  
4	8	7	9	1	5	4	6  

Tableau 2 :  
7	6	5	2	1	3	7	4  

Tableau à constituer :  
11	14	12	11	2	8	11	10

```
Variables i, N en Numérique
Tableaux T1[], T2[], T3[] en Numérique
Debut
… (on suppose que T1 et T2 comptent N éléments, et qu’ils sont déjà saisis)
Redim T3[N-1]
…
Pour i ← 0 à N - 1
  T3[i] ← T1[i] + T2[i]
i Suivant
Fin
```

# Exercice 6.11
Toujours à partir de deux tableaux précédemment saisis, écrivez un algorithme qui calcule le schtroumpf des deux tableaux. Pour calculer le schtroumpf, il faut multiplier chaque élément du tableau 1 par chaque élément du tableau 2, et additionner le tout. Par exemple si l'on a :  
Tableau 1 :  
4	8	7	12

Tableau 2 :  
3	6

Le Schtroumpf sera :  
3 * 4 + 3 * 8 + 3 * 7 + 3 * 12 + 6 * 4 + 6 * 8 + 6 * 7 + 6 * 12 = 279  

```
Variables i, j, N1, N2, S en Numérique
Tableaux T1[], T2[] en Numérique
Debut
… On ne programme pas la saisie des tableaux T1 et T2.
On suppose que T1 possède N1 éléments, et que T2 en possède T2)
…
S ← 0
Pour i ← 0 à N1 – 1
  Pour j ← 0 à N2 – 1
    S ← S + T1[i] * T2[j]
  j Suivant
i Suivant
Ecrire "Le schtroumpf est : ", S
Fin
```

# Exercice 6.12
Ecrivez un algorithme qui permette la saisie d’un nombre quelconque de valeurs, sur le principe de l’ex 6.8. Toutes les valeurs doivent être ensuite augmentées de 1, et le nouveau tableau sera affiché à l’écran.

```
Variables Nb, i en Numérique
Tableau T[] en Numérique
Debut
Ecrire "Entrez le nombre de valeurs : "
Lire Nb
Redim T[Nb-1]
Pour i ← 0 à Nb - 1
  Ecrire "Entrez le nombre n° ", i + 1
  Lire T[i]
i Suivant
Ecrire "Nouveau tableau : "
Pour i ← 0 à Nb – 1
  T[i] ← T[i] + 1
  Ecrire T[i]
i Suivant
Fin
```

# Exercice 6.13
Ecrivez un algorithme permettant, toujours sur le même principe, à l’utilisateur de saisir un nombre déterminé de valeurs. Le programme, une fois la saisie terminée, renvoie la plus grande valeur en précisant quelle position elle occupe dans le tableau. On prendra soin d’effectuer la saisie dans un premier temps, et la recherche de la plus grande valeur du tableau dans un second temps.
```
Variables i, Nb, Posmaxi en Numérique
Tableau T[] en Numérique
Ecrire "Entrez le nombre de valeurs :"
Lire Nb
Redim T[Nb-1]
Pour i ← 0 à Nb - 1
  Ecrire "Entrez le nombre n° ", i + 1
  Lire T[i]
i Suivant
Posmaxi ← 0
Pour i ← 0 à Nb - 1
  Si T[i] > T[Posmaxi] alors
    Posmaxi ← i
  Finsi
i Suivant
Ecrire "Element le plus grand : ", T[Posmaxi]
Ecrire "Position de cet élément : ", Posmaxi
Fin
```
# Exercice 6.14
Toujours et encore sur le même principe, écrivez un algorithme permettant, à l’utilisateur de saisir les notes d'une classe. Le programme, une fois la saisie terminée, renvoie le nombre de ces notes supérieures à la moyenne de la classe.

```
Variables Nb, i, Som, Moy, Nbsup en Numérique
Tableau T[] en Numérique
Debut
Ecrire "Entrez le nombre de notes à saisir : "
Lire Nb
Redim T[Nb-1]
Pour i ← 0 à Nb - 1
  Ecrire "Entrez le nombre n° ", i + 1
  Lire T[i]
i Suivant
Som ← 0
Pour i ← 0 à Nb - 1
  Som ← Som + T[i]
i Suivant
Moy ← Som / Nb
NbSup ← 0
Pour i ← 0 à Nb - 1
  Si T[i] > Moy Alors
    NbSup ← NbSup + 1
  FinSi
i Suivant
Ecrire NbSup, " élèves dépassent la moyenne de la classe"
Fin
```