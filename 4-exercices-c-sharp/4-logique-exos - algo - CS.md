# Exercice 4.1
Formulez un algorithme équivalent à l’algorithme suivant :
```
Si Tutu > Toto + 4 OU Tata = "OK" Alors
  Tutu ← Tutu + 1
Sinon
  Tutu ← Tutu – 1
Finsi
```
```
Aucune difficulté, il suffit d’appliquer la règle de la transformation du OU en ET vue en cours (loi de Morgan). Attention toutefois à la rigueur dans la transformation des conditions en leur contraire...
Si Tutu <= Toto + 4 ET Tata <> "OK" Alors
  Tutu ← Tutu - 1
Sinon
  Tutu ← Tutu + 1
Finsi
```
```c#
using UnityEngine;

public class Exercice4_1 : MonoBehaviour
{
    public int Tutu;
    public int Toto;
    public string Tata;

    void Start()
    {
        // Exemple de valeurs initiales
        Tutu = 10;
        Toto = 5;
        Tata = "OK";

        // Appel de la méthode pour exécuter l'algorithme
        UpdateTutu();

        // Affichage du résultat
        Debug.Log("Tutu = " + Tutu);
    }

    void UpdateTutu()
    {
        if (Tutu <= Toto + 4 && Tata != "OK")
        {
            Tutu -= 1;
        }
        else
        {
            Tutu += 1;
        }
    }
}
```
Explication du code C#
Déclaration des variables publiques :

```c#
public int Tutu;
public int Toto;
public string Tata;
```
Initialisation des valeurs dans la méthode Start :

```c#
Tutu = 10;
Toto = 5;
Tata = "OK";
```
Appel de la méthode UpdateTutu pour exécuter l'algorithme :

```c#
UpdateTutu();
```
Méthode UpdateTutu pour mettre à jour la valeur de Tutu en fonction des conditions :

```c#
void UpdateTutu()
{
    if (Tutu <= Toto + 4 && Tata != "OK")
    {
        Tutu -= 1;
    }
    else
    {
        Tutu += 1;
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui exécute l'algorithme équivalent à l'algorithme original.

# Exercice 4.2
Cet algorithme est destiné à prédire l'avenir, et il doit être infaillible !
Il lira au clavier l’heure et les minutes, et il affichera l’heure qu’il sera une minute plus tard. Par exemple, si l'utilisateur tape 21 puis 32, l'algorithme doit répondre :
"Dans une minute, il sera 21 heure(s) 33".
NB : on suppose que l'utilisateur entre une heure valide. Pas besoin donc de la vérifier.
```
Variables h, m en Numérique
Début
Ecrire "Entrez les heures, puis les minutes : "
Lire h, m
m ← m + 1
Si m = 60 Alors
  m ← 0
  h ← h + 1
FinSi
Si h = 24 Alors
  h ← 0
FinSi
Ecrire "Dans une minute il sera ", h, "heure(s) ", m, "minute(s)"
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter deux InputField pour l'entrée de l'heure et des minutes :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Hour, InputField_Minute).
Ajouter un Button pour déclencher le calcul de l'heure suivante :

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

public class Exercice4_2 : MonoBehaviour
{
    public InputField inputField_Hour; // Référence à l'InputField pour l'heure
    public InputField inputField_Minute; // Référence à l'InputField pour les minutes
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Hour == null || inputField_Minute == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void PredictNextMinute()
    {
        // Lire les valeurs des InputField
        string hourInput = inputField_Hour.text;
        string minuteInput = inputField_Minute.text;

        // Convertir les valeurs en nombres
        if (int.TryParse(hourInput, out int hour) && int.TryParse(minuteInput, out int minute))
        {
            // Calculer l'heure suivante
            minute += 1;
            if (minute == 60)
            {
                minute = 0;
                hour += 1;
                if (hour == 24)
                {
                    hour = 0;
                }
            }

            // Afficher le résultat
            resultText.text = "Dans une minute, il sera " + hour + " heure(s) " + minute.ToString("D2");
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer une heure et des minutes valides.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Hour et InputField_Minute du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_2 -> PredictNextMinute.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Hour;
public InputField inputField_Minute;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Hour == null || inputField_Minute == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode PredictNextMinute pour lire les entrées, calculer l'heure suivante, et afficher le résultat :

```c#
public void PredictNextMinute()
{
    string hourInput = inputField_Hour.text;
    string minuteInput = inputField_Minute.text;

    if (int.TryParse(hourInput, out int hour) && int.TryParse(minuteInput, out int minute))
    {
        minute += 1;
        if (minute == 60)
        {
            minute = 0;
            hour += 1;
            if (hour == 24)
            {
                hour = 0;
            }
        }

        resultText.text = "Dans une minute, il sera " + hour + " heure(s) " + minute.ToString("D2");
    }
    else
    {
        resultText.text = "Veuillez entrer une heure et des minutes valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui lit l'heure et les minutes au clavier, puis affiche l'heure qu'il sera une minute plus tard.

# Exercice 4.3
De même que le précédent, cet algorithme doit demander une heure et en afficher une autre. Mais cette fois, il doit gérer également les secondes, et afficher l'heure qu'il sera une seconde plus tard.
Par exemple, si l'utilisateur tape 21, puis 32, puis 8, l'algorithme doit répondre : "Dans une seconde, il sera 21 heure(s), 32 minute(s) et 9 seconde(s)".
NB : là encore, on suppose que l'utilisateur entre une date valide.
```
Variables h, m, s en Numérique
Début
Ecrire "Entrez les heures, puis les minutes, puis les secondes : "
Lire h, m, s
s ← s + 1
Si s = 60 Alors
  s ← 0
  m ← m + 1
FinSi
Si m = 60 Alors
  m ← 0
  h ← h + 1
FinSi
Si h = 24 Alors
  h ← 0
FinSi
Ecrire "Dans une seconde il sera ", h, "h", m, "m et ", s, "s"
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter trois InputField pour l'entrée de l'heure, des minutes et des secondes :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Hour, InputField_Minute, InputField_Second).
Ajouter un Button pour déclencher le calcul de l'heure suivante :

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

public class Exercice4_3 : MonoBehaviour
{
    public InputField inputField_Hour; // Référence à l'InputField pour l'heure
    public InputField inputField_Minute; // Référence à l'InputField pour les minutes
    public InputField inputField_Second; // Référence à l'InputField pour les secondes
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Hour == null || inputField_Minute == null || inputField_Second == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void PredictNextSecond()
    {
        // Lire les valeurs des InputField
        string hourInput = inputField_Hour.text;
        string minuteInput = inputField_Minute.text;
        string secondInput = inputField_Second.text;

        // Convertir les valeurs en nombres
        if (int.TryParse(hourInput, out int hour) && int.TryParse(minuteInput, out int minute) && int.TryParse(secondInput, out int second))
        {
            // Calculer l'heure suivante
            second += 1;
            if (second == 60)
            {
                second = 0;
                minute += 1;
                if (minute == 60)
                {
                    minute = 0;
                    hour += 1;
                    if (hour == 24)
                    {
                        hour = 0;
                    }
                }
            }

            // Afficher le résultat
            resultText.text = "Dans une seconde, il sera " + hour + " heure(s), " + minute.ToString("D2") + " minute(s) et " + second.ToString("D2") + " seconde(s)";
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer une heure, des minutes et des secondes valides.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Hour, InputField_Minute, et InputField_Second du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_3 -> PredictNextSecond.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Hour;
public InputField inputField_Minute;
public InputField inputField_Second;
public Text resultText;
```
Vérification des références dans la méthode Start :
```c#

if (inputField_Hour == null || inputField_Minute == null || inputField_Second == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode PredictNextSecond pour lire les entrées, calculer l'heure suivante, et afficher le résultat :

```c#
public void PredictNextSecond()
{
    string hourInput = inputField_Hour.text;
    string minuteInput = inputField_Minute.text;
    string secondInput = inputField_Second.text;

    if (int.TryParse(hourInput, out int hour) && int.TryParse(minuteInput, out int minute) && int.TryParse(secondInput, out int second))
    {
        second += 1;
        if (second == 60)
        {
            second = 0;
            minute += 1;
            if (minute == 60)
            {
                minute = 0;
                hour += 1;
                if (hour == 24)
                {
                    hour = 0;
                }
            }
        }

        resultText.text = "Dans une seconde, il sera " + hour + " heure(s), " + minute.ToString("D2") + " minute(s) et " + second.ToString("D2") + " seconde(s)";
    }
    else
    {
        resultText.text = "Veuillez entrer une heure, des minutes et des secondes valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui lit l'heure, les minutes et les secondes au clavier, puis affiche l'heure qu'il sera une seconde plus tard.

# Exercice 4.4
Un magasin de reprographie facture 0,10 E les dix premières photocopies, 0,09 E les vingt suivantes et 0,08 E au-delà. Ecrivez un algorithme qui demande à l’utilisateur le nombre de photocopies effectuées et qui affiche la facture correspondante.

```
Variables n, p en Numérique
Début
Ecrire "Nombre de photocopies : "
Lire n
Si n <= 10 Alors
  p ← n * 0,1
SinonSi n <= 30 Alors
  p ← 10 * 0,1 + (n – 10) * 0,09
Sinon
  p ← 10 * 0,1 + 20 * 0,09 + (n – 30) * 0,08
FinSi
Ecrire "Le prix total est: ", p
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre de photocopies :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher le calcul de la facture :

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

public class Exercice4_4 : MonoBehaviour
{
    public InputField inputField_Copies; // Référence à l'InputField pour le nombre de photocopies
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Copies == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateBill()
    {
        // Lire la valeur de l'InputField
        string input = inputField_Copies.text;

        // Convertir la valeur en nombre
        if (int.TryParse(input, out int copies))
        {
            // Calculer la facture
            float totalCost = 0;

            if (copies <= 10)
            {
                totalCost = copies * 0.10f;
            }
            else if (copies <= 30)
            {
                totalCost = 10 * 0.10f + (copies - 10) * 0.09f;
            }
            else
            {
                totalCost = 10 * 0.10f + 20 * 0.09f + (copies - 30) * 0.08f;
            }

            // Afficher le résultat
            resultText.text = "Le coût total est de " + totalCost.ToString("F2") + " €";
        }
        else
        {
            // Afficher un message d'erreur si l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide de photocopies.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Copies du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_4 -> CalculateBill.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Copies;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Copies == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CalculateBill pour lire l'entrée, calculer la facture en fonction du nombre de photocopies, et afficher le résultat :

```c#
public void CalculateBill()
{
    string input = inputField_Copies.text;
    if (int.TryParse(input, out int copies))
    {
        float totalCost = 0;

        if (copies <= 10)
        {
            totalCost = copies * 0.10f;
        }
        else if (copies <= 30)
        {
            totalCost = 10 * 0.10f + (copies - 10) * 0.09f;
        }
        else
        {
            totalCost = 10 * 0.10f + 20 * 0.09f + (copies - 30) * 0.08f;
        }

        resultText.text = "Le coût total est de " + totalCost.ToString("F2") + " €";
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide de photocopies.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande à l'utilisateur le nombre de photocopies effectuées et affiche la facture correspondante en fonction des tarifs spécifiés.

# Exercice 4.5
Les habitants de Zorglub paient l’impôt selon les règles suivantes :  
les hommes de plus de 20 ans paient l’impôt  
les femmes paient l’impôt si elles ont entre 18 et 35 ans  
les autres ne paient pas d’impôt  
Le programme demandera donc l’âge et le sexe du Zorglubien, et se prononcera donc ensuite sur le fait que l’habitant est imposable.  
```
Variable sex en Caractère
Variable age en Numérique
Variables C1, C2 en Booléen
Début
Ecrire "Entrez le sexe (M/F) : "
Lire sex
Ecrire "Entrez l’âge: "
Lire age
C1 ← sex = "M" ET age > 20
C2 ← sex = "F" ET (age > 18 ET age < 35)
Si C1 ou C2 Alors
  Ecrire "Imposable"
Sinon
  Ecrire "Non Imposable"
FinSi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de l'âge :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Dropdown pour l'entrée du sexe :

Allez dans le menu GameObject > UI > Dropdown.
Positionnez-le dans la scène.
Ajoutez les options "Homme" et "Femme" au Dropdown.
Ajouter un Button pour déclencher la vérification de l'imposabilité :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Étape 2 : Configurer le Dropdown
Sélectionnez le Dropdown dans la scène.
Dans l'inspecteur, ajoutez les options "Homme" et "Femme" :
Cliquez sur le + dans la section Dropdown pour ajouter une nouvelle option.
Remplissez le champ Text avec "Homme".
Cliquez à nouveau sur le + pour ajouter une autre option.
Remplissez le champ Text avec "Femme".
Étape 3 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice4_5 : MonoBehaviour
{
    public InputField inputField_Age; // Référence à l'InputField pour l'âge
    public Dropdown dropdown_Sex; // Référence au Dropdown pour le sexe
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Age == null || dropdown_Sex == null || resultText == null)
        {
            Debug.LogError("Les références à InputField, Dropdown ou Text ne sont pas assignées.");
        }
    }

    public void CheckTaxStatus()
    {
        // Lire la valeur de l'InputField
        string ageInput = inputField_Age.text;

        // Convertir la valeur en nombre
        if (int.TryParse(ageInput, out int age))
        {
            // Lire la valeur du Dropdown
            string sex = dropdown_Sex.options[dropdown_Sex.value].text;

            // Déterminer si l'habitant est imposable
            bool isTaxable = false;
            if (sex == "Homme" && age > 20)
            {
                isTaxable = true;
            }
            else if (sex == "Femme" && age >= 18 && age <= 35)
            {
                isTaxable = true;
            }

            // Afficher le résultat
            if (isTaxable)
            {
                resultText.text = "L'habitant est imposable.";
            }
            else
            {
                resultText.text = "L'habitant n'est pas imposable.";
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
Étape 4 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser l'InputField dans le champ InputField_Age du script.
Faites glisser le Dropdown dans le champ Dropdown_Sex du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 5 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_5 -> CheckTaxStatus.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Age;
public Dropdown dropdown_Sex;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Age == null || dropdown_Sex == null || resultText == null)
{
    Debug.LogError("Les références à InputField, Dropdown ou Text ne sont pas assignées.");
}
```
Méthode CheckTaxStatus pour lire les entrées, déterminer si l'habitant est imposable en fonction de son âge et de son sexe, et afficher le résultat :

```c#
public void CheckTaxStatus()
{
    string ageInput = inputField_Age.text;
    if (int.TryParse(ageInput, out int age))
    {
        string sex = dropdown_Sex.options[dropdown_Sex.value].text;
        bool isTaxable = false;
        if (sex == "Homme" && age > 20)
        {
            isTaxable = true;
        }
        else if (sex == "Femme" && age >= 18 && age <= 35)
        {
            isTaxable = true;
        }

        if (isTaxable)
        {
            resultText.text = "L'habitant est imposable.";
        }
        else
        {
            resultText.text = "L'habitant n'est pas imposable.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un âge valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande l'âge et le sexe d'un habitant de Zorglub et détermine s'il est imposable en fonction des règles spécifiées.

# Exercice 4.6
Les élections législatives, en Guignolerie Septentrionale, obéissent à la règle suivante :
lorsque l'un des candidats obtient plus de 50% des suffrages, il est élu dès le premier tour.
en cas de deuxième tour, peuvent participer uniquement les candidats ayant obtenu au moins 12,5% des voix au premier tour.  
Vous devez écrire un algorithme qui permette la saisie des scores de quatre candidats au premier tour. Cet algorithme traitera ensuite le candidat numéro 1 (et uniquement lui) : il dira s'il est élu, battu, s'il se trouve en ballottage favorable (il participe au second tour en étant arrivé en tête à l'issue du premier tour) ou défavorable (il participe au second tour sans avoir été en tête au premier tour).  
<hr>
Cet exercice, du pur point de vue algorithmique, n'est pas très méchant. En revanche, il représente dignement la catégorie des énoncés piégés.
En effet, rien de plus facile que d'écrire : si le candidat a plus de 50%, il est élu, sinon s'il a plus de 12,5 %, il est au deuxième tour, sinon il est éliminé. Hé hé hé... mais il ne faut pas oublier que le candidat peut très bien avoir eu 20 % mais être tout de même éliminé, tout simplement parce que l'un des autres a fait plus de 50 % et donc qu'il n'y a pas de deuxième tour !...
Moralité : ne jamais se jeter sur la programmation avant d'avoir soigneusement mené l'analyse du problème à traiter.

```
Variables A, B, C, D en Numérique
Variables C1, C2, C3, C4 en Booléen
Début
Ecrire "Entrez les scores des quatre prétendants :"
Lire A, B, C, D
C1 ← A > 50
C2 ← B > 50 ou C > 50 ou D > 50
C3 ← A >= B et A >= C et A >= D
C4 ← A >= 12,5
Si C1 Alors
  Ecrire “Elu au premier tour"
Sinonsi C2 ou Non(C4) Alors
  Ecrire “Battu, éliminé, sorti !!!”
SinonSi C3 Alors
  Ecrire "Ballotage favorable"
Sinon
  Ecrire "Ballotage défavorable"
FinSi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter quatre InputField pour l'entrée des scores des quatre candidats :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Candidate1, InputField_Candidate2, InputField_Candidate3, InputField_Candidate4).
Ajouter un Button pour déclencher l'analyse des résultats :

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

public class Exercice4_6 : MonoBehaviour
{
    public InputField inputField_Candidate1; // Référence à l'InputField pour le score du candidat 1
    public InputField inputField_Candidate2; // Référence à l'InputField pour le score du candidat 2
    public InputField inputField_Candidate3; // Référence à l'InputField pour le score du candidat 3
    public InputField inputField_Candidate4; // Référence à l'InputField pour le score du candidat 4
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Candidate1 == null || inputField_Candidate2 == null || inputField_Candidate3 == null || inputField_Candidate4 == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void AnalyzeResults()
    {
        // Lire les valeurs des InputField
        string score1Input = inputField_Candidate1.text;
        string score2Input = inputField_Candidate2.text;
        string score3Input = inputField_Candidate3.text;
        string score4Input = inputField_Candidate4.text;

        // Convertir les valeurs en nombres
        if (float.TryParse(score1Input, out float score1) &&
            float.TryParse(score2Input, out float score2) &&
            float.TryParse(score3Input, out float score3) &&
            float.TryParse(score4Input, out float score4))
        {
            // Calculer le total des voix
            float totalVotes = score1 + score2 + score3 + score4;

            // Calculer les pourcentages
            float percentage1 = (score1 / totalVotes) * 100;
            float percentage2 = (score2 / totalVotes) * 100;
            float percentage3 = (score3 / totalVotes) * 100;
            float percentage4 = (score4 / totalVotes) * 100;

            // Déterminer le statut du candidat numéro 1
            if (percentage1 > 50)
            {
                resultText.text = "Le candidat numéro 1 est élu dès le premier tour.";
            }
            else if (percentage1 >= 12.5f)
            {
                if (score1 >= score2 && score1 >= score3 && score1 >= score4)
                {
                    resultText.text = "Le candidat numéro 1 est en ballottage favorable.";
                }
                else
                {
                    resultText.text = "Le candidat numéro 1 est en ballottage défavorable.";
                }
            }
            else
            {
                resultText.text = "Le candidat numéro 1 est battu.";
            }
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer des scores valides pour les quatre candidats.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Candidate1, InputField_Candidate2, InputField_Candidate3, et InputField_Candidate4 du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_6 -> AnalyzeResults.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Candidate1;
public InputField inputField_Candidate2;
public InputField inputField_Candidate3;
public InputField inputField_Candidate4;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Candidate1 == null || inputField_Candidate2 == null || inputField_Candidate3 == null || inputField_Candidate4 == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode AnalyzeResults pour lire les entrées, calculer les pourcentages, déterminer le statut du candidat numéro 1, et afficher le résultat :

```c#
public void AnalyzeResults()
{
    string score1Input = inputField_Candidate1.text;
    string score2Input = inputField_Candidate2.text;
    string score3Input = inputField_Candidate3.text;
    string score4Input = inputField_Candidate4.text;

    if (float.TryParse(score1Input, out float score1) &&
        float.TryParse(score2Input, out float score2) &&
        float.TryParse(score3Input, out float score3) &&
        float.TryParse(score4Input, out float score4))
    {
        float totalVotes = score1 + score2 + score3 + score4;
        float percentage1 = (score1 / totalVotes) * 100;
        float percentage2 = (score2 / totalVotes) * 100;
        float percentage3 = (score3 / totalVotes) * 100;
        float percentage4 = (score4 / totalVotes) * 100;

        if (percentage1 > 50)
        {
            resultText.text = "Le candidat numéro 1 est élu dès le premier tour.";
        }
        else if (percentage1 >= 12.5f)
        {
            if (score1 >= score2 && score1 >= score3 && score1 >= score4)
            {
                resultText.text = "Le candidat numéro 1 est en ballottage favorable.";
            }
            else
            {
                resultText.text = "Le candidat numéro 1 est en ballottage défavorable.";
            }
        }
        else
        {
            resultText.text = "Le candidat numéro 1 est battu.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer des scores valides pour les quatre candidats.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande les scores des quatre candidats au premier tour des élections législatives en Guignolerie Septentrionale et détermine le statut du candidat numéro 1 en fonction des règles spécifiées.

# Exercice 4.7
Une compagnie d'assurance automobile propose à ses clients quatre familles de tarifs identifiables par une couleur, du moins au plus onéreux : tarifs bleu, vert, orange et rouge. Le tarif dépend de la situation du conducteur :  
un conducteur de moins de 25 ans et titulaire du permis depuis moins de deux ans, se voit attribuer le tarif rouge, si toutefois il n'a jamais été responsable d'accident. Sinon, la compagnie refuse de l'assurer.  
un conducteur de moins de 25 ans et titulaire du permis depuis plus de deux ans, ou de plus de 25 ans mais titulaire du permis depuis moins de deux ans a le droit au tarif orange s'il n'a jamais provoqué d'accident, au tarif rouge pour un accident, sinon il est refusé.
un conducteur de plus de 25 ans titulaire du permis depuis plus de deux ans bénéficie du tarif vert s'il n'est à l'origine d'aucun accident et du tarif orange pour un accident, du tarif rouge pour deux accidents, et refusé au-delà  
De plus, pour encourager la fidélité des clients acceptés, la compagnie propose un contrat de la couleur immédiatement la plus avantageuse s'il est entré dans la maison depuis plus de cinq ans. Ainsi, s'il satisfait à cette exigence, un client normalement "vert" devient "bleu", un client normalement "orange" devient "vert", et le "rouge" devient orange.  
Ecrire l'algorithme permettant de saisir les données nécessaires (sans contrôle de saisie) et de traiter ce problème. Avant de se lancer à corps perdu dans cet exercice, on pourra réfléchir un peu et s'apercevoir qu'il est plus simple qu'il n'en a l'air (cela s'appelle faire une analyse !)

<hr>
Là encore, on illustre l'utilité d'une bonne analyse. Je propose deux corrigés différents. Le premier suit l'énoncé pas à pas. C'est juste, mais c'est vraiment lourd. La deuxième version s'appuie sur une vraie compréhension d'une situation pas si embrouillée qu'elle n'en a l'air.
Dans les deux cas, un recours aux variables booléennes aère sérieusement l'écriture.
Donc, premier corrigé, on suit le texte de l'énoncé pas à pas :  

```
Variables age, perm, acc, assur en Numérique
Variables C1, C2, C3 en Booléen
Variable situ en Caractère
Début
Ecrire "Entrez l’âge: "
Lire age
Ecrire "Entrez le nombre d'années de permis: "
Lire perm
Ecrire "Entrez le nombre d'accidents: "
Lire acc
Ecrire "Entrez le nombre d'années d'assurance: "
Lire assur
C1 ← age >= 25
C2 ← perm >= 2
C3 ← assur > 5
Si Non(C1) et Non(C2) Alors
  Si acc = 0 Alors
    situ ← "Rouge"
  Sinon
    situ ← "Refusé"
  FinSi
Sinonsi ((Non(C1) et C2) ou (C1 et Non(C2)) Alors
  Si acc = 0 Alors
    situ ← "Orange"
  SinonSi acc = 1 Alors
    situ ← "Rouge"
  Sinon
    situ ← "Refusé"
  FinSi
Sinon
  Si acc = 0 Alors
    situ ← "Vert"
  SinonSi acc = 1 Alors
    situ ← "Orange"
  SinonSi acc = 2 Alors
    situ ← "Rouge"
  Sinon
    situ ← "Refusé"
  FinSi
FinSi
Si C3 Alors
  Si situ = "Rouge" Alors
    situ ← "Orange"
  SinonSi situ = "Orange" Alors
    situ ← "Vert"
  SinonSi situ = "Vert" Alors
    situ ← "Bleu"
  FinSi
FinSi
Ecrire "Votre situation : ", situ
Fin
```
Vous trouvez cela compliqué ? Oh, certes oui, ça l'est ! Et d'autant plus qu'en lisant entre les lignes, on pouvait s'apercevoir que ce galimatias de tarifs recouvre en fait une logique très simple : un système à points. Et il suffit de comptabiliser les points pour que tout s'éclaire... Reprenons juste après l'affectation des trois variables booléennes C1, C2, et C3. On écrit :  
```
P ← 0
Si Non(C1) Alors
  P ← P + 1
FinSi
Si Non(C2) Alors
  P ← P + 1
FinSi
P ← P + acc
Si P < 3 et C3 Alors
  P ← P - 1
FinSi
Si P = -1 Alors
  situ ← "Bleu"
SinonSi P = 0 Alors
  situ ← "Vert"
SinonSi P = 1 Alors
  situ ← "Orange"
SinonSi P = 2 Alors
  situ ← "Rouge"
Sinon
  situ ← "Refusé"
FinSi
Ecrire "Votre situation : ", situ
Fin
```
Cool, non ?

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de l'âge :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un InputField pour l'entrée de l'ancienneté du permis :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un InputField pour l'entrée du nombre d'accidents :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un InputField pour l'entrée de l'ancienneté dans la compagnie :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Ajouter un Button pour déclencher le calcul du tarif :

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

public class Exercice4_7 : MonoBehaviour
{
    public InputField inputField_Age; // Référence à l'InputField pour l'âge
    public InputField inputField_Permis; // Référence à l'InputField pour l'ancienneté du permis
    public InputField inputField_Accidents; // Référence à l'InputField pour le nombre d'accidents
    public InputField inputField_Anciennete; // Référence à l'InputField pour l'ancienneté dans la compagnie
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Age == null || inputField_Permis == null || inputField_Accidents == null || inputField_Anciennete == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CalculateTarif()
    {
        // Lire les valeurs des InputField
        string ageInput = inputField_Age.text;
        string permisInput = inputField_Permis.text;
        string accidentsInput = inputField_Accidents.text;
        string ancienneteInput = inputField_Anciennete.text;

        // Convertir les valeurs en nombres
        if (int.TryParse(ageInput, out int age) &&
            int.TryParse(permisInput, out int permis) &&
            int.TryParse(accidentsInput, out int accidents) &&
            int.TryParse(ancienneteInput, out int anciennete))
        {
            // Déterminer le tarif initial
            string tarif = "Refusé";
            if (age < 25 && permis < 2)
            {
                if (accidents == 0)
                {
                    tarif = "Rouge";
                }
            }
            else if ((age < 25 && permis >= 2) || (age >= 25 && permis < 2))
            {
                if (accidents == 0)
                {
                    tarif = "Orange";
                }
                else if (accidents == 1)
                {
                    tarif = "Rouge";
                }
            }
            else if (age >= 25 && permis >= 2)
            {
                if (accidents == 0)
                {
                    tarif = "Vert";
                }
                else if (accidents == 1)
                {
                    tarif = "Orange";
                }
                else if (accidents == 2)
                {
                    tarif = "Rouge";
                }
            }

            // Appliquer la réduction pour fidélité
            if (anciennete > 5)
            {
                if (tarif == "Vert")
                {
                    tarif = "Bleu";
                }
                else if (tarif == "Orange")
                {
                    tarif = "Vert";
                }
                else if (tarif == "Rouge")
                {
                    tarif = "Orange";
                }
            }

            // Afficher le résultat
            resultText.text = "Le tarif est : " + tarif;
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
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Age, InputField_Permis, InputField_Accidents, et InputField_Anciennete du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_7 -> CalculateTarif.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Age;
public InputField inputField_Permis;
public InputField inputField_Accidents;
public InputField inputField_Anciennete;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Age == null || inputField_Permis == null || inputField_Accidents == null || inputField_Anciennete == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CalculateTarif pour lire les entrées, déterminer le tarif en fonction des critères, et afficher le résultat :

```c#
public void CalculateTarif()
{
    string ageInput = inputField_Age.text;
    string permisInput = inputField_Permis.text;
    string accidentsInput = inputField_Accidents.text;
    string ancienneteInput = inputField_Anciennete.text;

    if (int.TryParse(ageInput, out int age) &&
        int.TryParse(permisInput, out int permis) &&
        int.TryParse(accidentsInput, out int accidents) &&
        int.TryParse(ancienneteInput, out int anciennete))
    {
        string tarif = "Refusé";
        if (age < 25 && permis < 2)
        {
            if (accidents == 0)
            {
                tarif = "Rouge";
            }
        }
        else if ((age < 25 && permis >= 2) || (age >= 25 && permis < 2))
        {
            if (accidents == 0)
            {
                tarif = "Orange";
            }
            else if (accidents == 1)
            {
                tarif = "Rouge";
            }
        }
        else if (age >= 25 && permis >= 2)
        {
            if (accidents == 0)
            {
                tarif = "Vert";
            }
            else if (accidents == 1)
            {
                tarif = "Orange";
            }
            else if (accidents == 2)
            {
                tarif = "Rouge";
            }
        }

        if (anciennete > 5)
        {
            if (tarif == "Vert")
            {
                tarif = "Bleu";
            }
            else if (tarif == "Orange")
            {
                tarif = "Vert";
            }
            else if (tarif == "Rouge")
            {
                tarif = "Orange";
            }
        }

        resultText.text = "Le tarif est : " + tarif;
    }
    else
    {
        resultText.text = "Veuillez entrer des valeurs valides.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande les données nécessaires (âge, ancienneté du permis, nombre d'accidents, ancienneté dans la compagnie) et détermine le tarif d'assurance automobile en fonction des règles spécifiées.
# Exercice 4.8
Ecrivez un algorithme qui a près avoir demandé un numéro de jour, de mois et d'année à l'utilisateur, renvoie s'il s'agit ou non d'une date valide.  
Cet exercice est certes d’un manque d’originalité affligeant, mais après tout, en algorithmique comme ailleurs, il faut connaître ses classiques ! Et quand on a fait cela une fois dans sa vie, on apprécie pleinement l’existence d’un type numérique « date » dans certains langages…).
Il n'est sans doute pas inutile de rappeler rapidement que le mois de février compte 28 jours, sauf si l’année est bissextile, auquel cas il en compte 29. L’année est bissextile si elle est divisible par quatre. Toutefois, les années divisibles par 100 ne sont pas bissextiles, mais les années divisibles par 400 le sont. Ouf !  
Un dernier petit détail : vous ne savez pas, pour l’instant, exprimer correctement en pseudo-code l’idée qu’un nombre A est divisible par un nombre B. Aussi, vous vous contenterez d’écrire en bons télégraphistes que A divisible par B se dit « A dp B ».
<hr>

En ce qui concerne le début de cet algorithme, il n’y a aucune difficulté. C’est de la saisie bête et même pas méchante:
```
Variables J, M, A, JMax en Numérique
Variables VJ, VM, B en Booleen
Début
Ecrire "Entrez le numéro du jour"
Lire J
Ecrire "Entrez le numéro du mois"
Lire M
Ecrire "Entrez l'année"
Lire A
```
C'est évidemment ensuite que les ennuis commencent… La première manière d'aborder la chose consiste à se dire que fondamentalement, la structure logique de ce problème est très simple. Si nous créons deux variables booléennes VJ et VM, représentant respectivement la validité du jour et du mois entrés, la fin de l'algorithme sera d'une simplicité biblique (l’année est valide par définition, si on évacue le débat byzantin concernant l’existence de l’année zéro) :  
```
Si VJ et VM alors
  Ecrire "La date est valide"
Sinon
  Ecrire "La date n'est pas valide"
FinSi
```
Toute la difficulté consiste à affecter correctement les variables VJ et VM, selon les valeurs des variables J, M et A. Dans l'absolu, VJ et VM pourraient être les objets d'une affectation monstrueuse, avec des conditions atrocement composées. Mais franchement, écrire ces conditions en une seule fois est un travail de bénédictin sans grand intérêt. Pour éviter d'en arriver à une telle extrémité, on peut sérier la difficulté en créant deux variables supplémentaires :

B       : variable booléenne qui indique s'il s'agit d'une année bissextile
JMax : variable numérique qui indiquera le dernier jour valable pour le mois entré.

Avec tout cela, on peut y aller et en ressortir vivant.
On commence par initialiser nos variables booléennes, puis on traite les années, puis les mois, puis les jours.
On note "dp" la condition "divisible par" :  
```
B ← A dp 400 ou (non(A dp 100) et A dp 4)
Jmax ← 0
VM ← M >= 1 et M =< 12
Si VM Alors
  Si M = 2 et B Alors
    JMax ← 29
  SinonSi M = 2 Alors
    JMax ← 28
  SinonSi M = 4 ou M = 6 ou M = 9 ou M = 11 Alors
    JMax ← 30
  Sinon
    JMax ← 31
  FinSi
  VJ ← J >= 1 et J =< Jmax
FinSi
```
Cette solution a le mérite de ne pas trop compliquer la structure des tests, et notamment de ne pas répéter l'écriture finale à l'écran. Les variables booléennes intermédiaires nous épargnent des conditions composées trop lourdes, mais celles-ci restent néanmoins sérieuses.

Une approche différente consisterait à limiter les conditions composées, quitte à le payer par une structure beaucoup plus exigeante de tests imbriqués. Là encore, on évite de jouer les extrémistes et l'on s'autorise quelques conditions composées lorsque cela nous simplifie l'existence. On pourrait aussi dire que la solution précédente "part de la fin" du problème (la date est elle valide ou non ?), alors que celle qui suit "part du début" (quelles sont les données entrées au clavier ?) :

```
Si M < 1 ou M > 12 Alors
  Ecrire "Date Invalide"
SinonSi M = 2 Alors
  Si A dp 400 Alors
    Si J < 1 ou J > 29 Alors
      Ecrire "Date Invalide"
    Sinon
      Ecrire "Date Valide"
    FinSi
  SinonSi A dp 100 Alors
    Si J < 1 ou J > 28 Alors
      Ecrire "Date Invalide"
    Sinon
      Ecrire "Date Valide"
    FinSi
  SinonSi A dp 4 Alors
    Si J < 1 ou J > 29Alors
      Ecrire "Date Invalide"
    Sinon
      Ecrire "Date Valide"
    FinSi
  Sinon
    Si J < 1 ou J > 28 Alors
      Ecrire "Date Invalide"
    Sinon
      Ecrire "Date Valide"
    FinSi
  FinSi
SinonSi M = 4 ou M = 6 ou M = 9 ou M = 11 Alors
  Si J < 1 ou J > 30 Alors
    Ecrire "Date Invalide"
  Sinon
    Ecrire "Date Valide"
  FinSi
Sinon
  Si J < 1 ou J > 31 Alors
    Ecrire "Date Invalide"
  Sinon
    Ecrire "Date Valide"
  FinSi
FinSi
```
On voit que dans ce cas, l'alternative finale (Date valide ou invalide) se trouve répétée un grand nombre de fois. Ce n'est en soi ni une bonne, ni une mauvaise chose. C'est simplement une question de choix stylistique.
Personnellement, j'avoue préférer assez nettement la première solution, qui fait ressortir beaucoup plus clairement la structure logique du problème (il n'y a qu'une seule alternative, autant que cette alternative ne soit écrite qu'une seule fois).

Il convient enfin de citer une solution très simple et élégante, un peu plus difficile peut-être à imaginer du premier coup, mais qui avec le recul apparaît comme très immédiate. Sur le fond, cela consiste à dire qu'il y a quatre cas pour qu'une date soit valide : celui d'un jour compris entre 1 et 31 dans un mois à 31 jours, celui d'un jour compris entre 1 et 30 dans un mois à 30 jours, celui d'un jour compris entre 1 et 29 en février d'une année bissextile, et celui d'un jour de février compris entre 1 et 28. Ainsi :
```
B ← (A dp 4 et Non(A dp 100)) ou A dp 400
K1 ← (m=1 ou m=3 ou m=5 ou m=7 ou m=8 ou m=10 ou m=12) et (J>=1 et J=<31)
K2 ← (m=4 ou m=6 ou m=9 ou m=11) et (J>=1 et J=<30)
K3 ← m=2 et B et J>=1 et J=<29
K4 ← m=2 et J>=1 et J=<28
Si K1 ou K2 ou K3 ou K4 Alors
  Ecrire "Date valide"
Sinon
  Ecrire "Date non valide"
FinSi
Fin
```
Tout est alors réglé avec quelques variables booléennes et quelques conditions composées, en un minimum de lignes de code.
La morale de ce long exercice - et non moins long corrigé, c'est qu'un problème de test un peu compliqué admet une pléiade de solutions justes...
...Mais que certaines sont plus astucieuses que d'autres !

Étape 1 : Créer l'interface utilisateur
Ajouter trois InputField pour l'entrée du jour, du mois et de l'année :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les pour plus de clarté (par exemple, InputField_Day, InputField_Month, InputField_Year).
Ajouter un Button pour déclencher la vérification de la date :

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

public class Exercice4_8 : MonoBehaviour
{
    public InputField inputField_Day; // Référence à l'InputField pour le jour
    public InputField inputField_Month; // Référence à l'InputField pour le mois
    public InputField inputField_Year; // Référence à l'InputField pour l'année
    public Text resultText; // Référence au Text pour afficher le résultat

    void Start()
    {
        // Assurez-vous que les références sont assignées
        if (inputField_Day == null || inputField_Month == null || inputField_Year == null || resultText == null)
        {
            Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
        }
    }

    public void CheckDate()
    {
        // Lire les valeurs des InputField
        string dayInput = inputField_Day.text;
        string monthInput = inputField_Month.text;
        string yearInput = inputField_Year.text;

        // Convertir les valeurs en nombres
        if (int.TryParse(dayInput, out int day) &&
            int.TryParse(monthInput, out int month) &&
            int.TryParse(yearInput, out int year))
        {
            // Vérifier si la date est valide
            if (IsValidDate(day, month, year))
            {
                resultText.text = "La date est valide.";
            }
            else
            {
                resultText.text = "La date n'est pas valide.";
            }
        }
        else
        {
            // Afficher un message d'erreur si les entrées ne sont pas valides
            resultText.text = "Veuillez entrer une date valide.";
        }
    }

    bool IsValidDate(int day, int month, int year)
    {
        // Vérifier les limites des mois et des jours
        if (year < 1 || month < 1 || month > 12 || day < 1)
        {
            return false;
        }

        // Tableau des jours par mois
        int[] daysInMonth = { 0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };

        // Vérifier si l'année est bissextile
        if (month == 2 && IsLeapYear(year))
        {
            daysInMonth[2] = 29;
        }

        // Vérifier si le jour est valide pour le mois donné
        return day <= daysInMonth[month];
    }

    bool IsLeapYear(int year)
    {
        // Une année est bissextile si elle est divisible par 4,
        // mais les années divisibles par 100 ne sont pas bissextiles,
        // sauf si elles sont divisibles par 400.
        return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script.
Dans l'inspecteur, faites glisser les InputField correspondants dans les champs InputField_Day, InputField_Month, et InputField_Year du script.
Faites glisser le Text dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice4_8 -> CheckDate.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Day;
public InputField inputField_Month;
public InputField inputField_Year;
public Text resultText;
```
Vérification des références dans la méthode Start :

```c#
if (inputField_Day == null || inputField_Month == null || inputField_Year == null || resultText == null)
{
    Debug.LogError("Les références à InputField ou Text ne sont pas assignées.");
}
```
Méthode CheckDate pour lire les entrées, vérifier si la date est valide, et afficher le résultat :

```c#
public void CheckDate()
{
    string dayInput = inputField_Day.text;
    string monthInput = inputField_Month.text;
    string yearInput = inputField_Year.text;

    if (int.TryParse(dayInput, out int day) &&
        int.TryParse(monthInput, out int month) &&
        int.TryParse(yearInput, out int year))
    {
        if (IsValidDate(day, month, year))
        {
            resultText.text = "La date est valide.";
        }
        else
        {
            resultText.text = "La date n'est pas valide.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer une date valide.";
    }
}
```
Méthode IsValidDate pour vérifier si la date est valide :

```c#
bool IsValidDate(int day, int month, int year)
{
    if (year < 1 || month < 1 || month > 12 || day < 1)
    {
        return false;
    }

    int[] daysInMonth = { 0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };

    if (month == 2 && IsLeapYear(year))
    {
        daysInMonth[2] = 29;
    }

    return day <= daysInMonth[month];
}
```

Méthode IsLeapYear pour vérifier si une année est bissextile :

```c#
bool IsLeapYear(int year)
{
    return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un numéro de jour, de mois et d'année à l'utilisateur et vérifie si la date est valide.
