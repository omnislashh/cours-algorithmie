# Exercice 7.1
Ecrivez un algorithme qui permette de saisir un nombre quelconque de valeurs, et qui les range au fur et à mesure dans un tableau. Le programme, une fois la saisie terminée, doit dire si les éléments du tableau sont tous consécutifs ou non.
Par exemple, si le tableau est :  
 
12	13	14	15	16	17	18  

ses éléments sont tous consécutifs. En revanche, si le tableau est :  
 
9	10	11	15	16	17	18  

ses éléments ne sont pas tous consécutifs.  
```
Variables Nb, i en Entier
Variable Flag en Booleen
Tableau T[] en Entier
Debut
Ecrire "Entrez le nombre de valeurs :"
Lire Nb
Redim T[Nb-1]
Pour i ← 0 à Nb - 1
  Ecrire "Entrez le nombre n° ", i + 1
  Lire T[i]
i Suivant
Flag ← Vrai
Pour i ← 1 à Nb - 1
  Si T[i] <> T[i – 1] + 1 Alors
    Flag ← Faux
  FinSi
i Suivant
Si Flag Alors
  Ecrire "Les nombres sont consécutifs"
Sinon
  Ecrire "Les nombres ne sont pas consécutifs"
FinSi
Fin
```
Cette programmation est sans doute la plus spontanée, mais elle présente le défaut d'examiner la totalité du tableau, même lorsqu'on découvre dès le départ deux éléments non consécutifs. Aussi, dans le cas d'un grand tableau, est-elle dispendieuse en temps de traitement. Une autre manière de procéder serait de sortir de la boucle dès que deux éléments non consécutifs sont détectés. La deuxième partie de l'algorithme deviendrait donc :  
```
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

public class Exercice7_1 : MonoBehaviour
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
                // Vérifier si les éléments du tableau sont tous consécutifs
                bool areConsecutive = true;
                for (int i = 1; i < values.Count; i++)
                {
                    if (values[i] != values[i - 1] + 1)
                    {
                        areConsecutive = false;
                        break;
                    }
                }

                // Afficher le résultat
                if (areConsecutive)
                {
                    resultText.text = "Les éléments du tableau sont tous consécutifs.";
                }
                else
                {
                    resultText.text = "Les éléments du tableau ne sont pas tous consécutifs.";
                }
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

Dans le menu déroulant, sélectionnez Exercice7_1 -> SetCount.

Sélectionnez le Button pour entrer les valeurs (Button_EnterValue) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (ValueInputManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice7_1 -> EnterValue.  

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
Méthode SetCount pour lire l'entrée du nombre de valeurs, initialiser les variables, et afficher les instructions :


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
Méthode EnterValue pour lire l'entrée des valeurs, ajouter la valeur à la liste, vérifier si les éléments du tableau sont tous consécutifs, et afficher les instructions ou le résultat :

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
            bool areConsecutive = true;
            for (int i = 1; i < values.Count; i++)
            {
                if (values[i] != values[i - 1] + 1)
                {
                    areConsecutive = false;
                    break;
                }
            }

            if (areConsecutive)
            {
                resultText.text = "Les éléments du tableau sont tous consécutifs.";
            }
            else
            {
                resultText.text = "Les éléments du tableau ne sont pas tous consécutifs.";
            }
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une valeur valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir un nombre quelconque de valeurs, les range dans un tableau, et vérifie si les éléments du tableau sont tous consécutifs.


# Exercice 7.2
Ecrivez un algorithme qui trie un tableau dans l’ordre décroissant.
Vous écrirez bien entendu deux versions de cet algorithme, l'une employant le tri par sélection, l'autre le tri à bulles.

On suppose que N est le nombre d’éléments du tableau. Tri par insertion :
```
…
Pour i ← 0 à N - 2
  posmaxi = i
  Pour j ← i + 1 à N - 1
    Si t[j] > t[posmaxi] alors
      posmaxi ← j
    Finsi
  j suivant
  temp ← t[posmaxi]
  t[posmaxi] ← t[i]
  t[i] ← temp
i suivant
Fin

Tri à bulles :

…
Yapermut ← Vrai
TantQue Yapermut
  Yapermut ← Faux
  Pour i ← 0 à N - 2
    Si t[i] < t[i + 1] Alors
      temp ← t[i]
      t[i] ← t[i + 1]
      t[i + 1] ← temp
      Yapermut ← Vrai
    Finsi
  i suivant
FinTantQue
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le tri par sélection :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SelectionSort.
Ajouter un Button pour déclencher le tri à bulles :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_BubbleSort.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice7_2 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[] array; // Tableau pour stocker les valeurs

    void Start()
    {
        // Initialiser le tableau avec des valeurs préalablement saisies
        array = new int[] { 4, 8, 7, 12, 3, 6, 5, 10, 9, 1 };

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void SelectionSort()
    {
        // Trier le tableau dans l'ordre décroissant en utilisant le tri par sélection
        int n = array.Length;
        for (int i = 0; i < n - 1; i++)
        {
            int maxIndex = i;
            for (int j = i + 1; j < n; j++)
            {
                if (array[j] > array[maxIndex])
                {
                    maxIndex = j;
                }
            }
            int temp = array[maxIndex];
            array[maxIndex] = array[i];
            array[i] = temp;
        }

        // Afficher le tableau trié
        string result = "Tableau trié (tri par sélection) : ";
        foreach (int value in array)
        {
            result += value + " ";
        }
        resultText.text = result;
    }

    public void BubbleSort()
    {
        // Trier le tableau dans l'ordre décroissant en utilisant le tri à bulles
        int n = array.Length;
        for (int i = 0; i < n - 1; i++)
        {
            for (int j = 0; j < n - i - 1; j++)
            {
                if (array[j] < array[j + 1])
                {
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }

        // Afficher le tableau trié
        string result = "Tableau trié (tri à bulles) : ";
        foreach (int value in array)
        {
            result += value + " ";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, SortManager).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter des fonctions aux boutons
Sélectionnez le Button pour déclencher le tri par sélection (Button_SelectionSort) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (SortManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice7_2 -> SelectionSort.

Sélectionnez le Button pour déclencher le tri à bulles (Button_BubbleSort) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script (SortManager) dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice7_2 -> BubbleSort.

Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Déclaration de la variable privée pour stocker les valeurs :
```c#

private int[] array;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    array = new int[] { 4, 8, 7, 12, 3, 6, 5, 10, 9, 1 };
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode SelectionSort pour trier le tableau dans l'ordre décroissant en utilisant le tri par sélection et afficher le résultat :

```c#
public void SelectionSort()
{
    int n = array.Length;
    for (int i = 0; i < n - 1; i++)
    {
        int maxIndex = i;
        for (int j = i + 1; j < n; j++)
        {
            if (array[j] > array[maxIndex])
            {
                maxIndex = j;
            }
        }
        int temp = array[maxIndex];
        array[maxIndex] = array[i];
        array[i] = temp;
    }

    string result = "Tableau trié (tri par sélection) : ";
    foreach (int value in array)
    {
        result += value + " ";
    }
    resultText.text = result;
}
```
Méthode BubbleSort pour trier le tableau dans l'ordre décroissant en utilisant le tri à bulles et afficher le résultat :

```c#
public void BubbleSort()
{
    int n = array.Length;
    for (int i = 0; i < n - 1; i++)
    {
        for (int j = 0; j < n - i - 1; j++)
        {
            if (array[j] < array[j + 1])
            {
                int temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
    }

    string result = "Tableau trié (tri à bulles) : ";
    foreach (int value in array)
    {
        result += value + " ";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet de trier un tableau dans l'ordre décroissant en utilisant soit le tri par sélection, soit le tri à bulles, et affiche le résultat dans un Text.

# Exercice 7.3
Ecrivez un algorithme qui inverse l’ordre des éléments d’un tableau dont on suppose qu'il a été préalablement saisi (« les premiers seront les derniers… »)

On suppose que n est le nombre d’éléments du tableau préalablement saisi

```
…
Pour i ← 0 à (N-1)/2
  Temp ← T[i]
  T[i] ← T[N-1-i]
  T[N-1-i] ← Temp
i suivant
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher l'inversion du tableau :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_ReverseArray.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice7_3 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[] array; // Tableau pour stocker les valeurs

    void Start()
    {
        // Initialiser le tableau avec des valeurs préalablement saisies
        array = new int[] { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void ReverseArray()
    {
        // Inverser l'ordre des éléments du tableau
        int n = array.Length;
        for (int i = 0; i < n / 2; i++)
        {
            int temp = array[i];
            array[i] = array[n - i - 1];
            array[n - i - 1] = temp;
        }

        // Afficher le tableau inversé
        string result = "Tableau inversé : ";
        foreach (int value in array)
        {
            result += value + " ";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ArrayReverser).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher l'inversion du tableau (Button_ReverseArray) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (ArrayReverser) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice7_3 -> ReverseArray.
Explication du code C#
Déclaration de la variable publique pour la référence UI :
```c#

public Text resultText;
```
Déclaration de la variable privée pour stocker les valeurs :

```c#
private int[] array;
```
Initialisation des variables dans la méthode Start :
```c#

void Start()
{
    array = new int[] { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
Méthode ReverseArray pour inverser l'ordre des éléments du tableau et afficher le résultat :


public void ReverseArray()
{
    int n = array.Length;
    for (int i = 0; i < n / 2; i++)
    {
        int temp = array[i];
        array[i] = array[n - i - 1];
        array[n - i - 1] = temp;
    }

    string result = "Tableau inversé : ";
    foreach (int value in array)
    {
        result += value + " ";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui inverse l'ordre des éléments d'un tableau et affiche le tableau inversé dans un Text.
# Exercice 7.4
Ecrivez un algorithme qui permette à l’utilisateur de supprimer une valeur d’un tableau préalablement saisi. L’utilisateur donnera l’indice de la valeur qu’il souhaite supprimer. Attention, il ne s’agit pas de remettre une valeur à zéro, mais bel et bien de la supprimer du tableau lui-même ! Si le tableau de départ était :  
 
12	8	4	45	64	9	2  

Et que l’utilisateur souhaite supprimer la valeur d’indice 4, le nouveau tableau sera :  
 
12	8	4	45	9	2  

```
…
Ecrire "Rang de la valeur à supprimer ?"
Lire S
Pour i ← S à N-2
  T[i] ← T[i+1]
i suivant
Redim T[N–1]
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de l'indice de la valeur à supprimer :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Index.
Ajouter un Button pour déclencher la suppression de la valeur :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_RemoveValue.
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

public class Exercice7_4 : MonoBehaviour
{
    public InputField inputField_Index; // Référence à l'InputField pour l'indice de la valeur à supprimer
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<int> values; // Liste pour stocker les valeurs

    void Start()
    {
        // Initialiser le tableau avec des valeurs préalablement saisies
        values = new List<int> { 12, 8, 4, 45, 64, 9, 2 };

        // Afficher l'instruction initiale
        resultText.text = "Entrez l'indice de la valeur à supprimer :";
    }

    public void RemoveValue()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Index.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int index))
        {
            // Vérifier si l'indice est valide
            if (index >= 0 && index < values.Count)
            {
                // Supprimer la valeur à l'indice spécifié
                values.RemoveAt(index);

                // Afficher le nouveau tableau
                string result = "Nouveau tableau : ";
                foreach (int value in values)
                {
                    result += value + " ";
                }
                resultText.text = result;
            }
            else
            {
                // Afficher un message d'erreur si l'indice n'est pas valide
                resultText.text = "Indice invalide. Veuillez entrer un indice valide.";
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ValueRemover).
Dans l'inspecteur, faites glisser l'InputField pour l'indice de la valeur à supprimer (InputField_Index) dans le champ InputField_Index du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la suppression de la valeur (Button_RemoveValue) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (ValueRemover) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice7_4 -> RemoveValue.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Index;
public Text resultText;
```
Déclaration de la variable privée pour stocker les valeurs :

```c#
private List<int> values;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    values = new List<int> { 12, 8, 4, 45, 64, 9, 2 };
    resultText.text = "Entrez l'indice de la valeur à supprimer :";
}
```
Méthode RemoveValue pour lire l'entrée de l'indice, vérifier si l'indice est valide, supprimer la valeur à l'indice spécifié, et afficher le nouveau tableau :

```c#
public void RemoveValue()
{
    string input = inputField_Index.text;
    if (int.TryParse(input, out int index))
    {
        if (index >= 0 && index < values.Count)
        {
            values.RemoveAt(index);
            string result = "Nouveau tableau : ";
            foreach (int value in values)
            {
                result += value + " ";
            }
            resultText.text = result;
        }
        else
        {
            resultText.text = "Indice invalide. Veuillez entrer un indice valide.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de supprimer une valeur d'un tableau en spécifiant l'indice de la valeur à supprimer, et affiche le nouveau tableau dans un Text.

# Exercice 7.5
Ecrivez l'algorithme qui recherche un mot saisi au clavier dans un dictionnaire. Le dictionnaire est supposé être codé dans un tableau préalablement rempli et trié.

```
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
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du mot à rechercher :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Word.
Ajouter un Button pour déclencher la recherche du mot :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SearchWord.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice7_5 : MonoBehaviour
{
    public InputField inputField_Word; // Référence à l'InputField pour le mot à rechercher
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private string[] dictionary; // Tableau pour stocker le dictionnaire

    void Start()
    {
        // Initialiser le dictionnaire avec des mots préalablement saisis et triés
        dictionary = new string[] { "apple", "banana", "cherry", "date", "fig", "grape", "kiwi", "lemon", "mango", "orange" };

        // Afficher l'instruction initiale
        resultText.text = "Entrez le mot à rechercher :";
    }

    public void SearchWord()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Word.text;

        // Rechercher le mot dans le dictionnaire
        bool found = false;
        for (int i = 0; i < dictionary.Length; i++)
        {
            if (dictionary[i].Equals(input, System.StringComparison.OrdinalIgnoreCase))
            {
                found = true;
                break;
            }
        }

        // Afficher le résultat
        if (found)
        {
            resultText.text = "Le mot '" + input + "' a été trouvé dans le dictionnaire.";
        }
        else
        {
            resultText.text = "Le mot '" + input + "' n'a pas été trouvé dans le dictionnaire.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, WordSearcher).
Dans l'inspecteur, faites glisser l'InputField pour le mot à rechercher (InputField_Word) dans le champ InputField_Word du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la recherche du mot (Button_SearchWord) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (WordSearcher) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice7_5 -> SearchWord.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Word;
public Text resultText;
```
Déclaration de la variable privée pour stocker le dictionnaire :

```c#
private string[] dictionary;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    dictionary = new string[] { "apple", "banana", "cherry", "date", "fig", "grape", "kiwi", "lemon", "mango", "orange" };
    resultText.text = "Entrez le mot à rechercher :";
}
```
Méthode SearchWord pour lire l'entrée du mot, rechercher le mot dans le dictionnaire, et afficher le résultat :

```c#
public void SearchWord()
{
    string input = inputField_Word.text;
    bool found = false;
    for (int i = 0; i < dictionary.Length; i++)
    {
        if (dictionary[i].Equals(input, System.StringComparison.OrdinalIgnoreCase))
        {
            found = true;
            break;
        }
    }

    if (found)
    {
        resultText.text = "Le mot '" + input + "' a été trouvé dans le dictionnaire.";
    }
    else
    {
        resultText.text = "Le mot '" + input + "' n'a pas été trouvé dans le dictionnaire.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de rechercher un mot dans un dictionnaire préalablement rempli et trié, et affiche le résultat dans un Text.
# Exercice 7.6
Écrivez un algorithme qui fusionne deux tableaux (déjà existants) dans un troisième, qui devra être trié.
Attention ! On présume que les deux tableaux de départ sont préalablement triés : il est donc irrationnel de faire une simple concaténation des deux tableaux de départ, puis d'opérer un tri : comme quand on se trouve face à deux tas de papiers déjà triés et qu'on veut les réunir, il existe une méthode bien plus économique (et donc, bien plus rationnelle...)

Les deux tableaux de départ, A[m] et B[n], sont déjà triés : pas question donc de les empiler simplement pour se relancer dans un (long) tri. On prend simplement les deux tableaux, et on avance dans l'un puis dans l'autre selon celui des deux éléments auquel on est parvenu est le plus petit (il suffit de s'imaginer devant deux tas de papiers triés par date, et de vouloir constituer un tas unique, pour comprendre ce qu'on va faire). Le truc est qu'on ne sait pas par avance où on va en être à un moment donné dans un tableau et dans l'autre : il nous faut donc deux compteurs différents pour noter notre position dans chacun des deux tableaux. On appelle C le tableau de destination, et ic la variable qui indique où on en est dans celui-ci.

```
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

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher la fusion des tableaux :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_MergeArrays.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice7_6 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    private int[] array1; // Tableau 1
    private int[] array2; // Tableau 2
    private int[] mergedArray; // Tableau résultant

    void Start()
    {
        // Initialiser les tableaux avec des valeurs préalablement saisies et triés
        array1 = new int[] { 1, 3, 5, 7, 9 };
        array2 = new int[] { 2, 4, 6, 8, 10 };
        mergedArray = new int[array1.Length + array2.Length];

        // Assurez-vous que les références sont assignées
        if (resultText == null)
        {
            Debug.LogError("La référence à Text n'est pas assignée.");
        }
    }

    public void MergeArrays()
    {
        // Fusionner les deux tableaux dans un troisième tableau trié
        int i = 0, j = 0, k = 0;

        while (i < array1.Length && j < array2.Length)
        {
            if (array1[i] < array2[j])
            {
                mergedArray[k++] = array1[i++];
            }
            else
            {
                mergedArray[k++] = array2[j++];
            }
        }

        // Copier les éléments restants de array1, s'il y en a
        while (i < array1.Length)
        {
            mergedArray[k++] = array1[i++];
        }

        // Copier les éléments restants de array2, s'il y en a
        while (j < array2.Length)
        {
            mergedArray[k++] = array2[j++];
        }

        // Afficher le tableau résultant
        string result = "Tableau fusionné et trié : ";
        foreach (int value in mergedArray)
        {
            result += value + " ";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, ArrayMerger).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la fusion des tableaux (Button_MergeArrays) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (ArrayMerger) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice7_6 -> MergeArrays.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Déclaration des variables privées pour stocker les tableaux :

```c#
private int[] array1;
private int[] array2;
private int[] mergedArray;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    array1 = new int[] { 1, 3, 5, 7, 9 };
    array2 = new int[] { 2, 4, 6, 8, 10 };
    mergedArray = new int[array1.Length + array2.Length];
    if (resultText == null)
    {
        Debug.LogError("La référence à Text n'est pas assignée.");
    }
}
```
Méthode MergeArrays pour fusionner les deux tableaux dans un troisième tableau trié et afficher le résultat :

```c#
public void MergeArrays()
{
    int i = 0, j = 0, k = 0;

    while (i < array1.Length && j < array2.Length)
    {
        if (array1[i] < array2[j])
        {
            mergedArray[k++] = array1[i++];
        }
        else
        {
            mergedArray[k++] = array2[j++];
        }
    }

    while (i < array1.Length)
    {
        mergedArray[k++] = array1[i++];
    }

    while (j < array2.Length)
    {
        mergedArray[k++] = array2[j++];
    }

    string result = "Tableau fusionné et trié : ";
    foreach (int value in mergedArray)
    {
        result += value + " ";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui fusionne deux tableaux déjà triés dans un troisième tableau, qui sera également trié, et affiche le résultat dans un Text.