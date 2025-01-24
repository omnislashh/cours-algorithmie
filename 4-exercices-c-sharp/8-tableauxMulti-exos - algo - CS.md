# Exercice 8.1
Écrivez un algorithme remplissant un tableau de 6 sur 13, avec des zéros.

```
Tableau Truc[5, 12] en Entier
Debut
Pour i ← 0 à 5
  Pour j ← 0 à 12
    Truc[i, j] ← 0
  j Suivant
i Suivant
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le remplissage du tableau :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_FillArray.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice8_1 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[,] array; // Tableau à deux dimensions pour stocker les valeurs

    void Start()
    {
        // Initialiser le tableau avec des zéros
        array = new int[6, 13];

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void FillArray()
    {
        // Remplir le tableau avec des zéros
        for (int i = 0; i < 6; i++)
        {
            for (int j = 0; j < 13; j++)
            {
                array[i, j] = 0;
            }
        }

        // Afficher le tableau rempli
        string result = "Tableau rempli avec des zéros :\n";
        for (int i = 0; i < 6; i++)
        {
            for (int j = 0; j < 13; j++)
            {
                result += array[i, j] + " ";
            }
            result += "\n";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ArrayFiller).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le remplissage du tableau (Button_FillArray) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (ArrayFiller) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice8_1 -> FillArray.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Déclaration de la variable privée pour stocker le tableau à deux dimensions :
```c#

private int[,] array;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    array = new int[6, 13];
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode FillArray pour remplir le tableau avec des zéros et afficher le résultat :

```c#
public void FillArray()
{
    for (int i = 0; i < 6; i++)
    {
        for (int j = 0; j < 13; j++)
        {
            array[i, j] = 0;
        }
    }

    string result = "Tableau rempli avec des zéros :\n";
    for (int i = 0; i < 6; i++)
    {
        for (int j = 0; j < 13; j++)
        {
            result += array[i, j] + " ";
        }
        result += "\n";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui remplit un tableau à deux dimensions de taille 6x13 avec des zéros et affiche le tableau rempli dans un Text.

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
```
Cet algorithme remplit un tableau de la manière suivante:
X[0, 0] = 1
X[0, 1] = 2
X[0, 2] = 3
X[1, 0] = 4
X[1, 1] = 5
X[1, 2] = 6
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.
```

Analyse de l'algorithme
Déclaration du tableau et des variables :
```
Tableau X[1, 2] en Entier : Déclare un tableau X de dimensions 1x2.
Variables i, j, val en Entier : Déclare les variables i, j, et val de type entier.
Initialisation de la variable val :

Val ← 1 : Initialise val à 1.
Première boucle Pour :

Pour i ← 0 à 1 : Boucle de i allant de 0 à 1.
Pour j ← 0 à 2 : Boucle de j allant de 0 à 2.
X[i, j] ← Val : Assigne la valeur de val à X[i, j].
Val ← Val + 1 : Incrémente val de 1.
j Suivant : Fin de la boucle interne.
i Suivant : Fin de la boucle externe.
Deuxième boucle Pour :

Pour i ← 0 à 1 : Boucle de i allant de 0 à 1.
Pour j ← 0 à 2 : Boucle de j allant de 0 à 2.
Ecrire X[i, j] : Affiche la valeur de X[i, j].
j Suivant : Fin de la boucle interne.
i Suivant : Fin de la boucle externe.
Suivi des étapes
Initialisation :

val = 1
Première boucle Pour :

i = 0
j = 0
X[0, 0] = 1
val = 2
j = 1
X[0, 1] = 2
val = 3
j = 2
X[0, 2] = 3
val = 4
i = 1
j = 0
X[1, 0] = 4
val = 5
j = 1
X[1, 1] = 5
val = 6
j = 2
X[1, 2] = 6
val = 7
Deuxième boucle Pour :

i = 0
j = 0
Ecrire X[0, 0] = 1
j = 1
Ecrire X[0, 1] = 2
j = 2
Ecrire X[0, 2] = 3
i = 1
j = 0
Ecrire X[1, 0] = 4
j = 1
Ecrire X[1, 1] = 5
j = 2
Ecrire X[1, 2] = 6
Résultat final
Le tableau X sera rempli et affiché comme suit :


1 2 3
4 5 6
```
En suivant ces étapes, nous voyons que l'algorithme remplit le tableau X avec les valeurs de 1 à 6 dans l'ordre croissant, puis affiche ces valeurs.

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
```
Cet algorithme remplit un tableau de la manière suivante:
X[0, 0] = 1
X[1, 0] = 4
X[0, 1] = 2
X[1, 1] = 5
X[0, 2] = 3
X[1, 2] = 6
Il écrit ensuite ces valeurs à l’écran, dans cet ordre.
```
```
Analyse de l'algorithme
Déclaration du tableau et des variables :

Tableau X[1, 2] en Entier : Déclare un tableau X de dimensions 1x2.
Variables i, j, val en Entier : Déclare les variables i, j, et val de type entier.
Initialisation de la variable val :

Val ← 1 : Initialise val à 1.
Première boucle Pour :

Pour i ← 0 à 1 : Boucle de i allant de 0 à 1.
Pour j ← 0 à 2 : Boucle de j allant de 0 à 2.
X[i, j] ← Val : Assigne la valeur de val à X[i, j].
Val ← Val + 1 : Incrémente val de 1.
j Suivant : Fin de la boucle interne.
i Suivant : Fin de la boucle externe.
Deuxième boucle Pour :

Pour j ← 0 à 2 : Boucle de j allant de 0 à 2.
Pour i ← 0 à 1 : Boucle de i allant de 0 à 1.
Ecrire X[i, j] : Affiche la valeur de X[i, j].
i Suivant : Fin de la boucle interne.
j Suivant : Fin de la boucle externe.
Suivi des étapes
Initialisation :

val = 1
Première boucle Pour :

i = 0
j = 0
X[0, 0] = 1
val = 2
j = 1
X[0, 1] = 2
val = 3
j = 2
X[0, 2] = 3
val = 4
i = 1
j = 0
X[1, 0] = 4
val = 5
j = 1
X[1, 1] = 5
val = 6
j = 2
X[1, 2] = 6
val = 7
Deuxième boucle Pour :

j = 0
i = 0
Ecrire X[0, 0] = 1
i = 1
Ecrire X[1, 0] = 4
j = 1
i = 0
Ecrire X[0, 1] = 2
i = 1
Ecrire X[1, 1] = 5
j = 2
i = 0
Ecrire X[0, 2] = 3
i = 1
Ecrire X[1, 2] = 6
Résultat final
Le tableau X sera rempli et affiché comme suit :


1 4
2 5
3 6
```
En suivant ces étapes, nous voyons que l'algorithme remplit le tableau X avec les valeurs de 1 à 6 dans l'ordre croissant, puis affiche ces valeurs colonne par colonne.

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
```
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
```
Analyse de l'algorithme
Déclaration du tableau et des variables :

Tableau T[3, 1] en Entier : Déclare un tableau T de dimensions 3x1.
Variables k, m en Entier : Déclare les variables k et m de type entier.
Première boucle Pour :

Pour k ← 0 à 3 : Boucle de k allant de 0 à 3.
Pour m ← 0 à 1 : Boucle de m allant de 0 à 1.
T[k, m] ← k + m : Assigne la valeur k + m à T[k, m].
m Suivant : Fin de la boucle interne.
k Suivant : Fin de la boucle externe.
Deuxième boucle Pour :

Pour k ← 0 à 3 : Boucle de k allant de 0 à 3.
Pour m ← 0 à 1 : Boucle de m allant de 0 à 1.
Ecrire T[k, m] : Affiche la valeur de T[k, m].
m Suivant : Fin de la boucle interne.
k Suivant : Fin de la boucle externe.
Suivi des étapes
Première boucle Pour :

k = 0
m = 0
T[0, 0] = 0 + 0 = 0
m = 1
T[0, 1] = 0 + 1 = 1
k = 1
m = 0
T[1, 0] = 1 + 0 = 1
m = 1
T[1, 1] = 1 + 1 = 2
k = 2
m = 0
T[2, 0] = 2 + 0 = 2
m = 1
T[2, 1] = 2 + 1 = 3
k = 3
m = 0
T[3, 0] = 3 + 0 = 3
m = 1
T[3, 1] = 3 + 1 = 4
Deuxième boucle Pour :

k = 0
m = 0
Ecrire T[0, 0] = 0
m = 1
Ecrire T[0, 1] = 1
k = 1
m = 0
Ecrire T[1, 0] = 1
m = 1
Ecrire T[1, 1] = 2
k = 2
m = 0
Ecrire T[2, 0] = 2
m = 1
Ecrire T[2, 1] = 3
k = 3
m = 0
Ecrire T[3, 0] = 3
m = 1
Ecrire T[3, 1] = 4
Résultat final
Le tableau T sera rempli et affiché comme suit :


0 1
1 2
2 3
3 4
```
En suivant ces étapes, nous voyons que l'algorithme remplit le tableau T avec les valeurs de k + m et affiche ces valeurs ligne par ligne.


# Exercice 8.5
Mêmes questions, en remplaçant la ligne :
```
T[k, m] ← k + m
par
T[k, m] ← 2 * k + [m + 1]
puis par :
T[k, m] ← [k + 1] + 4 * m
```

```
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
```
Analyse de l'algorithme
Déclaration du tableau et des variables :

Tableau T[3, 1] en Entier : Déclare un tableau T de dimensions 3x1.
Variables k, m en Entier : Déclare les variables k et m de type entier.
Première boucle Pour :

Pour k ← 0 à 3 : Boucle de k allant de 0 à 3.
Pour m ← 0 à 1 : Boucle de m allant de 0 à 1.
T[k, m] ← 2 * k + [m + 1] : Assigne la valeur 2 * k + (m + 1) à T[k, m].
m Suivant : Fin de la boucle interne.
k Suivant : Fin de la boucle externe.
Deuxième boucle Pour :

Pour k ← 0 à 3 : Boucle de k allant de 0 à 3.
Pour m ← 0 à 1 : Boucle de m allant de 0 à 1.
Ecrire T[k, m] : Affiche la valeur de T[k, m].
m Suivant : Fin de la boucle interne.
k Suivant : Fin de la boucle externe.
Suivi des étapes pour la première modification
Première boucle Pour :

k = 0
m = 0
T[0, 0] = 2 * 0 + (0 + 1) = 1
m = 1
T[0, 1] = 2 * 0 + (1 + 1) = 2
k = 1
m = 0
T[1, 0] = 2 * 1 + (0 + 1) = 3
m = 1
T[1, 1] = 2 * 1 + (1 + 1) = 4
k = 2
m = 0
T[2, 0] = 2 * 2 + (0 + 1) = 5
m = 1
T[2, 1] = 2 * 2 + (1 + 1) = 6
k = 3
m = 0
T[3, 0] = 2 * 3 + (0 + 1) = 7
m = 1
T[3, 1] = 2 * 3 + (1 + 1) = 8
Deuxième boucle Pour :

k = 0
m = 0
Ecrire T[0, 0] = 1
m = 1
Ecrire T[0, 1] = 2
k = 1
m = 0
Ecrire T[1, 0] = 3
m = 1
Ecrire T[1, 1] = 4
k = 2
m = 0
Ecrire T[2, 0] = 5
m = 1
Ecrire T[2, 1] = 6
k = 3
m = 0
Ecrire T[3, 0] = 7
m = 1
Ecrire T[3, 1] = 8
Résultat final pour la première modification
Le tableau T sera rempli et affiché comme suit :


1 2
3 4
5 6
7 8
```
```
Suivi des étapes pour la deuxième modification
Première boucle Pour :

k = 0
m = 0
T[0, 0] = (0 + 1) + 4 * 0 = 1
m = 1
T[0, 1] = (0 + 1) + 4 * 1 = 5
k = 1
m = 0
T[1, 0] = (1 + 1) + 4 * 0 = 2
m = 1
T[1, 1] = (1 + 1) + 4 * 1 = 6
k = 2
m = 0
T[2, 0] = (2 + 1) + 4 * 0 = 3
m = 1
T[2, 1] = (2 + 1) + 4 * 1 = 7
k = 3
m = 0
T[3, 0] = (3 + 1) + 4 * 0 = 4
m = 1
T[3, 1] = (3 + 1) + 4 * 1 = 8
Deuxième boucle Pour :

k = 0
m = 0
Ecrire T[0, 0] = 1
m = 1
Ecrire T[0, 1] = 5
k = 1
m = 0
Ecrire T[1, 0] = 2
m = 1
Ecrire T[1, 1] = 6
k = 2
m = 0
Ecrire T[2, 0] = 3
m = 1
Ecrire T[2, 1] = 7
k = 3
m = 0
Ecrire T[3, 0] = 4
m = 1
Ecrire T[3, 1] = 8
Résultat final pour la deuxième modification
Le tableau T sera rempli et affiché comme suit :


1 5
2 6
3 7
4 8
```
En suivant ces étapes, nous voyons que l'algorithme remplit le tableau T avec les valeurs calculées selon les modifications apportées à la ligne d'affectation et affiche ces valeurs ligne par ligne.

# Exercice 8.6
Soit un tableau T à deux dimensions [12, 8] préalablement rempli de valeurs numériques.
Écrire un algorithme qui recherche la plus grande valeur au sein de ce tableau.
```
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

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher la recherche de la plus grande valeur :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_FindMax.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice8_6 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[,] array; // Tableau à deux dimensions pour stocker les valeurs

    void Start()
    {
        // Initialiser le tableau avec des valeurs préalablement saisies
        array = new int[,]
        {
            { 3, 5, 7, 9, 11, 13, 15, 17 },
            { 2, 4, 6, 8, 10, 12, 14, 16 },
            { 1, 3, 5, 7, 9, 11, 13, 15 },
            { 0, 2, 4, 6, 8, 10, 12, 14 },
            { 1, 3, 5, 7, 9, 11, 13, 15 },
            { 2, 4, 6, 8, 10, 12, 14, 16 },
            { 3, 5, 7, 9, 11, 13, 15, 17 },
            { 4, 6, 8, 10, 12, 14, 16, 18 },
            { 5, 7, 9, 11, 13, 15, 17, 19 },
            { 6, 8, 10, 12, 14, 16, 18, 20 },
            { 7, 9, 11, 13, 15, 17, 19, 21 },
            { 8, 10, 12, 14, 16, 18, 20, 22 }
        };

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void FindMaxValue()
    {
        // Rechercher la plus grande valeur dans le tableau
        int maxValue = array[0, 0];
        for (int i = 0; i < array.GetLength(0); i++)
        {
            for (int j = 0; j < array.GetLength(1); j++)
            {
                if (array[i, j] > maxValue)
                {
                    maxValue = array[i, j];
                }
            }
        }

        // Afficher la plus grande valeur
        resultText.text = "La plus grande valeur dans le tableau est : " + maxValue;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ArrayMaxFinder).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la recherche de la plus grande valeur (Button_FindMax) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (ArrayMaxFinder) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice8_6 -> FindMaxValue.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Déclaration de la variable privée pour stocker le tableau à deux dimensions :

```c#
private int[,] array;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    array = new int[,]
    {
        { 3, 5, 7, 9, 11, 13, 15, 17 },
        { 2, 4, 6, 8, 10, 12, 14, 16 },
        { 1, 3, 5, 7, 9, 11, 13, 15 },
        { 0, 2, 4, 6, 8, 10, 12, 14 },
        { 1, 3, 5, 7, 9, 11, 13, 15 },
        { 2, 4, 6, 8, 10, 12, 14, 16 },
        { 3, 5, 7, 9, 11, 13, 15, 17 },
        { 4, 6, 8, 10, 12, 14, 16, 18 },
        { 5, 7, 9, 11, 13, 15, 17, 19 },
        { 6, 8, 10, 12, 14, 16, 18, 20 },
        { 7, 9, 11, 13, 15, 17, 19, 21 },
        { 8, 10, 12, 14, 16, 18, 20, 22 }
    };
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode FindMaxValue pour rechercher la plus grande valeur dans le tableau et afficher le résultat :

```c#
public void FindMaxValue()
{
    int maxValue = array[0, 0];
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            if (array[i, j] > maxValue)
            {
                maxValue = array[i, j];
            }
        }
    }
    resultText.text = "La plus grande valeur dans le tableau est : " + maxValue;
}
```
En suivant ces étapes, vous aurez un programme Unity qui recherche la plus grande valeur dans un tableau à deux dimensions de taille 12x8 préalablement rempli de valeurs numériques et affiche le résultat dans un Text.

# Exercice 8.7
Écrire un algorithme de jeu de dames très simplifié.  
L’ordinateur demande à l’utilisateur dans quelle case se trouve son pion (quelle ligne, quelle colonne). On met en place un contrôle de saisie afin de vérifier la validité des valeurs entrées.
Ensuite, on demande à l’utilisateur quel mouvement il veut effectuer : 0 (en haut à gauche), 1 (en haut à droite), 2 (en bas à gauche), 3 (en bas à droite).  
Si le mouvement est impossible (i.e. on sort du damier ), on le signale à l’utilisateur et on s’arrête là . Sinon, on déplace le pion et on affiche le damier résultant, en affichant un « O » pour une case vide et un « X » pour la case où se trouve le pion.
```
Variables i, j , posi, posj, i2, j2 en Entier
Variables Correct, MoveOK en Booléen
Tableau Damier[7, 7] en Booléen
Tableau Mouv[3, 1] en Entier
```
Le damier contenant un seul pion, on choisit de le coder à l'économie, en le représentant par un tableau de booléens à deux dimensions. Dans chacun des emplacements de ce damier, Faux signifie l'absence du pion, Vrai sa présence.

Par ailleurs, on emploie une méchante astuce, pas obligatoire, mais bien pratique dans beaucoup de situations. L'idée est de faire correspondre les choix possibles de l'utilisateur avec les mouvements du pion. On entre donc dans un tableau Mouv à deux dimensions, les déplacements du pion selon les quatre directions, en prenant soin que chaque ligne du tableau corresponde à une saisie de l’utilisateur. La première valeur étant le déplacement en i, la seconde le déplacement en j. Ceci nous épargnera par la suite de faire quatre fois les mêmes tests.
```
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
```
Pour i ← 0 à 7
  Pour j ← 0 à 7
    Damier[i, j] ← Faux
  j suivant
i suivant
```
Saisie de la coordonnée en i ("posi") avec contrôle de saisie
```
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
```
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
```
Damier[posi, posj] ← Vrai
```
Saisie du déplacement, avec contrôle
```
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
```
i2 ← posi + Mouv[Dep, 0]
j2 ← posj + Mouv[Dep, 1]
MoveOK ← i2 >= 0 et i2 <= 7 et j2 >= 0 et j2 <= 7
```
Cas où le déplacement est valide
```
Si MoveOK Alors
  Damier[posi, posj] ← Faux
  Damier[i2, j2] ← Vrai
  ```
Affichage du nouveau damier
```
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
```
  Ecrire "Mouvement impossible"
FinSi
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la ligne du pion :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Row.
Ajouter un InputField pour l'entrée de la colonne du pion :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Col.
Ajouter un InputField pour l'entrée du mouvement :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Move.
Ajouter un Button pour déclencher le mouvement du pion :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_MovePiece.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice8_7 : MonoBehaviour
{
    public InputField inputField_Row; // Référence à l'InputField pour la ligne du pion
    public InputField inputField_Col; // Référence à l'InputField pour la colonne du pion
    public InputField inputField_Move; // Référence à l'InputField pour le mouvement
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private bool[,] damier; // Tableau à deux dimensions pour représenter le damier
    private int[,] mouv; // Tableau à deux dimensions pour les mouvements
    private int posi, posj, i2, j2; // Variables pour les positions
    private bool correct, moveOK; // Variables booléennes pour le contrôle de saisie et la validité du mouvement

    void Start()
    {
        // Initialiser le damier avec des valeurs par défaut (false pour vide, true pour le pion)
        damier = new bool[8, 8];
        mouv = new int[4, 2];

        // Initialiser les mouvements
        mouv[0, 0] = -1; mouv[0, 1] = -1; // En haut à gauche
        mouv[1, 0] = -1; mouv[1, 1] = 1; // En haut à droite
        mouv[2, 0] = 1; mouv[2, 1] = -1; // En bas à gauche
        mouv[3, 0] = 1; mouv[3, 1] = 1; // En bas à droite

        // Initialiser le damier
        for (int i = 0; i < 8; i++)
        {
            for (int j = 0; j < 8; j++)
            {
                damier[i, j] = false;
            }
        }

        // Afficher l'instruction initiale
        resultText.text = "Entrez la ligne et la colonne de votre pion :";
    }

    public void MovePiece()
    {
        // Lire les valeurs des InputFields
        string rowInput = inputField_Row.text;
        string colInput = inputField_Col.text;
        string moveInput = inputField_Move.text;

        // Convertir les valeurs en entiers
        if (int.TryParse(rowInput, out int row) && int.TryParse(colInput, out int col) && int.TryParse(moveInput, out int move))
        {
            // Vérifier la validité des valeurs entrées
            if (row >= 0 && row < 8 && col >= 0 && col < 8 && move >= 0 && move <= 3)
            {
                // Mettre à jour la position du pion
                posi = row;
                posj = col;

                // Positionner le pion sur le damier virtuel
                damier[posi, posj] = true;

                // Calculer la nouvelle position en fonction du mouvement
                i2 = posi + mouv[move, 0];
                j2 = posj + mouv[move, 1];

                // Vérifier si le mouvement est possible
                moveOK = i2 >= 0 && i2 < 8 && j2 >= 0 && j2 < 8;

                // Cas où le déplacement est valide
                if (moveOK)
                {
                    damier[posi, posj] = false;
                    damier[i2, j2] = true;

                    // Afficher le damier résultant
                    string result = "Damier résultant :\n";
                    for (int i = 0; i < 8; i++)
                    {
                        for (int j = 0; j < 8; j++)
                        {
                            result += damier[i, j] ? "X " : "O ";
                        }
                        result += "\n";
                    }
                    resultText.text = result;
                }
                else
                {
                    // Signaler que le mouvement est impossible
                    resultText.text = "Mouvement impossible. Vous sortez du damier.";
                }
            }
            else
            {
                // Signaler que les valeurs entrées sont invalides
                resultText.text = "Valeurs invalides. Veuillez entrer des valeurs correctes.";
            }
        }
        else
        {
            // Signaler que les entrées ne sont pas des nombres valides
            resultText.text = "Veuillez entrer des nombres valides.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, CheckersGame).
Dans l'inspecteur, faites glisser l'InputField pour la ligne du pion (InputField_Row) dans le champ InputField_Row du script.
Faites glisser l'InputField pour la colonne du pion (InputField_Col) dans le champ InputField_Col du script.
Faites glisser l'InputField pour le mouvement (InputField_Move) dans le champ InputField_Move du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le mouvement du pion (Button_MovePiece) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (CheckersGame) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice8_7 -> MovePiece.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Row;
public InputField inputField_Col;
public InputField inputField_Move;
public Text resultText;
```
Déclaration des variables privées pour stocker le damier, les mouvements et les positions :

```c#
private bool[,] damier;
private int[,] mouv;
private int posi, posj, i2, j2;
private bool correct, moveOK;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    damier = new bool[8, 8];
    mouv = new int[4, 2];

    mouv[0, 0] = -1; mouv[0, 1] = -1; // En haut à gauche
    mouv[1, 0] = -1; mouv[1, 1] = 1; // En haut à droite
    mouv[2, 0] = 1; mouv[2, 1] = -1; // En bas à gauche
    mouv[3, 0] = 1; mouv[3, 1] = 1; // En bas à droite

    for (int i = 0; i < 8; i++)
    {
        for (int j = 0; j < 8; j++)
        {
            damier[i, j] = false;
        }
    }

    resultText.text = "Entrez la ligne et la colonne de votre pion :";
}
```
Méthode MovePiece pour lire les entrées, vérifier la validité des valeurs, calculer la nouvelle position du pion, vérifier si le mouvement est possible, déplacer le pion, et afficher le damier résultant :

```c#
public void MovePiece()
{
    string rowInput = inputField_Row.text;
    string colInput = inputField_Col.text;
    string moveInput = inputField_Move.text;

    if (int.TryParse(rowInput, out int row) && int.TryParse(colInput, out int col) && int.TryParse(moveInput, out int move))
    {
        if (row >= 0 && row < 8 && col >= 0 && col < 8 && move >= 0 && move <= 3)
        {
            posi = row;
            posj = col;

            damier[posi, posj] = true;

            i2 = posi + mouv[move, 0];
            j2 = posj + mouv[move, 1];

            moveOK = i2 >= 0 && i2 < 8 && j2 >= 0 && j2 < 8;

            if (moveOK)
            {
                damier[posi, posj] = false;
                damier[i2, j2] = true;

                string result = "Damier résultant :\n";
                for (int i = 0; i < 8; i++)
                {
                    for (int j = 0; j < 8; j++)
                    {
                        result += damier[i, j] ? "X " : "O ";
                    }
                    result += "\n";
                }
                resultText.text = result;
            }
            else
            {
                resultText.text = "Mouvement impossible. Vous sortez du damier.";
            }
        }
        else
        {
            resultText.text = "Valeurs invalides. Veuillez entrer des valeurs correctes.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer des nombres valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de jouer à un jeu de dames simplifié, en entrant la position de son pion et le mouvement souhaité, et affiche le damier résultant dans un Text.