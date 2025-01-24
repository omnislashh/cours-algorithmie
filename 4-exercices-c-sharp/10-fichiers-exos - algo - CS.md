# Exercice 10.1
Quel résultat cet algorithme produit-il ?
```
Variable Truc en Caractère
Début
Ouvrir "Exemple.txt" sur 5 en Lecture
Tantque Non EOF(5)
  LireFichier 5, Truc
  Ecrire Truc
FinTantQue
Fermer 5
Fin
```
```
Analyse de l'algorithme
Déclaration de la variable :

Variable Truc en Caractère : Déclare une variable Truc de type caractère.
Ouverture du fichier :

Ouvrir "Exemple.txt" sur 5 en Lecture : Ouvre le fichier "Exemple.txt" en mode lecture et associe le fichier au descripteur de fichier 5.
Boucle de lecture :

TantQue Non EOF(5) : Boucle tant que la fin du fichier (EOF) n'est pas atteinte pour le descripteur de fichier 5.
LireFichier 5, Truc : Lit un caractère du fichier associé au descripteur 5 et le stocke dans la variable Truc.
Ecrire Truc : Affiche le caractère lu.
FinTantQue : Fin de la boucle.
Fermeture du fichier :

Fermer 5 : Ferme le fichier associé au descripteur 5.
Fin de l'algorithme :

Fin : Fin de l'algorithme.
Résultat de l'algorithme
L'algorithme ouvre le fichier "Exemple.txt" en mode lecture, lit chaque caractère du fichier un par un, et affiche chaque caractère lu jusqu'à ce qu'il atteigne la fin du fichier. Ensuite, il ferme le fichier.

Exemple de contenu de "Exemple.txt"
Supposons que le fichier "Exemple.txt" contient le texte suivant :


Bonjour le monde!
Résultat produit par l'algorithme
L'algorithme affichera chaque caractère du fichier un par un :


B
o
n
j
o
u
r

l
e

m
o
n
d
e
!
```
Conclusion
L'algorithme lit et affiche chaque caractère du fichier "Exemple.txt" un par un jusqu'à la fin du fichier. Le résultat produit par l'algorithme est l'affichage de chaque caractère du fichier, ligne par ligne.

Cet algorithme écrit l'intégralité du fichier quot;Exemple.txt" à l'écran  
# Exercice 10.2
Ecrivez l’algorithme qui produit un résultat similaire au précédent, mais le fichier texte "Exemple.txt" est cette fois de type délimité (caractère de délimitation : /). On produira à l'écran un affichage où pour des raisons esthétiques, ce caractère sera remplacé avec des espaces.

```
Variable Truc en Caractère
Variable i en Entier
Debut
Ouvrir "Exemple.txt" sur 5 en Lecture
Tantque Non EOF(5)
  LireFichier 5, Truc
  Pour i ← 1 à Len(Truc)
    Si Mid(Truc, i, 1) = "/" Alors
      Ecrire " "
    Sinon
      Ecrire Mid(Truc, i, 1)
    FinSi
  i Suivant
FinTantQue
Fermer 5
```
Pour que le fichier "Exemple.txt" soit accessible par votre application Unity, il doit être stocké dans un répertoire accessible par l'application. Voici quelques options pour stocker le fichier :

Option 1 : Stocker le fichier dans le répertoire de l'application
Créer un dossier StreamingAssets dans votre projet Unity :

Dans le répertoire de votre projet Unity, créez un dossier nommé StreamingAssets s'il n'existe pas déjà.
Placer le fichier Exemple.txt dans le dossier StreamingAssets :

Copiez le fichier Exemple.txt dans le dossier StreamingAssets.
Modifier le script pour lire le fichier depuis le dossier StreamingAssets :

Utilisez Application.streamingAssetsPath pour obtenir le chemin du fichier.
Voici le script modifié pour lire le fichier depuis le dossier StreamingAssets :
```c#

using UnityEngine;
using UnityEngine.UI;
using System.IO;

public class Exercice10_2 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    public void ReadFile()
    {
        // Chemin du fichier à lire dans le dossier StreamingAssets
        string filePath = Path.Combine(Application.streamingAssetsPath, "Exemple.txt");

        // Vérifier si le fichier existe
        if (File.Exists(filePath))
        {
            // Lire le contenu du fichier
            string[] lines = File.ReadAllLines(filePath);

            // Remplacer le caractère de délimitation '/' par des espaces
            string result = string.Join(" ", lines).Replace('/', ' ');

            // Afficher le résultat
            resultText.text = result;
        }
        else
        {
            // Signaler que le fichier n'existe pas
            resultText.text = "Le fichier 'Exemple.txt' n'existe pas.";
        }
    }
}
```
Option 2 : Stocker le fichier dans un répertoire personnalisé
Créer un dossier personnalisé dans votre projet Unity :

Créez un dossier nommé CustomFiles ou tout autre nom de votre choix dans le répertoire de votre projet Unity.
Placer le fichier Exemple.txt dans le dossier personnalisé :

Copiez le fichier Exemple.txt dans le dossier CustomFiles.
Modifier le script pour lire le fichier depuis le dossier personnalisé :

Utilisez Application.dataPath pour obtenir le chemin du répertoire de données de l'application et construire le chemin complet du fichier.
Voici le script modifié pour lire le fichier depuis le dossier personnalisé :
```c#

using UnityEngine;
using UnityEngine.UI;
using System.IO;

public class Exercice10_2 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher le résultat

    public void ReadFile()
    {
        // Chemin du fichier à lire dans le dossier personnalisé
        string filePath = Path.Combine(Application.dataPath, "CustomFiles/Exemple.txt");

        // Vérifier si le fichier existe
        if (File.Exists(filePath))
        {
            // Lire le contenu du fichier
            string[] lines = File.ReadAllLines(filePath);

            // Remplacer le caractère de délimitation '/' par des espaces
            string result = string.Join(" ", lines).Replace('/', ' ');

            // Afficher le résultat
            resultText.text = result;
        }
        else
        {
            // Signaler que le fichier n'existe pas
            resultText.text = "Le fichier 'Exemple.txt' n'existe pas.";
        }
    }
}
```
Conclusion
En suivant l'une de ces options, vous pouvez stocker le fichier Exemple.txt dans un répertoire accessible par votre application Unity et lire son contenu pour afficher le résultat dans un Text.

# Exercice 10.3
On travaille avec le fichier du carnet d’adresses en champs de largeur fixe.
Ecrivez un algorithme qui permet à l’utilisateur de saisir au clavier un nouvel individu qui sera ajouté à ce carnet d’adresses.
```
Variables Nom * 20, Prénom * 17, Tel * 10, Mail * 20, Lig en Caractère
Debut
Ecrire "Entrez le nom : "
Lire Nom
Ecrire "Entrez le prénom : "
Lire Prénom
Ecrire "Entrez le téléphone : "
Lire Tel
Ecrire "Entrez le nom : "
Lire Mail
Lig ← Nom & Prénom & Tel & Mail
Ouvrir "Adresse.txt" sur 1 pour Ajout
EcrireFichier 1, Lig
Fermer 1
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter des InputField pour les informations de l'individu :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les InputField_Name, InputField_Address, InputField_Phone, etc., selon les informations que vous souhaitez collecter.
Ajouter un Button pour déclencher l'ajout de l'individu au carnet d'adresses :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_AddIndividual.
Ajouter un Text pour afficher les messages de confirmation :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.IO;

public class Exercice10_3 : MonoBehaviour
{
    public InputField inputField_Name; // Référence à l'InputField pour le nom
    public InputField inputField_Address; // Référence à l'InputField pour l'adresse
    public InputField inputField_Phone; // Référence à l'InputField pour le téléphone
    public Text resultText; // Référence au Text pour afficher les messages de confirmation

    public void AddIndividual()
    {
        // Lire les valeurs des InputFields
        string name = inputField_Name.text;
        string address = inputField_Address.text;
        string phone = inputField_Phone.text;

        // Chemin du fichier de carnet d'adresses
        string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

        // Formater les informations de l'individu en champs de largeur fixe
        string newEntry = FormatEntry(name, address, phone);

        // Ajouter l'individu au fichier de carnet d'adresses
        try
        {
            File.AppendAllText(filePath, newEntry + Environment.NewLine);
            resultText.text = "Individu ajouté avec succès.";
        }
        catch (IOException e)
        {
            resultText.text = "Erreur lors de l'ajout de l'individu : " + e.Message;
        }
    }

    private string FormatEntry(string name, string address, string phone)
    {
        // Formater les informations en champs de largeur fixe
        // Par exemple, 20 caractères pour le nom, 30 pour l'adresse, et 15 pour le téléphone
        return string.Format("{0,-20} {1,-30} {2,-15}", name, address, phone);
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, AddressBookManager).
Dans l'inspecteur, faites glisser les InputField pour le nom, l'adresse et le téléphone (InputField_Name, InputField_Address, InputField_Phone) dans les champs correspondants du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher l'ajout de l'individu au carnet d'adresses (Button_AddIndividual) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (AddressBookManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice10_3 -> AddIndividual.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_Name;
public InputField inputField_Address;
public InputField inputField_Phone;
public Text resultText;
```
Méthode AddIndividual pour lire les entrées de l'utilisateur, formater les informations en champs de largeur fixe, et ajouter l'individu au fichier de carnet d'adresses :
```c#

public void AddIndividual()
{
    string name = inputField_Name.text;
    string address = inputField_Address.text;
    string phone = inputField_Phone.text;

    string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

    string newEntry = FormatEntry(name, address, phone);

    try
    {
        File.AppendAllText(filePath, newEntry + Environment.NewLine);
        resultText.text = "Individu ajouté avec succès.";
    }
    catch (IOException e)
    {
        resultText.text = "Erreur lors de l'ajout de l'individu : " + e.Message;
    }
}
```
Méthode FormatEntry pour formater les informations de l'individu en champs de largeur fixe :
```c#

private string FormatEntry(string name, string address, string phone)
{
    return string.Format("{0,-20} {1,-30} {2,-15}", name, address, phone);
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de saisir les informations d'un nouvel individu et de les ajouter à un fichier de carnet d'adresses en champs de largeur fixe. Le fichier sera stocké dans le répertoire de données persistantes de l'application, ce qui permet de conserver les données entre les sessions de l'application.

# Exercice 10.4
Même question, mais cette fois le carnet est supposé être déjà trié par ordre alphabétique. Il suffit donc d'insérer l’individu au bon endroit dans le fichier.  

Là, comme indiqué dans le cours, on passe par un tableau de strutures en mémoire vive, ce qui est la technique la plus fréquemment employée. Le tri - qui est en fait un simple test - sera effectué sur le premier champ (nom).

```
Structure Bottin
  Nom en Caractère * 20
  Prénom en Caractère * 15
  Tel en Caractère * 10
  Mail en Caractère * 20
Fin Structure
Tableau Mespotes[] en Bottin
Variables MonPote, Nouveau en Bottin
Variables i, j en Numérique
Debut
Ecrire "Entrez le nom : "
Lire Nouveau.Nom
Ecrire "Entrez le prénom : "
Lire Nouveau.Prénom
Ecrire "Entrez le téléphone : "
Lire Nouveau.Tel
Ecrire "Entrez le mail :
Lire Nouveau.Mail
```
On recopie l'intégralité de "Adresses" dans MesPotes[]. Et après tout, c'est l'occasion : quand on tombe au bon endroit, on insère subrepticement notre nouveau copain dans le tableau.

```
Ouvrir "Adresse.txt" sur 1 pour Lecture
i ← -1
inséré ← Faux
Tantque Non EOF(1)
  i ← i + 1
  Redim MesPotes[i]
  LireFichier 1, MonPote
  Si MonPote.Nom > Nouveau.Nom et Non Inséré Alors
    MesPotes[i] ← Nouveau
    Inséré ← Vrai
    i ← i + 1
    Redim MesPotes[i]
  FinSi
  MesPotes[i] ← MonPote
FinTantQue
Fermer 1
Si Non Inséré Alors
    i ← i + 1
    Redim MesPotes[i]
    MesPotes[i] ← Nouveau
    Inséré ← Vrai
FinSi
```
Et le tour est quasiment joué. Il ne reste plus qu'à rebalancer tel quel l'intégralité du tableau MesPotes dans le fichier, en écrasant l'ancienne version.

```
Ouvrir quot;Adresse.txt" sur 1 pour Ecriture
Pour j ← 0 à i
  EcrireFichier 1, MesPotes[j]
j suivant
Fermer 1
Fin
```
Stocker le fichier dans un répertoire personnalisé
Créer un dossier personnalisé dans votre projet Unity :

Créez un dossier nommé CustomFiles ou tout autre nom de votre choix dans le répertoire de votre projet Unity.
Placer le fichier AddressBook.txt dans le dossier personnalisé :

Copiez le fichier AddressBook.txt dans le dossier CustomFiles.
Modifier le script pour lire et écrire le fichier depuis le dossier personnalisé :

Utilisez Application.dataPath pour obtenir le chemin du répertoire de données de l'application et construire le chemin complet du fichier.
Voici le script modifié pour lire et écrire le fichier depuis le dossier personnalisé :
```c#

using UnityEngine;
using UnityEngine.UI;
using System.IO;
using System.Collections.Generic;

public class Exercice10_4 : MonoBehaviour
{
    public InputField inputField_Name; // Référence à l'InputField pour le nom
    public InputField inputField_Address; // Référence à l'InputField pour l'adresse
    public InputField inputField_Phone; // Référence à l'InputField pour le téléphone
    public Text resultText; // Référence au Text pour afficher les messages de confirmation

    public void AddIndividual()
    {
        // Lire les valeurs des InputFields
        string name = inputField_Name.text;
        string address = inputField_Address.text;
        string phone = inputField_Phone.text;

        // Chemin du fichier de carnet d'adresses dans le dossier personnalisé
        string filePath = Path.Combine(Application.dataPath, "CustomFiles/AddressBook.txt");

        // Formater les informations de l'individu en champs de largeur fixe
        string newEntry = FormatEntry(name, address, phone);

        // Lire le contenu actuel du fichier
        List<string> lines = new List<string>();
        if (File.Exists(filePath))
        {
            lines = new List<string>(File.ReadAllLines(filePath));
        }

        // Insérer le nouvel individu au bon endroit
        bool inserted = false;
        for (int i = 0; i < lines.Count; i++)
        {
            if (string.Compare(GetNameFromEntry(lines[i]), name, true) > 0)
            {
                lines.Insert(i, newEntry);
                inserted = true;
                break;
            }
        }

        // Si l'individu n'a pas été inséré, l'ajouter à la fin
        if (!inserted)
        {
            lines.Add(newEntry);
        }

        // Écrire le contenu mis à jour dans le fichier
        try
        {
            File.WriteAllLines(filePath, lines);
            resultText.text = "Individu ajouté avec succès.";
        }
        catch (IOException e)
        {
            resultText.text = "Erreur lors de l'ajout de l'individu : " + e.Message;
        }
    }

    private string FormatEntry(string name, string address, string phone)
    {
        // Formater les informations en champs de largeur fixe
        // Par exemple, 20 caractères pour le nom, 30 pour l'adresse, et 15 pour le téléphone
        return string.Format("{0,-20} {1,-30} {2,-15}", name, address, phone);
    }

    private string GetNameFromEntry(string entry)
    {
        // Extraire le nom de l'entrée formatée
        return entry.Substring(0, 20).Trim();
    }
}
```
Conclusion
En suivant l'une de ces options, vous pouvez stocker le fichier AddressBook.txt dans un répertoire accessible par votre application Unity et lire son contenu pour afficher le résultat dans un Text. Le répertoire de données persistantes est généralement préféré car il est géré par Unity et est approprié pour stocker des fichiers qui doivent persister entre les sessions de l'application.
# Exercice 10.5
Ecrivez un algorithme qui permette de modifier un renseignement (pour simplifier, disons uniquement le nom de famille) d’un membre du carnet d’adresses. Il faut donc demander à l’utilisateur quel est le nom à modifier, puis quel est le nouveau nom, et mettre à jour le fichier. Si le nom recherché n'existe pas, le programme devra le signaler.

C'est un peu du même tonneau que ce qu'on vient de faire, à quelques variantes près. Il y a essentiellement une petite gestion de flag pour faire bonne mesure.

```
Structure Bottin
  Nom en Caractère * 20
  Prénom en Caractère * 15
  Tel en caractère * 10
  Mail en Caractère * 20
Fin Structure
Tableau Mespotes[] en Bottin
Variables MonPote en Bottin
Variables Ancien, Nouveau en Caractère*20
Variables i, j en Numérique
Variable Trouvé en Booléen
Debut
Ecrire "Entrez le nom à modifier : "
Lire Ancien
Ecrire "Entrez le nouveau nom : "
Lire Nouveau
```
On recopie l'intégralité de "Adresses" dans Fic, tout en recherchant le clampin. Si on le trouve, on procède à la modification.
```
Ouvrir “Adresse.txt” sur 1 pour Lecture
i ← -1
Trouvé ← Faux
Tantque Non EOF(1)
  i ← i + 1
  Redim MesPotes[i]
  LireFichier 1, MonPote
  Si MonPote.Nom = Ancien.Nom Alors
    Trouvé ← Vrai
    MonPote.Nom ← Nouveau
  FinSi
  MesPotes[i] ← MonPote
FinTantQue
Fermer 1
```
On recopie ensuite l'intégralité de Fic dans "Adresse"
```
Ouvrir "Adresse.txt" sur 1 pour Ecriture
Pour j ← 0 à i
  EcrireFichier 1, MesPotes[j]
j Suivant
Fermer 1
```
Et un petit message pour finir !
```
Si Trouvé Alors
  Ecrire "Modification effectuée"
Sinon
  Ecrire "Nom inconnu. Aucune modification effectuée"
FinSi
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter des InputField pour les informations de l'utilisateur :

Allez dans le menu GameObject > UI > Input Field.
Positionnez-les dans la scène et renommez-les InputField_OldName et InputField_NewName.
Ajouter un Button pour déclencher la modification du nom :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_UpdateName.
Ajouter un Text pour afficher les messages de confirmation :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :
```c#

using UnityEngine;
using UnityEngine.UI;
using System.IO;
using System.Collections.Generic;

public class Exercice10_5 : MonoBehaviour
{
    public InputField inputField_OldName; // Référence à l'InputField pour le nom actuel
    public InputField inputField_NewName; // Référence à l'InputField pour le nouveau nom
    public Text resultText; // Référence au Text pour afficher les messages de confirmation

    public void UpdateName()
    {
        // Lire les valeurs des InputFields
        string oldName = inputField_OldName.text;
        string newName = inputField_NewName.text;

        // Chemin du fichier de carnet d'adresses dans le répertoire de données persistantes
        string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

        // Lire le contenu actuel du fichier
        List<string> lines = new List<string>();
        if (File.Exists(filePath))
        {
            lines = new List<string>(File.ReadAllLines(filePath));
        }

        // Rechercher le nom à modifier et le mettre à jour
        bool found = false;
        for (int i = 0; i < lines.Count; i++)
        {
            if (GetNameFromEntry(lines[i]).Equals(oldName, System.StringComparison.OrdinalIgnoreCase))
            {
                lines[i] = UpdateEntryName(lines[i], newName);
                found = true;
                break;
            }
        }

        // Écrire le contenu mis à jour dans le fichier
        if (found)
        {
            try
            {
                File.WriteAllLines(filePath, lines);
                resultText.text = "Nom mis à jour avec succès.";
            }
            catch (IOException e)
            {
                resultText.text = "Erreur lors de la mise à jour du nom : " + e.Message;
            }
        }
        else
        {
            resultText.text = "Le nom recherché n'existe pas.";
        }
    }

    private string GetNameFromEntry(string entry)
    {
        // Extraire le nom de l'entrée formatée
        return entry.Substring(0, 20).Trim();
    }

    private string UpdateEntryName(string entry, string newName)
    {
        // Mettre à jour le nom dans l'entrée formatée
        return string.Format("{0,-20} {1}", newName, entry.Substring(20));
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, AddressBookManager).
Dans l'inspecteur, faites glisser les InputField pour le nom actuel et le nouveau nom (InputField_OldName, InputField_NewName) dans les champs correspondants du script.
Faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la modification du nom (Button_UpdateName) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (AddressBookManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice10_5 -> UpdateName.
Explication du code C#
Déclaration des variables publiques pour les références UI :
```c#

public InputField inputField_OldName;
public InputField inputField_NewName;
public Text resultText;
```
Méthode UpdateName pour lire les entrées de l'utilisateur, rechercher le nom à modifier, mettre à jour le nom, et écrire le contenu mis à jour dans le fichier :
```c#

public void UpdateName()
{
    string oldName = inputField_OldName.text;
    string newName = inputField_NewName.text;

    string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

    List<string> lines = new List<string>();
    if (File.Exists(filePath))
    {
        lines = new List<string>(File.ReadAllLines(filePath));
    }

    bool found = false;
    for (int i = 0; i < lines.Count; i++)
    {
        if (GetNameFromEntry(lines[i]).Equals(oldName, System.StringComparison.OrdinalIgnoreCase))
        {
            lines[i] = UpdateEntryName(lines[i], newName);
            found = true;
            break;
        }
    }

    if (found)
    {
        try
        {
            File.WriteAllLines(filePath, lines);
            resultText.text = "Nom mis à jour avec succès.";
        }
        catch (IOException e)
        {
            resultText.text = "Erreur lors de la mise à jour du nom : " + e.Message;
        }
    }
    else
    {
        resultText.text = "Le nom recherché n'existe pas.";
    }
}
```
Méthode GetNameFromEntry pour extraire le nom de l'entrée formatée :

```c#
private string GetNameFromEntry(string entry)
{
    return entry.Substring(0, 20).Trim();
}
```
Méthode UpdateEntryName pour mettre à jour le nom dans l'entrée formatée :
```c#

private string UpdateEntryName(string entry, string newName)
{
    return string.Format("{0,-20} {1}", newName, entry.Substring(20));
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet à l'utilisateur de modifier le nom de famille d'un membre du carnet d'adresses et de mettre à jour le fichier en conséquence. Le fichier sera stocké dans le répertoire de données persistantes de l'application, ce qui permet de conserver les données entre les sessions de l'application.
# Exercice 10.6
Ecrivez un algorithme qui trie les individus du carnet d’adresses par ordre alphabétique.

Là, c'est un tri sur un tableau de structures, rien de plus facile. Et on est bien content de disposer des structures, autrement dit de ne se coltiner qu'un seul tableau...

```
Structure Bottin Nom en Caractère * 20
Prénom en Caractère * 15
Tel en caractère * 10
Mail en Caractère * 20
Fin Structure
Tableau Mespotes[] en Bottin
Variables Mini en Bottin
Variables i, j en Numérique
Debut
```
On recopie l'intégralité de "Adresses" dans MesPotes...
```
Ouvrir "Adresse.txt" sur 1 pour Lecture
i ← -1
Tantque Non EOF(1)
  i ← i + 1
  Redim MesPotes[i]
  LireFichier 1, MesPotes[i]
FinTantQue
Fermer 1
```
On trie le tableau selon l'algorithme de tri par insertion déjà étudié, en utilisant le champ Nom de la structure :
```
Pour j ← 0 à i - 1
  Mini ← MesPotes[j]
  posmini ← j
  Pour k ← j + 1 à i
    Si MesPotes[k].Nom < Mini.Nom Alors
      mini ← MesPotes[k]
      posmini ← k
    Finsi
  k suivant
  MesPotes[posmini] ← MesPotes[j]
  MesPotes[j] ← Mini
j suivant
```
On recopie ensuite l'intégralité du tableau dans "Adresse"
```
Ouvrir "Adresse.txt" sur 1 pour Ecriture
Pour j ← 0 à i
  EcrireFichier 1, MesPotes[j]
j suivant
Fermer 1
Fin
```
Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le tri du carnet d'adresses :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_SortAddressBook.
Ajouter un Text pour afficher les messages de confirmation :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.IO;
using System.Collections.Generic;
using System.Linq;

public class Exercice10_6 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher les messages de confirmation

    public void SortAddressBook()
    {
        // Chemin du fichier de carnet d'adresses dans le répertoire de données persistantes
        string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

        // Lire le contenu actuel du fichier
        List<string> lines = new List<string>();
        if (File.Exists(filePath))
        {
            lines = new List<string>(File.ReadAllLines(filePath));
        }

        // Trier les entrées par ordre alphabétique en fonction du nom de famille
        var sortedLines = lines.OrderBy(line => GetNameFromEntry(line)).ToList();

        // Écrire le contenu trié dans le fichier
        try
        {
            File.WriteAllLines(filePath, sortedLines);
            resultText.text = "Carnet d'adresses trié avec succès.";
        }
        catch (IOException e)
        {
            resultText.text = "Erreur lors du tri du carnet d'adresses : " + e.Message;
        }
    }

    private string GetNameFromEntry(string entry)
    {
        // Extraire le nom de l'entrée formatée
        return entry.Substring(0, 20).Trim();
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, AddressBookManager).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le tri du carnet d'adresses (Button_SortAddressBook) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (AddressBookManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice10_6 -> SortAddressBook.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Méthode SortAddressBook pour lire le contenu du fichier, trier les entrées par ordre alphabétique en fonction du nom de famille, et écrire le contenu trié dans le fichier :

```c#
public void SortAddressBook()
{
    string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

    List<string> lines = new List<string>();
    if (File.Exists(filePath))
    {
        lines = new List<string>(File.ReadAllLines(filePath));
    }

    var sortedLines = lines.OrderBy(line => GetNameFromEntry(line)).ToList();

    try
    {
        File.WriteAllLines(filePath, sortedLines);
        resultText.text = "Carnet d'adresses trié avec succès.";
    }
    catch (IOException e)
    {
        resultText.text = "Erreur lors du tri du carnet d'adresses : " + e.Message;
    }
}
```
Méthode GetNameFromEntry pour extraire le nom de l'entrée formatée :

```c#
private string GetNameFromEntry(string entry)
{
    return entry.Substring(0, 20).Trim();
}
```
En suivant ces étapes, vous aurez un programme Unity qui permet de trier les individus du carnet d'adresses par ordre alphabétique en fonction du nom de famille et de mettre à jour le fichier en conséquence. Le fichier sera stocké dans le répertoire de données persistantes de l'application, ce qui permet de conserver les données entre les sessions de l'application.

# Exercice 10.7
Soient Toto.txt et Tata.txt deux fichiers dont les enregistrements ont la même structure. Ecrire un algorithme qui recopie tout le fichier Toto dans le fichier Tutu, puis à sa suite, tout le fichier Tata (concaténation de fichiers).

Bon, celui-là est tellement idiot qu'on n'a même pas besoin de passer par des tableaux en mémoire vive.

```
Variable Lig en Caractère
Début
Ouvrir "Tutu.txt" sur 1 pour Ajout
Ouvrir “Toto.txt” sur 2 pour Lecture
Tantque Non EOF(2)
  LireFichier 2, Lig
  EcrireFichier 1, Lig
FinTantQue
Fermer 2
Ouvrir “Tata.txt” sur 3 pour Lecture
Tantque Non EOF(3)
  LireFichier 3, Lig
  EcrireFichier 1, Lig
FinTantQue
Fermer 3
Fermer 1
Fin
```
Pour cet exercice, nous devons écrire un algorithme qui copie tout le contenu du fichier Toto.txt dans un nouveau fichier Tutu.txt, puis ajoute tout le contenu du fichier Tata.txt à la suite dans Tutu.txt. Nous allons utiliser des éléments UI de Unity pour interagir avec l'utilisateur et afficher les messages de confirmation.

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher la concaténation des fichiers :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_ConcatenateFiles.
Ajouter un Text pour afficher les messages de confirmation :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.IO;

public class Exercice10_7 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher les messages de confirmation

    public void ConcatenateFiles()
    {
        // Chemins des fichiers source et destination
        string totoFilePath = Path.Combine(Application.persistentDataPath, "Toto.txt");
        string tataFilePath = Path.Combine(Application.persistentDataPath, "Tata.txt");
        string tutuFilePath = Path.Combine(Application.persistentDataPath, "Tutu.txt");

        // Vérifier si les fichiers source existent
        if (File.Exists(totoFilePath) && File.Exists(tataFilePath))
        {
            try
            {
                // Lire le contenu des fichiers source
                string[] totoLines = File.ReadAllLines(totoFilePath);
                string[] tataLines = File.ReadAllLines(tataFilePath);

                // Concaténer les contenus des fichiers source
                string[] combinedLines = new string[totoLines.Length + tataLines.Length];
                totoLines.CopyTo(combinedLines, 0);
                tataLines.CopyTo(combinedLines, totoLines.Length);

                // Écrire le contenu combiné dans le fichier destination
                File.WriteAllLines(tutuFilePath, combinedLines);

                // Afficher le message de confirmation
                resultText.text = "Fichiers concaténés avec succès.";
            }
            catch (IOException e)
            {
                // Afficher le message d'erreur
                resultText.text = "Erreur lors de la concaténation des fichiers : " + e.Message;
            }
        }
        else
        {
            // Afficher le message d'erreur si les fichiers source n'existent pas
            resultText.text = "Les fichiers Toto.txt et Tata.txt doivent exister.";
        }
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, FileManager).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la concaténation des fichiers (Button_ConcatenateFiles) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (FileManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice10_7 -> ConcatenateFiles.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Méthode ConcatenateFiles pour lire le contenu des fichiers source, concaténer les contenus, et écrire le contenu combiné dans le fichier destination :

```c#
public void ConcatenateFiles()
{
    string totoFilePath = Path.Combine(Application.persistentDataPath, "Toto.txt");
    string tataFilePath = Path.Combine(Application.persistentDataPath, "Tata.txt");
    string tutuFilePath = Path.Combine(Application.persistentDataPath, "Tutu.txt");

    if (File.Exists(totoFilePath) && File.Exists(tataFilePath))
    {
        try
        {
            string[] totoLines = File.ReadAllLines(totoFilePath);
            string[] tataLines = File.ReadAllLines(tataFilePath);

            string[] combinedLines = new string[totoLines.Length + tataLines.Length];
            totoLines.CopyTo(combinedLines, 0);
            tataLines.CopyTo(combinedLines, totoLines.Length);

            File.WriteAllLines(tutuFilePath, combinedLines);

            resultText.text = "Fichiers concaténés avec succès.";
        }
        catch (IOException e)
        {
            resultText.text = "Erreur lors de la concaténation des fichiers : " + e.Message;
        }
    }
    else
    {
        resultText.text = "Les fichiers Toto.txt et Tata.txt doivent exister.";
    }
}
```
En suivant ces étapes, vous aurez un programme Unity qui concatène le contenu des fichiers Toto.txt et Tata.txt dans un nouveau fichier Tutu.txt et affiche un message de confirmation dans un Text. Les fichiers seront stockés dans le répertoire de données persistantes de l'application, ce qui permet de conserver les données entre les sessions de l'application.
# Exercice 10.8
Ecrire un algorithme qui supprime dans notre carnet d'adresses tous les individus dont le mail est invalide (pour employer un critère simple, on considèrera que sont invalides les mails ne comportant aucune arobase, ou plus d'une arobase).

On va éliminer les mauvaises entrées dès la recopie : si l'enregistrement ne présente pas un mail valide, on l'ignore, sinon on le copie dans le tableau.

```
Structure Bottin
  Nom en Caractère * 20
  Prénom en Caractère * 15
  Tel en caractère * 10
  Mail en Caractère * 20
Fin Structure
Tableau Mespotes[] en Bottin
Variable MonPote en Bottin
Variables i, j en Numérique
Debut
```
On recopie "Adresses" dans MesPotes en testant le mail...

```
Ouvrir "Adresse.txt" sur 1 pour Lecture
i ← -1
Tantque Non EOF(1)
  LireFichier 1, MonPote
  nb ← 0
  Pour i ← 1 à Len(MonPote.Mail)
    Si Mid(MonPote.Mail, i, 1) = "@" Alors
      nb ← nb + 1
    FinSi
  i suivant
  Si nb = 1 Alors
    i ← i + 1
    Redim MesPotes[i]
    MesPotes[i] ← MonPote
  FinSi
FinTantQue
Fermer 1
```
On recopie ensuite l'intégralité de Fic dans "Adresse"

```
Ouvrir "Adresse.txt" sur 1 pour Ecriture
Pour j ← 0 à i
  EcrireFichier 1, MesPotes[j]
j Suivant
Fermer 1
Fin
```

Pour cet exercice, nous devons écrire un algorithme qui supprime tous les individus du carnet d'adresses dont l'adresse e-mail est invalide. Une adresse e-mail sera considérée comme invalide si elle ne comporte aucune arobase (@) ou plus d'une arobase. Nous allons utiliser des éléments UI de Unity pour interagir avec l'utilisateur et afficher les messages de confirmation.

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher la suppression des individus avec des adresses e-mail invalides :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_RemoveInvalidEmails.
Ajouter un Text pour afficher les messages de confirmation :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.IO;
using System.Collections.Generic;
using System.Linq;

public class Exercice10_8 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher les messages de confirmation

    public void RemoveInvalidEmails()
    {
        // Chemin du fichier de carnet d'adresses dans le répertoire de données persistantes
        string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

        // Lire le contenu actuel du fichier
        List<string> lines = new List<string>();
        if (File.Exists(filePath))
        {
            lines = new List<string>(File.ReadAllLines(filePath));
        }

        // Filtrer les lignes pour supprimer les individus avec des adresses e-mail invalides
        var validLines = lines.Where(line => IsValidEmail(GetEmailFromEntry(line))).ToList();

        // Écrire le contenu filtré dans le fichier
        try
        {
            File.WriteAllLines(filePath, validLines);
            resultText.text = "Individus avec des adresses e-mail invalides supprimés avec succès.";
        }
        catch (IOException e)
        {
            resultText.text = "Erreur lors de la suppression des individus : " + e.Message;
        }
    }

    private string GetEmailFromEntry(string entry)
    {
        // Extraire l'adresse e-mail de l'entrée formatée
        // Supposons que l'adresse e-mail se trouve dans les 30 derniers caractères de l'entrée
        return entry.Substring(entry.Length - 30).Trim();
    }

    private bool IsValidEmail(string email)
    {
        // Vérifier si l'adresse e-mail est valide (comporte exactement une arobase)
        return email.Count(c => c == '@') == 1;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, AddressBookManager).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher la suppression des individus avec des adresses e-mail invalides (Button_RemoveInvalidEmails) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (AddressBookManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice10_8 -> RemoveInvalidEmails.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Méthode RemoveInvalidEmails pour lire le contenu du fichier, filtrer les lignes pour supprimer les individus avec des adresses e-mail invalides, et écrire le contenu filtré dans le fichier :

```c#
public void RemoveInvalidEmails()
{
    string filePath = Path.Combine(Application.persistentDataPath, "AddressBook.txt");

    List<string> lines = new List<string>();
    if (File.Exists(filePath))
    {
        lines = new List<string>(File.ReadAllLines(filePath));
    }

    var validLines = lines.Where(line => IsValidEmail(GetEmailFromEntry(line))).ToList();

    try
    {
        File.WriteAllLines(filePath, validLines);
        resultText.text = "Individus avec des adresses e-mail invalides supprimés avec succès.";
    }
    catch (IOException e)
    {
        resultText.text = "Erreur lors de la suppression des individus : " + e.Message;
    }
}
```

Méthode GetEmailFromEntry pour extraire l'adresse e-mail de l'entrée formatée :

```c#
private string GetEmailFromEntry(string entry)
{
    return entry.Substring(entry.Length - 30).Trim();
}
```
Méthode IsValidEmail pour vérifier si l'adresse e-mail est valide (comporte exactement une arobase) :

```c#
private bool IsValidEmail(string email)
{
    return email.Count(c => c == '@') == 1;
}
```
En suivant ces étapes, vous aurez un programme Unity qui supprime tous les individus du carnet d'adresses dont l'adresse e-mail est invalide et affiche un message de confirmation dans un Text. Le fichier sera stocké dans le répertoire de données persistantes de l'application, ce qui permet de conserver les données entre les sessions de l'application.
# Exercice 10.9
Les enregistrements d’un fichier contiennent les deux champs Nom (chaîne de caractères) et Montant (Entier). Chaque enregistrement correspond à une vente conclue par un commercial d’une société.
On veut mémoriser dans un tableau, puis afficher à l'écran, le total de ventes par vendeur. Pour simplifier, on suppose que le fichier de départ est déjà trié alphabétiquement par vendeur.
<hr>

Une fois de plus, le passage par un tableau de structures est une stratégie commode. Attention toutefois, comme il s'agit d'un fichier texte, tout est stocké en caractère. Il faudra donc convertir en numérique les caractères représentant les ventes, pour pouvoir effectuer les calculs demandés. Pour le traitement, il y a deux possibilités. Soit on recopie le fichier à l'identique dans un premier tableau, et on traite ensuite ce tableau pour faire la somme par vendeur. Soit on fait le traitement directement, dès la lecture du fichier. C'est cette option qui est choisie dans ce corrigé.

```
Structure Vendeur
  Nom en Caractère * 20
  Montant en Numérique
Fin Structure
Tableau MesVendeurs[] en Vendeur
Variables NomPrec * 20, Lig, Nom en caractère
Variables Somme, Vente en Numérique
```
On balaye le fichier en faisant nos additions.
Dès que le nom a changé (on est passé au vendeur suivant), on range le résultat et on remet tout à zéro

```
Debut
Ouvrir "Ventes.txt” sur 1 pour Lecture
i ← -1
Somme ← 0
NomPréc ← ""
Tantque Non EOF(1)
  LireFichier 1, Lig
  Nom ← Mid(Lig, 1, 20)
  Vente ← CNum(Mid(Lig, 21, 10)
  Si Nom = NomPrec Alors
    Somme ← Somme + Vente
  Sinon
    i ← i + 1
    Redim MesVendeurs(i)
    MesVendeurs[i].Nom ← NomPrec
    MesVendeurs[i].Montant ← Somme
    Somme ← 0
    NomPrec ← Nom
  FinSi
FinTantQue
```

Et n'oublions pas un petit tour de plus pour le dernier de ces messieurs-dames…

```
i ← i + 1
Redim MesVendeurs[i]
MesVendeurs[i].Nom ← NomPrec
MesVendeurs[i].Montant ← Somme
Fermer 1
```

Pour terminer, on affiche le tableau à l'écran

```
Pour j ← 0 à i
  Ecrire MesVendeurs[j]
j suivant
Fin
```

Étape 1 : Créer l'interface utilisateur
Ajouter un Button pour déclencher le calcul des totaux de ventes par vendeur :

Allez dans le menu GameObject > UI > Button.
Positionnez-le dans la scène.
Renommez-le Button_CalculateSales.
Ajouter un Text pour afficher les totaux de ventes par vendeur :

Allez dans le menu GameObject > UI > Text.
Positionnez-le dans la scène.
Renommez-le Text_Result.
Étape 2 : Écrire le script C#
Créez un nouveau script C# et attachez-le à un GameObject dans votre scène. Voici le code pour le script :

```c#
using UnityEngine;
using UnityEngine.UI;
using System.IO;
using System.Collections.Generic;

public class Exercice10_9 : MonoBehaviour
{
    public Text resultText; // Référence au Text pour afficher les totaux de ventes par vendeur

    public void CalculateSales()
    {
        // Chemin du fichier de ventes dans le répertoire de données persistantes
        string filePath = Path.Combine(Application.persistentDataPath, "Sales.txt");

        // Dictionnaire pour mémoriser le total des ventes par vendeur
        Dictionary<string, int> salesTotals = new Dictionary<string, int>();

        // Lire le contenu du fichier
        if (File.Exists(filePath))
        {
            string[] lines = File.ReadAllLines(filePath);

            // Parcourir chaque ligne du fichier
            foreach (string line in lines)
            {
                // Extraire le nom du vendeur et le montant de la vente
                string[] parts = line.Split(',');
                if (parts.Length == 2)
                {
                    string sellerName = parts[0].Trim();
                    if (int.TryParse(parts[1].Trim(), out int amount))
                    {
                        // Ajouter le montant de la vente au total du vendeur
                        if (salesTotals.ContainsKey(sellerName))
                        {
                            salesTotals[sellerName] += amount;
                        }
                        else
                        {
                            salesTotals[sellerName] = amount;
                        }
                    }
                }
            }
        }

        // Afficher les totaux de ventes par vendeur
        string result = "Totaux de ventes par vendeur :\n";
        foreach (var entry in salesTotals)
        {
            result += $"{entry.Key}: {entry.Value}\n";
        }
        resultText.text = result;
    }
}
```
Étape 3 : Assigner les références
Sélectionnez le GameObject auquel vous avez attaché le script (par exemple, SalesManager).
Dans l'inspecteur, faites glisser le Text (Text_Result) dans le champ Result Text du script.
Étape 4 : Ajouter une fonction au bouton
Sélectionnez le Button pour déclencher le calcul des totaux de ventes par vendeur (Button_CalculateSales) dans la scène.
Dans l'inspecteur, faites défiler vers le bas jusqu'à la section Button.
Cliquez sur le + pour ajouter une nouvelle entrée à la liste On Click ().
Faites glisser le GameObject contenant le script (SalesManager) dans le champ vide.
Dans le menu déroulant, sélectionnez Exercice10_9 -> CalculateSales.
Explication du code C#
Déclaration de la variable publique pour la référence UI :

```c#
public Text resultText;
```
Méthode CalculateSales pour lire le contenu du fichier, mémoriser le total des ventes par vendeur dans un dictionnaire, et afficher les totaux de ventes par vendeur :
```c#

public void CalculateSales()
{
    string filePath = Path.Combine(Application.persistentDataPath, "Sales.txt");

    Dictionary<string, int> salesTotals = new Dictionary<string, int>();

    if (File.Exists(filePath))
    {
        string[] lines = File.ReadAllLines(filePath);

        foreach (string line in lines)
        {
            string[] parts = line.Split(',');
            if (parts.Length == 2)
            {
                string sellerName = parts[0].Trim();
                if (int.TryParse(parts[1].Trim(), out int amount))
                {
                    if (salesTotals.ContainsKey(sellerName))
                    {
                        salesTotals[sellerName] += amount;
                    }
                    else
                    {
                        salesTotals[sellerName] = amount;
                    }
                }
            }
        }
    }

    string result = "Totaux de ventes par vendeur :\n";
    foreach (var entry in salesTotals)
    {
        result += $"{entry.Key}: {entry.Value}\n";
    }
    resultText.text = result;
}
```
En suivant ces étapes, vous aurez un programme Unity qui lit un fichier contenant des enregistrements de ventes, mémorise le total des ventes par vendeur dans un tableau, et affiche les totaux de ventes par vendeur dans un Text. Le fichier sera stocké dans le répertoire de données persistantes de l'application, ce qui permet de conserver les données entre les sessions de l'application.