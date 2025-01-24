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

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le remplissage du tableau :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice6_1 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void FillArray()
    {
        // Déclarer et remplir un tableau de 7 valeurs numériques avec des zéros
        int[] array = new int[7];

        // Afficher le tableau dans le Text
        string result = "Tableau : ";
        for (int i = 0; i < array.Length; i++)
        {
            result += array[i] + " ";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_1 -> FillArray.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (resultText == null)
{
    Debug.LogError("La référence à Text n'est pas assignée.");
}
```
Méthode FillArray pour déclarer et remplir un tableau de 7 valeurs numériques avec des zéros, puis afficher le tableau dans le Text :

```c#
public void FillArray()
{
    int[] array = new int[7];

    string result = "Tableau : ";
    for (int i = 0; i < array.Length; i++)
    {
        result += array[i] + " ";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui déclare un tableau de 7 valeurs numériques, les met toutes à zéro, et affiche le tableau dans un Text.


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
Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le remplissage du tableau :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice6_2 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void FillVowelsArray()
    {
        // Déclarer et remplir un tableau contenant les six voyelles de l'alphabet latin
        char[] vowels = { 'a', 'e', 'i', 'o', 'u', 'y' };

        // Afficher le tableau dans le Text
        string result = "Voyelles : ";
        foreach (char vowel in vowels)
        {
            result += vowel + " ";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_2 -> FillVowelsArray.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Vérification des références dans la méthode Start :
```c#

if (resultText == null)
{
    Debug.LogError("La référence à Text n'est pas assignée.");
}
```
Méthode FillVowelsArray pour déclarer et remplir un tableau contenant les six voyelles de l'alphabet latin, puis afficher le tableau dans le Text :

```c#
public void FillVowelsArray()
{
    char[] vowels = { 'a', 'e', 'i', 'o', 'u', 'y' };

    string result = "Voyelles : ";
    foreach (char vowel in vowels)
    {
        result += vowel + " ";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui déclare un tableau contenant les six voyelles de l'alphabet latin, les affiche dans un Text.
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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée des notes :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Note.
Ajouter un Button pour déclencher l'entrée de la note suivante :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterNote.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice6_3 : MonoBehaviour
{
    public InputField inputField_Note; // Référence à l'InputField pour les notes
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private float[] notes; // Tableau pour stocker les notes
    private int currentIndex; // Index actuel pour suivre le nombre de notes entrées

    void Start()
    {
        // Initialiser le tableau de notes
        notes = new float[9];
        currentIndex = 0;

        // Afficher l'instruction initiale
        resultText.text = "Entrez la note numéro 1 :";
    }

    public void EnterNote()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Note.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float note))
        {
            // Ajouter la note au tableau
            notes[currentIndex] = note;
            currentIndex++;

            // Vérifier si toutes les notes ont été entrées
            if (currentIndex < 9)
            {
                // Afficher l'instruction pour la note suivante
                resultText.text = "Entrez la note numéro " + (currentIndex + 1) + " :";
                inputField_Note.text = ""; // Effacer l'InputField pour la prochaine entrée
            }
            else
            {
                // Afficher le tableau des notes
                string result = "Les notes entrées sont : ";
                foreach (float n in notes)
                {
                    result += n + " ";
                }
                resultText.text = result;
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une note valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (NoteInputManager).
Dans l'inspecteur, faites glisser l'InputField (InputField_Note) dans le champ InputField_Note du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button (Button_EnterNote) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (NoteInputManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_3 -> EnterNote.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Note;
public Text resultText;
```
Déclaration des variables privées pour stocker les notes et suivre les indices :

```c#
private float[] notes;
private int currentIndex;
```
Initialisation des variables dans la méthode Start :
```c#

void Start()
{
    notes = new float[9];
    currentIndex = 0;
    resultText.text = "Entrez la note numéro 1 :";
}
```
Méthode EnterNote pour lire l'entrée des notes, ajouter la note au tableau, et afficher les instructions ou le résultat :

```c#
public void EnterNote()
{
    string input = inputField_Note.text;
    if (float.TryParse(input, out float note))
    {
        notes[currentIndex] = note;
        currentIndex++;

        if (currentIndex < 9)
        {
            resultText.text = "Entrez la note numéro " + (currentIndex + 1) + " :";
            inputField_Note.text = "";
        }
        else
        {
            string result = "Les notes entrées sont : ";
            foreach (float n in notes)
            {
                result += n + " ";
            }
            resultText.text = result;
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une note valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir 9 notes, les stocke dans un tableau, et affiche les notes entrées.

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

Analyse de l'algorithme
Déclaration du tableau et de la variable :
```
Tableau Nb[5] en Entier : Déclare un tableau Nb de 5 éléments de type entier.
Variable i en Entier : Déclare une variable i de type entier.
Première boucle Pour :

Pour i ← 0 à 5 : Boucle de i allant de 0 à 5.
Nb[i] ← i * i : Assigne la valeur i * i à Nb[i].
Deuxième boucle Pour :

Pour i ← 0 à 5 : Boucle de i allant de 0 à 5.
Ecrire Nb[i] : Affiche la valeur de Nb[i].
Résultat de l'algorithme
Le tableau Nb sera rempli avec les carrés des indices de 0 à 4, et ensuite ces valeurs seront affichées. Voici le contenu du tableau après la première boucle :

Nb[0] = 0 * 0 = 0
Nb[1] = 1 * 1 = 1
Nb[2] = 2 * 2 = 4
Nb[3] = 3 * 3 = 9
Nb[4] = 4 * 4 = 16
Nb[5] = 5 * 5 = 25
L'algorithme affichera ensuite :


0
1
4
9
16
25
Simplification de l'algorithme
L'algorithme peut être simplifié en combinant les deux boucles en une seule. Au lieu de remplir le tableau d'abord et de l'afficher ensuite, nous pouvons remplir et afficher les valeurs dans la même boucle.
```
Algorithme simplifié
```
Tableau Nb[5] en Entier
Variable i en Entier
Début
Pour i ← 0 à 5
  Nb[i] ← i * i
  Ecrire Nb[i]
i suivant
Fin
Explication de la simplification
Déclaration du tableau et de la variable :

Tableau Nb[5] en Entier : Déclare un tableau Nb de 5 éléments de type entier.
Variable i en Entier : Déclare une variable i de type entier.
Boucle Pour combinée :

Pour i ← 0 à 5 : Boucle de i allant de 0 à 5.
Nb[i] ← i * i : Assigne la valeur i * i à Nb[i].
Ecrire Nb[i] : Affiche la valeur de Nb[i].
Résultat de l'algorithme simplifié
Le résultat sera le même que l'algorithme original, mais avec une seule boucle :


0
1
4
9
16
25
En combinant les deux boucles en une seule, nous réduisons la complexité de l'algorithme tout en obtenant le même résultat.
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
```
Analyse de l'algorithme
Déclaration du tableau et des variables :

Tableau N[6] en Entier : Déclare un tableau N de 6 éléments de type entier.
Variables i, k en Entier : Déclare deux variables i et k de type entier.
Initialisation du premier élément :

N[0] ← 1 : Assigne la valeur 1 à N[0].
Première boucle Pour :

Pour k ← 1 à 6 : Boucle de k allant de 1 à 6.
N[k] ← N[k-1] + 2 : Assigne la valeur N[k-1] + 2 à N[k].
Deuxième boucle Pour :

Pour i ← 0 à 6 : Boucle de i allant de 0 à 6.
Ecrire N[i] : Affiche la valeur de N[i].
Résultat de l'algorithme
Le tableau N sera rempli avec une suite arithmétique où chaque élément est égal à l'élément précédent plus 2. Voici le contenu du tableau après la première boucle :

N[0] = 1
N[1] = N[0] + 2 = 1 + 2 = 3
N[2] = N[1] + 2 = 3 + 2 = 5
N[3] = N[2] + 2 = 5 + 2 = 7
N[4] = N[3] + 2 = 7 + 2 = 9
N[5] = N[4] + 2 = 9 + 2 = 11
N[6] = N[5] + 2 = 11 + 2 = 13
L'algorithme affichera ensuite :


1
3
5
7
9
11
13
```
Simplification de l'algorithme
```
L'algorithme peut être simplifié en combinant les deux boucles en une seule. Au lieu de remplir le tableau d'abord et de l'afficher ensuite, nous pouvons remplir et afficher les valeurs dans la même boucle.

Algorithme simplifié

Tableau N[6] en Entier
Variables i, k en Entier
Début
N[0] ← 1
Ecrire N[0]
Pour k ← 1 à 6
  N[k] ← N[k-1] + 2
  Ecrire N[k]
k Suivant
Fin
Explication de la simplification
Déclaration du tableau et des variables :

Tableau N[6] en Entier : Déclare un tableau N de 6 éléments de type entier.
Variables i, k en Entier : Déclare deux variables i et k de type entier.
Initialisation du premier élément et affichage :

N[0] ← 1 : Assigne la valeur 1 à N[0].
Ecrire N[0] : Affiche la valeur de N[0].
Boucle Pour combinée :

Pour k ← 1 à 6 : Boucle de k allant de 1 à 6.
N[k] ← N[k-1] + 2 : Assigne la valeur N[k-1] + 2 à N[k].
Ecrire N[k] : Affiche la valeur de N[k].
Résultat de l'algorithme simplifié
Le résultat sera le même que l'algorithme original, mais avec une seule boucle :


1
3
5
7
9
11
13
```
En combinant les deux boucles en une seule, nous réduisons la complexité de l'algorithme tout en obtenant le même résultat.
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
```
Analyse de l'algorithme
Déclaration du tableau et de la variable :

Tableau Suite[7] en Entier : Déclare un tableau Suite de 7 éléments de type entier.
Variable i en Entier : Déclare une variable i de type entier.
Initialisation des deux premiers éléments :

Suite[0] ← 1 : Assigne la valeur 1 à Suite[0].
Suite[1] ← 1 : Assigne la valeur 1 à Suite[1].
Première boucle Pour :

Pour i ← 2 à 7 : Boucle de i allant de 2 à 7.
Suite[i] ← Suite[i-1] + Suite[i-2] : Assigne la valeur Suite[i-1] + Suite[i-2] à Suite[i].
Deuxième boucle Pour :

Pour i ← 0 à 7 : Boucle de i allant de 0 à 7.
Ecrire Suite[i] : Affiche la valeur de Suite[i].
Résultat de l'algorithme
Le tableau Suite sera rempli avec les premiers termes de la suite de Fibonacci. Voici le contenu du tableau après la première boucle :

Suite[0] = 1
Suite[1] = 1
Suite[2] = Suite[1] + Suite[0] = 1 + 1 = 2
Suite[3] = Suite[2] + Suite[1] = 2 + 1 = 3
Suite[4] = Suite[3] + Suite[2] = 3 + 2 = 5
Suite[5] = Suite[4] + Suite[3] = 5 + 3 = 8
Suite[6] = Suite[5] + Suite[4] = 8 + 5 = 13
Suite[7] = Suite[6] + Suite[5] = 13 + 8 = 21
L'algorithme affichera ensuite :


1
1
2
3
5
8
13
21
```
Simplification de l'algorithme
```
L'algorithme peut être simplifié en combinant les deux boucles en une seule. Au lieu de remplir le tableau d'abord et de l'afficher ensuite, nous pouvons remplir et afficher les valeurs dans la même boucle.

Algorithme simplifié

Tableau Suite[7] en Entier
Variable i en Entier
Début
Suite[0] ← 1
Ecrire Suite[0]
Suite[1] ← 1
Ecrire Suite[1]
Pour i ← 2 à 7
  Suite[i] ← Suite[i-1] + Suite[i-2]
  Ecrire Suite[i]
i suivant
Fin
Explication de la simplification
Déclaration du tableau et de la variable :

Tableau Suite[7] en Entier : Déclare un tableau Suite de 7 éléments de type entier.
Variable i en Entier : Déclare une variable i de type entier.
Initialisation des deux premiers éléments et affichage :

Suite[0] ← 1 : Assigne la valeur 1 à Suite[0].
Ecrire Suite[0] : Affiche la valeur de Suite[0].
Suite[1] ← 1 : Assigne la valeur 1 à Suite[1].
Ecrire Suite[1] : Affiche la valeur de Suite[1].
Boucle Pour combinée :

Pour i ← 2 à 7 : Boucle de i allant de 2 à 7.
Suite[i] ← Suite[i-1] + Suite[i-2] : Assigne la valeur Suite[i-1] + Suite[i-2] à Suite[i].
Ecrire Suite[i] : Affiche la valeur de Suite[i].
Résultat de l'algorithme simplifié
Le résultat sera le même que l'algorithme original, mais avec une seule boucle :


1
1
2
3
5
8
13
21
```
En combinant les deux boucles en une seule, nous réduisons la complexité de l'algorithme tout en obtenant le même résultat.

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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée des notes :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Note.
Ajouter un Button pour déclencher l'entrée de la note suivante :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterNote.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice6_7 : MonoBehaviour
{
    public InputField inputField_Note; // Référence à l'InputField pour les notes
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private float[] notes; // Tableau pour stocker les notes
    private int currentIndex; // Index actuel pour suivre le nombre de notes entrées

    void Start()
    {
        // Initialiser le tableau de notes
        notes = new float[9];
        currentIndex = 0;

        // Afficher l'instruction initiale
        resultText.text = "Entrez la note numéro 1 :";
    }

    public void EnterNote()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Note.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float note))
        {
            // Ajouter la note au tableau
            notes[currentIndex] = note;
            currentIndex++;

            // Vérifier si toutes les notes ont été entrées
            if (currentIndex < 9)
            {
                // Afficher l'instruction pour la note suivante
                resultText.text = "Entrez la note numéro " + (currentIndex + 1) + " :";
                inputField_Note.text = ""; // Effacer l'InputField pour la prochaine entrée
            }
            else
            {
                // Calculer la moyenne des notes
                float sum = 0;
                foreach (float n in notes)
                {
                    sum += n;
                }
                float average = sum / notes.Length;

                // Afficher les notes et la moyenne
                string result = "Les notes entrées sont : ";
                foreach (float n in notes)
                {
                    result += n + " ";
                }
                result += "\nLa moyenne des notes est : " + average.ToString("F2");
                resultText.text = result;
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une note valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, NoteInputManager).
Dans l'inspecteur, faites glisser l'InputField (InputField_Note) dans le champ InputField_Note du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button (Button_EnterNote) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (NoteInputManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_7 -> EnterNote.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Note;
public Text resultText;
```
Déclaration des variables privées pour stocker les notes et suivre les indices :

```c#
private float[] notes;
private int currentIndex;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    notes = new float[9];
    currentIndex = 0;
    resultText.text = "Entrez la note numéro 1 :";
}
```
Méthode EnterNote pour lire l'entrée des notes, ajouter la note au tableau, et afficher les instructions ou le résultat :

```c#
public void EnterNote()
{
    string input = inputField_Note.text;
    if (float.TryParse(input, out float note))
    {
        notes[currentIndex] = note;
        currentIndex++;

        if (currentIndex < 9)
        {
            resultText.text = "Entrez la note numéro " + (currentIndex + 1) + " :";
            inputField_Note.text = "";
        }
        else
        {
            float sum = 0;
            foreach (float n in notes)
            {
                sum += n;
            }
            float average = sum / notes.Length;

            string result = "Les notes entrées sont : ";
            foreach (float n in notes)
            {
                result += n + " ";
            }
            result += "\nLa moyenne des notes est : " + average.ToString("F2");
            resultText.text = result;
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une note valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir 9 notes, les stocke dans un tableau, calcule la moyenne des notes, et affiche les notes entrées ainsi que la moyenne.
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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de valeurs :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Count.
Ajouter un Button pour déclencher la saisie du nombre de valeurs :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SetCount.
Ajouter un InputField pour l'entrée des valeurs :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Value.
Ajouter un Button pour déclencher l'entrée de la valeur suivante :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterValue.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.Collections.Generic;

public class Exercice6_8 : MonoBehaviour
{
    public InputField inputField_Count; // Référence à l'InputField pour le nombre de valeurs
    public InputField inputField_Value; // Référence à l'InputField pour les valeurs
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<float> values; // Liste pour stocker les valeurs
    private int totalValues; // Nombre total de valeurs à saisir
    private int currentIndex; // Index actuel pour suivre le nombre de valeurs entrées
    private int negativeCount; // Compteur pour les valeurs négatives
    private int positiveCount; // Compteur pour les valeurs positives

    void Start()
    {
        // Initialiser les variables
        values = new List<float>();
        totalValues = 0;
        currentIndex = 0;
        negativeCount = 0;
        positiveCount = 0;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le nombre de valeurs à saisir :";
    }

    public void SetCount()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Count.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int count))
        {
            // Initialiser le nombre total de valeurs à saisir
            totalValues = count;
            currentIndex = 0;
            values.Clear();
            negativeCount = 0;
            positiveCount = 0;

            // Afficher l'instruction pour la première valeur
            resultText.text = "Entrez la valeur numéro 1 :";
            inputField_Value.gameObject.SetActive(true);
            inputField_Count.gameObject.SetActive(false);
            inputField_Value.text = "";
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }

    public void EnterValue()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Value.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float value))
        {
            // Ajouter la valeur à la liste
            values.Add(value);
            currentIndex++;

            // Mettre à jour les compteurs de valeurs négatives et positives
            if (value < 0)
            {
                negativeCount++;
            }
            else if (value > 0)
            {
                positiveCount++;
            }

            // Vérifier si toutes les valeurs ont été entrées
            if (currentIndex < totalValues)
            {
                // Afficher l'instruction pour la valeur suivante
                resultText.text = "Entrez la valeur numéro " + (currentIndex + 1) + " :";
                inputField_Value.text = "";
            }
            else
            {
                // Afficher le résultat
                resultText.text = "Nombre de valeurs négatives : " + negativeCount + "\n" +
                                  "Nombre de valeurs positives : " + positiveCount;
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une valeur valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ValueInputManager).
Dans l'inspecteur, faites glisser l'InputField pour le nombre de valeurs (InputField_Count) dans le champ InputField_Count du script.
Faites glisser l'InputField pour les valeurs (InputField_Value) dans le champ InputField_Value du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter des fonctions aux boutons
Sélectionnez le Button pour entrer le nombre de valeurs (Button_SetCount) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_8 -> SetCount.

Sélectionnez le Button pour entrer les valeurs (Button_EnterValue) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_8 -> EnterValue.

Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Count;
public InputField inputField_Value;
public Text resultText;
```
Déclaration des variables privées pour stocker les valeurs et suivre les indices :

```c#
private List<float> values;
private int totalValues;
private int currentIndex;
private int negativeCount;
private int positiveCount;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    values = new List<float>();
    totalValues = 0;
    currentIndex = 0;
    negativeCount = 0;
    positiveCount = 0;
    resultText.text = "Entrez le nombre de valeurs à saisir :";
}
```
Méthode SetCount pour lire l'entrée du nombre de valeurs, initialiser les variables, et afficher les instructions :

```c#
public void SetCount()
{
    string input = inputField_Count.text;
    if (int.TryParse(input, out int count))
    {
        totalValues = count;
        currentIndex = 0;
        values.Clear();
        negativeCount = 0;
        positiveCount = 0;
        resultText.text = "Entrez la valeur numéro 1 :";
        inputField_Value.gameObject.SetActive(true);
        inputField_Count.gameObject.SetActive(false);
        inputField_Value.text = "";
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
Méthode EnterValue pour lire l'entrée des valeurs, ajouter la valeur à la liste, mettre à jour les compteurs, et afficher les instructions ou le résultat :

```c#
public void EnterValue()
{
    string input = inputField_Value.text;
    if (float.TryParse(input, out float value))
    {
        values.Add(value);
        currentIndex++;

        if (value < 0)
        {
            negativeCount++;
        }
        else if (value > 0)
        {
            positiveCount++;
        }

        if (currentIndex < totalValues)
        {
            resultText.text = "Entrez la valeur numéro " + (currentIndex + 1) + " :";
            inputField_Value.text = "";
        }
        else
        {
            resultText.text = "Nombre de valeurs négatives : " + negativeCount + "\n" +
                              "Nombre de valeurs positives : " + positiveCount;
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une valeur valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir un nombre quelconque de valeurs, les stocke dans un tableau, et affiche le nombre de valeurs négatives et positives.


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

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le calcul de la somme :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CalculateSum.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice6_9 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[] values; // Tableau pour stocker les valeurs

    void Start()
    {
        // Initialiser le tableau avec des valeurs préalablement saisies
        values = new int[] { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void CalculateSum()
    {
        // Calculer la somme des valeurs du tableau
        int sum = 0;
        foreach (int value in values)
        {
            sum += value;
        }

        // Afficher le résultat
        resultText.text = "La somme des valeurs du tableau est : " + sum;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, SumCalculator).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour calculer la somme (Button_CalculateSum) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (SumCalculator) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_9 -> CalculateSum.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Déclaration de la variable privée pour stocker les valeurs :

```c#
private int[] values;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    values = new int[] { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode CalculateSum pour calculer la somme des valeurs du tableau et afficher le résultat :
```c#

public void CalculateSum()
{
    int sum = 0;
    foreach (int value in values)
    {
        sum += value;
    }
    resultText.text = "La somme des valeurs du tableau est : " + sum;
}
```
En suivant ces étapes, vous aurez un programme Unity qui calcule la somme des valeurs d'un tableau préalablement saisi et affiche le résultat dans un Text.

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

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher la création du nouveau tableau :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CreateArray.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice6_10 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[] array1; // Tableau 1
    private int[] array2; // Tableau 2
    private int[] resultArray; // Tableau résultant

    void Start()
    {
        // Initialiser les tableaux avec des valeurs préalablement saisies
        array1 = new int[] { 4, 8, 7, 9, 1, 5, 4, 6 };
        array2 = new int[] { 7, 6, 5, 2, 1, 3, 7, 4 };
        resultArray = new int[array1.Length];

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void CreateResultArray()
    {
        // Calculer la somme des éléments des deux tableaux de départ
        for (int i = 0; i < array1.Length; i++)
        {
            resultArray[i] = array1[i] + array2[i];
        }

        // Afficher le tableau résultant
        string result = "Tableau résultant : ";
        foreach (int value in resultArray)
        {
            result += value + " ";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ArraySumCalculator).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour créer le nouveau tableau (Button_CreateArray) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (ArraySumCalculator) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_10 -> CreateResultArray.
Explication du code C#
Déclaration de la variable publique pour la référence UI :
```c#

public Text resultText;
```
Déclaration des variables privées pour stocker les tableaux :

```c#
private int[] array1;
private int[] array2;
private int[] resultArray;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    array1 = new int[] { 4, 8, 7, 9, 1, 5, 4, 6 };
    array2 = new int[] { 7, 6, 5, 2, 1, 3, 7, 4 };
    resultArray = new int[array1.Length];
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode CreateResultArray pour calculer la somme des éléments des deux tableaux de départ et afficher le tableau résultant :

```c#
public void CreateResultArray()
{
    for (int i = 0; i < array1.Length; i++)
    {
        resultArray[i] = array1[i] + array2[i];
    }

    string result = "Tableau résultant : ";
    foreach (int value in resultArray)
    {
        result += value + " ";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui constitue un nouveau tableau à partir de deux tableaux de même longueur préalablement saisis, calcule la somme des éléments des deux tableaux de départ, et affiche le tableau résultant dans un Text.


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
Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le calcul du schtroumpf :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CalculateSchtroumpf.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice6_11 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[] array1; // Tableau 1
    private int[] array2; // Tableau 2

    void Start()
    {
        // Initialiser les tableaux avec des valeurs préalablement saisies
        array1 = new int[] { 4, 8, 7, 12 };
        array2 = new int[] { 3, 6 };

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void CalculateSchtroumpf()
    {
        // Calculer le schtroumpf des deux tableaux
        int schtroumpf = 0;
        foreach (int value1 in array1)
        {
            foreach (int value2 in array2)
            {
                schtroumpf += value1 * value2;
            }
        }

        // Afficher le résultat
        resultText.text = "Le schtroumpf des deux tableaux est : " + schtroumpf;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, SchtroumpfCalculator).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour calculer le schtroumpf (Button_CalculateSchtroumpf) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (SchtroumpfCalculator) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice6_11 -> CalculateSchtroumpf.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Déclaration des variables privées pour stocker les tableaux :

```c#
private int[] array1;
private int[] array2;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    array1 = new int[] { 4, 8, 7, 12 };
    array2 = new int[] { 3, 6 };
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode CalculateSchtroumpf pour calculer le schtroumpf des deux tableaux et afficher le résultat :

```c#
public void CalculateSchtroumpf()
{
    int schtroumpf = 0;
    foreach (int value1 in array1)
    {
        foreach (int value2 in array2)
        {
            schtroumpf += value1 * value2;
        }
    }
    resultText.text = "Le schtroumpf des deux tableaux est : " + schtroumpf;
}
```
En suivant ces étapes, vous aurez un programme Unity qui calcule le schtroumpf de deux tableaux préalablement saisis et affiche le résultat dans un Text.

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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de valeurs :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Count.
Ajouter un Button pour déclencher la saisie du nombre de valeurs :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SetCount.
Ajouter un InputField pour l'entrée des valeurs :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Value.
Ajouter un Button pour déclencher l'entrée de la valeur suivante :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterValue.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.Collections.Generic;

public class Exercice6_12 : MonoBehaviour
{
    public InputField inputField_Count; // Référence à l'InputField pour le nombre de valeurs
    public InputField inputField_Value; // Référence à l'InputField pour les valeurs
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<int> values; // Liste pour stocker les valeurs
    private int totalValues; // Nombre total de valeurs à saisir
    private int currentIndex; // Index actuel pour suivre le nombre de valeurs entrées

    void Start()
    {
        // Initialiser les variables
        values = new List<int>();
        totalValues = 0;
        currentIndex = 0;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le nombre de valeurs à saisir :";
    }

    public void SetCount()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Count.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int count))
        {
            // Initialiser le nombre total de valeurs à saisir
            totalValues = count;
            currentIndex = 0;
            values.Clear();

            // Afficher l'instruction pour la première valeur
            resultText.text = "Entrez la valeur numéro 1 :";
            inputField_Value.gameObject.SetActive(true);
            inputField_Count.gameObject.SetActive(false);
            inputField_Value.text = "";
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }

    public void EnterValue()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Value.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int value))
        {
            // Ajouter la valeur à la liste
            values.Add(value);
            currentIndex++;

            // Vérifier si toutes les valeurs ont été entrées
            if (currentIndex < totalValues)
            {
                // Afficher l'instruction pour la valeur suivante
                resultText.text = "Entrez la valeur numéro " + (currentIndex + 1) + " :";
                inputField_Value.text = "";
            }
            else
            {
                // Augmenter chaque valeur de 1
                for (int i = 0; i < values.Count; i++)
                {
                    values[i] += 1;
                }

                // Afficher le nouveau tableau
                string result = "Le nouveau tableau est : ";
                foreach (int v in values)
                {
                    result += v + " ";
                }
                resultText.text = result;
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une valeur valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ValueInputManager).
Dans l'inspecteur, faites glisser l'InputField pour le nombre de valeurs (InputField_Count) dans le champ InputField_Count du script.
Faites glisser l'InputField pour les valeurs (InputField_Value) dans le champ InputField_Value du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter des fonctions aux boutons
Sélectionnez le Button pour entrer le nombre de valeurs (Button_SetCount) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_12 -> SetCount.

Sélectionnez le Button pour entrer les valeurs (Button_EnterValue) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_12 -> EnterValue.

Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Count;
public InputField inputField_Value;
public Text resultText;
```
Déclaration des variables privées pour stocker les valeurs et suivre les indices :

```c#
private List<int> values;
private int totalValues;
private int currentIndex;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    values = new List<int>();
    totalValues = 0;
    currentIndex = 0;
    resultText.text = "Entrez le nombre de valeurs à saisir :";
}
```
Méthode SetCount pour lire l'entrée du nombre de valeurs, initialiser les variables, et afficher les instructions :

```c#
public void SetCount()
{
    string input = inputField_Count.text;
    if (int.TryParse(input, out int count))
    {
        totalValues = count;
        currentIndex = 0;
        values.Clear();
        resultText.text = "Entrez la valeur numéro 1 :";
        inputField_Value.gameObject.SetActive(true);
        inputField_Count.gameObject.SetActive(false);
        inputField_Value.text = "";
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
Méthode EnterValue pour lire l'entrée des valeurs, ajouter la valeur à la liste, augmenter chaque valeur de 1, et afficher les instructions ou le résultat :

```c#
public void EnterValue()
{
    string input = inputField_Value.text;
    if (int.TryParse(input, out int value))
    {
        values.Add(value);
        currentIndex++;

        if (currentIndex < totalValues)
        {
            resultText.text = "Entrez la valeur numéro " + (currentIndex + 1) + " :";
            inputField_Value.text = "";
        }
        else
        {
            for (int i = 0; i < values.Count; i++)
            {
                values[i] += 1;
            }

            string result = "Le nouveau tableau est : ";
            foreach (int v in values)
            {
                result += v + " ";
            }
            resultText.text = result;
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une valeur valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir un nombre quelconque de valeurs, les augmente de 1, et affiche le nouveau tableau à l'écran.

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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de valeurs :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Count.
Ajouter un Button pour déclencher la saisie du nombre de valeurs :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SetCount.
Ajouter un InputField pour l'entrée des valeurs :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Value.
Ajouter un Button pour déclencher l'entrée de la valeur suivante :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterValue.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.Collections.Generic;

public class Exercice6_13 : MonoBehaviour
{
    public InputField inputField_Count; // Référence à l'InputField pour le nombre de valeurs
    public InputField inputField_Value; // Référence à l'InputField pour les valeurs
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<int> values; // Liste pour stocker les valeurs
    private int totalValues; // Nombre total de valeurs à saisir
    private int currentIndex; // Index actuel pour suivre le nombre de valeurs entrées

    void Start()
    {
        // Initialiser les variables
        values = new List<int>();
        totalValues = 0;
        currentIndex = 0;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le nombre de valeurs à saisir :";
    }

    public void SetCount()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Count.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int count))
        {
            // Initialiser le nombre total de valeurs à saisir
            totalValues = count;
            currentIndex = 0;
            values.Clear();

            // Afficher l'instruction pour la première valeur
            resultText.text = "Entrez la valeur numéro 1 :";
            inputField_Value.gameObject.SetActive(true);
            inputField_Count.gameObject.SetActive(false);
            inputField_Value.text = "";
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }

    public void EnterValue()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Value.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int value))
        {
            // Ajouter la valeur à la liste
            values.Add(value);
            currentIndex++;

            // Vérifier si toutes les valeurs ont été entrées
            if (currentIndex < totalValues)
            {
                // Afficher l'instruction pour la valeur suivante
                resultText.text = "Entrez la valeur numéro " + (currentIndex + 1) + " :";
                inputField_Value.text = "";
            }
            else
            {
                // Rechercher la plus grande valeur et sa position
                int maxValue = values[0];
                int maxIndex = 0;

                for (int i = 1; i < values.Count; i++)
                {
                    if (values[i] > maxValue)
                    {
                        maxValue = values[i];
                        maxIndex = i;
                    }
                }

                // Afficher le résultat
                resultText.text = "La plus grande valeur est : " + maxValue + "\nElle se trouve à la position : " + (maxIndex + 1);
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une valeur valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ValueInputManager).
Dans l'inspecteur, faites glisser l'InputField pour le nombre de valeurs (InputField_Count) dans le champ InputField_Count du script.
Faites glisser l'InputField pour les valeurs (InputField_Value) dans le champ InputField_Value du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter des fonctions aux boutons
Sélectionnez le Button pour entrer le nombre de valeurs (Button_SetCount) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_13 -> SetCount.

Sélectionnez le Button pour entrer les valeurs (Button_EnterValue) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_13 -> EnterValue.

Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Count;
public InputField inputField_Value;
public Text resultText;
```
Déclaration des variables privées pour stocker les valeurs et suivre les indices :

```c#
private List<int> values;
private int totalValues;
private int currentIndex;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    values = new List<int>();
    totalValues = 0;
    currentIndex = 0;
    resultText.text = "Entrez le nombre de valeurs à saisir :";
}
```
Méthode SetCount pour lire l'entrée du nombre de valeurs, initialiser les variables, et afficher les instructions :
```c#

public void SetCount()
{
    string input = inputField_Count.text;
    if (int.TryParse(input, out int count))
    {
        totalValues = count;
        currentIndex = 0;
        values.Clear();
        resultText.text = "Entrez la valeur numéro 1 :";
        inputField_Value.gameObject.SetActive(true);
        inputField_Count.gameObject.SetActive(false);
        inputField_Value.text = "";
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
Méthode EnterValue pour lire l'entrée des valeurs, ajouter la valeur à la liste, rechercher la plus grande valeur et sa position, et afficher les instructions ou le résultat :

```c#
public void EnterValue()
{
    string input = inputField_Value.text;
    if (int.TryParse(input, out int value))
    {
        values.Add(value);
        currentIndex++;

        if (currentIndex < totalValues)
        {
            resultText.text = "Entrez la valeur numéro " + (currentIndex + 1) + " :";
            inputField_Value.text = "";
        }
        else
        {
            int maxValue = values[0];
            int maxIndex = 0;

            for (int i = 1; i < values.Count; i++)
            {
                if (values[i] > maxValue)
                {
                    maxValue = values[i];
                    maxIndex = i;
                }
            }

            resultText.text = "La plus grande valeur est : " + maxValue + "\nElle se trouve à la position : " + (maxIndex + 1);
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une valeur valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir un nombre déterminé de valeurs, recherche la plus grande valeur dans le tableau, et affiche cette valeur ainsi que sa position.

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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de notes :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Count.
Ajouter un Button pour déclencher la saisie du nombre de notes :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SetCount.
Ajouter un InputField pour l'entrée des notes :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Note.
Ajouter un Button pour déclencher l'entrée de la note suivante :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterNote.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.Collections.Generic;

public class Exercice6_14 : MonoBehaviour
{
    public InputField inputField_Count; // Référence à l'InputField pour le nombre de notes
    public InputField inputField_Note; // Référence à l'InputField pour les notes
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<float> notes; // Liste pour stocker les notes
    private int totalNotes; // Nombre total de notes à saisir
    private int currentIndex; // Index actuel pour suivre le nombre de notes entrées

    void Start()
    {
        // Initialiser les variables
        notes = new List<float>();
        totalNotes = 0;
        currentIndex = 0;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le nombre de notes à saisir :";
    }

    public void SetCount()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Count.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int count))
        {
            // Initialiser le nombre total de notes à saisir
            totalNotes = count;
            currentIndex = 0;
            notes.Clear();

            // Afficher l'instruction pour la première note
            resultText.text = "Entrez la note numéro 1 :";
            inputField_Note.gameObject.SetActive(true);
            inputField_Count.gameObject.SetActive(false);
            inputField_Note.text = "";
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }

    public void EnterNote()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Note.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float note))
        {
            // Ajouter la note à la liste
            notes.Add(note);
            currentIndex++;

            // Vérifier si toutes les notes ont été entrées
            if (currentIndex < totalNotes)
            {
                // Afficher l'instruction pour la note suivante
                resultText.text = "Entrez la note numéro " + (currentIndex + 1) + " :";
                inputField_Note.text = "";
            }
            else
            {
                // Calculer la moyenne des notes
                float sum = 0;
                foreach (float n in notes)
                {
                    sum += n;
                }
                float average = sum / notes.Count;

                // Compter le nombre de notes supérieures à la moyenne
                int aboveAverageCount = 0;
                foreach (float n in notes)
                {
                    if (n > average)
                    {
                        aboveAverageCount++;
                    }
                }

                // Afficher le résultat
                resultText.text = "La moyenne des notes est : " + average.ToString("F2") + "\n" +
                                  "Nombre de notes supérieures à la moyenne : " + aboveAverageCount;
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une note valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, NoteInputManager).
Dans l'inspecteur, faites glisser l'InputField pour le nombre de notes (InputField_Count) dans le champ InputField_Count du script.
Faites glisser l'InputField pour les notes (InputField_Note) dans le champ InputField_Note du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter des fonctions aux boutons
Sélectionnez le Button pour entrer le nombre de notes (Button_SetCount) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (NoteInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_14 -> SetCount.

Sélectionnez le Button pour entrer les notes (Button_EnterNote) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (NoteInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice6_14 -> EnterNote.

Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Count;
public InputField inputField_Note;
public Text resultText;
```
Déclaration des variables privées pour stocker les notes et suivre les indices :

```c#
private List<float> notes;
private int totalNotes;
private int currentIndex;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    notes = new List<float>();
    totalNotes = 0;
    currentIndex = 0;
    resultText.text = "Entrez le nombre de notes à saisir :";
}
```
Méthode SetCount pour lire l'entrée du nombre de notes, initialiser les variables, et afficher les instructions :

```c#
public void SetCount()
{
    string input = inputField_Count.text;
    if (int.TryParse(input, out int count))
    {
        totalNotes = count;
        currentIndex = 0;
        notes.Clear();
        resultText.text = "Entrez la note numéro 1 :";
        inputField_Note.gameObject.SetActive(true);
        inputField_Count.gameObject.SetActive(false);
        inputField_Note.text = "";
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
Méthode EnterNote pour lire l'entrée des notes, ajouter la note à la liste, calculer la moyenne des notes, compter le nombre de notes supérieures à la moyenne, et afficher les instructions ou le résultat :

```c#
public void EnterNote()
{
    string input = inputField_Note.text;
    if (float.TryParse(input, out float note))
    {
        notes.Add(note);
        currentIndex++;

        if (currentIndex < totalNotes)
        {
            resultText.text = "Entrez la note numéro " + (currentIndex + 1) + " :";
            inputField_Note.text = "";
        }
        else
        {
            float sum = 0;
            foreach (float n in notes)
            {
                sum += n;
            }
            float average = sum / notes.Count;

            int aboveAverageCount = 0;
            foreach (float n in notes)
            {
                if (n > average)
                {
                    aboveAverageCount++;
                }
            }

            resultText.text = "La moyenne des notes est : " + average.ToString("F2") + "\n" +
                               "Nombre de notes supérieures à la moyenne : " + aboveAverageCount;
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une note valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir les notes d'une classe, calcule la moyenne des notes, et affiche le nombre de notes supérieures à cette moyenne.
