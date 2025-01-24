# Exercice 3.1
Ecrire un algorithme qui demande un nombre à l’utilisateur, et l’informe ensuite si ce nombre est positif ou négatif (on laisse de côté le cas où le nombre vaut zéro).
```
Variable n en Entier
Début
Ecrire "Entrez un nombre : "
Lire n
Si n > 0 Alors
  Ecrire "Ce nombre est positif”
Sinon
  Ecrire "Ce nombre est négatif"
Finsi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher la vérification :

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

public class Exercice3_1 : MonoBehaviour
{
    public InputField inputField; // Référence à l'InputField
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckNumber()
    {
        // Lire la valeur de l'InputField
        string input = inputField.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float number))
        {
            // Vérifier si le nombre est positif ou négatif
            if (number > 0)
            {
                resultText.text = "Le nombre est positif.";
            }
            else if (number < 0)
            {
                resultText.text = "Le nombre est négatif.";
            }
            else
            {
                resultText.text = "Le nombre est zéro.";
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
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice3_1 -> CheckNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField;
public Text resultText;
Vérification des références dans la méthode Start :


if (inputField == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CheckNumber pour lire l'entrée, vérifier si le nombre est positif ou négatif, et afficher le résultat :


public void CheckNumber()
{
    string input = inputField.text;
    if (float.TryParse(input, out float number))
    {
        if (number > 0)
        {
            resultText.text = "Le nombre est positif.";
        }
        else if (number < 0)
        {
            resultText.text = "Le nombre est négatif.";
        }
        else
        {
            resultText.text = "Le nombre est zéro.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre à l'utilisateur et l'informe si ce nombre est positif ou négatif.

# Exercice 3.2
Ecrire un algorithme qui demande deux nombres à l’utilisateur et l’informe ensuite si leur produit est négatif ou positif (on laisse de côté le cas où le produit est nul). Attention toutefois : on ne doit pas calculer le produit des deux nombres.
```
Variables m, n en Entier
Début
Ecrire "Entrez deux nombres : "
Lire m, n
Si (m > 0 ET n > 0) OU (m < 0 ET n < 0) Alors
  Ecrire "Leur produit est positif"
Sinon
  Ecrire "Leur produit est négatif"
Finsi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter deux InputField pour l'entrée des deux nombres :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Number1, InputField_Number2).
Ajouter un Button pour déclencher la vérification :

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

public class Exercice3_2 : MonoBehaviour
{
    public InputField inputField_Number1; // Référence à l'InputField pour le premier nombre
    public InputField inputField_Number2; // Référence à l'InputField pour le deuxième nombre
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number1 == null || inputField_Number2 == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckProductSign()
    {
        // Lire les valeurs des InputField
        string input1 = inputField_Number1.text;
        string input2 = inputField_Number2.text;

        // Convertir les valeurs en nombres
        if (float.TryParse(input1, out float number1) && float.TryParse(input2, out float number2))
        {
            // Vérifier le signe du produit sans le calculer
            if ((number1 > 0 && number2 > 0) || (number1 < 0 && number2 < 0))
            {
                resultText.text = "Le produit est positif.";
            }
            else if ((number1 > 0 && number2 < 0) || (number1 < 0 && number2 > 0))
            {
                resultText.text = "Le produit est négatif.";
            }
            else
            {
                resultText.text = "Le produit est nul.";
            }
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer des nombres valides.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Number1 et InputField_Number2 du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice3_2 -> CheckProductSign.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Number1;
public InputField inputField_Number2;
public Text resultText;
Vérification des références dans la méthode Start :


if (inputField_Number1 == null || inputField_Number2 == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CheckProductSign pour lire les entrées, vérifier le signe du produit sans le calculer, et afficher le résultat :


public void CheckProductSign()
{
    string input1 = inputField_Number1.text;
    string input2 = inputField_Number2.text;

    if (float.TryParse(input1, out float number1) && float.TryParse(input2, out float number2))
    {
        if ((number1 > 0 && number2 > 0) || (number1 < 0 && number2 < 0))
        {
            resultText.text = "Le produit est positif.";
        }
        else if ((number1 > 0 && number2 < 0) || (number1 < 0 && number2 > 0))
        {
            resultText.text = "Le produit est négatif.";
        }
        else
        {
            resultText.text = "Le produit est nul.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer des nombres valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande deux nombres à l'utilisateur et l'informe si leur produit est négatif ou positif, sans calculer le produit des deux nombres.
# Exercice 3.3
Ecrire un algorithme qui demande trois noms à l’utilisateur et l’informe ensuite s’ils sont rangés ou non dans l’ordre alphabétique.
```
Variables a, b, c en Caractère
Début
Ecrire "Entrez successivement trois noms : "
Lire a, b, c
Si a < b ET b < c Alors
  Ecrire "Ces noms sont classés alphabétiquement"
Sinon
  Ecrire "Ces noms ne sont pas classés"
Finsi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter trois InputField pour l'entrée des trois noms :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Name1, InputField_Name2, InputField_Name3).
Ajouter un Button pour déclencher la vérification :

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

public class Exercice3_3 : MonoBehaviour
{
    public InputField inputField_Name1; // Référence à l'InputField pour le premier nom
    public InputField inputField_Name2; // Référence à l'InputField pour le deuxième nom
    public InputField inputField_Name3; // Référence à l'InputField pour le troisième nom
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Name1 == null || inputField_Name2 == null || inputField_Name3 == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckAlphabeticalOrder()
    {
        // Lire les valeurs des InputField
        string name1 = inputField_Name1.text;
        string name2 = inputField_Name2.text;
        string name3 = inputField_Name3.text;

        // Vérifier si les noms sont dans l'ordre alphabétique
        if (string.Compare(name1, name2, StringComparison.Ordinal) <= 0 &&
            string.Compare(name2, name3, StringComparison.Ordinal) <= 0)
        {
            resultText.text = "Les noms sont dans l'ordre alphabétique.";
        }
        else
        {
            resultText.text = "Les noms ne sont pas dans l'ordre alphabétique.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Name1, InputField_Name2, et InputField_Name3 du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice3_3 -> CheckAlphabeticalOrder.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Name1;
public InputField inputField_Name2;
public InputField inputField_Name3;
public Text resultText;
Vérification des références dans la méthode Start :


if (inputField_Name1 == null || inputField_Name2 == null || inputField_Name3 == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CheckAlphabeticalOrder pour lire les entrées, vérifier si les noms sont dans l'ordre alphabétique, et afficher le résultat :


public void CheckAlphabeticalOrder()
{
    string name1 = inputField_Name1.text;
    string name2 = inputField_Name2.text;
    string name3 = inputField_Name3.text;

    if (string.Compare(name1, name2, StringComparison.Ordinal) <= 0 &&
        string.Compare(name2, name3, StringComparison.Ordinal) <= 0)
    {
        resultText.text = "Les noms sont dans l'ordre alphabétique.";
    }
    else
    {
        resultText.text = "Les noms ne sont pas dans l'ordre alphabétique.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande trois noms à l'utilisateur et l'informe si ces noms sont rangés dans l'ordre alphabétique.

# Exercice 3.4
Ecrire un algorithme qui demande un nombre à l’utilisateur, et l’informe ensuite si ce nombre est positif ou négatif (on inclut cette fois le traitement du cas où le nombre vaut zéro).
```
Variable n en Entier
Début
Ecrire "Entrez un nombre : "
Lire n
Si n < 0 Alors
  Ecrire "Ce nombre est négatif"
SinonSi n = 0 Alors
  Ecrire "Ce nombre est nul"
Sinon
  Ecrire "Ce nombre est positif"
Finsi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher la vérification :

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

public class Exercice3_4 : MonoBehaviour
{
    public InputField inputField; // Référence à l'InputField
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckNumber()
    {
        // Lire la valeur de l'InputField
        string input = inputField.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float number))
        {
            // Vérifier si le nombre est positif, négatif ou zéro
            if (number > 0)
            {
                resultText.text = "Le nombre est positif.";
            }
            else if (number < 0)
            {
                resultText.text = "Le nombre est négatif.";
            }
            else
            {
                resultText.text = "Le nombre est zéro.";
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
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice3_4 -> CheckNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField;
public Text resultText;
Vérification des références dans la méthode Start :


if (inputField == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CheckNumber pour lire l'entrée, vérifier si le nombre est positif, négatif ou zéro, et afficher le résultat :


public void CheckNumber()
{
    string input = inputField.text;
    if (float.TryParse(input, out float number))
    {
        if (number > 0)
        {
            resultText.text = "Le nombre est positif.";
        }
        else if (number < 0)
        {
            resultText.text = "Le nombre est négatif.";
        }
        else
        {
            resultText.text = "Le nombre est zéro.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre à l'utilisateur et l'informe si ce nombre est positif, négatif ou égal à zéro.

# Exercice 3.5
Ecrire un algorithme qui demande deux nombres à l’utilisateur et l’informe ensuite si le produit est négatif ou positif (on inclut cette fois le traitement du cas où le produit peut être nul). Attention toutefois, on ne doit pas calculer le produit !
```
Variables m, n en Entier
Début
Ecrire "Entrez deux nombres : "
Lire m, n
Si m = 0 OU n = 0 Alors
  Ecrire "Le produit est nul"
SinonSi (m < 0 ET n < 0) OU (m > 0 ET n > 0) Alors
  Ecrire "Le produit est positif"
Sinon
  Ecrire "Le produit est négatif"
Finsi
Fin
Si on souhaite simplifier l’écriture de la condition lourde du SinonSi, on peut toujours passer par des variables booléennes intermédiaires. Une astuce de sioux consiste également à employer un Xor (c'est l'un des rares cas dans lesquels il est pertinent)
```
Étape 1 : Créer l'interface utilisateur
Ajouter deux InputField pour l'entrée des deux nombres :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Number1, InputField_Number2).
Ajouter un Button pour déclencher la vérification :

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

public class Exercice3_5 : MonoBehaviour
{
    public InputField inputField_Number1; // Référence à l'InputField pour le premier nombre
    public InputField inputField_Number2; // Référence à l'InputField pour le deuxième nombre
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Number1 == null || inputField_Number2 == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckProductSign()
    {
        // Lire les valeurs des InputField
        string input1 = inputField_Number1.text;
        string input2 = inputField_Number2.text;

        // Convertir les valeurs en nombres
        if (float.TryParse(input1, out float number1) && float.TryParse(input2, out float number2))
        {
            // Vérifier le signe du produit sans le calculer
            if (number1 == 0 || number2 == 0)
            {
                resultText.text = "Le produit est nul.";
            }
            else if ((number1 > 0 && number2 > 0) || (number1 < 0 && number2 < 0))
            {
                resultText.text = "Le produit est positif.";
            }
            else
            {
                resultText.text = "Le produit est négatif.";
            }
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer des nombres valides.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Number1 et InputField_Number2 du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice3_5 -> CheckProductSign.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Number1;
public InputField inputField_Number2;
public Text resultText;
Vérification des références dans la méthode Start :


if (inputField_Number1 == null || inputField_Number2 == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CheckProductSign pour lire les entrées, vérifier le signe du produit sans le calculer, et afficher le résultat :


public void CheckProductSign()
{
    string input1 = inputField_Number1.text;
    string input2 = inputField_Number2.text;

    if (float.TryParse(input1, out float number1) && float.TryParse(input2, out float number2))
    {
        if (number1 == 0 || number2 == 0)
        {
            resultText.text = "Le produit est nul.";
        }
        else if ((number1 > 0 && number2 > 0) || (number1 < 0 && number2 < 0))
        {
            resultText.text = "Le produit est positif.";
        }
        else
        {
            resultText.text = "Le produit est négatif.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer des nombres valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande deux nombres à l'utilisateur et l'informe si le produit est négatif, positif ou nul, sans calculer le produit des deux nombres.
# Exercice 3.6
Ecrire un algorithme qui demande l’âge d’un enfant à l’utilisateur. Ensuite, il l’informe de sa catégorie :  
"Poussin" de 6 à 7 ans  
"Pupille" de 8 à 9 ans  
"Minime" de 10 à 11 ans  
"Cadet" après 12 ans  
Peut-on concevoir plusieurs algorithmes équivalents menant à ce résultat ?

```
Variable age en Entier
Début
Ecrire "Entrez l’âge de l’enfant : "
Lire age
Si age >= 12 Alors
  Ecrire "Catégorie Cadet"
SinonSi age >= 10 Alors
  Ecrire "Catégorie Minime"
SinonSi age >= 8 Alors
  Ecrire "Catégorie Pupille"
SinonSi age >= 6 Alors
  Ecrire "Catégorie Poussin"
Finsi
Fin
On peut évidemment écrire cet algorithme de différentes façons, ne serait-ce qu’en commençant par la catégorie la plus jeune.
```
Algorithme 1 : Utilisation de structures conditionnelles if-else
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de l'âge :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher la vérification :

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

public class Exercice3_6 : MonoBehaviour
{
    public InputField inputField_Age; // Référence à l'InputField pour l'âge
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Age == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void DetermineCategory()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Age.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int age))
        {
            // Déterminer la catégorie en fonction de l'âge
            if (age >= 6 && age <= 7)
            {
                resultText.text = "Catégorie : Poussin";
            }
            else if (age >= 8 && age <= 9)
            {
                resultText.text = "Catégorie : Pupille";
            }
            else if (age >= 10 && age <= 11)
            {
                resultText.text = "Catégorie : Minime";
            }
            else if (age >= 12)
            {
                resultText.text = "Catégorie : Cadet";
            }
            else
            {
                resultText.text = "L'âge n'est pas dans les catégories définies.";
            }
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un âge valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Age du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice3_6 -> DetermineCategory.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Age;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Age == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode DetermineCategory pour lire l'entrée, déterminer la catégorie en fonction de l'âge, et afficher le résultat :

```c#
public void DetermineCategory()
{
    string input = inputField_Age.text;
    if (int.TryParse(input, out int age))
    {
        if (age >= 6 && age <= 7)
        {
            resultText.text = "Catégorie : Poussin";
        }
        else if (age >= 8 && age <= 9)
        {
            resultText.text = "Catégorie : Pupille";
        }
        else if (age >= 10 && age <= 11)
        {
            resultText.text = "Catégorie : Minime";
        }
        else if (age >= 12)
        {
            resultText.text = "Catégorie : Cadet";
        }
        else
        {
            resultText.text = "L'âge n'est pas dans les catégories définies.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un âge valide.";
    }
}
```
Algorithme 2 : Utilisation d'un tableau de correspondance
Une autre approche consiste à utiliser un tableau de correspondance pour mapper les âges aux catégories. Voici comment vous pouvez le faire :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice3_6_Alternative : MonoBehaviour
{
    public InputField inputField_Age; // Référence à l'InputField pour l'âge
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Age == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void DetermineCategory()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Age.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int age))
        {
            // Tableau de correspondance
            string[] categories = { "Poussin", "Poussin", "Pupille", "Pupille", "Minime", "Minime", "Cadet" };
            int[] ageRanges = { 6, 7, 8, 9, 10, 11, 12 };

            // Déterminer la catégorie en fonction de l'âge
            string category = "L'âge n'est pas dans les catégories définies.";
            for (int i = 0; i < ageRanges.Length; i++)
            {
                if (age == ageRanges[i])
                {
                    category = categories[i];
                    break;
                }
            }

            resultText.text = "Catégorie : " + category;
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un âge valide.";
        }
    }
}
```
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Age;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Age == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode DetermineCategory pour lire l'entrée, déterminer la catégorie en fonction de l'âge en utilisant un tableau de correspondance, et afficher le résultat :

```c#
public void DetermineCategory()
{
    string input = inputField_Age.text;
    if (int.TryParse(input, out int age))
    {
        string[] categories = { "Poussin", "Poussin", "Pupille", "Pupille", "Minime", "Minime", "Cadet" };
        int[] ageRanges = { 6, 7, 8, 9, 10, 11, 12 };

        string category = "L'âge n'est pas dans les catégories définies.";
        for (int i = 0; i < ageRanges.Length; i++)
        {
            if (age == ageRanges[i])
            {
                category = categories[i];
                break;
            }
        }

        resultText.text = "Catégorie : " + category;
    }
    else
    {
        resultText.text = "Veuillez entrer un âge valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande l'âge d'un enfant à l'utilisateur et l'informe de sa catégorie en utilisant deux approches différentes.