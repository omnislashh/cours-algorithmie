# Exercice 5.1
Ecrire un algorithme qui demande à l’utilisateur un nombre compris entre 1 et 3 jusqu’à ce que la réponse convienne.
```
Variable N en Entier
Debut
N ← 0
Ecrire "Entrez un nombre entre 1 et 3"
TantQue N < 1 ou N > 3
  Lire N
    Si N < 1 ou N > 3 Alors
      Ecrire "Saisie erronée. Recommencez”
    FinSi
  FinTantQue
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher la vérification du nombre :

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

public class Exercice5_1 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckNumber()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int number))
        {
            // Vérifier si le nombre est compris entre 1 et 3
            if (number >= 1 && number <= 3)
            {
                resultText.text = "Le nombre est valide.";
            }
            else
            {
                resultText.text = "Veuillez entrer un nombre compris entre 1 et 3.";
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_1 -> CheckNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CheckNumber pour lire l'entrée, vérifier si le nombre est compris entre 1 et 3, et afficher le résultat :

```c#
public void CheckNumber()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int number))
    {
        if (number >= 1 && number <= 3)
        {
            resultText.text = "Le nombre est valide.";
        }
        else
        {
            resultText.text = "Veuillez entrer un nombre compris entre 1 et 3.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande à l'utilisateur un nombre compris entre 1 et 3 jusqu'à ce que la réponse soit correcte.
# Exercice 5.2
Ecrire un algorithme qui demande un nombre compris entre 10 et 20, jusqu’à ce que la réponse convienne. En cas de réponse supérieure à 20, on fera apparaître un message : « Plus petit ! », et inversement, « Plus grand ! » si le nombre est inférieur à 10.
```
Variable N en Entier
Debut
N ← 0
Ecrire "Entrez un nombre entre 10 et 20"
TantQue N < 10 ou N > 20
  Lire N
  Si N < 10 Alors
    Ecrire "Plus grand !"
  SinonSi N > 20 Alors
    Ecrire "Plus petit !"
  FinSi
FinTantQue
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher la vérification du nombre :

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

public class Exercice5_2 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckNumber()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int number))
        {
            // Vérifier si le nombre est compris entre 10 et 20
            if (number >= 10 && number <= 20)
            {
                resultText.text = "Le nombre est valide.";
            }
            else if (number > 20)
            {
                resultText.text = "Plus petit !";
            }
            else
            {
                resultText.text = "Plus grand !";
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_2 -> CheckNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :
```c#

if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CheckNumber pour lire l'entrée, vérifier si le nombre est compris entre 10 et 20, et afficher le résultat :

```c#
public void CheckNumber()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int number))
    {
        if (number >= 10 && number <= 20)
        {
            resultText.text = "Le nombre est valide.";
        }
        else if (number > 20)
        {
            resultText.text = "Plus petit !";
        }
        else
        {
            resultText.text = "Plus grand !";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande à l'utilisateur un nombre compris entre 10 et 20 jusqu'à ce que la réponse soit correcte, et affiche des messages appropriés si le nombre est trop grand ou trop petit.
# Exercice 5.3
Ecrire un algorithme qui demande un nombre de départ, et qui ensuite affiche les dix nombres suivants. Par exemple, si l'utilisateur entre le nombre 17, le programme affichera les nombres de 18 à 27.

On peut imaginer deux variantes, strictement équivalentes :  
```
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Stop ← N+10
Ecrire "Les 10 nombres suivants sont : "
TantQue N < Stop
   N ← N+1
   Ecrire N
FinTantQue
Fin
```
Ou bien :

```
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
i ← 0
Ecrire "Les 10 nombres suivants sont : "
TantQue i < 10
   i ← i + 1
   Ecrire N + i
FinTantQue
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de départ :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher l'affichage des nombres suivants :

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

public class Exercice5_3 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre de départ
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void DisplayNextNumbers()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int startNumber))
        {
            // Afficher les dix nombres suivants
            string result = "";
            for (int i = 1; i <= 10; i++)
            {
                result += (startNumber + i).ToString() + " ";
            }
            resultText.text = "Les dix nombres suivants sont : " + result;
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_3 -> DisplayNextNumbers.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode DisplayNextNumbers pour lire l'entrée, calculer les dix nombres suivants, et afficher le résultat :

```c#
public void DisplayNextNumbers()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int startNumber))
    {
        string result = "";
        for (int i = 1; i <= 10; i++)
        {
            result += (startNumber + i).ToString() + " ";
        }
        resultText.text = "Les dix nombres suivants sont : " + result;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre de départ à l'utilisateur et affiche les dix nombres suivants.

# Exercice 5.4
Réécrire l'algorithme précédent, en utilisant cette fois l'instruction Pour

Là encore, deux variantes, correspondant trait pour trait à celles du corrigé précédent :
```
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Ecrire "Les 10 nombres suivants sont : "
Pour i ← N + 1 à N + 10
  Ecrire i
i Suivant
Fin
```
Ou bien :
```
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Ecrire "Les 10 nombres suivants sont : "
Pour i ← 1 à 10
  Ecrire N + i
i Suivant
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de départ :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher l'affichage des nombres suivants :

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

public class Exercice5_4 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre de départ
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void DisplayNextNumbers()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int startNumber))
        {
            // Afficher les dix nombres suivants
            string result = "";
            int currentNumber = startNumber + 1;
            int count = 0;

            while (count < 10)
            {
                result += currentNumber.ToString() + " ";
                currentNumber++;
                count++;
            }

            resultText.text = "Les dix nombres suivants sont : " + result;
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_4 -> DisplayNextNumbers.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode DisplayNextNumbers pour lire l'entrée, calculer les dix nombres suivants en utilisant une boucle while, et afficher le résultat :

```c#
public void DisplayNextNumbers()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int startNumber))
    {
        string result = "";
        int currentNumber = startNumber + 1;
        int count = 0;

        while (count < 10)
        {
            result += currentNumber.ToString() + " ";
            currentNumber++;
            count++;
        }

        resultText.text = "Les dix nombres suivants sont : " + result;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre de départ à l'utilisateur et affiche les dix nombres suivants en utilisant une boucle while.


# Exercice 5.5
Ecrire un algorithme qui demande un nombre de départ, et qui ensuite écrit la table de multiplication de ce nombre, présentée comme suit (cas où l'utilisateur entre le nombre 7) :
Table de 7 :  
7 x 1 = 7  
7 x 2 = 14  
7 x 3 = 21  
…  
7 x 10 = 70  
```
Variables N, i en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Ecrire "La table de multiplication de ce nombre est : "
Pour i ← 1 à 10
  Ecrire N, " x ", i, " = ", n*i
i Suivant
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de départ :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher l'affichage de la table de multiplication :

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

public class Exercice5_5 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre de départ
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void DisplayMultiplicationTable()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int startNumber))
        {
            // Afficher la table de multiplication
            string result = $"Table de {startNumber} :\n";
            for (int i = 1; i <= 10; i++)
            {
                result += $"{startNumber} x {i} = {startNumber * i}\n";
            }
            resultText.text = result;
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_5 -> DisplayMultiplicationTable.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode DisplayMultiplicationTable pour lire l'entrée, calculer la table de multiplication, et afficher le résultat :

```c#
public void DisplayMultiplicationTable()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int startNumber))
    {
        string result = $"Table de {startNumber} :\n";
        for (int i = 1; i <= 10; i++)
        {
            result += $"{startNumber} x {i} = {startNumber * i}\n";
        }
        resultText.text = result;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre de départ à l'utilisateur et affiche la table de multiplication de ce nombre.

# Exercice 5.6
Ecrire un algorithme qui demande un nombre de départ, et qui calcule la somme des entiers jusqu’à ce nombre. Par exemple, si l’on entre 5, le programme doit calculer :  
1 + 2 + 3 + 4 + 5 = 15  
NB : on souhaite afficher uniquement le résultat, pas la décomposition du calcul.  

```
Variables N, i, Som en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
Som ← 0
Pour i ← 1 à N
  Som ← Som + i
i Suivant
Ecrire "La somme est : ", Som
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de départ :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher le calcul de la somme :

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

public class Exercice5_6 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre de départ
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateSum()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int startNumber))
        {
            // Calculer la somme des entiers jusqu'à ce nombre
            int sum = 0;
            for (int i = 1; i <= startNumber; i++)
            {
                sum += i;
            }

            // Afficher le résultat
            resultText.text = "La somme des entiers jusqu'à " + startNumber + " est : " + sum;
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_6 -> CalculateSum.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CalculateSum pour lire l'entrée, calculer la somme des entiers jusqu'à ce nombre, et afficher le résultat :

```c#
public void CalculateSum()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int startNumber))
    {
        int sum = 0;
        for (int i = 1; i <= startNumber; i++)
        {
            sum += i;
        }
        resultText.text = "La somme des entiers jusqu'à " + startNumber + " est : " + sum;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre de départ à l'utilisateur et calcule la somme des entiers jusqu'à ce nombre, affichant uniquement le résultat.


# Exercice 5.7
Ecrire un algorithme qui demande un nombre de départ, et qui calcule sa factorielle.
NB : la factorielle de 8, notée 8 !, vaut  
1 x 2 x 3 x 4 x 5 x 6 x 7 x 8  

```
Variables N, i, F en Entier
Debut
Ecrire "Entrez un nombre : "
Lire N
F ← 1
Pour i ← 2 à N
  F ← F * i
i Suivant
Ecrire "La factorielle est : ", F
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de départ :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher le calcul de la factorielle :

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

public class Exercice5_7 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre de départ
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateFactorial()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int number))
        {
            // Calculer la factorielle
            long factorial = 1;
            for (int i = 1; i <= number; i++)
            {
                factorial *= i;
            }

            // Afficher le résultat
            resultText.text = "La factorielle de " + number + " est : " + factorial;
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_7 -> CalculateFactorial.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Number;
public Text resultText;
```
Vérification des références dans la méthode Start :
```c#

if (inputField_Number == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CalculateFactorial pour lire l'entrée, calculer la factorielle, et afficher le résultat :

```c#
public void CalculateFactorial()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int number))
    {
        long factorial = 1;
        for (int i = 1; i <= number; i++)
        {
            factorial *= i;
        }
        resultText.text = "La factorielle de " + number + " est : " + factorial;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre de départ à l'utilisateur et calcule sa factorielle, affichant uniquement le résultat.

# Exercice 5.8
Ecrire un algorithme qui demande successivement 20 nombres à l’utilisateur, et qui lui dise ensuite quel était le plus grand parmi ces 20 nombres :  
Entrez le nombre numéro 1 : 12  
Entrez le nombre numéro 2 : 14  
etc.  
Entrez le nombre numéro 20 : 6  
Le plus grand de ces nombres est  : 14  
Modifiez ensuite l’algorithme pour que le programme affiche de surcroît en quelle position avait été saisie ce nombre :  
C’était le nombre numéro 2  

```
Variables N, i, PG en Entier
Debut
PG ← 0
Pour i ← 1 à 20
  Ecrire "Entrez un nombre : "
  Lire N
  Si i = 1 ou N > PG Alors
    PG ← N
  FinSi
i Suivant
Ecrire "Le nombre le plus grand était : ", PG
Fin
```
En ligne 3, on peut mettre n’importe quoi dans PG, il suffit que cette variable soit affectée pour que le premier passage en ligne 7 ne provoque pas d'erreur.

Pour la version améliorée, cela donne :

```
Variables N, i, PG, IPG en Entier
Debut
PG ← 0
Pour i ← 1 à 20
  Ecrire "Entrez un nombre : "
  Lire N
  Si i = 1 ou N > PG Alors
    PG ← N
    IPG ← i
  FinSi
i Suivant
Ecrire "Le nombre le plus grand était : ", PG
Ecrire "Il a été saisi en position numéro ", IPG
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée des nombres :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher l'entrée du nombre suivant :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.Collections.Generic;

public class Exercice5_8 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour les nombres
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<int> numbers; // Liste pour stocker les nombres entrés
    private int currentIndex; // Index actuel pour suivre le nombre de nombres entrés
    private int maxNumber; // Le plus grand nombre
    private int maxIndex; // La position du plus grand nombre

    void Start()
    {
        // Initialiser les variables
        numbers = new List<int>();
        currentIndex = 0;
        maxNumber = int.MinValue;
        maxIndex = -1;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le nombre numéro 1 :";
    }

    public void EnterNumber()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int number))
        {
            // Ajouter le nombre à la liste
            numbers.Add(number);
            currentIndex++;

            // Mettre à jour le plus grand nombre et sa position
            if (number > maxNumber)
            {
                maxNumber = number;
                maxIndex = currentIndex;
            }

            // Vérifier si tous les nombres ont été entrés
            if (currentIndex < 20)
            {
                // Afficher l'instruction pour le nombre suivant
                resultText.text = "Entrez le nombre numéro " + (currentIndex + 1) + " :";
                inputField_Number.text = ""; // Effacer l'InputField pour la prochaine entrée
            }
            else
            {
                // Afficher le résultat
                resultText.text = "Le plus grand de ces nombres est : " + maxNumber + "\nC'était le nombre numéro " + maxIndex;
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_8 -> EnterNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Déclaration des variables privées pour stocker les nombres et suivre les indices :

```c#
private List<int> numbers;
private int currentIndex;
private int maxNumber;
private int maxIndex;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    numbers = new List<int>();
    currentIndex = 0;
    maxNumber = int.MinValue;
    maxIndex = -1;
    resultText.text = "Entrez le nombre numéro 1 :";
}
```
Méthode EnterNumber pour lire l'entrée, ajouter le nombre à la liste, mettre à jour le plus grand nombre et sa position, et afficher les instructions ou le résultat :

```c#
public void EnterNumber()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int number))
    {
        numbers.Add(number);
        currentIndex++;

        if (number > maxNumber)
        {
            maxNumber = number;
            maxIndex = currentIndex;
        }

        if (currentIndex < 20)
        {
            resultText.text = "Entrez le nombre numéro " + (currentIndex + 1) + " :";
            inputField_Number.text = "";
        }
        else
        {
            resultText.text = "Le plus grand de ces nombres est : " + maxNumber + "\nC'était le nombre numéro " + maxIndex;
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande successivement 20 nombres à l'utilisateur, détermine le plus grand nombre parmi ces 20 nombres, et affiche sa position.

# Exercice 5.9
Réécrire l’algorithme précédent, mais cette fois-ci on ne connaît pas d’avance combien l’utilisateur souhaite saisir de nombres. La saisie des nombres s’arrête lorsque l’utilisateur entre un zéro.  
```
Variables N, i, PG, IPG en Entier
Debut
N ← 1
i ← 0
PG ← 0
TantQue N <> 0
  Ecrire "Entrez un nombre : "
  Lire N
  i ← i + 1
  Si i = 1 ou N > PG Alors
    PG ← N
    IPG ← i
  FinSi
FinTantQue
Ecrire "Le nombre le plus grand était : ", PG
Ecrire "Il a été saisi en position numéro ", IPG
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée des nombres :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher l'entrée du nombre suivant :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.Collections.Generic;

public class Exercice5_9 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour les nombres
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<int> numbers; // Liste pour stocker les nombres entrés
    private int currentIndex; // Index actuel pour suivre le nombre de nombres entrés
    private int maxNumber; // Le plus grand nombre
    private int maxIndex; // La position du plus grand nombre

    void Start()
    {
        // Initialiser les variables
        numbers = new List<int>();
        currentIndex = 0;
        maxNumber = int.MinValue;
        maxIndex = -1;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le nombre numéro 1 :";
    }

    public void EnterNumber()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Number.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int number))
        {
            // Vérifier si l'utilisateur a entré zéro pour arrêter la saisie
            if (number == 0)
            {
                // Afficher le résultat
                resultText.text = "Le plus grand de ces nombres est : " + maxNumber + "\nC'était le nombre numéro " + maxIndex;
            }
            else
            {
                // Ajouter le nombre à la liste
                numbers.Add(number);
                currentIndex++;

                // Mettre à jour le plus grand nombre et sa position
                if (number > maxNumber)
                {
                    maxNumber = number;
                    maxIndex = currentIndex;
                }

                // Afficher l'instruction pour le nombre suivant
                resultText.text = "Entrez le nombre numéro " + (currentIndex + 1) + " :";
                inputField_Number.text = ""; // Effacer l'InputField pour la prochaine entrée
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
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Number du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_9 -> EnterNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number;
public Text resultText;
```
Déclaration des variables privées pour stocker les nombres et suivre les indices :

```c#
private List<int> numbers;
private int currentIndex;
private int maxNumber;
private int maxIndex;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    numbers = new List<int>();
    currentIndex = 0;
    maxNumber = int.MinValue;
    maxIndex = -1;
    resultText.text = "Entrez le nombre numéro 1 :";
}
```
Méthode EnterNumber pour lire l'entrée, ajouter le nombre à la liste, mettre à jour le plus grand nombre et sa position, et afficher les instructions ou le résultat :

```c#
public void EnterNumber()
{
    string input = inputField_Number.text;
    if (int.TryParse(input, out int number))
    {
        if (number == 0)
        {
            resultText.text = "Le plus grand de ces nombres est : " + maxNumber + "\nC'était le nombre numéro " + maxIndex;
        }
        else
        {
            numbers.Add(number);
            currentIndex++;

            if (number > maxNumber)
            {
                maxNumber = number;
                maxIndex = currentIndex;
            }

            resultText.text = "Entrez le nombre numéro " + (currentIndex + 1) + " :";
            inputField_Number.text = "";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur d'entrer un nombre indéterminé de nombres, s'arrête lorsque l'utilisateur entre un zéro, et affiche le plus grand nombre ainsi que sa position.
# Exercice 5.10
Lire la suite des prix (en euros entiers et terminée par zéro) des achats d’un client. Calculer la somme qu’il doit, lire la somme qu’il paye, et simuler la remise de la monnaie en affichant les textes "10 Euros", "5 Euros" et "1 Euro" autant de fois qu’il y a de coupures de chaque sorte à rendre.
```
Variables E, somdue, M, Reste, Nb10E, Nb5E En Entier
Debut
E ← 1
somdue ← 0
TantQue E <> 0
  Ecrire "Entrez le montant : "
  Lire E
  somdue ← somdue + E
FinTantQue
Ecrire "Vous devez :", somdue, " euros"
Ecrire "Montant versé :"
Lire M
Reste ← M - somdue
Nb10E ← 0
TantQue Reste >= 10
  Nb10E ← Nb10E + 1
  Reste ← Reste – 10
FinTantQue
Nb5E ← 0
Si Reste >= 5
  Nb5E ← 1
  Reste ← Reste – 5
FinSi
Ecrire "Rendu de la monnaie :"
Ecrire "Billets de 10 E : ", Nb10E
Ecrire "Billets de  5 E : ", Nb5E
Ecrire "Pièces de 1 E : ", reste
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée des prix :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Price.
Ajouter un InputField pour l'entrée de la somme payée :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_PaidAmount.
Désactivez-le initialement (décocher la case Active dans l'inspecteur).
Ajouter un Button pour déclencher l'entrée du prix suivant :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterPrice.
Ajouter un Button pour déclencher l'entrée de la somme payée :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EnterPaidAmount.
Désactivez-le initialement (décocher la case Active dans l'inspecteur).
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

public class Exercice5_10 : MonoBehaviour
{
    public InputField inputField_Price; // Référence à l'InputField pour les prix
    public InputField inputField_PaidAmount; // Référence à l'InputField pour la somme payée
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    private List<int> prices; // Liste pour stocker les prix entrés
    private int totalAmount; // Somme totale des prix
    private int paidAmount; // Somme payée par le client
    private bool isPriceEntry; // Indicateur pour savoir si l'entrée des prix est terminée

    void Start()
    {
        // Initialiser les variables
        prices = new List<int>();
        totalAmount = 0;
        paidAmount = 0;
        isPriceEntry = true;

        // Afficher l'instruction initiale
        resultText.text = "Entrez le prix de l'achat numéro 1 :";
    }

    public void EnterPrice()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Price.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int price))
        {
            // Vérifier si l'utilisateur a entré zéro pour arrêter la saisie des prix
            if (price == 0)
            {
                isPriceEntry = false;
                resultText.text = "Entrez la somme payée :";
                inputField_PaidAmount.gameObject.SetActive(true);
                inputField_Price.gameObject.SetActive(false);
                inputField_PaidAmount.text = ""; // Effacer l'InputField pour la prochaine entrée
            }
            else
            {
                // Ajouter le prix à la liste et mettre à jour la somme totale
                prices.Add(price);
                totalAmount += price;

                // Afficher l'instruction pour le prix suivant
                resultText.text = "Entrez le prix de l'achat numéro " + (prices.Count + 1) + " :";
                inputField_Price.text = ""; // Effacer l'InputField pour la prochaine entrée
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un prix valide.";
        }
    }

    public void EnterPaidAmount()
    {
        // Lire la valeur de l'InputField
        string input = inputField_PaidAmount.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int amount))
        {
            paidAmount = amount;

            // Calculer la monnaie à rendre
            int change = paidAmount - totalAmount;
            if (change >= 0)
            {
                // Simuler la remise de la monnaie
                resultText.text = "Monnaie à rendre :\n";
                int tenEuros = change / 10;
                change %= 10;
                int fiveEuros = change / 5;
                change %= 5;
                int oneEuros = change;

                for (int i = 0; i < tenEuros; i++)
                {
                    resultText.text += "10 Euros\n";
                }
                for (int i = 0; i < fiveEuros; i++)
                {
                    resultText.text += "5 Euros\n";
                }
                for (int i = 0; i < oneEuros; i++)
                {
                    resultText.text += "1 Euro\n";
                }
            }
            else
            {
                resultText.text = "La somme payée est insuffisante.";
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer une somme valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField pour les prix (InputField_Price) dans le champ InputField_Price du script.
Faites glisser l'InputField pour la somme payée (InputField_PaidAmount) dans le champ InputField_PaidAmount du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter des fonctions aux boutons
Sélectionnez le Button pour entrer les prix (Button_EnterPrice) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice5_10 -> EnterPrice.

Sélectionnez le Button pour entrer la somme payée (Button_EnterPaidAmount) dans la scène.

Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.

Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().

Faites glisser le GameObject contenant le script dans le champ vide.

Dans le menu déroulant, sélectionnez Exercice5_10 -> EnterPaidAmount.

Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Price;
public InputField inputField_PaidAmount;
public Text resultText;
```
Déclaration des variables privées pour stocker les prix, la somme totale, la somme payée et l'indicateur de saisie des prix :

```c#
private List<int> prices;
private int totalAmount;
private int paidAmount;
private bool isPriceEntry;
```
Initialisation des variables dans la méthode Start :

```c#
void Start()
{
    prices = new List<int>();
    totalAmount = 0;
    paidAmount = 0;
    isPriceEntry = true;
    resultText.text = "Entrez le prix de l'achat numéro 1 :";
}
```
Méthode EnterPrice pour lire l'entrée des prix, ajouter le prix à la liste, mettre à jour la somme totale, et afficher les instructions ou le résultat :
```c#

public void EnterPrice()
{
    string input = inputField_Price.text;
    if (int.TryParse(input, out int price))
    {
        if (price == 0)
        {
            isPriceEntry = false;
            resultText.text = "Entrez la somme payée :";
            inputField_PaidAmount.gameObject.SetActive(true);
            inputField_Price.gameObject.SetActive(false);
            inputField_PaidAmount.text = "";
        }
        else
        {
            prices.Add(price);
            totalAmount += price;
            resultText.text = "Entrez le prix de l'achat numéro " + (prices.Count + 1) + " :";
            inputField_Price.text = "";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un prix valide.";
    }
}
```
Méthode EnterPaidAmount pour lire l'entrée de la somme payée, calculer la monnaie à rendre, et afficher le résultat :

```c#
public void EnterPaidAmount()
{
    string input = inputField_PaidAmount.text;
    if (int.TryParse(input, out int amount))
    {
        paidAmount = amount;
        int change = paidAmount - totalAmount;
        if (change >= 0)
        {
            resultText.text = "Monnaie à rendre :\n";
            int tenEuros = change / 10;
            change %= 10;
            int fiveEuros = change / 5;
            change %= 5;
            int oneEuros = change;

            for (int i = 0; i < tenEuros; i++)
            {
                resultText.text += "10 Euros\n";
            }
            for (int i = 0; i < fiveEuros; i++)
            {
                resultText.text += "5 Euros\n";
            }
            for (int i = 0; i < oneEuros; i++)
            {
                resultText.text += "1 Euro\n";
            }
        }
        else
        {
            resultText.text = "La somme payée est insuffisante.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une somme valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui lit une suite de prix des achats d'un client, calcule la somme qu'il doit, lit la somme qu'il paye, et simule la remise de la monnaie en affichant les textes "10 Euros", "5 Euros" et "1 Euro" autant de fois qu'il y a de coupures de chaque sorte à rendre.

# Exercice 5.11
Écrire un algorithme qui permette de connaître ses chances de gagner au tiercé, quarté, quinté et autres impôts volontaires.  
On demande à l’utilisateur le nombre de chevaux partants, et le nombre de chevaux joués. Les deux messages affichés devront être :  
Dans l’ordre : une chance sur X de gagner
Dans le désordre : une chance sur Y de gagner
X et Y nous sont donnés par la formule suivante, si n est le nombre de chevaux partants et p le nombre de chevaux joués (on rappelle que le signe ! signifie "factorielle", comme dans l'exercice 5.7 ci-dessus) : 
``` 
X = n ! / (n - p) !
Y = n ! / (p ! * (n – p) !)
```
NB : cet algorithme peut être écrit d’une manière simple, mais relativement peu performante. Ses performances peuvent être singulièrement augmentées par une petite astuce. Vous commencerez par écrire la manière la plus simple, puis vous identifierez le problème, et écrirez une deuxième version permettant de le résoudre.

<hr>

Spontanément, on est tenté d'écrire l'algorithme suivant :
```
Variables N, P, i, Numé, Déno1, Déno2 en Entier
Debut Ecrire "Entrez le nombre de chevaux partants : "
Lire N
Ecrire "Entrez le nombre de chevaux joués : "
Lire P
Numé ← 1
Pour i ← 2 à N
  Numé ← Numé * i
i Suivant
Déno1 ← 1
Pour i ← 2 à N-P
  Déno1 ← Déno1 * i
i Suivant
Déno2 ← 1
Pour i ← 2 à P
  Déno2 ← Déno2 * i
i Suivant
Ecrire "Dans l’ordre, une chance sur ", Numé / Déno1
Ecrire "Dans le désordre, une sur ", Numé / (Déno1 * Déno2)
Fin
```

Cette version, formellement juste, comporte tout de même deux faiblesses.

La première, et la plus grave, concerne la manière dont elle calcule le résultat final. Celui-ci est le quotient d'un nombre par un autre ; or, ces nombres auront rapidement tendance à être très grands. En calculant, comme on le fait ici, d'abord le numérateur, puis ensuite le dénominateur, on prend le risque de demander à la machine de stocker des nombres trop grands pour qu'elle soit capable de les coder (cf. le préambule). C'est d'autant plus bête que rien ne nous oblige à procéder ainsi : on n'est pas obligé de passer par la division de deux très grands nombres pour obtenir le résultat voulu.

La deuxième remarque est qu'on a programmé ici trois boucles successives. Or, en y regardant bien, on peut voir qu'après simplification de la formule, ces trois boucles comportent le même nombre de tours ! (si vous ne me croyez pas, écrivez un exemple de calcul et biffez les nombres identiques au numérateur et au dénominateur). Ce triple calcul (ces trois boucles) peut donc être ramené(es) à un(e) seul(e). Et voilà le travail, qui est non seulement bien plus court, mais aussi plus performant :
```
Variables N, P, i, A, B en Numérique
Debut
Ecrire "Entrez le nombre de chevaux partants : "
Lire N
Ecrire "Entrez le nombre de chevaux joués : "
Lire P
A ← 1
B ← 1
Pour i ← 1 à P
  A ← A * (i + N - P)
  B ← B * i
i Suivant
Ecrire "Dans l’ordre, une chance sur ", A
Ecrire "Dans le désordre, une chance sur ", A / B
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de chevaux partants :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Horses.
Ajouter un InputField pour l'entrée du nombre de chevaux joués :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Played.
Ajouter un Button pour déclencher le calcul des chances :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_Calculate.
Ajouter un Text pour afficher les instructions et le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice5_11 : MonoBehaviour
{
    public InputField inputField_Horses; // Référence à l'InputField pour le nombre de chevaux partants
    public InputField inputField_Played; // Référence à l'InputField pour le nombre de chevaux joués
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Horses == null || inputField_Played == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateChances()
    {
        // Lire les valeurs des InputField
        string horsesInput = inputField_Horses.text;
        string playedInput = inputField_Played.text;

        // Convertir les valeurs en nombres
        if (int.TryParse(horsesInput, out int n) && int.TryParse(playedInput, out int p))
        {
            // Vérifier que les valeurs sont valides
            if (n >= p && p > 0)
            {
                // Calculer les chances de gagner
                long X = Factorial(n) / Factorial(n - p);
                long Y = Factorial(n) / (Factorial(p) * Factorial(n - p));

                // Afficher les résultats
                resultText.text = "Dans l’ordre : une chance sur " + X + " de gagner\n" +
                                  "Dans le désordre : une chance sur " + Y + " de gagner";
            }
            else
            {
                resultText.text = "Veuillez entrer des valeurs valides.";
            }
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas des nombres valides
            resultText.text = "Veuillez entrer des nombres valides.";
        }
    }

    // Méthode pour calculer la factorielle d'un nombre
    private long Factorial(int number)
    {
        long result = 1;
        for (int i = 1; i <= number; i++)
        {
            result *= i;
        }
        return result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField pour le nombre de chevaux partants (InputField_Horses) dans le champ InputField_Horses du script.
Faites glisser l'InputField pour le nombre de chevaux joués (InputField_Played) dans le champ InputField_Played du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour calculer les chances (Button_Calculate) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice5_11 -> CalculateChances.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Horses;
public InputField inputField_Played;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Horses == null || inputField_Played == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CalculateChances pour lire les entrées, vérifier les valeurs, calculer les chances de gagner, et afficher les résultats :

```c#
public void CalculateChances()
{
    string horsesInput = inputField_Horses.text;
    string playedInput = inputField_Played.text;

    if (int.TryParse(horsesInput, out int n) && int.TryParse(playedInput, out int p))
    {
        if (n >= p && p > 0)
        {
            long X = Factorial(n) / Factorial(n - p);
            long Y = Factorial(n) / (Factorial(p) * Factorial(n - p));

            resultText.text = "Dans l’ordre : une chance sur " + X + " de gagner\n" +
                              "Dans le désordre : une chance sur " + Y + " de gagner";
        }
        else
        {
            resultText.text = "Veuillez entrer des valeurs valides.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer des nombres valides.";
    }
}
Méthode Factorial pour calculer la factorielle d'un nombre :


private long Factorial(int number)
{
    long result = 1;
    for (int i = 1; i <= number; i++)
    {
        result *= i;
    }
    return result;
}
```
Optimisation de la performance
Pour améliorer les performances, nous pouvons éviter de calculer les factorielles de manière répétitive. Nous pouvons utiliser une approche plus efficace en utilisant des boucles pour calculer directement les valeurs de X et Y sans recalculer les factorielles.

Voici la version optimisée du script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice5_11_Optimized : MonoBehaviour
{
    public InputField inputField_Horses; // Référence à l'InputField pour le nombre de chevaux partants
    public InputField inputField_Played; // Référence à l'InputField pour le nombre de chevaux joués
    public Text resultText; // Référence au Text pour afficher les instructions et le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Horses == null || inputField_Played == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateChances()
    {
        // Lire les valeurs des InputField
        string horsesInput = inputField_Horses.text;
        string playedInput = inputField_Played.text;

        // Convertir les valeurs en nombres
        if (int.TryParse(horsesInput, out int n) && int.TryParse(playedInput, out int p))
        {
            // Vérifier que les valeurs sont valides
            if (n >= p && p > 0)
            {
                // Calculer les chances de gagner de manière optimisée
                long X = 1;
                long Y = 1;

                for (int i = n; i > n - p; i--)
                {
                    X *= i;
                }

                for (int i = n; i > p; i--)
                {
                    Y *= i;
                }

                Y /= Factorial(p);

                // Afficher les résultats
                resultText.text = "Dans l’ordre : une chance sur " + X + " de gagner\n" +
                                  "Dans le désordre : une chance sur " + Y + " de gagner";
            }
            else
            {
                resultText.text = "Veuillez entrer des valeurs valides.";
            }
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas des nombres valides
            resultText.text = "Veuillez entrer des nombres valides.";
        }
    }

    // Méthode pour calculer la factorielle d'un nombre
    private long Factorial(int number)
    {
        long result = 1;
        for (int i = 1; i <= number; i++)
        {
            result *= i;
        }
        return result;
    }
}
```
Explication de l'optimisation  
Calcul direct de X et Y :
```c#
long X = 1;
long Y = 1;

for (int i = n; i > n - p; i--)
{
    X *= i;
}

for (int i = n; i > p; i--)
{
    Y *= i;
}

Y /= Factorial(p);
```
En suivant ces étapes, vous aurez un programme Unity qui calcule les chances de gagner au tiercé, quarté, quinté, etc., en fonction du nombre de chevaux partants et du nombre de chevaux joués, avec une version optimisée pour améliorer les performances.