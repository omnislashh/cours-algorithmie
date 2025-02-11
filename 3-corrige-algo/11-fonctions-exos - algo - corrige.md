# Exercice 11.1
Écrivez une fonction qui renvoie la somme de cinq nombres fournis en argument.
```C#
Fonction Sum(a, b, c, d, e) en Numérique
  Renvoyer a + b + c + d + e
FinFonction
```

# Exercice 11.2
Écrivez une fonction qui renvoie le nombre de voyelles contenues dans une chaîne de caractères passée en argument. Au passage, notez qu'une fonction a tout à fait le droit d'appeler une autre fonction.
```C#
Fonction NbVoyelles(Mot en Caractère) en Numérique
Variables i, nb en Numérique
nb ← 0
Pour i ← 1 à Len(Mot)
  Si Trouve("aeiouy", Mid(Mot, i, 1)) <> 0 Alors
    nb ← nb + 1
  FinSi
i suivant
Renvoyer nb
FinFonction
```
# Exercice 11.3
Réécrivez la fonction Trouve, vue précédemment, à l’aide des fonctions Mid et Len (comme quoi, Trouve, à la différence de Mid et Len, n’est pas une fonction indispensable dans un langage).
```C#
Fonction Trouve(a en Caractère, b en Caractère) en Numérique
Variable i en Numérique
Début
i ← 1
TantQue i < Len(a) - Len(b) et b <> Mid(a, i, Len(b))
  i ← i + 1
FinTantQue
Si b <> Mid(a, i, Len(b)) Alors
  Renvoyer 0
Sinon
 
FinSi
Renvoyer i
FinFonction
```
# Exercice 11.4
Ecrivez une fonction qui purge une chaîne d'un caractère, la chaîne comme le caractère étant passés en argument. Si le caractère spécifié ne fait pas partie de la chaîne, celle-ci devra être retournée intacte. Par exemple :  
```C#
Purge("Bonjour","o") renverra "Bnjur"
Purge("J'ai horreur des espaces"," ") renverra "J'aihorreurdesespaces"
Purge("Moi, je m'en fous", "y") renverra "Moi, je m'en fous"
```

```C#
Fonction PurgeSimple(a en Caractère, b en Caractère) en Caractère
Variable Sortie en Caractère
Variable i en Numérique
Début
Sortie ← ''
Pour i ← 1 à Len(a)
   Si Mid(a, i, 1) <> b Alors
      Sortie ← Sortie & Mid(a, i, 1)
   FinSi
i suivant
Renvoyer Sortie
FinFonction
```
Version commentée :
```C#
Fonction PurgeSimple(a en Caractère, b en Caractère) en Caractère
  Variable Sortie en Caractère  // Variable pour stocker la chaîne résultante
  Variable i en Numérique  // Compteur pour parcourir la chaîne

  Début
    Sortie ← ''  // Initialisation de la chaîne résultante vide

    // Parcours de la chaîne a
    Pour i ← 1 à Len(a)  // Pour chaque caractère de la chaîne a
      // Si le caractère courant n'est pas égal à b
      Si Mid(a, i, 1) <> b Alors
        Sortie ← Sortie & Mid(a, i, 1)  // Ajoute le caractère courant à la chaîne Sortie
      FinSi
    i suivant

    Renvoyer Sortie  // Retourne la chaîne modifiée
  FinFonction
```
# Exercice 11.5
Même question que précédement, mais cette fois, la fonction Purgebis doit pouvoir recevoir un nombre quelconque de caractères à supprimer en argument. Par exemple, Purgebis(phrase, "aeiouy") enlèvera toutes les voyelles que contient la variable phrase.

```C#
Fonction PurgeMultiple(a en Caractère, b en Caractère) en Caractère
Variable Sortie en Caractère
Variable i en Numérique
Début
Sortie ← ''
Pour i ← 1 à Len(a)
   Si Trouve(b, Mid(a, i, 1)) = 0 Alors
      Sortie ← Sortie & Mid(a, i, 1)
   FinSi
i suivant
Renvoyer Sortie
FinFonction
```

# Exercice 11.6
Ecrire un traitement qui effectue le tri d'un tableau envoyé en argument (on considère que le code appelant devra également fournir le nombre d'éléments du tableau).

```C#
Procédure TriTableau(T[] en Numérique par Référence, n en Numérique par Valeur)
Variables i, posmini, temp en Numérique
Début
Pour i ← 0 à n-2
   posmini ← i
   Pour j ← i + 1 à n-1
      Si T[j] < T[posmini] Alors
         posmini ← j
      Finsi
   j suivant
   temp ← T[posmini]
   T[posmini] ← T[i]
   T[i] ← temp
i suivant
FinProcédure
```
Version commentée :
```C#
Procédure TriTableau(T[] en Numérique par Référence, n en Numérique par Valeur)
  Variables i, posmini, temp en Numérique  // Déclaration des variables

  Début
    // Boucle extérieure pour parcourir le tableau
    Pour i ← 0 à n-2  // On parcourt du premier élément jusqu'à l'avant-dernier
      posmini ← i  // On suppose que l'élément courant est le plus petit

      // Boucle intérieure pour trouver le plus petit élément à partir de i
      Pour j ← i + 1 à n-1  // On parcourt les éléments suivants
        Si T[j] < T[posmini] Alors  // Si on trouve un élément plus petit
          posmini ← j  // On met à jour la position du plus petit élément
        Finsi
      j suivant

      // Échange des éléments
      temp ← T[posmini]  // On sauvegarde la valeur du plus petit élément
      T[posmini] ← T[i]  // On met l'élément courant à la position du plus petit
      T[i] ← temp  // On place le plus petit élément à la position initiale

    i suivant  // On passe à l'élément suivant de la boucle extérieure
  FinProcédure
```
# Exercice 11.7
Ecrire un traitement qui informe si un un tableau envoyé en argument est formé ou non d'éléments tous rangés en ordre croissant.
```C#
Fonction TableauCroissant(T[] en Numérique, n en Numérique) en Booléen
Variable i en Numérique
Variable Flag en Booléen
Début
Flag ← Vrai
i ← 0
TantQue Flag et i < n-1
   Flag ← T[i] < T[i+1]
   i ← i+1
FinTantQue
Renvoyer Flag
FinFonction
```
Version commentée :
```C#
Fonction TableauCroissant(T[] en Numérique, n en Numérique) en Booléen
  Variable i en Numérique
  Variable Flag en Booléen
  Début
    Flag ← Vrai  // On suppose initialement que le tableau est croissant
    i ← 0  // On commence à la première position du tableau

    // Tant que le tableau n'est pas encore vérifié et qu'on n'a pas atteint la fin
    TantQue Flag et i < n-1  // La condition de sortie est qu'on a vérifié toute la liste
      Flag ← T[i] < T[i+1]  // Si un élément est supérieur ou égal à l'élément suivant, on arrête
      i ← i + 1  // On passe à l'élément suivant
    FinTantQue

    // Si la boucle se termine, on renvoie le résultat de la vérification
    Renvoyer Flag  // Retourne Vrai si tous les éléments sont en ordre croissant, sinon Faux
  FinFonction
```

# Exercice 11.8
Ecrire un traitement qui inverse le contenu de deux valeurs passées en argument.  
```C#
Procédure Inversion(X en Numérique par Référence, Y en Numérique par Référence)
Variable Temp en Numérique
Début
Temp ← X
X ← Y
Y ← Temp
FinProcédure
```

# Exercice 11.9
reprendre l'exercice 11.6, mais cette fois la procédure comprendra un troisième paramètre, de type booléen. VRAI, celui-ci indiquera que le tri devra être effectué dans l'ordre croissant, FAUX dans l'ordre décroissant.

```C#
Procédure TriTableau(T[] en Numérique par Référence, n en Numérique par Valeur, Croissant en Booléen par Valeur)
Variables i, pos, temp en Numérique
Début
Pour i ← 0 à n-2
   pos ← i
   Pour j ← i + 1 à n-1
      Si Croissant Alors
         Si T[j] < T[pos] Alors
            pos ← j
         Finsi
      Sinon
         Si T[j] > T[pos] Alors
            pos ← j
         Finsi
      Finsi
   j suivant
   temp ← T[pos]
   T[pos] ← T[i]
   T[i] ← temp
i suivant
FinProcédure
```
Version commentée :
```C#
Procédure TriTableau(T[] en Numérique par Référence, n en Numérique par Valeur, Croissant en Booléen par Valeur)
  Variables i, pos, temp en Numérique
  Début
    Pour i ← 0 à n-2  // On parcourt tout le tableau, sauf le dernier élément
      pos ← i  // On suppose que l'élément à la position i est le plus petit (ou le plus grand, selon l'ordre)
      
      Pour j ← i + 1 à n-1  // On parcourt les éléments suivants
        Si Croissant Alors  // Si le tri est croissant
          Si T[j] < T[pos] Alors  // Si l'élément actuel est plus petit que l'élément de la position minimale
            pos ← j  // On met à jour la position minimale
          Finsi
        Sinon  // Si le tri est décroissant
          Si T[j] > T[pos] Alors  // Si l'élément actuel est plus grand que l'élément de la position maximale
            pos ← j  // On met à jour la position maximale
          Finsi
        Finsi
      j suivant
      
      // Une fois le plus petit (ou le plus grand) élément trouvé, on l'échange avec l'élément à la position i
      temp ← T[pos]  // On garde la valeur à la position trouvée
      T[pos] ← T[i]  // On remplace l'élément à la position i
      T[i] ← temp  // On place la valeur trouvée dans la position i
    i suivant
  FinProcédure
```

# Exercice 11.10
On va à présent réaliser une application complète, en utilisant une architecture sous forme de sous-procédures et de fonction. Cette application a pour tâche de générer des grilles de Sudoku. Une telle grille est formée de 81 cases (9 x 9), contenant un chiffre entre 1 et 9, et dans laquelle aucune ligne, aucune colonne et aucune "sous-grille" de 3x3, ne contient deux fois le même chiffre.
Pour parvenir à nos fins, on va utiliser une méthode particulièrement barbare et inefficace : la génération aléatoire des 81 valeurs de la grille. On vérifiera alors que la grille satisfait aux critères ; si tel n'est pas le cas... on recommence la génération jusqu'à ce que la grille convienne. En pratique, la probabilité de générer une grille adéquate est si faible que cette méthode prendra sans doute beaucoup de temps, mais passons.  
Tout le truc est de piger que vérifier que les neuf cases d'une ligne, d'une colonne, ou d'une sous-grille, sont toutes différentes, c'est en réalité du pareil au même. On va donc factoriser le code procédant à cette vérification sous la forme d'une fonction booléenne TousDifférents, à qui on passera un tableau de 9 valeurs en argument. La fonction renverra donc VRAI si les 9 valeurs du tableau sont toutes différentes, et FAUX sinon.  
     a. Ecrire la fonction TousDifferents   
Maintenant, bien que ce ne soit pas indispensable (car ce code n'est pas spécialement répété), on choisit également par pure commodité de confier la génération au hasard de la grille de 81 cases à un module dédié, RemplitGrille. (ce module, à qui on passera notre tableau de 81 cases en argument, est forcément une procédure, puisqu'il a pour tâche d'en modifier les 81 valeurs).  
     b. Ecrire la procédure RemplitGrille   
Il faut à présent vérifier que l'ensemble des lignes correspond à la condition voulue, à savoir qu'il n'y existe pas de doublons. On réalise donc une fonction, VerifLignes, qui va vérifier les neuf lignes de notre grille une par une (en utilisant bien sûr la fonction TousDifférents, déjà écrite) et renvoyer VRAI si toutes les lignes sont correctes, FAUX dans le cas contraire.  
     c. Ecrire la fonction Veriflignes   
On procède alors de même avec une fonction chargée de vérifir les colonnes, VérifColonnes.  
     d. Ecrire la fonction Verifcolonnes   
...et encore à nouveau, avec cette fois la vrification des neuf "sous-grilles" 3x3.  
     e. Ecrire la fonction VerifSousGrilles   
Il ne reste plus qu'à écrire la procédure principale, et l'affaire est dans le sac !  
     f. Ecrire la procédure principale de l'application  
### Fonction TousDifférents
```C#
Aucune difficulté particulière pour ce module. Il suffit de respecter le cahier des charges :
Fonction TousDifférents(T[8] en Num) en Booléen
Pour i ← 0 à 7
   Pour j ← i+1 à 8
      Si T[i] = T[j] Alors
         Renvoyer Faux
      FinSi
   j suivant
i suivant
Renvoyer Vrai FinFonction
``` 
Version commentée :
```C#
Fonction TousDifferents(T[8] en Num) en Booléen
    // Parcours des éléments du tableau pour comparer chaque élément à tous les autres
    Pour i ← 0 à 7  // Début de la première boucle pour l'élément i
        Pour j ← i+1 à 8  // Boucle interne pour comparer l'élément i avec tous les éléments suivants (pour éviter les doublons)
            Si T[i] = T[j] Alors  // Si un élément est égal à un autre, cela signifie qu'il y a un doublon
                Renvoyer Faux  // Si doublon trouvé, retourner Faux immédiatement
            FinSi
        j suivant  // Passage à l'élément suivant j
    i suivant  // Passage à l'élément suivant i
    Renvoyer Vrai  // Si aucun doublon n'a été trouvé, retourner Vrai
FinFonction
```

### Procédure RemplitGrille
Là non plus, rien à signaler. On peut même dire que c'est tout ballot.
```C#
Procédure RemplitGrille(T[8, 8] en Num par Référence)
Pour i ← 0 à 8
   Pour j ← 0 à 8
      T[i, j] ← Ent(Alea()*9)+1
   j suivant
i suivant FinProcédure
```
Version commentée :
```C#
Procédure RemplitGrille(T[8, 8] en Num par Référence)
    // Remplir la grille avec des valeurs aléatoires entre 1 et 9
    Pour i ← 0 à 8  // Parcours de toutes les lignes de la grille
        Pour j ← 0 à 8  // Parcours de toutes les colonnes de la grille
            T[i, j] ← Ent(Alea() * 9) + 1  // Remplir chaque case de la grille avec un nombre aléatoire entre 1 et 9
        j suivant  // Passage à la colonne suivante
    i suivant  // Passage à la ligne suivante
FinProcédure
```
### Fonction VerifLignes
Là, tout le truc consiste à tronçonner notre tableau en 9 lignes successives. Et à chaque fois, on envoie la ligne à la fonction TousDifferents. Si celle-ci retourne FAUX, la fonction VerifLignes, elle aussi, s'interrompt en renvoyant faux.
```C#
Fonction VerifLignes(Grille[8, 8] en Num) en Booléen
Tableau Ligne[8] en Numérique
Pour i ← 0 à 8
   Pour j ← 0 à 8
      Ligne[j] ← Grille[i, j]
   j suivant
   Si Non TousDifferents(Ligne[]) Alors
      Renvoyer Faux
   FinSi
i suivant
Renvoyer Vrai
FinFonction
```
Version commentée :
```C#
Fonction VerifLignes(Grille[8, 8] en Num) en Booléen
    Tableau Ligne[8] en Numérique  // Déclaration d'un tableau pour stocker les valeurs de chaque ligne
    Pour i ← 0 à 8  // Parcours des lignes de la grille
        Pour j ← 0 à 8  // Parcours des colonnes de la grille pour remplir le tableau "Ligne"
            Ligne[j] ← Grille[i, j]  // Remplir le tableau Ligne avec les valeurs de la ligne i
        j suivant  // Passage à la colonne suivante
        Si Non TousDifferents(Ligne[]) Alors  // Vérifier si la ligne contient des doublons
            Renvoyer Faux  // Si des doublons sont trouvés, retourner Faux
        FinSi
    i suivant  // Passage à la ligne suivante
    Renvoyer Vrai  // Si toutes les lignes sont valides, retourner Vrai
FinFonction
```

### Fonction VerifColonnes
Bon, une fois que le précédent est fait, c'est presque du copier-coller à un détail près, et c'est fingers in ze nose.
```C#
Fonction VerifColonnes(Grille[8, 8] en Num) en Booléen
Tableau Colonne[8] en Num
Pour j ← 0 à 8
   Pour i ← 0 à 8
      Colonne[i] ← Grille[i, j]
   i suivant
   Si Non TousDifferents(Colonne[]) Alors
      Renvoyer Faux
   FinSi
j suivant
Renvoyer Vrai
FinFonction
```
Version commentée :
```C#
Fonction VerifColonnes(Grille[8, 8] en Num) en Booléen
    Tableau Colonne[8] en Num  // Déclaration d'un tableau pour stocker les valeurs de chaque colonne
    Pour j ← 0 à 8  // Parcours des colonnes de la grille
        Pour i ← 0 à 8  // Parcours des lignes de la grille pour remplir le tableau "Colonne"
            Colonne[i] ← Grille[i, j]  // Remplir le tableau Colonne avec les valeurs de la colonne j
        i suivant  // Passage à la ligne suivante
        Si Non TousDifferents(Colonne[]) Alors  // Vérifier si la colonne contient des doublons
            Renvoyer Faux  // Si des doublons sont trouvés, retourner Faux
        FinSi
    j suivant  // Passage à la colonne suivante
    Renvoyer Vrai  // Si toutes les colonnes sont valides, retourner Vrai
FinFonction
```

### Fonction VerifSousGrilles
Le mécanisme fondamental est évidemment le même que pour les deux fonctions précédentes. Le truc pénible, c'est de réaliser le découpage des 9 carrés de 3x3. Première solution (barbare) on fait plein d'affectations à la main. Deuxième solution (fûtée) on comprend que tout cela obéit à un schéma régulier, et on s'en sort avec une jolie série de boucles imbriquées.
```C#
Fonction VerifSousGrilles(Grille[8, 8] en Num) en Booléen
Tableau SousGrille[8] en Num
Pour ancrei ← 0 à 6 pas 3
   Pour ancrej ← 0 à 6 pas 3
      Pour decali ← 0 à 2
         Pour decalj ← 0 à 2
            SousGrille[decali*3 + decalj] ← Grille[ancrei + decali, ancrej + decalj]
         decalj suivant
      decali suivant
      Si Non TousDifferents(SousGrille[]) Alors
         Renvoyer Faux
      FinSi
   ancrej suivant
ancrei suivant
Renvoyer Vrai
FinFonction
```
Version commentée :
```C#
Fonction VerifSousGrilles(Grille[8, 8] en Num) en Booléen
    Tableau SousGrille[8] en Num  // Déclaration d'un tableau pour stocker les valeurs de chaque sous-grille 3x3
    Pour ancrei ← 0 à 6 pas 3  // Parcours des lignes de la grille par blocs de 3 (0, 3, 6)
        Pour ancrej ← 0 à 6 pas 3  // Parcours des colonnes de la grille par blocs de 3 (0, 3, 6)
            Pour decali ← 0 à 2  // Parcours des lignes de la sous-grille 3x3
                Pour decalj ← 0 à 2  // Parcours des colonnes de la sous-grille 3x3
                    SousGrille[decali * 3 + decalj] ← Grille[ancrei + decali, ancrej + decalj]  // Remplir le tableau SousGrille avec les valeurs de la sous-grille
                decalj suivant  // Passage à la colonne suivante dans la sous-grille
            decali suivant  // Passage à la ligne suivante dans la sous-grille
            Si Non TousDifferents(SousGrille[]) Alors  // Vérifier si la sous-grille contient des doublons
                Renvoyer Faux  // Si des doublons sont trouvés, retourner Faux
            FinSi
        ancrej suivant  // Passage à la sous-grille suivante
    ancrei suivant  // Passage à la ligne suivante de sous-grilles
    Renvoyer Vrai  // Si toutes les sous-grilles sont valides, retourner Vrai
FinFonction
```
### Procédure principale
Avec ce qu'on a réalisé précédemment, c'est de la gnognote. On fait simplement générer la grille par la procédure idoine, et on recommence aussi longtemps que l'une des trois vérifications au moins nous dit que le résultat cloche. Le tout tient en cinq lignes.
```C#
Procédure principale()
Tableau Sudok[8, 8] en Num
Appeler RemplitGrille(Sudok[])
Tant Que Non VerifLignes(Sudok[]) ou Non VerifColonnes(Sudok[]) ou Non VerifSousGrilles(Sudok[])
   Appeler RemplitGrille(Sudok[])
FinTantQue>
FinProcédure
```
Version commentée :
```C#
Procédure principale()
    Tableau Sudok[8, 8] en Num  // Déclaration d'un tableau pour stocker la grille de Sudoku
    Appeler RemplitGrille(Sudok[])  // Remplir la grille avec des valeurs aléatoires entre 1 et 9
    Tant Que Non VerifLignes(Sudok[]) ou Non VerifColonnes(Sudok[]) ou Non VerifSousGrilles(Sudok[])  // Tant que la grille n'est pas valide
        Appeler RemplitGrille(Sudok[])  // Regénérer une nouvelle grille
    FinTantQue  // Lorsque la grille est valide, sortir de la boucle
FinProcédure  // Fin de la procédure principale
```