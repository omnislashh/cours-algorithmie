# Exercice 11.1
Écrivez une fonction qui renvoie la somme de cinq nombres fournis en argument.
```
Fonction Sum(a, b, c, d, e) en Numérique
  Renvoyer a + b + c + d + e
FinFonction
```

# Exercice 11.2
Écrivez une fonction qui renvoie le nombre de voyelles contenues dans une chaîne de caractères passée en argument. Au passage, notez qu'une fonction a tout à fait le droit d'appeler une autre fonction.
```
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
```
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
```
Purge("Bonjour","o") renverra "Bnjur"
Purge("J'ai horreur des espaces"," ") renverra "J'aihorreurdesespaces"
Purge("Moi, je m'en fous", "y") renverra "Moi, je m'en fous"
```

```
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
# Exercice 11.5
Même question que précédement, mais cette fois, la fonction Purgebis doit pouvoir recevoir un nombre quelconque de caractères à supprimer en argument. Par exemple, Purgebis(phrase, "aeiouy") enlèvera toutes les voyelles que contient la variable phrase.

```
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

```
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

# Exercice 11.7
Ecrire un traitement qui informe si un un tableau envoyé en argument est formé ou non d'éléments tous rangés en ordre croissant.
```
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

# Exercice 11.8
Ecrire un traitement qui inverse le contenu de deux valeurs passées en argument.  
```
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

```
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
```
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

### Procédure RemplitGrille
Là non plus, rien à signaler. On peut même dire que c'est tout ballot.
```
Procédure RemplitGrille(T[8, 8] en Num par Référence)
Pour i ← 0 à 8
   Pour j ← 0 à 8
      T[i, j] ← Ent(Alea()*9)+1
   j suivant
i suivant FinProcédure
```

### Fonction VerifLignes
Là, tout le truc consiste à tronçonner notre tableau en 9 lignes successives. Et à chaque fois, on envoie la ligne à la fonction TousDifferents. Si celle-ci retourne FAUX, la fonction VerifLignes, elle aussi, s'interrompt en renvoyant faux.
```
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

### Fonction VerifColonnes
Bon, une fois que le précédent est fait, c'est presque du copier-coller à un détail près, et c'est fingers in ze nose.
```
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

### Fonction VerifSousGrilles
Le mécanisme fondamental est évidemment le même que pour les deux fonctions précédentes. Le truc pénible, c'est de réaliser le découpage des 9 carrés de 3x3. Première solution (barbare) on fait plein d'affectations à la main. Deuxième solution (fûtée) on comprend que tout cela obéit à un schéma régulier, et on s'en sort avec une jolie série de boucles imbriquées.
```
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

### Procédure principale
Avec ce qu'on a réalisé précédemment, c'est de la gnognote. On fait simplement générer la grille par la procédure idoine, et on recommence aussi longtemps que l'une des trois vérifications au moins nous dit que le résultat cloche. Le tout tient en cinq lignes.
```
Procédure principale()
Tableau Sudok[8, 8] en Num
Appeler RemplitGrille(Sudok[])
Tant Que Non VerifLignes(Sudok[]) ou Non VerifColonnes(Sudok[]) ou Non VerifSousGrilles(Sudok[])
   Appeler RemplitGrille(Sudok[])
FinTantQue>
FinProcédure
```