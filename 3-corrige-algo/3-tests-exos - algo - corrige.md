# Exercice 3.1
Ecrire un algorithme qui demande un nombre à l’utilisateur, et l’informe ensuite si ce nombre est positif ou négatif (on laisse de côté le cas où le nombre vaut zéro).
```C#
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

# Exercice 3.2
Ecrire un algorithme qui demande deux nombres à l’utilisateur et l’informe ensuite si leur produit est négatif ou positif (on laisse de côté le cas où le produit est nul). Attention toutefois : on ne doit pas calculer le produit des deux nombres.
```C#
Variables m, n en Entier          // Déclaration de deux variables entières : m et n

Début  
Ecrire "Entrez deux nombres : "   // Demande à l'utilisateur d'entrer deux nombres  
Lire m, n                         // Stocke les valeurs saisies dans les variables m et n  

// Vérification du signe du produit sans calculer réellement le produit
Si (m > 0 ET n > 0) OU (m < 0 ET n < 0) Alors  
  // Si les deux nombres sont positifs OU si les deux nombres sont négatifs,
  // leur produit est forcément positif.
  Ecrire "Leur produit est positif"  

Sinon  
  // Sinon, cela signifie qu'un nombre est négatif et l'autre est positif,
  // donc leur produit est négatif.
  Ecrire "Leur produit est négatif"  

Finsi  // Fin de la structure conditionnelle  

Fin  // Fin du programme  
```

# Exercice 3.3
Ecrire un algorithme qui demande trois noms à l’utilisateur et l’informe ensuite s’ils sont rangés ou non dans l’ordre alphabétique.
```C#
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

# Exercice 3.4
Ecrire un algorithme qui demande un nombre à l’utilisateur, et l’informe ensuite si ce nombre est positif ou négatif (on inclut cette fois le traitement du cas où le nombre vaut zéro).
```C#
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


# Exercice 3.5
Ecrire un algorithme qui demande deux nombres à l’utilisateur et l’informe ensuite si le produit est négatif ou positif (on inclut cette fois le traitement du cas où le produit peut être nul). Attention toutefois, on ne doit pas calculer le produit !
```C#
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

# Exercice 3.6
Ecrire un algorithme qui demande l’âge d’un enfant à l’utilisateur. Ensuite, il l’informe de sa catégorie :  
"Poussin" de 6 à 7 ans  
"Pupille" de 8 à 9 ans  
"Minime" de 10 à 11 ans  
"Cadet" après 12 ans  
Peut-on concevoir plusieurs algorithmes équivalents menant à ce résultat ?

```C#
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