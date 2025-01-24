Partie 2
# Lecture et Ecriture
>« Un programme est un sort jeté sur un ordinateur, qui transforme tout texte saisi au clavier en message d’erreur. » - Anonyme
« Un clavier Azerty en vaut deux » - Anonyme
## 1. De quoi parle-t-on ?
Trifouiller des variables en mémoire vive par un chouette programme, c’est vrai que c’est très marrant, et d’ailleurs on a tous bien rigolé au chapitre précédent. Cela dit, à la fin de la foire, on peut tout de même se demander à quoi ça sert.
En effet. Imaginons que nous ayons fait un programme pour calculer le carré d’un nombre, mettons 12. Si on a fait au plus simple, on a écrit un truc du genre :
```
Variable A en Numérique
Début
A ← 12^2
Fin
```
D’une part, ce programme nous donne le carré de 12. C’est très gentil à lui. Mais si l’on veut le carré d’un autre nombre que 12, il faut réécrire le programme. Bof.  
D’autre part, le résultat est indubitablement calculé par la machine. Mais elle le garde soigneusement pour elle, et le pauvre utilisateur qui fait exécuter ce programme, lui, ne saura jamais quel est le carré de 12. Re-bof.  
C’est pourquoi, heureusement, il existe des d’instructions pour permettre à la machine de dialoguer avec l’utilisateur (et Lycée de Versailles, eût ajouté Pierre Dac, qui en précurseur méconnu de l’algorithmique, affirmait tout aussi profondément que « rien ne sert de penser, il faut réfléchir avant »).  
Dans un sens, ces instructions permettent à l’utilisateur de rentrer des valeurs au clavier pour qu’elles soient utilisées par le programme. Cette opération est la lecture.  
Dans l’autre sens, d’autres instructions permettent au programme de communiquer des valeurs à l’utilisateur en les affichant à l’écran. Cette opération est l’écriture.  
<hr>
Remarque essentielle : A première vue, on peut avoir l’impression que les informaticiens étaient beurrés comme des petits lus lorsqu’ils ont baptisé ces opérations ; puisque quand l’utilisateur doit écrire au clavier, on appelle cette instruction la lecture, et quand il doit lire sur l’écran on l'appelle l’écriture. Mais avant d’agonir d’insultes une digne corporation, il faut réfléchir un peu plus loin.  
<hr>
Un algorithme, c’est une suite d’instructions qui programme la machine, pas l’utilisateur ! Donc quand on dit à la machine de lire une valeur, cela implique que l’utilisateur va devoir écrire cette valeur. Et quand on demande à la machine d’écrire une valeur, c’est pour que l’utilisateur puisse la lire. Lecture et écriture sont donc des termes qui comme toujours en programmation, doivent être compris du point de vue de la machine qui sera chargée de les exécuter, et non de l'utilisateur qui se servira du programme. Et là, tout devient parfaitement logique. Et toc.


## 2. Les instructions de lecture et d’écriture
Tout bêtement, pour que l’utilisateur entre la (nouvelle) valeur de Titi, on mettra :
```
Lire Titi
```
Dès que le programme rencontre une instruction Lire, l’exécution s’interrompt, attendant la frappe d’une valeur au clavier. L'interruption peut durer quelques secondes, quelques minutes ou plusieurs heures : la seule chose qui fera exécuter la suite des instructions, c'est que la touche Entrée (Enter) ait été enfoncée.
Aussitôt que c'est le cas, il se passe deux choses. Pour commencer, tout ce qui a été frappé avant la touche Entrée (une suite de lettres, de chiffres, ou un mélange des deux) est rentré dans la variable qui suit l'instruction Lire (ici, Titi). Et ensuite, immédiatement, la machine exécute l'instruction suivante.  
Lire est donc une autre manière d'affecter une valeur à une variable. Avec l'instruction d'affectation, c'est le programmeur qui choisit à l'avance quelle doit être cette valeur. Avec l'instruction Lire, il laisse ce choix à l'utilisateur.
Dans le sens inverse, pour écrire quelque chose à l’écran, c’est aussi simple que :
```
Ecrire Toto
```
Parenthèse : « les bonnes manières du programmeur » : avant de Lire une variable, il est très fortement conseillé d’écrire des libellés à l’écran, afin de prévenir l’utilisateur de ce qu’il doit frapper (sinon, le pauvre utilisateur passe son temps à se demander ce que l’ordinateur attend de lui… et c’est très désagréable !) :
```
Ecrire "Entrez votre nom : "
Lire NomFamille
```
Lecture et Ecriture sont des instructions algorithmiques qui ne présentent pas de difficultés particulières, une fois qu’on a bien assimilé ce problème du sens du dialogue (homme → machine, ou machine ← homme).  
Et ça y est, vous savez d’ores et déjà sur cette question tout ce qu’il y a à savoir…
<hr>
<span style="color: #26B260">
Exercice 2.1
Exercice 2.2
Exercice 2.3
Exercice 2.4
</span>