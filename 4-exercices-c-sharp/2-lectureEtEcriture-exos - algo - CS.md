# Exercice 2.1
Quel résultat produit le programme suivant ?
```
Variables val, double numériques
Début
Val ← 231
Double ← Val * 2
Ecrire Val
Ecrire Double
Fin
```
On verra apparaître à l’écran 231, puis 462 (qui vaut 231 * 2)
```c#
using UnityEngine;

public class Exercice2_1 : MonoBehaviour
{
    void Start()
    {
        int val;
        int doubleVal;

        val = 231; // Valeur initiale de val
        doubleVal = val * 2; // Calcul de doubleVal

        Debug.Log("Val = " + val); // Affichera : Val = 231
        Debug.Log("Double = " + doubleVal); // Affichera : Double = 462
    }
}
```
Explication du code C#
Déclaration des variables val et doubleVal :

```c#
int val;
int doubleVal;
```
Initialisation de val :

```c#
val = 231;
```
Calcul de doubleVal :

```c#
doubleVal = val * 2;
```
Affichage des valeurs :

```c#
Debug.Log("Val = " + val); // Affichera : Val = 231
Debug.Log("Double = " + doubleVal); // Affichera : Double = 462
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de val et doubleVal seront affichées dans la console de Unity. La valeur de val sera 231 et la valeur de doubleVal sera 462.

# Exercice 2.2
Ecrire un programme qui demande un nombre à l’utilisateur, puis qui calcule et  affiche le carré de ce nombre.
```
Variables nb, carr en Entier
Début
Ecrire "Entrez un nombre :"
Lire nb
carr ← nb * nb
Ecrire "Son carré est : ", carr
Fin
En fait, on pourrait tout aussi bien économiser la variable carr en remplaçant les deux avant-dernières lignes par :
Ecrire "Son carré est : ", nb*nb
C'est une question de style ; dans un cas, on privilégie la lisibilité de l'algorithme, dans l'autre, on privilégie l'économie d'une variable.
```
Étape 1 : Créer l'interface utilisateur
Dans Unity, vous pouvez créer l'interface utilisateur en utilisant des éléments UI comme InputField, Button, et Text.

Ajouter un InputField pour l'entrée du nombre :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher le calcul :

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

public class Exercice2_2 : MonoBehaviour
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

    public void CalculateSquare()
    {
        // Lire la valeur de l'InputField
        string input = inputField.text;

        // Convertir la valeur en nombre
        if (float.TryParse(input, out float number))
        {
            // Calculer le carré du nombre
            float square = number * number;

            // Afficher le résultat
            resultText.text = "Le carré de " + number + " est " + square;
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
Dans le menu déroulant, sélectionnez Exercice2_2 -> CalculateSquare.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CalculateSquare pour lire l'entrée, calculer le carré et afficher le résultat :


public void CalculateSquare()
{
    string input = inputField.text;
    if (float.TryParse(input, out float number))
    {
        float square = number * number;
        resultText.text = "Le carré de " + number + " est " + square;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre à l'utilisateur, calcule le carré de ce nombre, et affiche le résultat.

# Exercice 2.3
Ecrire un programme qui demande son prénom à l'utilisateur, et qui lui réponde par un charmant « Bonjour » suivi du prénom. On aura ainsi le dialogue suivant :

machine : Quel est votre prénom ?
utilisateur : Marie-Cunégonde
machine : Bonjour, Marie Cunégonde !

```
Variable prenom en Caractere
Début
Ecrire "Quel est votre prenom ?"
Lire Prenom
Ecrire "Bonjour ", Prenom, " !"
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du prénom :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher la salutation :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher le message de salutation :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice2_3 : MonoBehaviour
{
    public InputField inputField; // Référence à l'InputField
    public Text resultText; // Référence au Text pour afficher le message de salutation

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void GreetUser()
    {
        // Lire la valeur de l'InputField
        string name = inputField.text;

        // Afficher le message de salutation
        resultText.text = "Bonjour, " + name + " !";
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
Dans le menu déroulant, sélectionnez Exercice2_3 -> GreetUser.
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
Méthode GreetUser pour lire l'entrée et afficher le message de salutation :


public void GreetUser()
{
    string name = inputField.text;
    resultText.text = "Bonjour, " + name + " !";
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande le prénom de l'utilisateur et répond avec un message de salutation personnalisé.

# Exercice 2.4
Ecrire un programme qui lit le prix HT d’un article, le nombre d’articles et le taux de TVA, et qui fournit le prix total TTC correspondant. Faire en sorte que des libellés apparaissent clairement.

```
Variables nb, pht, ttva, pttc en Numérique
Début
Ecrire "Entrez le prix hors taxes :"
Lire pht
Ecrire "Entrez le nombre d’articles :"
Lire nb
Ecrire "Entrez le taux de TVA :"
Lire ttva
pttc ← nb * pht * (1 + ttva)
Ecrire "Le prix toutes taxes est : ", pttc
Fin
Là aussi, on pourrait squeezer une variable et une ligne en écrivant directement. :
Ecrire "Le prix toutes taxes est : ", nb * pht * (1 + ttva)
C'est plus rapide, plus léger en mémoire, mais un peu plus difficile à relire (et à écrire !)
```

Étape 1 : Créer l'interface utilisateur
Ajouter des InputField pour l'entrée du prix HT, du nombre d'articles et du taux de TVA :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_HT, InputField_Quantity, InputField_VAT).
Ajouter un Button pour déclencher le calcul du prix total TTC :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher le prix total TTC :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Ajouter des Text pour les libellés :

Allez dans le menu GameObject > UI > Text.
Ajoutez des libellés pour "Prix HT", "Nombre d'articles", "Taux de TVA", et "Prix total TTC".
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice2_4 : MonoBehaviour
{
    public InputField inputField_HT; // Référence à l'InputField pour le prix HT
    public InputField inputField_Quantity; // Référence à l'InputField pour le nombre d'articles
    public InputField inputField_VAT; // Référence à l'InputField pour le taux de TVA
    public Text resultText; // Référence au Text pour afficher le prix total TTC

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_HT == null || inputField_Quantity == null || inputField_VAT == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateTotalPrice()
    {
        // Lire les valeurs des InputField
        string htInput = inputField_HT.text;
        string quantityInput = inputField_Quantity.text;
        string vatInput = inputField_VAT.text;

        // Convertir les valeurs en nombres
        if (float.TryParse(htInput, out float htPrice) &&
            int.TryParse(quantityInput, out int quantity) &&
            float.TryParse(vatInput, out float vatRate))
        {
            // Calculer le prix total TTC
            float totalHT = htPrice * quantity;
            float totalVAT = totalHT * (vatRate / 100);
            float totalTTC = totalHT + totalVAT;

            // Afficher le résultat
            resultText.text = "Prix total TTC : " + totalTTC.ToString("F2");
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer des valeurs valides.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_HT, InputField_Quantity, et InputField_VAT du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice2_4 -> CalculateTotalPrice.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_HT;
public InputField inputField_Quantity;
public InputField inputField_VAT;
public Text resultText;
Vérification des références dans la méthode Start :


if (inputField_HT == null || inputField_Quantity == null || inputField_VAT == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
Méthode CalculateTotalPrice pour lire les entrées, calculer le prix total TTC et afficher le résultat :


public void CalculateTotalPrice()
{
    string htInput = inputField_HT.text;
    string quantityInput = inputField_Quantity.text;
    string vatInput = inputField_VAT.text;

    if (float.TryParse(htInput, out float htPrice) &&
        int.TryParse(quantityInput, out int quantity) &&
        float.TryParse(vatInput, out float vatRate))
    {
        float totalHT = htPrice * quantity;
        float totalVAT = totalHT * (vatRate / 100);
        float totalTTC = totalHT + totalVAT;
        resultText.text = "Prix total TTC : " + totalTTC.ToString("F2");
    }
    else
    {
        resultText.text = "Veuillez entrer des valeurs valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui lit le prix HT d'un article, le nombre d'articles, et le taux de TVA, puis calcule et affiche le prix total TTC.