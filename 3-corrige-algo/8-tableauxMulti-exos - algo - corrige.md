# Exercice 8.1
Écrivez un algorithme remplissant un tableau de 6 sur 13, avec des zéros.

```C#
Tableau Truc[5, 12] en Entier
Debut
Pour i ← 0 à 5
  Pour j ← 0 à 12
    Truc[i, j] ← 0
  j Suivant
i Suivant
Fin
```

# Exercice 8.2
Quel résultat produira cet algorithme ?
```C#
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
```C#
Cet algorithme remplit un tableau de la manière suivante:
X[0, 0] = 1
X[0, 1] = 2
X[0, 2] = 3
X[1, 0] = 4
X[1, 1] = 5
X[1, 2] = 6
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.
```
# Exercice 8.3
Quel résultat produira cet algorithme ?
```C#
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
```C#
Cet algorithme remplit un tableau de la manière suivante:
X[0, 0] = 1
X[1, 0] = 4
X[0, 1] = 2
X[1, 1] = 5
X[0, 2] = 3
X[1, 2] = 6
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.
```
# Exercice 8.4
Quel résultat produira cet algorithme ?
```C#
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
```C#
Cet algorithme remplit un tableau de la manière suivante:
T[0, 0] = 0
T[0, 1] = 1
T[1, 0] = 1
T[1, 1] = 2
T[2, 0] = 2
T[2, 1] = 3
T[3, 0] = 3
T[3, 1] = 4
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.
```
# Exercice 8.5
Mêmes questions, en remplaçant la ligne :
```C#
T[k, m] ← k + m
par
T[k, m] ← 2 * k + [m + 1]
puis par :
T[k, m] ← [k + 1] + 4 * m
```

```C#
Version a : cet algorithme remplit un tableau de la manière suivante:
T[0, 0] = 1
T[0, 1] = 2
T[1, 0] = 3
T[1, 1] = 4
T[2, 0] = 5
T[2, 1] = 6
T[3, 0] = 7
T[3, 1] = 8
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.

Version b : cet algorithme remplit un tableau de la manière suivante:
T[0, 0] = 1
T[0, 1] = 5
T[1, 0] = 2
T[1, 1] = 6
T[2, 0] = 3
T[2, 1] = 7
T[3, 0] = 4
T[3, 1] = 8
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.
```
# Exercice 8.6
Soit un tableau T à deux dimensions [12, 8] préalablement rempli de valeurs numériques.
Écrire un algorithme qui recherche la plus grande valeur au sein de ce tableau.
```C#
Variables i, j, iMax, jMax en Numérique
Tableau T[12, 8] en Numérique
Le principe de la recherche dans un tableau à deux dimensions est strictement le même que dans un tableau à une dimension, ce qui ne doit pas nous étonner. La seule chose qui change, c'est qu'ici le balayage requiert deux boucles imbriquées, au lieu d'une seule.
Debut
...
iMax ← 0
jMax ← 0
Pour i ← 0 à 12
  Pour j ← 0 à 8
    Si T[i,j] > T[iMax,jMax] Alors
      iMax ← i
      jMax ← j
    FinSi
  j Suivant
i Suivant
Ecrire "Le plus grand élément est ", T[iMax, jMax]
Ecrire "Il se trouve aux indices ", iMax, "; ", jMax
Fin
```
Version commentée :
```C#
Variables i, j, iMax, jMax en Numérique
Tableau T[12, 8] en Numérique
Début
  // Initialisation des indices pour la plus grande valeur
  iMax ← 0
  jMax ← 0

  // Parcours du tableau à deux dimensions
  Pour i ← 0 à 11  // Parcours des lignes (indices de 0 à 11)
    Pour j ← 0 à 7   // Parcours des colonnes (indices de 0 à 7)
      Si T[i, j] > T[iMax, jMax] Alors
        iMax ← i   // Mettre à jour l'indice de la ligne de la plus grande valeur
        jMax ← j   // Mettre à jour l'indice de la colonne de la plus grande valeur
      FinSi
    j Suivant
  i Suivant

  // Affichage du résultat
  Ecrire "Le plus grand élément est ", T[iMax, jMax]
  Ecrire "Il se trouve aux indices ", iMax, "; ", jMax
Fin
```

# Exercice 8.7
Écrire un algorithme de jeu de dames très simplifié.  
L’ordinateur demande à l’utilisateur dans quelle case se trouve son pion (quelle ligne, quelle colonne). On met en place un contrôle de saisie afin de vérifier la validité des valeurs entrées.
Ensuite, on demande à l’utilisateur quel mouvement il veut effectuer : 0 (en haut à gauche), 1 (en haut à droite), 2 (en bas à gauche), 3 (en bas à droite).  
Si le mouvement est impossible (i.e. on sort du damier ), on le signale à l’utilisateur et on s’arrête là . Sinon, on déplace le pion et on affiche le damier résultant, en affichant un « O » pour une case vide et un « X » pour la case où se trouve le pion.
```C#
Variables i, j , posi, posj, i2, j2 en Entier
Variables Correct, MoveOK en Booléen
Tableau Damier[7, 7] en Booléen
Tableau Mouv[3, 1] en Entier
```
Le damier contenant un seul pion, on choisit de le coder à l'économie, en le représentant par un tableau de booléens à deux dimensions. Dans chacun des emplacements de ce damier, Faux signifie l'absence du pion, Vrai sa présence.

Par ailleurs, on emploie une méchante astuce, pas obligatoire, mais bien pratique dans beaucoup de situations. L'idée est de faire correspondre les choix possibles de l'utilisateur avec les mouvements du pion. On entre donc dans un tableau Mouv à deux dimensions, les déplacements du pion selon les quatre directions, en prenant soin que chaque ligne du tableau corresponde à une saisie de l’utilisateur. La première valeur étant le déplacement en i, la seconde le déplacement en j. Ceci nous épargnera par la suite de faire quatre fois les mêmes tests.
```C#
Debut
Choix 0 : pion en haut à droite
Mouv[0, 0] ← -1
Mouv[0, 1] ← -1
Choix 1 : pion en haut à droite
Mouv[1, 0] ← -1
Mouv[1, 1] ← 1
Choix 2 : pion en bas à gauche
Mouv[2, 0] ← 1
Mouv[2, 1] ← -1
Choix 3 : pion en bas à droite
Mouv[3, 0] ← 1
Mouv[3, 1] ← 1
```
Initialisation du damier; le pion n’est pour le moment nulle part
```C#
Pour i ← 0 à 7
  Pour j ← 0 à 7
    Damier[i, j] ← Faux
  j suivant
i suivant
```
Saisie de la coordonnée en i ("posi") avec contrôle de saisie
```C#
Correct ← Faux
TantQue Non Correct
  Ecrire "Entrez la ligne de votre pion: "
  Lire posi
  Si posi >= 0 et posi <= 7 Alors
    Correct ← vrai
  Finsi
Fintantque
```
Saisie de la coordonnée en j ("posj") avec contrôle de saisie
```C#
Correct ← Faux
TantQue Non Correct
  Ecrire "Entrez la colonne de votre pion: "
  Lire posj
    Si posj >= 0 et posj <= 7 Alors
      Correct ← Vrai
    Finsi
Fintantque
```
Positionnement du pion sur le damier virtuel.
```C#
Damier[posi, posj] ← Vrai
```
Saisie du déplacement, avec contrôle
```C#
Ecrire "Quel déplacement ?"
Ecrire " - 0: en haut à gauche"
Ecrire " - 1: en haut à droite"
Ecrire " - 2: en bas à gauche"
Ecrire " - 3: en bas à droite"
Correct ← Faux
TantQue Non Correct
  Lire Dep
  Si Dep >= 0 et Dep <= 3 Alors
    Correct ← Vrai
  FinSi
FinTantQue
```
i2 et j2 sont les futures coordonnées du pion. La variable booléenne MoveOK vérifie la validité de ce futur emplacement
```C#
i2 ← posi + Mouv[Dep, 0]
j2 ← posj + Mouv[Dep, 1]
MoveOK ← i2 >= 0 et i2 <= 7 et j2 >= 0 et j2 <= 7
```
Cas où le déplacement est valide
```C#
Si MoveOK Alors
  Damier[posi, posj] ← Faux
  Damier[i2, j2] ← Vrai
  ```
Affichage du nouveau damier
```C#
  Pour i ← 0 à 7
    Pour j ← 0 à 7
      Si Damier[i, j] Alors
        Ecrire " O ";
      Sinon
        Ecrire " X ";
      FinSi
    j suivant
    Ecrire ""
  i suivant
Sinon
```
Cas où le déplacement n’est pas valide
```C#
  Ecrire "Mouvement impossible"
FinSi
Fin
```
Version commentée :
```C#
Variables i, j , posi, posj, i2, j2 en Entier
Variables Correct, MoveOK en Booléen
Tableau Damier[7, 7] en Booléen  // Déclaration du damier avec des cases vides (Faux)
Tableau Mouv[3, 1] en Entier      // Déclaration des déplacements possibles du pion

// Initialisation des déplacements dans le tableau Mouv
Mouv[0, 0] ← -1   // Déplacement en haut à gauche : -1 pour la ligne, -1 pour la colonne
Mouv[0, 1] ← -1
Mouv[1, 0] ← -1   // Déplacement en haut à droite : -1 pour la ligne, +1 pour la colonne
Mouv[1, 1] ← 1
Mouv[2, 0] ← 1    // Déplacement en bas à gauche : +1 pour la ligne, -1 pour la colonne
Mouv[2, 1] ← -1
Mouv[3, 0] ← 1    // Déplacement en bas à droite : +1 pour la ligne, +1 pour la colonne
Mouv[3, 1] ← 1

// Initialisation du damier avec toutes les cases vides (Faux)
Pour i ← 0 à 7  // Parcours des lignes du damier
  Pour j ← 0 à 7  // Parcours des colonnes du damier
    Damier[i, j] ← Faux  // Initialise chaque case avec Faux (vide)
  j suivant
i suivant

// Demande à l'utilisateur de saisir la ligne du pion
Correct ← Faux
TantQue Non Correct
  Ecrire "Entrez la ligne de votre pion: "
  Lire posi
  Si posi >= 0 et posi <= 7 Alors  // Vérifie si la ligne est valide (entre 0 et 7)
    Correct ← vrai  // Si la saisie est correcte, on sort de la boucle
  Finsi
Fintantque

// Demande à l'utilisateur de saisir la colonne du pion
Correct ← Faux
TantQue Non Correct
  Ecrire "Entrez la colonne de votre pion: "
  Lire posj
  Si posj >= 0 et posj <= 7 Alors  // Vérifie si la colonne est valide (entre 0 et 7)
    Correct ← Vrai  // Si la saisie est correcte, on sort de la boucle
  Finsi
Fintantque

// Positionne le pion sur le damier aux coordonnées saisies
Damier[posi, posj] ← Vrai  // Met le pion à la position (posi, posj) en marquant la case comme occupée

// Demande à l'utilisateur de choisir un déplacement
Ecrire "Quel déplacement ?"
Ecrire " - 0: en haut à gauche"
Ecrire " - 1: en haut à droite"
Ecrire " - 2: en bas à gauche"
Ecrire " - 3: en bas à droite"
Correct ← Faux
TantQue Non Correct
  Lire Dep  // L'utilisateur choisit le type de déplacement (0 à 3)
  Si Dep >= 0 et Dep <= 3 Alors  // Vérifie que le choix est valide
    Correct ← Vrai  // Si la saisie est correcte, on sort de la boucle
  FinSi
FinTantQue

// Calcul des nouvelles coordonnées après le déplacement
i2 ← posi + Mouv[Dep, 0]  // Calcule la nouvelle ligne en fonction du déplacement choisi
j2 ← posj + Mouv[Dep, 1]  // Calcule la nouvelle colonne en fonction du déplacement choisi

// Vérification si le mouvement reste dans les limites du damier
MoveOK ← i2 >= 0 et i2 <= 7 et j2 >= 0 et j2 <= 7  // Vérifie si le déplacement est valide (les indices doivent être entre 0 et 7)

// Si le mouvement est valide
Si MoveOK Alors
  Damier[posi, posj] ← Faux  // Vide la case initiale (pion déplacé)
  Damier[i2, j2] ← Vrai  // Place le pion à la nouvelle position (i2, j2)

  // Affiche le damier après le déplacement
  Pour i ← 0 à 7  // Parcours des lignes du damier
    Pour j ← 0 à 7  // Parcours des colonnes du damier
      Si Damier[i, j] Alors  // Si la case est occupée par un pion
        Ecrire " X ";  // Affiche "X" pour un pion
      Sinon
        Ecrire " O ";  // Affiche "O" pour une case vide
      FinSi
    j suivant
    Ecrire ""  // Saut de ligne après chaque ligne du damier
  i suivant
Sinon
  // Si le mouvement est invalide (sort du damier), affiche un message d'erreur
  Ecrire "Mouvement impossible"
FinSi

Fin  // Fin de l'algorithme
```