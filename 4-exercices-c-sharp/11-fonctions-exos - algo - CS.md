# Exercice 11.1
Écrivez une fonction qui renvoie la somme de cinq nombres fournis en argument.
```
Fonction Sum(a, b, c, d, e) en Numérique
  Renvoyer a + b + c + d + e
FinFonction
```
Étape 1 : Créer la fonction
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;

public class Exercice11_1 : MonoBehaviour
{
    // Fonction qui prend cinq nombres en arguments et renvoie leur somme
    public int SumFiveNumbers(int num1, int num2, int num3, int num4, int num5)
    {
        return num1 + num2 + num3 + num4 + num5;
    }

    // Fonction pour tester la fonction SumFiveNumbers
    public void TestSumFiveNumbers()
    {
        int num1 = 1;
        int num2 = 2;
        int num3 = 3;
        int num4 = 4;
        int num5 = 5;

        int sum = SumFiveNumbers(num1, num2, num3, num4, num5);
        Debug.Log("La somme des cinq nombres est : " + sum);
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction SumFiveNumbers, vous pouvez appeler la méthode TestSumFiveNumbers dans la méthode Start ou Update de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_1 : MonoBehaviour
{
    // Fonction qui prend cinq nombres en arguments et renvoie leur somme
    public int SumFiveNumbers(int num1, int num2, int num3, int num4, int num5)
    {
        return num1 + num2 + num3 + num4 + num5;
    }

    // Fonction pour tester la fonction SumFiveNumbers
    public void TestSumFiveNumbers()
    {
        int num1 = 1;
        int num2 = 2;
        int num3 = 3;
        int num4 = 4;
        int num5 = 5;

        int sum = SumFiveNumbers(num1, num2, num3, num4, num5);
        Debug.Log("La somme des cinq nombres est : " + sum);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestSumFiveNumbers();
    }
}
```
Explication du code C#
Déclaration de la fonction SumFiveNumbers :

```c#
public int SumFiveNumbers(int num1, int num2, int num3, int num4, int num5)
{
    return num1 + num2 + num3 + num4 + num5;
}
```
Cette fonction prend cinq nombres entiers en arguments et renvoie leur somme.
Déclaration de la fonction TestSumFiveNumbers pour tester la fonction SumFiveNumbers :

```c#
public void TestSumFiveNumbers()
{
    int num1 = 1;
    int num2 = 2;
    int num3 = 3;
    int num4 = 4;
    int num5 = 5;

    int sum = SumFiveNumbers(num1, num2, num3, num4, num5);
    Debug.Log("La somme des cinq nombres est : " + sum);
}
```
Cette fonction initialise cinq nombres entiers, appelle la fonction SumFiveNumbers avec ces nombres, et affiche la somme dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestSumFiveNumbers();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestSumFiveNumbers dans cette méthode pour tester la fonction SumFiveNumbers lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui prend cinq nombres en arguments et renvoie leur somme, ainsi qu'une méthode pour tester cette fonction dans Unity.
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

Pour cet exercice, nous devons écrire une fonction qui prend une chaîne de caractères en argument et renvoie le nombre de voyelles contenues dans cette chaîne. Nous allons utiliser C# pour écrire cette fonction. Voici comment vous pouvez le faire :

Étape 1 : Créer la fonction
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;

public class Exercice11_2 : MonoBehaviour
{
    // Fonction qui prend une chaîne de caractères en argument et renvoie le nombre de voyelles
    public int CountVowels(string input)
    {
        int vowelCount = 0;
        foreach (char c in input)
        {
            if (IsVowel(c))
            {
                vowelCount++;
            }
        }
        return vowelCount;
    }

    // Fonction qui vérifie si un caractère est une voyelle
    private bool IsVowel(char c)
    {
        char lowerChar = char.ToLower(c);
        return lowerChar == 'a' || lowerChar == 'e' || lowerChar == 'i' || lowerChar == 'o' || lowerChar == 'u';
    }

    // Fonction pour tester la fonction CountVowels
    public void TestCountVowels()
    {
        string testString = "Bonjour tout le monde!";
        int vowelCount = CountVowels(testString);
        Debug.Log("Le nombre de voyelles dans la chaîne est : " + vowelCount);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestCountVowels();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction CountVowels, vous pouvez appeler la méthode TestCountVowels dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_2 : MonoBehaviour
{
    // Fonction qui prend une chaîne de caractères en argument et renvoie le nombre de voyelles
    public int CountVowels(string input)
    {
        int vowelCount = 0;
        foreach (char c in input)
        {
            if (IsVowel(c))
            {
                vowelCount++;
            }
        }
        return vowelCount;
    }

    // Fonction qui vérifie si un caractère est une voyelle
    private bool IsVowel(char c)
    {
        char lowerChar = char.ToLower(c);
        return lowerChar == 'a' || lowerChar == 'e' || lowerChar == 'i' || lowerChar == 'o' || lowerChar == 'u';
    }

    // Fonction pour tester la fonction CountVowels
    public void TestCountVowels()
    {
        string testString = "Bonjour tout le monde!";
        int vowelCount = CountVowels(testString);
        Debug.Log("Le nombre de voyelles dans la chaîne est : " + vowelCount);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestCountVowels();
    }
}
```
Explication du code C#
Déclaration de la fonction CountVowels :

```c#
public int CountVowels(string input)
{
    int vowelCount = 0;
    foreach (char c in input)
    {
        if (IsVowel(c))
        {
            vowelCount++;
        }
    }
    return vowelCount;
}
```
Cette fonction prend une chaîne de caractères en argument et renvoie le nombre de voyelles contenues dans cette chaîne. Elle utilise une boucle foreach pour parcourir chaque caractère de la chaîne et appelle la fonction IsVowel pour vérifier si le caractère est une voyelle.
Déclaration de la fonction IsVowel :

```c#
private bool IsVowel(char c)
{
    char lowerChar = char.ToLower(c);
    return lowerChar == 'a' || lowerChar == 'e' || lowerChar == 'i' || lowerChar == 'o' || lowerChar == 'u';
}
```
Cette fonction prend un caractère en argument et renvoie true si le caractère est une voyelle (a, e, i, o, u), sinon false. Elle convertit le caractère en minuscule pour éviter les problèmes de casse.
Déclaration de la fonction TestCountVowels pour tester la fonction CountVowels :

```c#
public void TestCountVowels()
{
    string testString = "Bonjour tout le monde!";
    int vowelCount = CountVowels(testString);
    Debug.Log("Le nombre de voyelles dans la chaîne est : " + vowelCount);
}
```
Cette fonction initialise une chaîne de caractères de test, appelle la fonction CountVowels avec cette chaîne, et affiche le nombre de voyelles dans la console Unity.
Appeler la fonction de test dans la méthode Start :
```c#

void Start()
{
    TestCountVowels();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestCountVowels dans cette méthode pour tester la fonction CountVowels lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui prend une chaîne de caractères en argument et renvoie le nombre de voyelles contenues dans cette chaîne, ainsi qu'une méthode pour tester cette fonction dans Unity.
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

Pour cet exercice, nous devons réécrire la fonction Trouve (qui recherche une sous-chaîne dans une chaîne) en utilisant les fonctions Mid et Len. En C#, nous pouvons utiliser les méthodes Substring et Length pour accomplir cela.

Étape 1 : Créer la fonction Trouve
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;

public class Exercice11_3 : MonoBehaviour
{
    // Fonction qui recherche une sous-chaîne dans une chaîne en utilisant Substring et Length
    public int Trouve(string chaine, string sousChaine)
    {
        int lenChaine = chaine.Length;
        int lenSousChaine = sousChaine.Length;

        for (int i = 0; i <= lenChaine - lenSousChaine; i++)
        {
            if (chaine.Substring(i, lenSousChaine) == sousChaine)
            {
                return i;
            }
        }
        return -1; // Retourne -1 si la sous-chaîne n'est pas trouvée
    }

    // Fonction pour tester la fonction Trouve
    public void TestTrouve()
    {
        string chaine = "Bonjour tout le monde!";
        string sousChaine = "tout";
        int index = Trouve(chaine, sousChaine);
        Debug.Log("La sous-chaîne '" + sousChaine + "' a été trouvée à l'index : " + index);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestTrouve();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction Trouve, vous pouvez appeler la méthode TestTrouve dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_3 : MonoBehaviour
{
    // Fonction qui recherche une sous-chaîne dans une chaîne en utilisant Substring et Length
    public int Trouve(string chaine, string sousChaine)
    {
        int lenChaine = chaine.Length;
        int lenSousChaine = sousChaine.Length;

        for (int i = 0; i <= lenChaine - lenSousChaine; i++)
        {
            if (chaine.Substring(i, lenSousChaine) == sousChaine)
            {
                return i;
            }
        }
        return -1; // Retourne -1 si la sous-chaîne n'est pas trouvée
    }

    // Fonction pour tester la fonction Trouve
    public void TestTrouve()
    {
        string chaine = "Bonjour tout le monde!";
        string sousChaine = "tout";
        int index = Trouve(chaine, sousChaine);
        Debug.Log("La sous-chaîne '" + sousChaine + "' a été trouvée à l'index : " + index);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestTrouve();
    }
}
```
Explication du code C#
Déclaration de la fonction Trouve :

```c#
public int Trouve(string chaine, string sousChaine)
{
    int lenChaine = chaine.Length;
    int lenSousChaine = sousChaine.Length;

    for (int i = 0; i <= lenChaine - lenSousChaine; i++)
    {
        if (chaine.Substring(i, lenSousChaine) == sousChaine)
        {
            return i;
        }
    }
    return -1; // Retourne -1 si la sous-chaîne n'est pas trouvée
}
```
Cette fonction prend deux chaînes de caractères en arguments : chaine (la chaîne principale) et sousChaine (la sous-chaîne à rechercher). Elle utilise une boucle for pour parcourir la chaîne principale et vérifie si la sous-chaîne existe à chaque position en utilisant la méthode Substring et Length. Si la sous-chaîne est trouvée, la fonction renvoie l'index de la première occurrence. Si la sous-chaîne n'est pas trouvée, la fonction renvoie -1.
Déclaration de la fonction TestTrouve pour tester la fonction Trouve :

```c#
public void TestTrouve()
{
    string chaine = "Bonjour tout le monde!";
    string sousChaine = "tout";
    int index = Trouve(chaine, sousChaine);
    Debug.Log("La sous-chaîne '" + sousChaine + "' a été trouvée à l'index : " + index);
}
```
Cette fonction initialise une chaîne de caractères de test et une sous-chaîne à rechercher, appelle la fonction Trouve avec ces chaînes, et affiche l'index de la première occurrence de la sous-chaîne dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestTrouve();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestTrouve dans cette méthode pour tester la fonction Trouve lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui recherche une sous-chaîne dans une chaîne en utilisant les méthodes Substring et Length, ainsi qu'une méthode pour tester cette fonction dans Unity.

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
Pour cet exercice, nous devons écrire une fonction qui prend une chaîne de caractères et un caractère en arguments, et renvoie la chaîne purgée de toutes les occurrences de ce caractère. Si le caractère spécifié ne fait pas partie de la chaîne, la chaîne sera retournée intacte.

Étape 1 : Créer la fonction
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;

public class Exercice11_4 : MonoBehaviour
{
    // Fonction qui purge une chaîne d'un caractère spécifié
    public string Purge(string input, char charToRemove)
    {
        // Utiliser la méthode Replace pour remplacer toutes les occurrences du caractère par une chaîne vide
        return input.Replace(charToRemove.ToString(), string.Empty);
    }

    // Fonction pour tester la fonction Purge
    public void TestPurge()
    {
        string testString1 = "Bonjour";
        char charToRemove1 = 'o';
        string result1 = Purge(testString1, charToRemove1);
        Debug.Log("Purge(\"" + testString1 + "\", '" + charToRemove1 + "') renvoie : " + result1);

        string testString2 = "J'ai horreur des espaces";
        char charToRemove2 = ' ';
        string result2 = Purge(testString2, charToRemove2);
        Debug.Log("Purge(\"" + testString2 + "\", '" + charToRemove2 + "') renvoie : " + result2);

        string testString3 = "Moi, je m'en fous";
        char charToRemove3 = 'y';
        string result3 = Purge(testString3, charToRemove3);
        Debug.Log("Purge(\"" + testString3 + "\", '" + charToRemove3 + "') renvoie : " + result3);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestPurge();
    }
}
Étape 2 : Tester la fonction
Pour tester la fonction Purge, vous pouvez appeler la méthode TestPurge dans la méthode Start de votre script. Voici comment vous pouvez le faire :


using UnityEngine;

public class Exercice11_4 : MonoBehaviour
{
    // Fonction qui purge une chaîne d'un caractère spécifié
    public string Purge(string input, char charToRemove)
    {
        // Utiliser la méthode Replace pour remplacer toutes les occurrences du caractère par une chaîne vide
        return input.Replace(charToRemove.ToString(), string.Empty);
    }

    // Fonction pour tester la fonction Purge
    public void TestPurge()
    {
        string testString1 = "Bonjour";
        char charToRemove1 = 'o';
        string result1 = Purge(testString1, charToRemove1);
        Debug.Log("Purge(\"" + testString1 + "\", '" + charToRemove1 + "') renvoie : " + result1);

        string testString2 = "J'ai horreur des espaces";
        char charToRemove2 = ' ';
        string result2 = Purge(testString2, charToRemove2);
        Debug.Log("Purge(\"" + testString2 + "\", '" + charToRemove2 + "') renvoie : " + result2);

        string testString3 = "Moi, je m'en fous";
        char charToRemove3 = 'y';
        string result3 = Purge(testString3, charToRemove3);
        Debug.Log("Purge(\"" + testString3 + "\", '" + charToRemove3 + "') renvoie : " + result3);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestPurge();
    }
}
```
Explication du code C#
Déclaration de la fonction Purge :

```c#
public string Purge(string input, char charToRemove)
{
    // Utiliser la méthode Replace pour remplacer toutes les occurrences du caractère par une chaîne vide
    return input.Replace(charToRemove.ToString(), string.Empty);
}
```
Cette fonction prend une chaîne de caractères input et un caractère charToRemove en arguments. Elle utilise la méthode Replace pour remplacer toutes les occurrences du caractère spécifié par une chaîne vide, ce qui a pour effet de supprimer toutes les occurrences de ce caractère dans la chaîne.
Déclaration de la fonction TestPurge pour tester la fonction Purge :

```c#
public void TestPurge()
{
    string testString1 = "Bonjour";
    char charToRemove1 = 'o';
    string result1 = Purge(testString1, charToRemove1);
    Debug.Log("Purge(\"" + testString1 + "\", '" + charToRemove1 + "') renvoie : " + result1);

    string testString2 = "J'ai horreur des espaces";
    char charToRemove2 = ' ';
    string result2 = Purge(testString2, charToRemove2);
    Debug.Log("Purge(\"" + testString2 + "\", '" + charToRemove2 + "') renvoie : " + result2);

    string testString3 = "Moi, je m'en fous";
    char charToRemove3 = 'y';
    string result3 = Purge(testString3, charToRemove3);
    Debug.Log("Purge(\"" + testString3 + "\", '" + charToRemove3 + "') renvoie : " + result3);
}
```
Cette fonction initialise plusieurs chaînes de caractères de test et des caractères à supprimer, appelle la fonction Purge avec ces chaînes et caractères, et affiche les résultats dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestPurge();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestPurge dans cette méthode pour tester la fonction Purge lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui purge une chaîne de caractères de toutes les occurrences d'un caractère spécifié, ainsi qu'une méthode pour tester cette fonction dans Unity.

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
Pour cet exercice, nous devons écrire une fonction Purgebis qui prend une chaîne de caractères et une chaîne de caractères à supprimer en arguments, et renvoie la chaîne purgée de toutes les occurrences de ces caractères.

Étape 1 : Créer la fonction
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;

public class Exercice11_5 : MonoBehaviour
{
    // Fonction qui purge une chaîne de plusieurs caractères spécifiés
    public string Purgebis(string input, string charsToRemove)
    {
        // Utiliser une boucle pour remplacer chaque caractère spécifié par une chaîne vide
        foreach (char c in charsToRemove)
        {
            input = input.Replace(c.ToString(), string.Empty);
        }
        return input;
    }

    // Fonction pour tester la fonction Purgebis
    public void TestPurgebis()
    {
        string testString1 = "Bonjour";
        string charsToRemove1 = "o";
        string result1 = Purgebis(testString1, charsToRemove1);
        Debug.Log("Purgebis(\"" + testString1 + "\", \"" + charsToRemove1 + "\") renvoie : " + result1);

        string testString2 = "J'ai horreur des espaces";
        string charsToRemove2 = " ";
        string result2 = Purgebis(testString2, charsToRemove2);
        Debug.Log("Purgebis(\"" + testString2 + "\", \"" + charsToRemove2 + "\") renvoie : " + result2);

        string testString3 = "Moi, je m'en fous";
        string charsToRemove3 = "y";
        string result3 = Purgebis(testString3, charsToRemove3);
        Debug.Log("Purgebis(\"" + testString3 + "\", \"" + charsToRemove3 + "\") renvoie : " + result3);

        string testString4 = "Bonjour tout le monde!";
        string charsToRemove4 = "aeiouy";
        string result4 = Purgebis(testString4, charsToRemove4);
        Debug.Log("Purgebis(\"" + testString4 + "\", \"" + charsToRemove4 + "\") renvoie : " + result4);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestPurgebis();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction Purgebis, vous pouvez appeler la méthode TestPurgebis dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_5 : MonoBehaviour
{
    // Fonction qui purge une chaîne de plusieurs caractères spécifiés
    public string Purgebis(string input, string charsToRemove)
    {
        // Utiliser une boucle pour remplacer chaque caractère spécifié par une chaîne vide
        foreach (char c in charsToRemove)
        {
            input = input.Replace(c.ToString(), string.Empty);
        }
        return input;
    }

    // Fonction pour tester la fonction Purgebis
    public void TestPurgebis()
    {
        string testString1 = "Bonjour";
        string charsToRemove1 = "o";
        string result1 = Purgebis(testString1, charsToRemove1);
        Debug.Log("Purgebis(\"" + testString1 + "\", \"" + charsToRemove1 + "\") renvoie : " + result1);

        string testString2 = "J'ai horreur des espaces";
        string charsToRemove2 = " ";
        string result2 = Purgebis(testString2, charsToRemove2);
        Debug.Log("Purgebis(\"" + testString2 + "\", \"" + charsToRemove2 + "\") renvoie : " + result2);

        string testString3 = "Moi, je m'en fous";
        string charsToRemove3 = "y";
        string result3 = Purgebis(testString3, charsToRemove3);
        Debug.Log("Purgebis(\"" + testString3 + "\", \"" + charsToRemove3 + "\") renvoie : " + result3);

        string testString4 = "Bonjour tout le monde!";
        string charsToRemove4 = "aeiouy";
        string result4 = Purgebis(testString4, charsToRemove4);
        Debug.Log("Purgebis(\"" + testString4 + "\", \"" + charsToRemove4 + "\") renvoie : " + result4);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestPurgebis();
    }
}
```
Explication du code C#
Déclaration de la fonction Purgebis :

```c#
public string Purgebis(string input, string charsToRemove)
{
    // Utiliser une boucle pour remplacer chaque caractère spécifié par une chaîne vide
    foreach (char c in charsToRemove)
    {
        input = input.Replace(c.ToString(), string.Empty);
    }
    return input;
}
```
Cette fonction prend une chaîne de caractères input et une chaîne de caractères charsToRemove en arguments. Elle utilise une boucle foreach pour parcourir chaque caractère dans charsToRemove et remplace toutes les occurrences de ce caractère dans input par une chaîne vide, ce qui a pour effet de supprimer toutes les occurrences de ce caractère dans la chaîne.
Déclaration de la fonction TestPurgebis pour tester la fonction Purgebis :

```c#
public void TestPurgebis()
{
    string testString1 = "Bonjour";
    string charsToRemove1 = "o";
    string result1 = Purgebis(testString1, charsToRemove1);
    Debug.Log("Purgebis(\"" + testString1 + "\", \"" + charsToRemove1 + "\") renvoie : " + result1);

    string testString2 = "J'ai horreur des espaces";
    string charsToRemove2 = " ";
    string result2 = Purgebis(testString2, charsToRemove2);
    Debug.Log("Purgebis(\"" + testString2 + "\", \"" + charsToRemove2 + "\") renvoie : " + result2);

    string testString3 = "Moi, je m'en fous";
    string charsToRemove3 = "y";
    string result3 = Purgebis(testString3, charsToRemove3);
    Debug.Log("Purgebis(\"" + testString3 + "\", \"" + charsToRemove3 + "\") renvoie : " + result3);

    string testString4 = "Bonjour tout le monde!";
    string charsToRemove4 = "aeiouy";
    string result4 = Purgebis(testString4, charsToRemove4);
    Debug.Log("Purgebis(\"" + testString4 + "\", \"" + charsToRemove4 + "\") renvoie : " + result4);
}
```
Cette fonction initialise plusieurs chaînes de caractères de test et des chaînes de caractères à supprimer, appelle la fonction Purgebis avec ces chaînes, et affiche les résultats dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestPurgebis();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestPurgebis dans cette méthode pour tester la fonction Purgebis lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui purge une chaîne de caractères de toutes les occurrences de plusieurs caractères spécifiés, ainsi qu'une méthode pour tester cette fonction dans Unity.
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
Pour cet exercice, nous devons écrire une fonction qui prend un tableau et le nombre d'éléments dans le tableau en arguments, et renvoie le tableau trié. Nous allons utiliser l'algorithme de tri par insertion pour trier le tableau.

Étape 1 : Créer la fonction de tri
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;

public class Exercice11_6 : MonoBehaviour
{
    // Fonction qui effectue le tri d'un tableau en utilisant l'algorithme de tri par insertion
    public void InsertionSort(int[] array, int n)
    {
        for (int i = 1; i < n; i++)
        {
            int key = array[i];
            int j = i - 1;

            // Déplacer les éléments du tableau qui sont plus grands que la clé vers une position à droite de leur position actuelle
            while (j >= 0 && array[j] > key)
            {
                array[j + 1] = array[j];
                j = j - 1;
            }
            array[j + 1] = key;
        }
    }

    // Fonction pour tester la fonction InsertionSort
    public void TestInsertionSort()
    {
        int[] testArray = { 12, 11, 13, 5, 6 };
        int n = testArray.Length;

        Debug.Log("Tableau avant le tri : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }

        InsertionSort(testArray, n);

        Debug.Log("Tableau après le tri : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestInsertionSort();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction InsertionSort, vous pouvez appeler la méthode TestInsertionSort dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_6 : MonoBehaviour
{
    // Fonction qui effectue le tri d'un tableau en utilisant l'algorithme de tri par insertion
    public void InsertionSort(int[] array, int n)
    {
        for (int i = 1; i < n; i++)
        {
            int key = array[i];
            int j = i - 1;

            // Déplacer les éléments du tableau qui sont plus grands que la clé vers une position à droite de leur position actuelle
            while (j >= 0 && array[j] > key)
            {
                array[j + 1] = array[j];
                j = j - 1;
            }
            array[j + 1] = key;
        }
    }

    // Fonction pour tester la fonction InsertionSort
    public void TestInsertionSort()
    {
        int[] testArray = { 12, 11, 13, 5, 6 };
        int n = testArray.Length;

        Debug.Log("Tableau avant le tri : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }

        InsertionSort(testArray, n);

        Debug.Log("Tableau après le tri : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestInsertionSort();
    }
}
```
Explication du code C#
Déclaration de la fonction InsertionSort :

```c#
public void InsertionSort(int[] array, int n)
{
    for (int i = 1; i < n; i++)
    {
        int key = array[i];
        int j = i - 1;

        // Déplacer les éléments du tableau qui sont plus grands que la clé vers une position à droite de leur position actuelle
        while (j >= 0 && array[j] > key)
        {
            array[j + 1] = array[j];
            j = j - 1;
        }
        array[j + 1] = key;
    }
}
```
Cette fonction prend un tableau d'entiers array et le nombre d'éléments n dans le tableau en arguments. Elle utilise l'algorithme de tri par insertion pour trier le tableau. L'algorithme de tri par insertion fonctionne en insérant chaque élément à sa position correcte dans le tableau trié.
Déclaration de la fonction TestInsertionSort pour tester la fonction InsertionSort :

```c#
public void TestInsertionSort()
{
    int[] testArray = { 12, 11, 13, 5, 6 };
    int n = testArray.Length;

    Debug.Log("Tableau avant le tri : ");
    for (int i = 0; i < n; i++)
    {
        Debug.Log(testArray[i] + " ");
    }

    InsertionSort(testArray, n);

    Debug.Log("Tableau après le tri : ");
    for (int i = 0; i < n; i++)
    {
        Debug.Log(testArray[i] + " ");
    }
}
```
Cette fonction initialise un tableau de test testArray, appelle la fonction InsertionSort avec ce tableau, et affiche le tableau avant et après le tri dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestInsertionSort();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestInsertionSort dans cette méthode pour tester la fonction InsertionSort lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui effectue le tri d'un tableau en utilisant l'algorithme de tri par insertion, ainsi qu'une méthode pour tester cette fonction dans Unity.
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
Pour cet exercice, nous devons écrire une fonction qui prend un tableau en argument et renvoie un booléen indiquant si le tableau est trié en ordre croissant ou non.

Étape 1 : Créer la fonction
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;

public class Exercice11_7 : MonoBehaviour
{
    // Fonction qui vérifie si un tableau est trié en ordre croissant
    public bool IsSorted(int[] array, int n)
    {
        for (int i = 0; i < n - 1; i++)
        {
            if (array[i] > array[i + 1])
            {
                return false;
            }
        }
        return true;
    }

    // Fonction pour tester la fonction IsSorted
    public void TestIsSorted()
    {
        int[] sortedArray = { 1, 2, 3, 4, 5 };
        int[] unsortedArray = { 3, 1, 4, 2, 5 };

        bool isSortedArraySorted = IsSorted(sortedArray, sortedArray.Length);
        bool isUnsortedArraySorted = IsSorted(unsortedArray, unsortedArray.Length);

        Debug.Log("Le tableau { 1, 2, 3, 4, 5 } est trié : " + isSortedArraySorted);
        Debug.Log("Le tableau { 3, 1, 4, 2, 5 } est trié : " + isUnsortedArraySorted);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestIsSorted();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction IsSorted, vous pouvez appeler la méthode TestIsSorted dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_7 : MonoBehaviour
{
    // Fonction qui vérifie si un tableau est trié en ordre croissant
    public bool IsSorted(int[] array, int n)
    {
        for (int i = 0; i < n - 1; i++)
        {
            if (array[i] > array[i + 1])
            {
                return false;
            }
        }
        return true;
    }

    // Fonction pour tester la fonction IsSorted
    public void TestIsSorted()
    {
        int[] sortedArray = { 1, 2, 3, 4, 5 };
        int[] unsortedArray = { 3, 1, 4, 2, 5 };

        bool isSortedArraySorted = IsSorted(sortedArray, sortedArray.Length);
        bool isUnsortedArraySorted = IsSorted(unsortedArray, unsortedArray.Length);

        Debug.Log("Le tableau { 1, 2, 3, 4, 5 } est trié : " + isSortedArraySorted);
        Debug.Log("Le tableau { 3, 1, 4, 2, 5 } est trié : " + isUnsortedArraySorted);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestIsSorted();
    }
}
```
Explication du code C#
Déclaration de la fonction IsSorted :

```c#
public bool IsSorted(int[] array, int n)
{
    for (int i = 0; i < n - 1; i++)
    {
        if (array[i] > array[i + 1])
        {
            return false;
        }
    }
    return true;
}
```
Cette fonction prend un tableau d'entiers array et le nombre d'éléments n dans le tableau en arguments. Elle parcourt le tableau et vérifie si chaque élément est inférieur ou égal à l'élément suivant. Si elle trouve un élément qui est supérieur à l'élément suivant, elle renvoie false, indiquant que le tableau n'est pas trié. Si elle parcourt tout le tableau sans trouver d'élément supérieur à l'élément suivant, elle renvoie true, indiquant que le tableau est trié.
Déclaration de la fonction TestIsSorted pour tester la fonction IsSorted :

```c#
public void TestIsSorted()
{
    int[] sortedArray = { 1, 2, 3, 4, 5 };
    int[] unsortedArray = { 3, 1, 4, 2, 5 };

    bool isSortedArraySorted = IsSorted(sortedArray, sortedArray.Length);
    bool isUnsortedArraySorted = IsSorted(unsortedArray, unsortedArray.Length);

    Debug.Log("Le tableau { 1, 2, 3, 4, 5 } est trié : " + isSortedArraySorted);
    Debug.Log("Le tableau { 3, 1, 4, 2, 5 } est trié : " + isUnsortedArraySorted);
}
```
Cette fonction initialise deux tableaux de test, un trié et un non trié. Elle appelle la fonction IsSorted avec ces tableaux et affiche les résultats dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestIsSorted();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestIsSorted dans cette méthode pour tester la fonction IsSorted lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui vérifie si un tableau est trié en ordre croissant, ainsi qu'une méthode pour tester cette fonction dans Unity.
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
Pour cet exercice, nous devons écrire une fonction qui prend deux valeurs en arguments et inverse leur contenu. En C#, nous pouvons utiliser des références pour modifier les valeurs des arguments passés à la fonction.

Étape 1 : Créer la fonction
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;

public class Exercice11_8 : MonoBehaviour
{
    // Fonction qui inverse le contenu de deux valeurs passées en argument
    public void Swap(ref int a, ref int b)
    {
        int temp = a;
        a = b;
        b = temp;
    }

    // Fonction pour tester la fonction Swap
    public void TestSwap()
    {
        int x = 5;
        int y = 10;

        Debug.Log("Avant l'échange : x = " + x + ", y = " + y);

        Swap(ref x, ref y);

        Debug.Log("Après l'échange : x = " + x + ", y = " + y);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestSwap();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction Swap, vous pouvez appeler la méthode TestSwap dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_8 : MonoBehaviour
{
    // Fonction qui inverse le contenu de deux valeurs passées en argument
    public void Swap(ref int a, ref int b)
    {
        int temp = a;
        a = b;
        b = temp;
    }

    // Fonction pour tester la fonction Swap
    public void TestSwap()
    {
        int x = 5;
        int y = 10;

        Debug.Log("Avant l'échange : x = " + x + ", y = " + y);

        Swap(ref x, ref y);

        Debug.Log("Après l'échange : x = " + x + ", y = " + y);
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestSwap();
    }
}
```
Explication du code C#
Déclaration de la fonction Swap :

```c#
public void Swap(ref int a, ref int b)
{
    int temp = a;
    a = b;
    b = temp;
}
```
Cette fonction prend deux arguments de type int passés par référence (ref). Elle utilise une variable temporaire temp pour échanger les valeurs de a et b.
Déclaration de la fonction TestSwap pour tester la fonction Swap :

```c#
public void TestSwap()
{
    int x = 5;
    int y = 10;

    Debug.Log("Avant l'échange : x = " + x + ", y = " + y);

    Swap(ref x, ref y);

    Debug.Log("Après l'échange : x = " + x + ", y = " + y);
}
```
Cette fonction initialise deux variables x et y avec des valeurs de test. Elle appelle la fonction Swap avec ces variables et affiche les valeurs avant et après l'échange dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestSwap();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestSwap dans cette méthode pour tester la fonction Swap lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui inverse le contenu de deux valeurs passées en argument, ainsi qu'une méthode pour tester cette fonction dans Unity.
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
Pour cet exercice, nous devons reprendre l'exercice 11.6 et modifier la fonction de tri pour inclure un troisième paramètre de type booléen. Ce paramètre indiquera si le tri doit être effectué dans l'ordre croissant (true) ou décroissant (false).

Étape 1 : Créer la fonction de tri
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;

public class Exercice11_9 : MonoBehaviour
{
    // Fonction qui effectue le tri d'un tableau en utilisant l'algorithme de tri par insertion
    public void InsertionSort(int[] array, int n, bool ascending)
    {
        for (int i = 1; i < n; i++)
        {
            int key = array[i];
            int j = i - 1;

            // Déplacer les éléments du tableau qui sont plus grands que la clé vers une position à droite de leur position actuelle
            if (ascending)
            {
                while (j >= 0 && array[j] > key)
                {
                    array[j + 1] = array[j];
                    j = j - 1;
                }
            }
            else
            {
                while (j >= 0 && array[j] < key)
                {
                    array[j + 1] = array[j];
                    j = j - 1;
                }
            }
            array[j + 1] = key;
        }
    }

    // Fonction pour tester la fonction InsertionSort
    public void TestInsertionSort()
    {
        int[] testArray = { 12, 11, 13, 5, 6 };
        int n = testArray.Length;

        Debug.Log("Tableau avant le tri : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }

        InsertionSort(testArray, n, true);

        Debug.Log("Tableau après le tri croissant : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }

        InsertionSort(testArray, n, false);

        Debug.Log("Tableau après le tri décroissant : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestInsertionSort();
    }
}
```
Étape 2 : Tester la fonction
Pour tester la fonction InsertionSort, vous pouvez appeler la méthode TestInsertionSort dans la méthode Start de votre script. Voici comment vous pouvez le faire :

```c#
using UnityEngine;

public class Exercice11_9 : MonoBehaviour
{
    // Fonction qui effectue le tri d'un tableau en utilisant l'algorithme de tri par insertion
    public void InsertionSort(int[] array, int n, bool ascending)
    {
        for (int i = 1; i < n; i++)
        {
            int key = array[i];
            int j = i - 1;

            // Déplacer les éléments du tableau qui sont plus grands que la clé vers une position à droite de leur position actuelle
            if (ascending)
            {
                while (j >= 0 && array[j] > key)
                {
                    array[j + 1] = array[j];
                    j = j - 1;
                }
            }
            else
            {
                while (j >= 0 && array[j] < key)
                {
                    array[j + 1] = array[j];
                    j = j - 1;
                }
            }
            array[j + 1] = key;
        }
    }

    // Fonction pour tester la fonction InsertionSort
    public void TestInsertionSort()
    {
        int[] testArray = { 12, 11, 13, 5, 6 };
        int n = testArray.Length;

        Debug.Log("Tableau avant le tri : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }

        InsertionSort(testArray, n, true);

        Debug.Log("Tableau après le tri croissant : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }

        InsertionSort(testArray, n, false);

        Debug.Log("Tableau après le tri décroissant : ");
        for (int i = 0; i < n; i++)
        {
            Debug.Log(testArray[i] + " ");
        }
    }

    // Appeler la fonction de test dans la méthode Start
    void Start()
    {
        TestInsertionSort();
    }
}
```
Explication du code C#
Déclaration de la fonction InsertionSort :
```c#

public void InsertionSort(int[] array, int n, bool ascending)
{
    for (int i = 1; i < n; i++)
    {
        int key = array[i];
        int j = i - 1;

        // Déplacer les éléments du tableau qui sont plus grands que la clé vers une position à droite de leur position actuelle
        if (ascending)
        {
            while (j >= 0 && array[j] > key)
            {
                array[j + 1] = array[j];
                j = j - 1;
            }
        }
        else
        {
            while (j >= 0 && array[j] < key)
            {
                array[j + 1] = array[j];
                j = j - 1;
            }
        }
        array[j + 1] = key;
    }
}
```
Cette fonction prend un tableau d'entiers array, le nombre d'éléments n dans le tableau, et un booléen ascending en arguments. Elle utilise l'algorithme de tri par insertion pour trier le tableau. Si ascending est true, le tableau est trié en ordre croissant. Si ascending est false, le tableau est trié en ordre décroissant.
Déclaration de la fonction TestInsertionSort pour tester la fonction InsertionSort :

```c#
public void TestInsertionSort()
{
    int[] testArray = { 12, 11, 13, 5, 6 };
    int n = testArray.Length;

    Debug.Log("Tableau avant le tri : ");
    for (int i = 0; i < n; i++)
    {
        Debug.Log(testArray[i] + " ");
    }

    InsertionSort(testArray, n, true);

    Debug.Log("Tableau après le tri croissant : ");
    for (int i = 0; i < n; i++)
    {
        Debug.Log(testArray[i] + " ");
    }

    InsertionSort(testArray, n, false);

    Debug.Log("Tableau après le tri décroissant : ");
    for (int i = 0; i < n; i++)
    {
        Debug.Log(testArray[i] + " ");
    }
}
```
Cette fonction initialise un tableau de test testArray, appelle la fonction InsertionSort avec ce tableau pour trier en ordre croissant et décroissant, et affiche le tableau avant et après chaque tri dans la console Unity.
Appeler la fonction de test dans la méthode Start :

```c#
void Start()
{
    TestInsertionSort();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la fonction TestInsertionSort dans cette méthode pour tester la fonction InsertionSort lorsque le script est chargé.
En suivant ces étapes, vous aurez une fonction en C# qui effectue le tri d'un tableau en utilisant l'algorithme de tri par insertion, avec la possibilité de trier en ordre croissant ou décroissant en fonction d'un paramètre booléen, ainsi qu'une méthode pour tester cette fonction dans Unity.

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

Pour réaliser cette application complète de génération de grilles de Sudoku, nous allons suivre les étapes décrites dans l'énoncé. Nous allons écrire les fonctions et procédures nécessaires pour générer et vérifier une grille de Sudoku.

Étape 1 : Écrire la fonction TousDifferents
Cette fonction vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes.

```c#
using UnityEngine;

public class SudokuGenerator : MonoBehaviour
{
    // Fonction qui vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes
    public bool TousDifferents(int[] tableau)
    {
        for (int i = 0; i < 9; i++)
        {
            for (int j = i + 1; j < 9; j++)
            {
                if (tableau[i] == tableau[j])
                {
                    return false;
                }
            }
        }
        return true;
    }
}
```
Étape 2 : Écrire la procédure RemplitGrille
Cette procédure remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9.

```c#
public class SudokuGenerator : MonoBehaviour
{
    // Fonction qui vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes
    public bool TousDifferents(int[] tableau)
    {
        for (int i = 0; i < 9; i++)
        {
            for (int j = i + 1; j < 9; j++)
            {
                if (tableau[i] == tableau[j])
                {
                    return false;
                }
            }
        }
        return true;
    }

    // Procédure qui remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9
    public void RemplitGrille(int[] grille)
    {
        for (int i = 0; i < 81; i++)
        {
            grille[i] = Random.Range(1, 10);
        }
    }
}
```
Étape 3 : Écrire la fonction VerifLignes
Cette fonction vérifie si toutes les lignes de la grille de Sudoku sont correctes.
```c#

public class SudokuGenerator : MonoBehaviour
{
    // Fonction qui vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes
    public bool TousDifferents(int[] tableau)
    {
        for (int i = 0; i < 9; i++)
        {
            for (int j = i + 1; j < 9; j++)
            {
                if (tableau[i] == tableau[j])
                {
                    return false;
                }
            }
        }
        return true;
    }

    // Procédure qui remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9
    public void RemplitGrille(int[] grille)
    {
        for (int i = 0; i < 81; i++)
        {
            grille[i] = Random.Range(1, 10);
        }
    }

    // Fonction qui vérifie si toutes les lignes de la grille de Sudoku sont correctes
    public bool VerifLignes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] ligne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                ligne[j] = grille[i * 9 + j];
            }
            if (!TousDifferents(ligne))
            {
                return false;
            }
        }
        return true;
    }
}
```
Étape 4 : Écrire la fonction VerifColonnes
Cette fonction vérifie si toutes les colonnes de la grille de Sudoku sont correctes.

```c#
public class SudokuGenerator : MonoBehaviour
{
    // Fonction qui vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes
    public bool TousDifferents(int[] tableau)
    {
        for (int i = 0; i < 9; i++)
        {
            for (int j = i + 1; j < 9; j++)
            {
                if (tableau[i] == tableau[j])
                {
                    return false;
                }
            }
        }
        return true;
    }

    // Procédure qui remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9
    public void RemplitGrille(int[] grille)
    {
        for (int i = 0; i < 81; i++)
        {
            grille[i] = Random.Range(1, 10);
        }
    }

    // Fonction qui vérifie si toutes les lignes de la grille de Sudoku sont correctes
    public bool VerifLignes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] ligne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                ligne[j] = grille[i * 9 + j];
            }
            if (!TousDifferents(ligne))
            {
                return false;
            }
        }
        return true;
    }

    // Fonction qui vérifie si toutes les colonnes de la grille de Sudoku sont correctes
    public bool VerifColonnes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] colonne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                colonne[j] = grille[j * 9 + i];
            }
            if (!TousDifferents(colonne))
            {
                return false;
            }
        }
        return true;
    }
}
```
Étape 5 : Écrire la fonction VerifSousGrilles
Cette fonction vérifie si toutes les sous-grilles 3x3 de la grille de Sudoku sont correctes.

```c#
public class SudokuGenerator : MonoBehaviour
{
    // Fonction qui vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes
    public bool TousDifferents(int[] tableau)
    {
        for (int i = 0; i < 9; i++)
        {
            for (int j = i + 1; j < 9; j++)
            {
                if (tableau[i] == tableau[j])
                {
                    return false;
                }
            }
        }
        return true;
    }

    // Procédure qui remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9
    public void RemplitGrille(int[] grille)
    {
        for (int i = 0; i < 81; i++)
        {
            grille[i] = Random.Range(1, 10);
        }
    }

    // Fonction qui vérifie si toutes les lignes de la grille de Sudoku sont correctes
    public bool VerifLignes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] ligne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                ligne[j] = grille[i * 9 + j];
            }
            if (!TousDifferents(ligne))
            {
                return false;
            }
        }
        return true;
    }

    // Fonction qui vérifie si toutes les colonnes de la grille de Sudoku sont correctes
    public bool VerifColonnes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] colonne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                colonne[j] = grille[j * 9 + i];
            }
            if (!TousDifferents(colonne))
            {
                return false;
            }
        }
        return true;
    }

    // Fonction qui vérifie si toutes les sous-grilles 3x3 de la grille de Sudoku sont correctes
    public bool VerifSousGrilles(int[] grille)
    {
        for (int i = 0; i < 9; i += 3)
        {
            for (int j = 0; j < 9; j += 3)
            {
                int[] sousGrille = new int[9];
                int index = 0;
                for (int k = 0; k < 3; k++)
                {
                    for (int l = 0; l < 3; l++)
                    {
                        sousGrille[index++] = grille[(i + k) * 9 + (j + l)];
                    }
                }
                if (!TousDifferents(sousGrille))
                {
                    return false;
                }
            }
        }
        return true;
    }
}
```
Étape 6 : Écrire la procédure principale
Cette procédure génère une grille de Sudoku valide en utilisant les fonctions et procédures précédentes.

```c#
public class SudokuGenerator : MonoBehaviour
{
    // Fonction qui vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes
    public bool TousDifferents(int[] tableau)
    {
        for (int i = 0; i < 9; i++)
        {
            for (int j = i + 1; j < 9; j++)
            {
                if (tableau[i] == tableau[j])
                {
                    return false;
                }
            }
        }
        return true;
    }

    // Procédure qui remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9
    public void RemplitGrille(int[] grille)
    {
        for (int i = 0; i < 81; i++)
        {
            grille[i] = Random.Range(1, 10);
        }
    }

    // Fonction qui vérifie si toutes les lignes de la grille de Sudoku sont correctes
    public bool VerifLignes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] ligne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                ligne[j] = grille[i * 9 + j];
            }
            if (!TousDifferents(ligne))
            {
                return false;
            }
        }
        return true;
    }

    // Fonction qui vérifie si toutes les colonnes de la grille de Sudoku sont correctes
    public bool VerifColonnes(int[] grille)
    {
        for (int i = 0; i < 9; i++)
        {
            int[] colonne = new int[9];
            for (int j = 0; j < 9; j++)
            {
                colonne[j] = grille[j * 9 + i];
            }
            if (!TousDifferents(colonne))
            {
                return false;
            }
        }
        return true;
    }

    // Fonction qui vérifie si toutes les sous-grilles 3x3 de la grille de Sudoku sont correctes
    public bool VerifSousGrilles(int[] grille)
    {
        for (int i = 0; i < 9; i += 3)
        {
            for (int j = 0; j < 9; j += 3)
            {
                int[] sousGrille = new int[9];
                int index = 0;
                for (int k = 0; k < 3; k++)
                {
                    for (int l = 0; l < 3; l++)
                    {
                        sousGrille[index++] = grille[(i + k) * 9 + (j + l)];
                    }
                }
                if (!TousDifferents(sousGrille))
                {
                    return false;
                }
            }
        }
        return true;
    }

    // Procédure principale qui génère une grille de Sudoku valide
    public void GenererGrilleSudoku()
    {
        int[] grille = new int[81];
        bool grilleValide = false;

        while (!grilleValide)
        {
            RemplitGrille(grille);
            grilleValide = VerifLignes(grille) && VerifColonnes(grille) && VerifSousGrilles(grille);
        }

        // Afficher la grille de Sudoku générée
        Debug.Log("Grille de Sudoku générée :");
        for (int i = 0; i < 9; i++)
        {
            string ligne = "";
            for (int j = 0; j < 9; j++)
            {
                ligne += grille[i * 9 + j] + " ";
            }
            Debug.Log(ligne);
        }
    }

    // Appeler la procédure principale dans la méthode Start
    void Start()
    {
        GenererGrilleSudoku();
    }
}
```
Explication du code C#
Déclaration de la fonction TousDifferents :

```c#
public bool TousDifferents(int[] tableau)
{
    for (int i = 0; i < 9; i++)
    {
        for (int j = i + 1; j < 9; j++)
        {
            if (tableau[i] == tableau[j])
            {
                return false;
            }
        }
    }
    return true;
}
```
Cette fonction vérifie si toutes les valeurs d'un tableau de 9 éléments sont différentes.
Déclaration de la procédure RemplitGrille :
```c#

public void RemplitGrille(int[] grille)
{
    for (int i = 0; i < 81; i++)
    {
        grille[i] = Random.Range(1, 10);
    }
}
```
Cette procédure remplit la grille de Sudoku avec des valeurs aléatoires entre 1 et 9.
Déclaration de la fonction VerifLignes :

```c#
public bool VerifLignes(int[] grille)
{
    for (int i = 0; i < 9; i++)
    {
        int[] ligne = new int[9];
        for (int j = 0; j < 9; j++)
        {
            ligne[j] = grille[i * 9 + j];
        }
        if (!TousDifferents(ligne))
        {
            return false;
        }
    }
    return true;
}
```
Cette fonction vérifie si toutes les lignes de la grille de Sudoku sont correctes.
Déclaration de la fonction VerifColonnes :

```c#
public bool VerifColonnes(int[] grille)
{
    for (int i = 0; i < 9; i++)
    {
        int[] colonne = new int[9];
        for (int j = 0; j < 9; j++)
        {
            colonne[j] = grille[j * 9 + i];
        }
        if (!TousDifferents(colonne))
        {
            return false;
        }
    }
    return true;
}
```
Cette fonction vérifie si toutes les colonnes de la grille de Sudoku sont correctes.
Déclaration de la fonction VerifSousGrilles :

```c#
public bool VerifSousGrilles(int[] grille)
{
    for (int i = 0; i < 9; i += 3)
    {
        for (int j = 0; j < 9; j += 3)
        {
            int[] sousGrille = new int[9];
            int index = 0;
            for (int k = 0; k < 3; k++)
            {
                for (int l = 0; l < 3; l++)
                {
                    sousGrille[index++] = grille[(i + k) * 9 + (j + l)];
                }
            }
            if (!TousDifferents(sousGrille))
            {
                return false;
            }
        }
    }
    return true;
}
```
Cette fonction vérifie si toutes les sous-grilles 3x3 de la grille de Sudoku sont correctes.
Déclaration de la procédure principale GenererGrilleSudoku :

```c#
public void GenererGrilleSudoku()
{
    int[] grille = new int[81];
    bool grilleValide = false;

    while (!grilleValide)
    {
        RemplitGrille(grille);
        grilleValide = VerifLignes(grille) && VerifColonnes(grille) && VerifSousGrilles(grille);
    }

    // Afficher la grille de Sudoku générée
    Debug.Log("Grille de Sudoku générée :");
    for (int i = 0; i < 9; i++)
    {
        string ligne = "";
        for (int j = 0; j < 9; j++)
        {
            ligne += grille[i * 9 + j] + " ";
        }
        Debug.Log(ligne);
    }
}
```
Cette procédure génère une grille de Sudoku valide en utilisant les fonctions et procédures précédentes.
Appeler la procédure principale dans la méthode Start :
```c#

void Start()
{
    GenererGrilleSudoku();
}
```
La méthode Start est appelée une fois lorsque le script est chargé. Nous appelons la procédure GenererGrilleSudoku dans cette méthode pour générer une grille de Sudoku valide lorsque le script est chargé.