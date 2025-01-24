# Exercice 1.1
Quelles seront les valeurs des variables A et B après exécution des instructions suivantes ?
```
Variables A, B en Entier

Début
A ← 1
B ← A + 3
A ← 3
Fin
```

```
Après         La valeur des variables est :
A ← 1         A = 1          B = ?
B ← A + 3     A = 1          B = 4
A ← 3         A = 3         B = 4
```

```c#
using UnityEngine;

public class Exercice1_1 : MonoBehaviour
{
    void Start()
    {
        int A, B;

        A = 1;
        B = A + 3;
        A = 3;

        Debug.Log("A = " + A); // Affichera : A = 3
        Debug.Log("B = " + B); // Affichera : B = 4
    }
}
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A et B seront affichées dans la console de Unity.
# Exercice 1.2
Quelles seront les valeurs des variables A, B et C après exécution des instructions suivantes ?
```
Variables A, B, C en Entier

Début
A ← 5
B ← 3
C ← A + B
A ← 2
C ← B – A
Fin
```
```
Après         La valeur des variables est :
A ← 5         A = 5          B = ?           C = ?
B ← 3         A = 5          B = 3           C = ?
C ← A + B     A = 5          B = 3           C = 8
A ← 2         A = 2          B = 3           C = 8
C ← B – A     A = 2         B = 3          C = 1
```

```c#
using UnityEngine;

public class Exercice1_2 : MonoBehaviour
{
    void Start()
    {
        int A, B, C;

        A = 5;
        B = 3;
        C = A + B;
        A = 2;
        C = B - A;

        Debug.Log("A = " + A); // Affichera : A = 2
        Debug.Log("B = " + B); // Affichera : B = 3
        Debug.Log("C = " + C); // Affichera : C = 1
    }
}
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A, B et C seront affichées dans la console de Unity.

# Exercice 1.3
Quelles seront les valeurs des variables A et B après exécution des instructions suivantes ?
```
Variables A, B en Entier

Début
A ← 5
B ← A + 4
A ← A + 1
B ← A – 4
Fin
```
```
Après         La valeur des variables est :
A ← 5         A = 5          B = ?
B ← A + 4     A = 5          B = 9
A ← A + 1     A = 6          B = 9
B ← A – 4     A = 6         B = 2
```
```c#
using UnityEngine;

public class Exercice1_3 : MonoBehaviour
{
    void Start()
    {
        int A, B;

        A = 5;
        B = A + 4;
        A = A + 1;
        B = A - 4;

        Debug.Log("A = " + A); // Affichera : A = 6
        Debug.Log("B = " + B); // Affichera : B = 2
    }
}
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A et B seront affichées dans la console de Unity.


# Exercice 1.4
Quelles seront les valeurs des variables A, B et C après exécution des instructions suivantes ?
```
Variables A, B, C en Entier
Début
 A ← 3
B ← 10
C ← A + B
B ← A + B
A ← C
Fin
```
```
Après         La valeur des variables est :
A ← 3         A = 3          B = ?           C = ?
B ← 10        A = 3          B = 10          C = ?
C ← A + B     A = 3          B = 10          C = 13
B ← A + B     A = 3          B = 13          C = 13
A ← C        A = 13         B = 13         C = 13
```

```c#
using UnityEngine;

public class Exercice1_4 : MonoBehaviour
{
    void Start()
    {
        int A, B, C;

        A = 3;
        B = 10;
        C = A + B;
        B = A + B;
        A = C;

        Debug.Log("A = " + A); // Affichera : A = 13
        Debug.Log("B = " + B); // Affichera : B = 13
        Debug.Log("C = " + C); // Affichera : C = 13
    }
}
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A, B et C seront affichées dans la console de Unity.

# Exercice 1.5
Quelles seront les valeurs des variables A et B après exécution des instructions suivantes ?
```
Variables A, B en Entier
Début
A ← 5
B ← 2
A ← B
B ← A
Fin
```
Moralité : les deux dernières instructions permettent-elles d’échanger les deux valeurs de B et A ? Si l’on inverse les deux dernières instructions, cela change-t-il quelque chose ?

```
Après         La valeur des variables est :
A ← 5         A = 5          B = ?
B ← 2         A = 5          B = 2
A ← B         A = 2          B = 2
B ← A         A = 2         B = 2
```
```c#
using UnityEngine;

public class Exercice1_5 : MonoBehaviour
{
    void Start()
    {
        int A, B;

        A = 5;
        B = 2;
        A = B;
        B = A;

        Debug.Log("A = " + A); // Affichera : A = 2
        Debug.Log("B = " + B); // Affichera : B = 2
    }
}
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A et B seront affichées dans la console de Unity.

# Exercice 1.6
Plus difficile, mais c’est un classique absolu, qu’il faut absolument maîtriser : écrire un algorithme permettant d’échanger les valeurs de deux variables A et B, et ce quel que soit leur contenu préalable.

```
Début
…
C ← A
A ← B
B ← C
Fin
Il existe différentes solutions possibles (comme toujours), mais le plus simple est de passer par une variable dite temporaire (la variable C).
```
```c#
using UnityEngine;

public class Exercice1_6 : MonoBehaviour
{
    void Start()
    {
        int A = 5; // Valeur initiale de A
        int B = 10; // Valeur initiale de B
        int Temp;

        Debug.Log("Avant l'échange : A = " + A + ", B = " + B);

        // Échange des valeurs
        Temp = A;
        A = B;
        B = Temp;

        Debug.Log("Après l'échange : A = " + A + ", B = " + B);
    }
}
```
Explication du code C#
Initialisation des variables A et B :

```c#
int A = 5;
int B = 10;
```
Nous initialisons A à 5 et B à 10.

Déclaration de la variable temporaire Temp :

```c#
int Temp;
```
Affichage des valeurs avant l'échange :

```c#
Debug.Log("Avant l'échange : A = " + A + ", B = " + B);
```
Échange des valeurs :

```c#
Temp = A;
A = B;
B = Temp;
```
Affichage des valeurs après l'échange :

```c#
Debug.Log("Après l'échange : A = " + A + ", B = " + B);
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A et B avant et après l'échange seront affichées dans la console de Unity.
# Exercice 1.7
Une variante du précédent : on dispose de trois variables A, B et C. Ecrivez un algorithme transférant à B la valeur de A, à C la valeur de B et à A la valeur de C (toujours quels que soient les contenus préalables de ces variables).
```
Début
…
D ← C
C ← B
B ← A
A ← D
Fin
En fait, quel que soit le nombre de variables, une seule variable temporaire suffit…
``` 
```c#
using UnityEngine;

public class Exercice1_7 : MonoBehaviour
{
    void Start()
    {
        int A = 5; // Valeur initiale de A
        int B = 10; // Valeur initiale de B
        int C = 15; // Valeur initiale de C
        int Temp;

        Debug.Log("Avant le transfert : A = " + A + ", B = " + B + ", C = " + C);

        // Transfert des valeurs
        Temp = A;
        A = C;
        C = B;
        B = Temp;

        Debug.Log("Après le transfert : A = " + A + ", B = " + B + ", C = " + C);
    }
}
```
Explication du code C#
Initialisation des variables A, B et C :

```c#
int A = 5;
int B = 10;
int C = 15;
```
Nous initialisons A à 5, B à 10 et C à 15.

Déclaration de la variable temporaire Temp :

```c#
int Temp;
```
Affichage des valeurs avant le transfert :

```c#
Debug.Log("Avant le transfert : A = " + A + ", B = " + B + ", C = " + C);
```
Transfert des valeurs :

```c#
Temp = A;
A = C;
C = B;
B = Temp;
```
Affichage des valeurs après le transfert :

```c#
Debug.Log("Après le transfert : A = " + A + ", B = " + B + ", C = " + C);
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A, B et C avant et après le transfert seront affichées dans la console de Unity.

# Exercice 1.8
Que produit l’algorithme suivant ?
```
Variables A, B, C en Caractères
Début
A ← "423"
B ← "12"
C ← A + B
Fin
```
Il ne peut produire qu’une erreur d’exécution, puisqu’on ne peut pas additionner des caractères.

```c#
using UnityEngine;

public class Exercice1_8 : MonoBehaviour
{
    void Start()
    {
        string A = "423"; // Valeur initiale de A
        string B = "12"; // Valeur initiale de B
        string C;

        // Concaténation des valeurs
        C = A + B;

        Debug.Log("A = " + A); // Affichera : A = 423
        Debug.Log("B = " + B); // Affichera : B = 12
        Debug.Log("C = " + C); // Affichera : C = 42312
    }
}
```
Explication du code C#
Initialisation des variables A et B :

```c#
string A = "423";
string B = "12";
```
Nous initialisons A à "423" et B à "12".

Déclaration de la variable C :

```c#
string C;
```
Concaténation des valeurs :

```c#
C = A + B;
```
Affichage des valeurs :

```c#
Debug.Log("A = " + A); // Affichera : A = 423
Debug.Log("B = " + B); // Affichera : B = 12
Debug.Log("C = " + C); // Affichera : C = 42312
```
Vous pouvez attacher ce script à un GameObject dans votre scène Unity, et lorsque vous exécuterez la scène, les valeurs de A, B et C seront affichées dans la console de Unity. La valeur de C sera "42312", résultat de la concaténation des chaînes de caractères A et B.


# Exercice 1.9
Que produit l’algorithme suivant ?
```
Variables A, B, C en Caractères
Début
A ← "423"
B ← "12"
C ← A & B
Fin
```

…En revanche, on peut les concaténer. A la fin de l’algorithme, C vaudra donc  "42312".

```c#
using UnityEngine;

public class Exercice1_9 : MonoBehaviour
{
    void Start()
    {
        string A = "423"; // Valeur initiale de A
        string B = "12"; // Valeur initiale de B
        string C;

        // Concaténation des valeurs
        C = A + B;

        Debug.Log("A = " + A); // Affichera : A = 423
        Debug.Log("B = " + B); // Affichera : B = 12
        Debug.Log("C = " + C); // Affichera : C = 42312
    }
}
```