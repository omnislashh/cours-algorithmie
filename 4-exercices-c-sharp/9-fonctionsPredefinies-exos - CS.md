# Exercice 9.1
Parmi ces affectations (considérées indépendamment les unes des autres), lesquelles provoqueront des erreurs, et pourquoi ?
```
Variables A, B, C en Numérique
Variable D en Caractère
A ← Sin(B)
A ← Sin(A + B * C)
B ← Sin(A) – Sin(D)
C ← Sin(A / B)
C ← Cos(Sin(A)
```
```
A ← Sin(B)            Aucun problème
A ← Sin(A + B * C)    Aucun problème
B ← Sin(A) – Sin(D)   Erreur ! D est en caractère
C ← Sin(A / B)        Aucun problème… si B est différent de zéro
C ← Cos(Sin(A)        Erreur ! Il manque une parenthèse fermante
```

Analyse des affectations
Variables :

A, B, C sont des variables numériques.
D est une variable de type caractère.
Affectations :

A ← Sin(B)
A ← Sin(A + B * C)
B ← Sin(A) – Sin(D)
C ← Sin(A / B)
C ← Cos(Sin(A))
```
Analyse des erreurs possibles
A ← Sin(B)

Analyse : Sin(B) est une opération mathématique valide si B est une variable numérique.
Conclusion : Pas d'erreur.
A ← Sin(A + B * C)

Analyse : A + B * C est une opération mathématique valide si A, B, et C sont des variables numériques. Sin(A + B * C) est donc valide.
Conclusion : Pas d'erreur.
B ← Sin(A) – Sin(D)

Analyse : Sin(A) est valide car A est une variable numérique. Cependant, Sin(D) n'est pas valide car D est une variable de type caractère. La fonction Sin attend un argument numérique.
Conclusion : Erreur. Sin(D) n'est pas valide car D est une variable de type caractère.
C ← Sin(A / B)

Analyse : A / B est une opération mathématique valide si A et B sont des variables numériques. Cependant, si B est égal à zéro, cela provoquera une division par zéro, ce qui est une erreur mathématique.
Conclusion : Erreur potentielle si B est égal à zéro (division par zéro).
C ← Cos(Sin(A))

Analyse : Sin(A) est valide car A est une variable numérique. Cos(Sin(A)) est donc valide.
Conclusion : Pas d'erreur.
Résumé des erreurs
B ← Sin(A) – Sin(D)

Erreur : Sin(D) n'est pas valide car D est une variable de type caractère.
Raison : La fonction Sin attend un argument numérique, mais D est un caractère.
C ← Sin(A / B)

Erreur potentielle : Division par zéro si B est égal à zéro.
Raison : La division par zéro est une erreur mathématique.
Conclusion
Les affectations B ← Sin(A) – Sin(D) et C ← Sin(A / B) provoqueront des erreurs. La première en raison de l'utilisation incorrecte de la fonction Sin avec une variable de type caractère, et la seconde en raison de la possibilité de division par zéro.
```
# Exercice 9.2
Ecrivez un algorithme qui demande un mot à l’utilisateur et qui affiche à l’écran le nombre de lettres de ce mot (c'est vraiment tout bête).

Vous étiez prévenus, c'est bête comme chou ! Il suffit de se servir de la fonction Len, et c'est réglé :

```
Variable Mot en Caractère
Variable Nb en Entier
Debut
Ecrire "Entrez un mot : "
Lire Mot
Nb ← Len(Mot)
Ecrire "Ce mot compte ", Nb, " lettres"
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du mot :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Word.
Ajouter un Button pour déclencher l'affichage du nombre de lettres :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CountLetters.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_2 : MonoBehaviour
{
    public InputField inputField_Word; // Référence à l'InputField pour le mot
    public Text resultText; // Référence au Text pour afficher le résultat

    public void CountLetters()
    {
        // Lire la valeur de l'InputField
        string word = inputField_Word.text;

        // Calculer le nombre de lettres dans le mot
        int letterCount = word.Length;

        // Afficher le nombre de lettres
        resultText.text = "Le mot contient " + letterCount + " lettres.";
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, WordCounter).
Dans l'inspecteur, faites glisser l'InputField pour le mot (InputField_Word) dans le champ InputField_Word du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher l'affichage du nombre de lettres (Button_CountLetters) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (WordCounter) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_2 -> CountLetters.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Word;
public Text resultText;
```
Méthode CountLetters pour lire l'entrée du mot, calculer le nombre de lettres, et afficher le résultat :

```c#
public void CountLetters()
{
    string word = inputField_Word.text;
    int letterCount = word.Length;
    resultText.text = "Le mot contient " + letterCount + " lettres.";
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un mot à l'utilisateur et affiche le nombre de lettres de ce mot dans un Text.

# Exercice 9.3
Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui affiche à l’écran le nombre de mots de cette phrase. On suppose que les mots ne sont séparés que par des espaces (et c'est déjà un petit peu moins bête).

Là, on est obligé de compter par une boucle le nombre d'espaces de la phrase, et on en déduit le nombre de mots. La boucle examine les caractères de la phrase un par un, du premier au dernier, et les compare à l'espace.

```
Variable Bla en Caractère
Variables Nb, i en Entier
Debut
Ecrire "Entrez une phrase : "
Lire Bla
Nb ← 0
Pour i ← 1 à Len(Bla)
  Si Mid(Bla, i , 1) = " " Alors
    Nb ← Nb + 1
  FinSi
i suivant
Ecrire "Cette phrase compte ", Nb + 1, " mots"
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un Button pour déclencher l'affichage du nombre de mots :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CountWords.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_3 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public Text resultText; // Référence au Text pour afficher le résultat

    public void CountWords()
    {
        // Lire la valeur de l'InputField
        string phrase = inputField_Phrase.text;

        // Calculer le nombre de mots dans la phrase
        string[] words = phrase.Split(' ');
        int wordCount = words.Length;

        // Afficher le nombre de mots
        resultText.text = "La phrase contient " + wordCount + " mots.";
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, WordCounter).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher l'affichage du nombre de mots (Button_CountWords) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (WordCounter) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_3 -> CountWords.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Phrase;
public Text resultText;
```
Méthode CountWords pour lire l'entrée de la phrase, calculer le nombre de mots, et afficher le résultat :

```c#
public void CountWords()
{
    string phrase = inputField_Phrase.text;
    string[] words = phrase.Split(' ');
    int wordCount = words.Length;
    resultText.text = "La phrase contient " + wordCount + " mots.";
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur et affiche le nombre de mots de cette phrase dans un Text.


# Exercice 9.4
Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui affiche à l’écran le nombre de voyelles contenues dans cette phrase.
On pourra écrire deux solutions. La première déploie une condition composée bien fastidieuse. La deuxième, en utilisant la fonction Trouve, allège considérablement l'algorithme.

Solution 1 : pour chaque caractère du mot, on pose une très douloureuse condition composée. Le moins que l'on puisse dire, c'est que ce choix ne se distingue pas par son élégance. Cela dit, il marche, donc après tout, pourquoi pas.

```
Variable Bla en Caractère
Variables Nb, i, j en Entier
Debut
Ecrire "Entrez une phrase : "
Lire Bla
Nb ← 0
Pour i ← 1 à Len(Bla)
  Si Mid(Bla, i, 1) = "a" ou Mid(Bla, i, 1) = "e" ou Mid(Bla, i, 1) = "i" ou Mid(Bla, i, 1) = "o" ou Mid(Bla, i, 1) = "u" ou Mid(Bla, i, 1) = "y" Alors
    Nb ← Nb + 1
  FinSi
i suivant
Ecrire "Cette phrase compte ", Nb, " voyelles"
Fin
```
Solution 2 : on stocke toutes les voyelles dans une chaîne. Grâce à la fonction Trouve, on détecte immédiatement si le caractère examiné est une voyelle ou non. C'est nettement plus sympathique...

```
Variables Bla, Voy en Caractère
Variables Nb, i, j en Entier
Debut
Ecrire "Entrez une phrase : "
Lire Bla
Nb ← 0
Voy ← "aeiouy"
Pour i ← 1 à Len(Bla)
  Si Trouve(Voy, Mid(Bla, i, 1)) <> 0 Alors
    Nb ← Nb + 1
  FinSi
i suivant
Ecrire "Cette phrase compte ", Nb, " voyelles"
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un Button pour déclencher l'affichage du nombre de voyelles :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CountVowels.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice9_4 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public Text resultText; // Référence au Text pour afficher le résultat

    public void CountVowels()
    {
        // Lire la valeur de l'InputField
        string phrase = inputField_Phrase.text;

        // Solution 1 : Utiliser une condition composée
        int vowelCount = 0;
        foreach (char c in phrase)
        {
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' ||
                c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U')
            {
                vowelCount++;
            }
        }

        // Solution 2 : Utiliser une fonction de recherche
        int vowelCount2 = 0;
        foreach (char c in phrase)
        {
            if ("aeiouAEIOU".IndexOf(c) >= 0)
            {
                vowelCount2++;
            }
        }

        // Afficher le nombre de voyelles
        resultText.text = "La phrase contient " + vowelCount + " voyelles (Solution 1).\n" +
                          "La phrase contient " + vowelCount2 + " voyelles (Solution 2).";
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, VowelCounter).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher l'affichage du nombre de voyelles (Button_CountVowels) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (VowelCounter) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_4 -> CountVowels.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Phrase;
public Text resultText;
```
Méthode CountVowels pour lire l'entrée de la phrase, calculer le nombre de voyelles, et afficher le résultat :

```c#
public void CountVowels()
{
    string phrase = inputField_Phrase.text;

    // Solution 1 : Utiliser une condition composée
    int vowelCount = 0;
    foreach (char c in phrase)
    {
        if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' ||
            c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U')
        {
            vowelCount++;
        }
    }

    // Solution 2 : Utiliser une fonction de recherche
    int vowelCount2 = 0;
    foreach (char c in phrase)
    {
        if ("aeiouAEIOU".IndexOf(c) >= 0)
        {
            vowelCount2++;
        }
    }

    resultText.text = "La phrase contient " + vowelCount + " voyelles (Solution 1).\n" +
                      "La phrase contient " + vowelCount2 + " voyelles (Solution 2).";
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur et affiche le nombre de voyelles de cette phrase dans un Text, en utilisant deux solutions différentes pour compter les voyelles.

# Exercice 9.5
Ecrivez un algorithme qui demande une phrase à l’utilisateur. Celui-ci entrera ensuite le rang d’un caractère à supprimer, et la nouvelle phrase doit être affichée (on doit réellement supprimer le caractère dans la variable qui stocke la phrase, et pas uniquement à l’écran).

Il n'existe aucun moyen de supprimer directement un caractère d'une chaîne… autrement qu'en procédant par collage. Il faut donc concaténer ce qui se trouve à gauche du caractère à supprimer, avec ce qui se trouve à sa droite. Attention aux paramètres des fonctions Mid, ils n'ont rien d'évident !
```
Variable Bla en Caractère
Variables Nb, i, j en Entier
Début
Ecrire "Entrez une phrase : "
Lire Bla
Ecrire "Entrez le rang du caractère à supprimer : "
Lire Nb
L ← Len(Bla)
Bla ← Mid(Bla, 1, Nb – 1) & Mid(Bla, Nb + 1, L – Nb)
Ecrire "La nouvelle phrase est : ", Bla
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un InputField pour l'entrée du rang du caractère à supprimer :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Index.
Ajouter un Button pour déclencher la suppression du caractère :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_RemoveCharacter.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_5 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public InputField inputField_Index; // Référence à l'InputField pour le rang du caractère à supprimer
    public Text resultText; // Référence au Text pour afficher le résultat

    public void RemoveCharacter()
    {
        // Lire la valeur de l'InputField pour la phrase
        string phrase = inputField_Phrase.text;

        // Lire la valeur de l'InputField pour le rang du caractère à supprimer
        string indexInput = inputField_Index.text;

        // Convertir la valeur en entier
        if (int.TryParse(indexInput, out int index))
        {
            // Vérifier si l'index est valide
            if (index >= 0 && index < phrase.Length)
            {
                // Supprimer le caractère à l'index spécifié
                phrase = phrase.Remove(index, 1);

                // Afficher la nouvelle phrase
                resultText.text = "Nouvelle phrase : " + phrase;
            }
            else
            {
                // Signaler que l'index est invalide
                resultText.text = "Index invalide. Veuillez entrer un index valide.";
            }
        }
        else
        {
            // Signaler que l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, CharacterRemover).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser l'InputField pour le rang du caractère à supprimer (InputField_Index) dans le champ InputField_Index du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la suppression du caractère (Button_RemoveCharacter) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (CharacterRemover) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_5 -> RemoveCharacter.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Phrase;
public InputField inputField_Index;
public Text resultText;
```
Méthode RemoveCharacter pour lire l'entrée de la phrase et du rang du caractère à supprimer, vérifier la validité de l'index, supprimer le caractère, et afficher la nouvelle phrase :

```c#
public void RemoveCharacter()
{
    string phrase = inputField_Phrase.text;
    string indexInput = inputField_Index.text;

    if (int.TryParse(indexInput, out int index))
    {
        if (index >= 0 && index < phrase.Length)
        {
            phrase = phrase.Remove(index, 1);
            resultText.text = "Nouvelle phrase : " + phrase;
        }
        else
        {
            resultText.text = "Index invalide. Veuillez entrer un index valide.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur, puis demande le rang d'un caractère à supprimer, et affiche la nouvelle phrase après avoir supprimé le caractère dans un Text.

# Exercice 9.6 - Cryptographie 1
Un des plus anciens systèmes de cryptographie (aisément déchiffrable) consiste à décaler les lettres d’un message pour le rendre illisible. Ainsi, les A deviennent des B, les B des C, etc. Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui la code selon ce principe. Comme dans le cas précédent, le codage doit s’effectuer au niveau de la variable stockant la phrase, et pas seulement à l’écran.

Sur l'ensemble des exercices de cryptographie, il y a deux grandes stratégies possibles :

- soit transformer les caractères en leurs codes ASCII. L'algorithme revient donc ensuite à traiter des nombres. Une fois ces nombres transformés, il faut les reconvertir en caractères.

- soit en rester au niveau des caractères, et procéder directement aux transformations à ce niveau. C'est cette dernière option qui est choisie ici, et pour tous les exercices de cryptographie à venir.

Pour cet exercice, il y a une règle générale : pour chaque lettre, on détecte sa position dans l'alphabet, et on la remplace par la lettre occupant la position suivante. Seul cas particulier, la vingt-sixième lettre (le Z) doit être codée par la première (le A), et non par la vingt-septième, qui n'existe pas !

```
Variables Bla, Cod, Alpha en Caractère
Variables i, Pos en Entier
Début
Ecrire "Entrez la phrase à coder : "
Lire Bla
Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
Cod ← ""
Pour i ← 1 à Len(Bla)
  Let ← Mid(Bla, i, 1)
  Si Let <> "Z" Alors
    Pos ← Trouve(Alpha, Let)
    Cod ← Cod & Mid(Alpha, Pos + 1, 1)
  Sinon
    Cod ← Cod & "A"
  FinSi
i Suivant
Bla ← Cod
Ecrire "La phrase codée est : ", Bla
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un Button pour déclencher le codage de la phrase :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EncodePhrase.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_6 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public Text resultText; // Référence au Text pour afficher le résultat

    public void EncodePhrase()
    {
        // Lire la valeur de l'InputField
        string phrase = inputField_Phrase.text;

        // Coder la phrase en décalant chaque lettre d'une position dans l'alphabet
        char[] charArray = phrase.ToCharArray();
        for (int i = 0; i < charArray.Length; i++)
        {
            if (char.IsLetter(charArray[i]))
            {
                char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
                charArray[i] = (char)((charArray[i] - baseChar + 1) % 26 + baseChar);
            }
        }
        string encodedPhrase = new string(charArray);

        // Afficher la phrase codée
        resultText.text = "Phrase codée : " + encodedPhrase;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, PhraseEncoder).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le codage de la phrase (Button_EncodePhrase) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (PhraseEncoder) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_6 -> EncodePhrase.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Phrase;
public Text resultText;
```
Méthode EncodePhrase pour lire l'entrée de la phrase, coder la phrase en décalant chaque lettre d'une position dans l'alphabet, et afficher la phrase codée :

```c#
public void EncodePhrase()
{
    string phrase = inputField_Phrase.text;

    char[] charArray = phrase.ToCharArray();
    for (int i = 0; i < charArray.Length; i++)
    {
        if (char.IsLetter(charArray[i]))
        {
            char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
            charArray[i] = (char)((charArray[i] - baseChar + 1) % 26 + baseChar);
        }
    }
    string encodedPhrase = new string(charArray);

    resultText.text = "Phrase codée : " + encodedPhrase;
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur, code la phrase en décalant chaque lettre d'une position dans l'alphabet, et affiche la phrase codée dans un Text.

# Exercice 9.7 - Cryptographie 2 - le chiffre de César
Une amélioration (relative) du principe précédent consiste à opérer avec un décalage non de 1, mais d’un nombre quelconque de lettres. Ainsi, par exemple, si l’on choisit un décalage de 12, les A deviennent des M, les B des N, etc.
Réalisez un algorithme sur le même principe que le précédent, mais qui demande en plus quel est le décalage à utiliser. Votre sens proverbial de l'élégance vous interdira bien sûr une série de vingt-six "Si...Alors"

Cet algorithme est une généralisation du précédent. Mais là, comme on ne connaît pas d'avance le décalage à appliquer, on ne sait pas a priori combien de "cas particuliers", à savoir de dépassements au-delà du Z, il va y avoir.
Il faut donc trouver un moyen simple de dire que si on obtient 27, il faut en réalité prendre la lettre numéro 1 de l'alphabet, que si on obtient 28, il faut en réalité prendre la numéro 2, etc. Ce moyen simple existe : il faut considérer le reste de la division par 26, autrement dit le modulo.
Il y a une petite ruse supplémentaire à appliquer, puisque 26 doit rester 26 et ne pas devenir 0.
```
Variable Bla, Cod, Alpha en Caractère
Variables i, Pos, Décal en Entier
Début
Ecrire "Entrez le décalage à appliquer : "
Lire Décal
Ecrire "Entrez la phrase à coder : "
Lire Bla
Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
Cod ← ""
Pour i ← 1 à Len(Bla)
  Let ← Mid(Bla, i, 1)
  Pos ← Trouve(Alpha, Let)
  NouvPos ← Mod(Pos + Décal, 26)
  Si NouvPos = 0 Alors
    NouvPos ← 26
  FinSi
  Cod ← Cod & Mid(Alpha, NouvPos, 1)
i Suivant
Bla ← Cod
Ecrire "La phrase codée est : ", Bla
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un InputField pour l'entrée du décalage :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Shift.
Ajouter un Button pour déclencher le codage de la phrase :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EncodePhrase.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_7 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public InputField inputField_Shift; // Référence à l'InputField pour le décalage
    public Text resultText; // Référence au Text pour afficher le résultat

    public void EncodePhrase()
    {
        // Lire la valeur de l'InputField pour la phrase
        string phrase = inputField_Phrase.text;

        // Lire la valeur de l'InputField pour le décalage
        string shiftInput = inputField_Shift.text;

        // Convertir la valeur en entier
        if (int.TryParse(shiftInput, out int shift))
        {
            // Coder la phrase en décalant chaque lettre du nombre de positions spécifié par le décalage
            char[] charArray = phrase.ToCharArray();
            for (int i = 0; i < charArray.Length; i++)
            {
                if (char.IsLetter(charArray[i]))
                {
                    char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
                    charArray[i] = (char)((charArray[i] - baseChar + shift) % 26 + baseChar);
                }
            }
            string encodedPhrase = new string(charArray);

            // Afficher la phrase codée
            resultText.text = "Phrase codée : " + encodedPhrase;
        }
        else
        {
            // Signaler que l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide pour le décalage.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, PhraseEncoder).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser l'InputField pour le décalage (InputField_Shift) dans le champ InputField_Shift du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le codage de la phrase (Button_EncodePhrase) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (PhraseEncoder) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_7 -> EncodePhrase.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Phrase;
public InputField inputField_Shift;
public Text resultText;
```
Méthode EncodePhrase pour lire l'entrée de la phrase et du décalage, coder la phrase en décalant chaque lettre du nombre de positions spécifié par le décalage, et afficher la phrase codée :

```c#
public void EncodePhrase()
{
    string phrase = inputField_Phrase.text;
    string shiftInput = inputField_Shift.text;

    if (int.TryParse(shiftInput, out int shift))
    {
        char[] charArray = phrase.ToCharArray();
        for (int i = 0; i < charArray.Length; i++)
        {
            if (char.IsLetter(charArray[i]))
            {
                char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
                charArray[i] = (char)((charArray[i] - baseChar + shift) % 26 + baseChar);
            }
        }
        string encodedPhrase = new string(charArray);

        resultText.text = "Phrase codée : " + encodedPhrase;
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide pour le décalage.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur et un décalage, code la phrase en décalant chaque lettre du nombre de positions spécifié par le décalage, et affiche la phrase codée dans un Text.

# Exercice 9.8 - Cryptographie 3
Une technique ultérieure de cryptographie consista à opérer non avec un décalage systématique, mais par une substitution aléatoire. Pour cela, on utilise un alphabet-clé, dans lequel les lettres se succèdent de manière désordonnée, par exemple :  
HYLUJPVREAKBNDOFSQZCWMGITX  
C’est cette clé qui va servir ensuite à coder le message. Selon notre exemple, les A deviendront des H, les B des Y, les C des L, etc.
Ecrire un algorithme qui effectue ce cryptage (l’alphabet-clé sera saisi par l’utilisateur, et on suppose qu'il effectue une saisie correcte).

Là, c'est assez direct.

```
Variable Bla, Cod, Alpha en Caractère
Variables i, Pos, Décal en Entier
Début
Ecrire "Entrez l’alphabet clé : "
Lire Clé
Ecrire "Entrez la phrase à coder : "
Lire Bla
Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
Cod ← ""
Pour i ← 1 à Len(Bla)
  Let ← Mid(Bla, i, 1)
  Pos ← Trouve(Alpha, Let)
  Cod ← Cod & Mid(Clé, Pos, 1)
i Suivant
Bla ← Cod
Ecrire "La phrase codée est : ", Bla
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un InputField pour l'entrée de l'alphabet-clé :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Key.
Ajouter un Button pour déclencher le codage de la phrase :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EncodePhrase.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_8 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public InputField inputField_Key; // Référence à l'InputField pour l'alphabet-clé
    public Text resultText; // Référence au Text pour afficher le résultat

    public void EncodePhrase()
    {
        // Lire la valeur de l'InputField pour la phrase
        string phrase = inputField_Phrase.text;

        // Lire la valeur de l'InputField pour l'alphabet-clé
        string key = inputField_Key.text;

        // Vérifier que l'alphabet-clé contient exactement 26 caractères uniques
        if (key.Length == 26 && HasUniqueCharacters(key))
        {
            // Coder la phrase en utilisant l'alphabet-clé pour effectuer une substitution aléatoire
            char[] charArray = phrase.ToCharArray();
            for (int i = 0; i < charArray.Length; i++)
            {
                if (char.IsLetter(charArray[i]))
                {
                    char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
                    int index = charArray[i] - baseChar;
                    charArray[i] = (char)(key[index] + (charArray[i] - baseChar));
                }
            }
            string encodedPhrase = new string(charArray);

            // Afficher la phrase codée
            resultText.text = "Phrase codée : " + encodedPhrase;
        }
        else
        {
            // Signaler que l'alphabet-clé n'est pas valide
            resultText.text = "L'alphabet-clé doit contenir exactement 26 caractères uniques.";
        }
    }

    private bool HasUniqueCharacters(string key)
    {
        bool[] used = new bool[26];
        foreach (char c in key)
        {
            int index = char.ToUpper(c) - 'A';
            if (index < 0 || index >= 26 || used[index])
            {
                return false;
            }
            used[index] = true;
        }
        return true;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, PhraseEncoder).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser l'InputField pour l'alphabet-clé (InputField_Key) dans le champ InputField_Key du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le codage de la phrase (Button_EncodePhrase) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (PhraseEncoder) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_8 -> EncodePhrase.
Explication du code C#
Déclaration des variables publiques pour les références UI :

```c#
public InputField inputField_Phrase;
public InputField inputField_Key;
public Text resultText;
```
Méthode EncodePhrase pour lire l'entrée de la phrase et de l'alphabet-clé, vérifier la validité de l'alphabet-clé, coder la phrase en utilisant l'alphabet-clé pour effectuer une substitution aléatoire, et afficher la phrase codée :

```c#
public void EncodePhrase()
{
    string phrase = inputField_Phrase.text;
    string key = inputField_Key.text;

    if (key.Length == 26 && HasUniqueCharacters(key))
    {
        char[] charArray = phrase.ToCharArray();
        for (int i = 0; i < charArray.Length; i++)
        {
            if (char.IsLetter(charArray[i]))
            {
                char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
                int index = charArray[i] - baseChar;
                charArray[i] = (char)(key[index] + (charArray[i] - baseChar));
            }
        }
        string encodedPhrase = new string(charArray);

        resultText.text = "Phrase codée : " + encodedPhrase;
    }
    else
    {
        resultText.text = "L'alphabet-clé doit contenir exactement 26 caractères uniques.";
    }
}
```
Méthode HasUniqueCharacters pour vérifier que l'alphabet-clé contient exactement 26 caractères uniques :

```c#
private bool HasUniqueCharacters(string key)
{
    bool[] used = new bool[26];
    foreach (char c in key)
    {
        int index = char.ToUpper(c) - 'A';
        if (index < 0 || index >= 26 || used[index])
        {
            return false;
        }
        used[index] = true;
    }
    return true;
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur et un alphabet-clé, code la phrase en utilisant l'alphabet-clé pour effectuer une substitution aléatoire, et affiche la phrase codée dans un Text.

# Exercice 9.9 - Cryptographie 4 - le chiffre de Vigenère
Un système de cryptographie beaucoup plus difficile à briser que les précédents fut inventé au XVIe siècle par le français Vigenère. Il consistait en une combinaison de différents chiffres de César.
On peut en effet écrire 25 alphabets décalés par rapport à l’alphabet normal :
l’alphabet qui commence par B et finit par …YZA
l’alphabet qui commence par C et finit par …ZAB
etc.
Le codage va s’effectuer sur le principe du chiffre de César : on remplace la lettre d’origine par la lettre occupant la même place dans l’alphabet décalé.
Mais à la différence du chiffre de César, un même message va utiliser non un, mais plusieurs alphabets décalés. Pour savoir quels alphabets doivent être utilisés, et dans quel ordre, on utilise une clé.
Si cette clé est "VIGENERE" et le message "Il faut coder cette phrase", on procèdera comme suit :
La première lettre du message, I, est la 9e lettre de l’alphabet normal. Elle doit être codée en utilisant l’alphabet commençant par la première lettre de la clé, V. Dans cet alphabet, la 9e lettre est le D. I devient donc D.
La deuxième lettre du message, L, est la 12e lettre de l’alphabet normal. Elle doit être codée en utilisant l’alphabet commençant par la deuxième lettre de la clé, I. Dans cet alphabet, la 12e lettre est le S. L devient donc S, etc.
Quand on arrive à la dernière lettre de la clé, on recommence à la première.
Ecrire l’algorithme qui effectue un cryptage de Vigenère, en demandant bien sûr au départ la clé à l’utilisateur.

Le codage de Vigenère n’est pas seulement plus difficile à briser; il est également un peu plus raide à programmer. La difficulté essentielle est de comprendre qu’il faut deux boucles: l’une pour parcourir la phrase à coder, l’autre pour parcourir la clé. Mais quand on y réfléchit bien, ces deux boucles ne doivent surtout pas être imbriquées. Et en réalité, quelle que soit la manière dont on l'écrit, elle n’en forment qu’une seule.
```
Variables Alpha, Bla, Cod, Clé, Let en Caractère
Variables i, Pos, PosClé, Décal en Entier
Début
Ecrire "Entrez la clé : "
Lire Clé
Ecrire "Entrez la phrase à coder : "
Lire Bla
Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
Cod ← ""
PosClé ← 0
Pour i ← 1 à Len(Bla)
```
On gère la progression dans la clé. J’ai effectué cela "à la main" par une boucle, mais un joli emploi de la fonction Modulo aurait permis une programmation en une seule ligne!
```
Posclé ← Posclé + 1
  Si PosClé > Len(Clé) Alors
    PosClé ← 1
  FinSi
```
On détermine quelle est la lettre clé et sa position dans l’alphabet
```
LetClé ← Mid(Clé, PosClé, 1)
  PosLetClé ← Trouve(Alpha, LetClé)
```
On détermine la position de la lettre à coder et le décalage à appliquer. Là encore, une solution alternative aurait été d’employer Mod : cela nous aurait épargné le Si…
```
Let ← Mid(Bla, i, 1)
  Pos ← Trouve(Alpha, Let)
  NouvPos ← Pos + PosLetClé - 1
  Si NouvPos > 26 Alors
    NouvPos ← NouvPos – 26
  FinSi
  Cod ← Cod & Mid(Alpha, NouvPos, 1)
i Suivant
Bla ← Cod
Ecrire "La phrase codée est : ", Bla
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée de la phrase :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Phrase.
Ajouter un InputField pour l'entrée de la clé :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Key.
Ajouter un Button pour déclencher le codage de la phrase :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_EncodePhrase.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;

public class Exercice9_9 : MonoBehaviour
{
    public InputField inputField_Phrase; // Référence à l'InputField pour la phrase
    public InputField inputField_Key; // Référence à l'InputField pour la clé
    public Text resultText; // Référence au Text pour afficher le résultat

    public void EncodePhrase()
    {
        // Lire la valeur de l'InputField pour la phrase
        string phrase = inputField_Phrase.text;

        // Lire la valeur de l'InputField pour la clé
        string key = inputField_Key.text;

        // Coder la phrase en utilisant le chiffre de Vigenère
        string encodedPhrase = VigenereCipher(phrase, key);

        // Afficher la phrase codée
        resultText.text = "Phrase codée : " + encodedPhrase;
    }

    private string VigenereCipher(string phrase, string key)
    {
        char[] charArray = phrase.ToCharArray();
        int keyLength = key.Length;
        int keyIndex = 0;

        for (int i = 0; i < charArray.Length; i++)
        {
            if (char.IsLetter(charArray[i]))
            {
                char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
                int shift = char.ToUpper(key[keyIndex % keyLength]) - 'A';
                charArray[i] = (char)((charArray[i] - baseChar + shift) % 26 + baseChar);
                keyIndex++;
            }
        }

        return new string(charArray);
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, PhraseEncoder).
Dans l'inspecteur, faites glisser l'InputField pour la phrase (InputField_Phrase) dans le champ InputField_Phrase du script.
Faites glisser l'InputField pour la clé (InputField_Key) dans le champ InputField_Key du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le codage de la phrase (Button_EncodePhrase) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (PhraseEncoder) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_9 -> EncodePhrase.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Phrase;
public InputField inputField_Key;
public Text resultText;
```
Méthode EncodePhrase pour lire l'entrée de la phrase et de la clé, coder la phrase en utilisant le chiffre de Vigenère, et afficher la phrase codée :

```c#
public void EncodePhrase()
{
    string phrase = inputField_Phrase.text;
    string key = inputField_Key.text;

    string encodedPhrase = VigenereCipher(phrase, key);

    resultText.text = "Phrase codée : " + encodedPhrase;
}
```
Méthode VigenereCipher pour coder la phrase en utilisant le chiffre de Vigenère :

```c#
private string VigenereCipher(string phrase, string key)
{
    char[] charArray = phrase.ToCharArray();
    int keyLength = key.Length;
    int keyIndex = 0;

    for (int i = 0; i < charArray.Length; i++)
    {
        if (char.IsLetter(charArray[i]))
        {
            char baseChar = char.IsUpper(charArray[i]) ? 'A' : 'a';
            int shift = char.ToUpper(key[keyIndex % keyLength]) - 'A';
            charArray[i] = (char)((charArray[i] - baseChar + shift) % 26 + baseChar);
            keyIndex++;
        }
    }

    return new string(charArray);
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande une phrase à l'utilisateur et une clé, code la phrase en utilisant le chiffre de Vigenère, et affiche la phrase codée dans un Text.


# Exercice 9.10
Ecrivez un algorithme qui demande un nombre entier à l’utilisateur. L’ordinateur affiche ensuite le message "Ce nombre est pair" ou "Ce nombre est impair" selon le cas.

On en revient à des choses plus simples...

```
Variable Nb en Entier
Ecrire "Entrez votre nombre : "
Lire Nb
Si Nb/2 = Ent(Nb/2) Alors
  Ecrire "Ce nombre est pair"
Sinon
  Ecrire "Ce nombre est impair"
FinSi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un InputField pour l'entrée du nombre :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-le dans la scène.
Renommez-le InputField_Number.
Ajouter un Button pour déclencher la vérification du nombre :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CheckNumber.
Ajouter un Text pour afficher le résultat :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice9_10 : MonoBehaviour
{
    public InputField inputField_Number; // Référence à l'InputField pour le nombre
    public Text resultText; // Référence au Text pour afficher le résultat

    public void CheckNumber()
    {
        // Lire la valeur de l'InputField
        string numberInput = inputField_Number.text;

        // Convertir la valeur en entier
        if (int.TryParse(numberInput, out int number))
        {
            // Vérifier si le nombre est pair ou impair
            if (number % 2 == 0)
            {
                resultText.text = "Ce nombre est pair.";
            }
            else
            {
                resultText.text = "Ce nombre est impair.";
            }
        }
        else
        {
            // Signaler que l'entrée n'est pas un nombre valide
            resultText.text = "Veuillez entrer un nombre valide.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, NumberChecker).
Dans l'inspecteur, faites glisser l'InputField pour le nombre (InputField_Number) dans le champ InputField_Number du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la vérification du nombre (Button_CheckNumber) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (NumberChecker) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_10 -> CheckNumber.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Number;
public Text resultText;
```
Méthode CheckNumber pour lire l'entrée du nombre, vérifier si le nombre est pair ou impair, et afficher le résultat :
```c#

public void CheckNumber()
{
    string numberInput = inputField_Number.text;

    if (int.TryParse(numberInput, out int number))
    {
        if (number % 2 == 0)
        {
            resultText.text = "Ce nombre est pair.";
        }
        else
        {
            resultText.text = "Ce nombre est impair.";
        }
    }
    else
    {
        resultText.text = "Veuillez entrer un nombre valide.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui demande un nombre entier à l'utilisateur et affiche un message indiquant si le nombre est pair ou impair dans un Text.
# Exercice 9.11
Ecrivez les algorithmes qui génèrent un nombre Glup aléatoire tel que …  
0 =< Glup < 2  
–1 =< Glup < 1  
1,35 =< Glup < 1,65  
Glup émule un dé à six faces  
–10,5 =< Glup < +6,5  
Glup émule la somme du jet simultané de deux dés à six faces  

```
a) Glup ← Alea() * 2
b) Glup ← Alea() * 2 - 1
c) Glup ← Alea() * 0,30 + 1,35
d) Glup ← Ent(Alea() * 6) + 1
e) Glup ← Alea() * 17 – 10,5
f) Glup ← Ent(Alea()*6) + Ent(Alea()*6) + 2
```

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher la génération des nombres aléatoires :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_GenerateNumbers.
Ajouter un Text pour afficher les résultats :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;

public class Exercice9_11 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher les résultats

    public void GenerateNumbers()
    {
        // Générer les nombres aléatoires dans les plages spécifiées
        float glup1 = Random.Range(0f, 2f);
        float glup2 = Random.Range(-1f, 1f);
        float glup3 = Random.Range(1.35f, 1.65f);
        int glup4 = Random.Range(1, 7); // Émule un dé à six faces
        float glup5 = Random.Range(-10.5f, 6.5f); // Émule la somme du jet simultané de deux dés à six faces

        // Afficher les résultats
        resultText.text = "Glup1 (0 <= Glup < 2) : " + glup1 + "\n" +
                          "Glup2 (-1 <= Glup < 1) : " + glup2 + "\n" +
                          "Glup3 (1.35 <= Glup < 1.65) : " + glup3 + "\n" +
                          "Glup4 (dé à six faces) : " + glup4 + "\n" +
                          "Glup5 (somme de deux dés à six faces) : " + glup5;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, NumberGenerator).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la génération des nombres aléatoires (Button_GenerateNumbers) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (NumberGenerator) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice9_11 -> GenerateNumbers.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Méthode GenerateNumbers pour générer les nombres aléatoires dans les plages spécifiées et afficher les résultats :

```c#
public void GenerateNumbers()
{
    float glup1 = Random.Range(0f, 2f);
    float glup2 = Random.Range(-1f, 1f);
    float glup3 = Random.Range(1.35f, 1.65f);
    int glup4 = Random.Range(1, 7); // Émule un dé à six faces
    float glup5 = Random.Range(-10.5f, 6.5f); // Émule la somme du jet simultané de deux dés à six faces

    resultText.text = "Glup1 (0 <= Glup < 2) : " + glup1 + "\n" +
                      "Glup2 (-1 <= Glup < 1) : " + glup2 + "\n" +
                      "Glup3 (1.35 <= Glup < 1.65) : " + glup3 + "\n" +
                      "Glup4 (dé à six faces) : " + glup4 + "\n" +
                      "Glup5 (somme de deux dés à six faces) : " + glup5;
}
```
En suivant ces étapes, vous aurez un programme Unity qui génère des nombres aléatoires dans différentes plages de valeurs spécifiées et affiche les résultats dans un Text.