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