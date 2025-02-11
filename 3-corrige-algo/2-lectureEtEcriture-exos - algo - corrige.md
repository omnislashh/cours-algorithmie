# Exercice 2.1
Quel résultat produit le programme suivant ?
```C#
Variables val, double numériques
Début
Val ← 231
Double ← Val * 2
Ecrire Val
Ecrire Double
Fin
```
On verra apparaître à l’écran 231, puis 462 (qui vaut 231 * 2)


# Exercice 2.2
Ecrire un programme qui demande un nombre à l’utilisateur, puis qui calcule et  affiche le carré de ce nombre.
```C#
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
# Exercice 2.3
Ecrire un programme qui demande son prénom à l'utilisateur, et qui lui réponde par un charmant « Bonjour » suivi du prénom. On aura ainsi le dialogue suivant :

machine : Quel est votre prénom ?
utilisateur : Marie-Cunégonde
machine : Bonjour, Marie Cunégonde !

```C#
Variable prenom en Caractere
Début
Ecrire "Quel est votre prenom ?"
Lire Prenom
Ecrire "Bonjour ", Prenom, " !"
Fin
```
# Exercice 2.4
Ecrire un programme qui lit le prix HT d’un article, le nombre d’articles et le taux de TVA, et qui fournit le prix total TTC correspondant. Faire en sorte que des libellés apparaissent clairement.

```C#
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