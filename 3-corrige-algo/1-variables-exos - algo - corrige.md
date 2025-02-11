# Exercice 1.1
Quelles seront les valeurs des variables A et B après exécution des instructions suivantes ?
```C#
Variables A, B en Entier

Début
A ← 1
B ← A + 3
A ← 3
Fin
```

```C#
Après         La valeur des variables est :
A ← 1         A = 1          B = ?
B ← A + 3     A = 1          B = 4
A ← 3         A = 3         B = 4
```
# Exercice 1.2
Quelles seront les valeurs des variables A, B et C après exécution des instructions suivantes ?
```C#
Variables A, B, C en Entier

Début
A ← 5
B ← 3
C ← A + B
A ← 2
C ← B – A
Fin
```
```C#
Après         La valeur des variables est :
A ← 5         A = 5          B = ?           C = ?
B ← 3         A = 5          B = 3           C = ?
C ← A + B     A = 5          B = 3           C = 8
A ← 2         A = 2          B = 3           C = 8
C ← B – A     A = 2         B = 3          C = 1
```
# Exercice 1.3
Quelles seront les valeurs des variables A et B après exécution des instructions suivantes ?
```C#
Variables A, B en Entier

Début
A ← 5
B ← A + 4
A ← A + 1
B ← A – 4
Fin
```
```C#
Après         La valeur des variables est :
A ← 5         A = 5          B = ?
B ← A + 4     A = 5          B = 9
A ← A + 1     A = 6          B = 9
B ← A – 4     A = 6         B = 2
```
# Exercice 1.4
Quelles seront les valeurs des variables A, B et C après exécution des instructions suivantes ?
```C#
Variables A, B, C en Entier
Début
 A ← 3
B ← 10
C ← A + B
B ← A + B
A ← C
Fin
```
```C#
Après         La valeur des variables est :
A ← 3         A = 3          B = ?           C = ?
B ← 10        A = 3          B = 10          C = ?
C ← A + B     A = 3          B = 10          C = 13
B ← A + B     A = 3          B = 13          C = 13
A ← C        A = 13         B = 13         C = 13
```
# Exercice 1.5
Quelles seront les valeurs des variables A et B après exécution des instructions suivantes ?
```C#
Variables A, B en Entier
Début
A ← 5
B ← 2
A ← B
B ← A
Fin
```
Moralité : les deux dernières instructions permettent-elles d’échanger les deux valeurs de B et A ? Si l’on inverse les deux dernières instructions, cela change-t-il quelque chose ?

```C#
Après         La valeur des variables est :
A ← 5         A = 5          B = ?
B ← 2         A = 5          B = 2
A ← B         A = 2          B = 2
B ← A         A = 2         B = 2
```

# Exercice 1.6
Plus difficile, mais c’est un classique absolu, qu’il faut absolument maîtriser : écrire un algorithme permettant d’échanger les valeurs de deux variables A et B, et ce quel que soit leur contenu préalable.

```C#
Début
…
C ← A
A ← B
B ← C
Fin
Il existe différentes solutions possibles (comme toujours), mais le plus simple est de passer par une variable dite temporaire (la variable C).
```

# Exercice 1.7
Une variante du précédent : on dispose de trois variables A, B et C. Ecrivez un algorithme transférant à B la valeur de A, à C la valeur de B et à A la valeur de C (toujours quels que soient les contenus préalables de ces variables).
```C#
Début
…
D ← C
C ← B
B ← A
A ← D
Fin
En fait, quel que soit le nombre de variables, une seule variable temporaire suffit…
``` 

# Exercice 1.8
Que produit l’algorithme suivant ?
```C#
Variables A, B, C en Caractères
Début
A ← "423"
B ← "12"
C ← A + B
Fin
```
Il ne peut produire qu’une erreur d’exécution, puisqu’on ne peut pas additionner des caractères.

# Exercice 1.9
Que produit l’algorithme suivant ?
```C#
Variables A, B, C en Caractères
Début
A ← "423"
B ← "12"
C ← A & B
Fin
```

…En revanche, on peut les concaténer. A la fin de l’algorithme, C vaudra donc  "42312".