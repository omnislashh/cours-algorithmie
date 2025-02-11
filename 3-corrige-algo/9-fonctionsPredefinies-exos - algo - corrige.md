# Exercice 9.1
Parmi ces affectations (considérées indépendamment les unes des autres), lesquelles provoqueront des erreurs, et pourquoi ?
```C#
Variables A, B, C en Numérique
Variable D en Caractère
A ← Sin(B)
A ← Sin(A + B * C)
B ← Sin(A) – Sin(D)
C ← Sin(A / B)
C ← Cos(Sin(A)
```
```C#
A ← Sin(B)            Aucun problème
A ← Sin(A + B * C)    Aucun problème
B ← Sin(A) – Sin(D)   Erreur ! D est en caractère
C ← Sin(A / B)        Aucun problème… si B est différent de zéro
C ← Cos(Sin(A)        Erreur ! Il manque une parenthèse fermante
```
# Exercice 9.2
Ecrivez un algorithme qui demande un mot à l’utilisateur et qui affiche à l’écran le nombre de lettres de ce mot (c'est vraiment tout bête).

Vous étiez prévenus, c'est bête comme chou ! Il suffit de se servir de la fonction Len, et c'est réglé :

```C#
Variable Mot en Caractère
Variable Nb en Entier
Debut
Ecrire "Entrez un mot : "
Lire Mot
Nb ← Len(Mot)
Ecrire "Ce mot compte ", Nb, " lettres"
Fin
```

# Exercice 9.3
Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui affiche à l’écran le nombre de mots de cette phrase. On suppose que les mots ne sont séparés que par des espaces (et c'est déjà un petit peu moins bête).

Là, on est obligé de compter par une boucle le nombre d'espaces de la phrase, et on en déduit le nombre de mots. La boucle examine les caractères de la phrase un par un, du premier au dernier, et les compare à l'espace.

```C#
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

# Exercice 9.4
Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui affiche à l’écran le nombre de voyelles contenues dans cette phrase.
On pourra écrire deux solutions. La première déploie une condition composée bien fastidieuse. La deuxième, en utilisant la fonction Trouve, allège considérablement l'algorithme.

Solution 1 : pour chaque caractère du mot, on pose une très douloureuse condition composée. Le moins que l'on puisse dire, c'est que ce choix ne se distingue pas par son élégance. Cela dit, il marche, donc après tout, pourquoi pas.

```C#
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
Version commentée :
```C#
Variable Bla en Caractère  // Déclare une variable pour stocker la phrase saisie par l'utilisateur
Variables Nb, i, j en Entier  // Déclare des variables pour compter les voyelles et pour les indices dans les boucles

Debut
  Ecrire "Entrez une phrase : "  // Demande à l'utilisateur de saisir une phrase
  Lire Bla  // Récupère la phrase saisie par l'utilisateur

  Nb ← 0  // Initialisation du compteur de voyelles à 0

  // Boucle qui parcourt chaque caractère de la phrase
  Pour i ← 1 à Len(Bla)  // La boucle commence à 1 car la fonction Mid est utilisée pour récupérer un caractère à partir de l'indice 1
    // Vérifie si le caractère à la position i est une voyelle
    Si Mid(Bla, i, 1) = "a" ou Mid(Bla, i, 1) = "e" ou Mid(Bla, i, 1) = "i" ou Mid(Bla, i, 1) = "o" ou Mid(Bla, i, 1) = "u" ou Mid(Bla, i, 1) = "y" Alors
      Nb ← Nb + 1  // Si c'est une voyelle, on incrémente le compteur de voyelles
    FinSi
  i suivant  // Passe à l'élément suivant

  Ecrire "Cette phrase compte ", Nb, " voyelles"  // Affiche le nombre de voyelles trouvées dans la phrase
Fin
```
Solution 2 : on stocke toutes les voyelles dans une chaîne. Grâce à la fonction Trouve, on détecte immédiatement si le caractère examiné est une voyelle ou non. C'est nettement plus sympathique...

```C#
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

# Exercice 9.5
Ecrivez un algorithme qui demande une phrase à l’utilisateur. Celui-ci entrera ensuite le rang d’un caractère à supprimer, et la nouvelle phrase doit être affichée (on doit réellement supprimer le caractère dans la variable qui stocke la phrase, et pas uniquement à l’écran).

Il n'existe aucun moyen de supprimer directement un caractère d'une chaîne… autrement qu'en procédant par collage. Il faut donc concaténer ce qui se trouve à gauche du caractère à supprimer, avec ce qui se trouve à sa droite. Attention aux paramètres des fonctions Mid, ils n'ont rien d'évident !
```C#
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


# Exercice 9.6 - Cryptographie 1
Un des plus anciens systèmes de cryptographie (aisément déchiffrable) consiste à décaler les lettres d’un message pour le rendre illisible. Ainsi, les A deviennent des B, les B des C, etc. Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui la code selon ce principe. Comme dans le cas précédent, le codage doit s’effectuer au niveau de la variable stockant la phrase, et pas seulement à l’écran.

Sur l'ensemble des exercices de cryptographie, il y a deux grandes stratégies possibles :

- soit transformer les caractères en leurs codes ASCII. L'algorithme revient donc ensuite à traiter des nombres. Une fois ces nombres transformés, il faut les reconvertir en caractères.

- soit en rester au niveau des caractères, et procéder directement aux transformations à ce niveau. C'est cette dernière option qui est choisie ici, et pour tous les exercices de cryptographie à venir.

Pour cet exercice, il y a une règle générale : pour chaque lettre, on détecte sa position dans l'alphabet, et on la remplace par la lettre occupant la position suivante. Seul cas particulier, la vingt-sixième lettre (le Z) doit être codée par la première (le A), et non par la vingt-septième, qui n'existe pas !

```C#
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
Version commentée :
```C#
Variables Bla, Cod, Alpha en Caractère  // Bla pour la phrase originale, Cod pour la phrase codée, Alpha pour l'alphabet
Variables i, Pos en Entier  // i pour l'index de parcours de la phrase, Pos pour la position de la lettre dans l'alphabet

Debut
  Ecrire "Entrez la phrase à coder : "  // Demande à l'utilisateur de saisir une phrase
  Lire Bla  // Récupère la phrase saisie

  Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"  // Initialisation de la chaîne Alpha avec toutes les lettres de l'alphabet
  Cod ← ""  // Initialisation de la variable Cod, qui contiendra la phrase codée

  // Boucle pour parcourir chaque caractère de la phrase
  Pour i ← 1 à Len(Bla)  // Parcours chaque caractère de la phrase
    Let ← Mid(Bla, i, 1)  // Extrait le caractère à la position i de la phrase

    // Vérifie si le caractère n'est pas un "Z"
    Si Let <> "Z" Alors
      Pos ← Trouve(Alpha, Let)  // Trouve la position de la lettre dans l'alphabet
      Cod ← Cod & Mid(Alpha, Pos + 1, 1)  // Ajoute la lettre suivante de l'alphabet à Cod
    Sinon
      Cod ← Cod & "A"  // Si la lettre est un "Z", la remplace par "A" (le décalage circulaire)
    FinSi
  i Suivant  // Passe à la lettre suivante de la phrase

  Bla ← Cod  // Remplace la phrase d'origine par la version codée
  Ecrire "La phrase codée est : ", Bla  // Affiche la phrase codée à l'utilisateur
Fin

```

# Exercice 9.7 - Cryptographie 2 - le chiffre de César
Une amélioration (relative) du principe précédent consiste à opérer avec un décalage non de 1, mais d’un nombre quelconque de lettres. Ainsi, par exemple, si l’on choisit un décalage de 12, les A deviennent des M, les B des N, etc.
Réalisez un algorithme sur le même principe que le précédent, mais qui demande en plus quel est le décalage à utiliser. Votre sens proverbial de l'élégance vous interdira bien sûr une série de vingt-six "Si...Alors"

Cet algorithme est une généralisation du précédent. Mais là, comme on ne connaît pas d'avance le décalage à appliquer, on ne sait pas a priori combien de "cas particuliers", à savoir de dépassements au-delà du Z, il va y avoir.
Il faut donc trouver un moyen simple de dire que si on obtient 27, il faut en réalité prendre la lettre numéro 1 de l'alphabet, que si on obtient 28, il faut en réalité prendre la numéro 2, etc. Ce moyen simple existe : il faut considérer le reste de la division par 26, autrement dit le modulo.
Il y a une petite ruse supplémentaire à appliquer, puisque 26 doit rester 26 et ne pas devenir 0.
```C#
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
Version commentée :
```C#
Variables Bla, Cod, Alpha en Caractère  // Bla pour la phrase originale, Cod pour la phrase codée, Alpha pour l'alphabet
Variables i, Pos, Décal en Entier  // i pour l'index de parcours de la phrase, Pos pour la position de la lettre, Décal pour le décalage

Début
  Ecrire "Entrez le décalage à appliquer : "  // Demande à l'utilisateur de saisir un décalage
  Lire Décal  // Récupère le décalage saisi

  Ecrire "Entrez la phrase à coder : "  // Demande à l'utilisateur de saisir une phrase
  Lire Bla  // Récupère la phrase saisie

  Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"  // Initialisation de l'alphabet
  Cod ← ""  // Initialisation de la variable Cod, qui contiendra la phrase codée

  // Boucle pour parcourir chaque caractère de la phrase
  Pour i ← 1 à Len(Bla)  // Parcours chaque caractère de la phrase
    Let ← Mid(Bla, i, 1)  // Extrait le caractère à la position i de la phrase

    // Trouve la position de la lettre dans l'alphabet
    Pos ← Trouve(Alpha, Let)  // Trouve la position de la lettre dans l'alphabet (A = 1, B = 2, ..., Z = 26)

    // Calcule la nouvelle position avec le décalage, et applique le modulo pour éviter de dépasser l'alphabet
    NouvPos ← Mod(Pos + Décal, 26)  // (Pos + Décal) % 26, cela permet de gérer les dépassements de l'alphabet

    // Si le résultat du modulo est 0 (cas où le décalage amène une position "Z" qui doit rester "Z"), on corrige
    Si NouvPos = 0 Alors
      NouvPos ← 26  // Si le modulo donne 0, cela correspond à "Z", donc on assigne NouvPos à 26
    FinSi

    // Ajoute la lettre codée à la phrase codée
    Cod ← Cod & Mid(Alpha, NouvPos, 1)  // Ajoute la lettre correspondante à la nouvelle position dans Cod
  i Suivant  // Passe au caractère suivant de la phrase

  Bla ← Cod  // Remplace la phrase d'origine par la version codée
  Ecrire "La phrase codée est : ", Bla  // Affiche la phrase codée à l'utilisateur
Fin
```

# Exercice 9.8 - Cryptographie 3
Une technique ultérieure de cryptographie consista à opérer non avec un décalage systématique, mais par une substitution aléatoire. Pour cela, on utilise un alphabet-clé, dans lequel les lettres se succèdent de manière désordonnée, par exemple :  
HYLUJPVREAKBNDOFSQZCWMGITX  
C’est cette clé qui va servir ensuite à coder le message. Selon notre exemple, les A deviendront des H, les B des Y, les C des L, etc.
Ecrire un algorithme qui effectue ce cryptage (l’alphabet-clé sera saisi par l’utilisateur, et on suppose qu'il effectue une saisie correcte).

Là, c'est assez direct.

```C#
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
Version commentée :
```C#
Variables Bla, Cod, Alpha, Clé en Caractère  // Bla pour la phrase à coder, Cod pour la phrase codée, Alpha pour l'alphabet standard, Clé pour l'alphabet-clé
Variables i, Pos en Entier  // i pour l'index de parcours de la phrase, Pos pour la position de la lettre dans l'alphabet

Début
  Ecrire "Entrez l’alphabet clé : "  // Demande à l'utilisateur de saisir l'alphabet clé
  Lire Clé  // Récupère l'alphabet clé saisi par l'utilisateur

  Ecrire "Entrez la phrase à coder : "  // Demande à l'utilisateur de saisir la phrase à coder
  Lire Bla  // Récupère la phrase saisie

  Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"  // Initialisation de l'alphabet standard (A à Z)
  Cod ← ""  // Initialisation de la variable Cod, qui contiendra la phrase codée

  // Boucle pour parcourir chaque caractère de la phrase
  Pour i ← 1 à Len(Bla)  // Parcours chaque caractère de la phrase
    Let ← Mid(Bla, i, 1)  // Extrait le caractère à la position i de la phrase

    // Trouve la position de la lettre dans l'alphabet standard
    Pos ← Trouve(Alpha, Let)  // Trouve la position de la lettre dans l'alphabet standard (A = 1, B = 2, ..., Z = 26)

    // Remplace la lettre par la lettre correspondante dans l'alphabet-clé
    Cod ← Cod & Mid(Clé, Pos, 1)  // Ajoute la lettre correspondante de l'alphabet-clé à la phrase codée
  i Suivant  // Passe au caractère suivant de la phrase

  Bla ← Cod  // Remplace la phrase d'origine par la version codée
  Ecrire "La phrase codée est : ", Bla  // Affiche la phrase codée à l'utilisateur
Fin

```

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
```C#
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
```C#
Posclé ← Posclé + 1
  Si PosClé > Len(Clé) Alors
    PosClé ← 1
  FinSi
```
On détermine quelle est la lettre clé et sa position dans l’alphabet
```C#
LetClé ← Mid(Clé, PosClé, 1)
  PosLetClé ← Trouve(Alpha, LetClé)
```
On détermine la position de la lettre à coder et le décalage à appliquer. Là encore, une solution alternative aurait été d’employer Mod : cela nous aurait épargné le Si…
```C#
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
Version commentée :
```C#
Variables Alpha, Bla, Cod, Clé, Let en Caractère  // Alpha pour l'alphabet, Bla pour le message, Cod pour le message codé, Clé pour la clé, Let pour une lettre du message
Variables i, Pos, PosClé, Décal en Entier  // i pour l'index de la boucle, Pos pour la position de la lettre dans l'alphabet, PosClé pour la position dans la clé, Décal pour le décalage

Début
  Ecrire "Entrez la clé : "  // Demande à l'utilisateur de saisir la clé
  Lire Clé  // Lire la clé

  Ecrire "Entrez la phrase à coder : "  // Demande à l'utilisateur de saisir la phrase à coder
  Lire Bla  // Lire la phrase

  Alpha ← "ABCDEFGHIJKLMNOPQRSTUVWXYZ"  // L'alphabet de référence (A à Z)
  Cod ← ""  // Initialisation de la variable Cod, qui contiendra la phrase codée

  PosClé ← 0  // Initialisation de la position dans la clé

  // Parcourir chaque caractère du message à coder
  Pour i ← 1 à Len(Bla)  // Boucle pour chaque lettre du message
    // Gérer la progression dans la clé
    PosClé ← PosClé + 1  // On avance à la lettre suivante dans la clé
    Si PosClé > Len(Clé) Alors  // Si on arrive à la fin de la clé
      PosClé ← 1  // On recommence depuis la première lettre de la clé
    FinSi

    LetClé ← Mid(Clé, PosClé, 1)  // Extraire la lettre correspondante de la clé
    PosLetClé ← Trouve(Alpha, LetClé)  // Trouver la position de la lettre clé dans l'alphabet (A = 1, B = 2, ..., Z = 26)

    Let ← Mid(Bla, i, 1)  // Extraire la lettre actuelle du message à coder
    Pos ← Trouve(Alpha, Let)  // Trouver la position de la lettre du message dans l'alphabet

    NouvPos ← Pos + PosLetClé - 1  // Calculer la nouvelle position en tenant compte du décalage
    Si NouvPos > 26 Alors  // Si la nouvelle position dépasse 26 (Z)
      NouvPos ← NouvPos - 26  // Revenir au début de l'alphabet (retour à A)
    FinSi

    Cod ← Cod & Mid(Alpha, NouvPos, 1)  // Ajouter la lettre codée à la chaîne Cod
  i Suivant  // Passer à la lettre suivante du message

  Bla ← Cod  // Remplacer la phrase d'origine par la version codée
  Ecrire "La phrase codée est : ", Bla  // Afficher la phrase codée
Fin
```

# Exercice 9.10
Ecrivez un algorithme qui demande un nombre entier à l’utilisateur. L’ordinateur affiche ensuite le message "Ce nombre est pair" ou "Ce nombre est impair" selon le cas.

On en revient à des choses plus simples...

```C#
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

# Exercice 9.11
Ecrivez les algorithmes qui génèrent un nombre Glup aléatoire tel que …  
0 =< Glup < 2  
–1 =< Glup < 1  
1,35 =< Glup < 1,65  
Glup émule un dé à six faces  
–10,5 =< Glup < +6,5  
Glup émule la somme du jet simultané de deux dés à six faces  

```C#
a) Glup ← Alea() * 2
b) Glup ← Alea() * 2 - 1
c) Glup ← Alea() * 0,30 + 1,35
d) Glup ← Ent(Alea() * 6) + 1
e) Glup ← Alea() * 17 – 10,5
f) Glup ← Ent(Alea()*6) + Ent(Alea()*6) + 2
```