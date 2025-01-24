# Exercice 8.1
Écrivez un algorithme remplissant un tableau de 6 sur 13, avec des zéros.

# Exercice 8.2
Quel résultat produira cet algorithme ?
```
Tableau X[1, 2] en Entier
Variables i, j, val en Entier
Début
Val ← 1
Pour i ← 0 à 1
  Pour j ← 0 à 2
    X[i, j] ← Val
    Val ← Val + 1
  j Suivant
i Suivant
Pour i ← 0 à 1
  Pour j ← 0 à 2
    Ecrire X[i, j]
  j Suivant
i Suivant
Fin
```

# Exercice 8.3
Quel résultat produira cet algorithme ?
```
Tableau X[1, 2] en Entier
Variables i, j, val en Entier
Début
Val ← 1
Pour i ← 0 à 1
  Pour j ← 0 à 2
    X[i, j] ← Val
    Val ← Val + 1
  j Suivant
i Suivant
Pour j ← 0 à 2
  Pour i ← 0 à 1
    Ecrire X[i, j]
  i Suivant
j Suivant
Fin
```

# Exercice 8.4
Quel résultat produira cet algorithme ?
```
Tableau T[3, 1] en Entier
Variables k, m, en Entier
Début
Pour k ← 0 à 3
  Pour m ← 0 à 1
    T[k, m] ← k + m
  m Suivant
k Suivant
Pour k ← 0 à 3
  Pour m ← 0 à 1
    Ecrire T[k, m]
  m Suivant
k Suivant
Fin
```
# Exercice 8.5
Mêmes questions, en remplaçant la ligne :
```
T[k, m] ← k + m
par
T[k, m] ← 2 * k + [m + 1]
puis par :
T[k, m] ← [k + 1] + 4 * m
```
# Exercice 8.6
Soit un tableau T à deux dimensions [12, 8] préalablement rempli de valeurs numériques.
Écrire un algorithme qui recherche la plus grande valeur au sein de ce tableau.

# Exercice 8.7
Écrire un algorithme de jeu de dames très simplifié.  
L’ordinateur demande à l’utilisateur dans quelle case se trouve son pion (quelle ligne, quelle colonne). On met en place un contrôle de saisie afin de vérifier la validité des valeurs entrées.
Ensuite, on demande à l’utilisateur quel mouvement il veut effectuer : 0 (en haut à gauche), 1 (en haut à droite), 2 (en bas à gauche), 3 (en bas à droite).  
Si le mouvement est impossible (i.e. on sort du damier ), on le signale à l’utilisateur et on s’arrête là . Sinon, on déplace le pion et on affiche le damier résultant, en affichant un « O » pour une case vide et un « X » pour la case où se trouve le pion.