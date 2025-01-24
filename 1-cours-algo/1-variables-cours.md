Partie 1
# Les Variables
>« N’attribuez jamais à la malveillance ce qui s’explique très bien par l’incompétence. » - Napoléon Bonaparte
« A l’origine de toute erreur attribuée à l’ordinateur, vous trouverez au moins deux erreurs humaines. Dont celle consistant à attribuer l’erreur à l’ordinateur. » - Anonyme
## 1. A quoi servent les variables ?
Dans un programme informatique, on va avoir en permanence besoin de stocker provisoirement des valeurs. Il peut s’agir de données issues du disque dur, fournies par l’utilisateur (frappées au clavier), ou que sais-je encore. Il peut aussi s’agir de résultats obtenus par le programme, intermédiaires ou définitifs. Ces données peuvent être de plusieurs types (on en reparlera) : elles peuvent être des nombres, du texte, etc. Toujours est-il que dès que l’on a besoin de stocker une information au cours d’un programme, on utilise une variable.
Pour employer une image, une variable est une boîte, que le programme (l’ordinateur) va repérer par une étiquette. Pour avoir accès au contenu de la boîte, il suffit de la désigner par son étiquette.
En réalité, dans la mémoire vive de l’ordinateur, il n’y a bien sûr pas une vraie boîte, et pas davantage de vraie étiquette collée dessus (j’avais bien prévenu que la boîte et l’étiquette, c’était une image). Dans l’ordinateur, physiquement, il y a un emplacement de mémoire, repéré par une adresse binaire. Si on programmait dans un langage directement compréhensible par la machine, on devrait se fader de désigner nos données par de superbes 10011001 et autres 01001001 (enchanté !). Mauvaise nouvelle : de tels langages existent ! Ils portent le doux nom d’assembleur. Bonne nouvelle : ce ne sont pas les seuls langages disponibles.
Les langages informatiques plus évolués (ce sont ceux que presque tout le monde emploie) se chargent précisément, entre autres rôles, d’épargner au programmeur la gestion fastidieuse des emplacements mémoire et de leurs adresses. Et, comme vous commencez à le comprendre, il est beaucoup plus facile d’employer les étiquettes de son choix, que de devoir manier des adresses binaires.

## 2. Déclaration des variables
La première chose à faire avant de pouvoir utiliser une variable est de créer la boîte et de lui coller une étiquette. Ceci se fait tout au début de l’algorithme, avant même les instructions proprement dites. C’est ce qu’on appelle la déclaration des variables. C’est un genre de déclaration certes moins romantique qu’une déclaration d’amour, mais d’un autre côté moins désagréable qu’une déclaration d’impôts.
Le nom de la variable (l’étiquette de la boîte) obéit à des impératifs changeant selon les langages. Toutefois, une règle absolue est qu’un nom de variable peut comporter des lettres et des chiffres, mais qu’il exclut la plupart des signes de ponctuation, en particulier les espaces. Un nom de variable correct commence également impérativement par une lettre. Quant au nombre maximal de signes pour un nom de variable, il dépend du langage utilisé.
En pseudo-code algorithmique, on est bien sûr libre du nombre de signes pour un nom de variable, même si pour des raisons purement pratiques, et au grand désespoir de Stéphane Bern, on évite généralement les noms à rallonge.
Lorsqu’on déclare une variable, il ne suffit pas de créer une boîte (réserver un emplacement mémoire) ; encore doit-on préciser ce que l’on voudra mettre dedans, car de cela dépendent la taille de la boîte (de l’emplacement mémoire) et le type de codage utilisé.
### 2.1 Types numériques classiques
Commençons par le cas très fréquent, celui d’une variable destinée à recevoir des nombres.
Si l’on réserve un octet pour coder un nombre, je rappelle pour ceux qui dormaient en lisant le chapitre précédent qu’on ne pourra coder que 28 = 256 valeurs différentes. Cela peut signifier par exemple les nombres entiers de 1 à 256, ou de 0 à 255, ou de –127 à +128… Si l’on réserve deux octets, on a droit à 65 536 valeurs ; avec trois octets, 16 777 216, etc. Et là se pose un autre problème : ce codage doit-il représenter des nombres décimaux ? des nombres négatifs ?
Bref, le type de codage (autrement dit, le type de variable) choisi pour un nombre va déterminer :
les valeurs maximales et minimales des nombres pouvant être stockés dans la variable
la précision de ces nombres (dans le cas de nombres décimaux).
Tous les langages, quels qu’ils soient offrent un « bouquet » de types numériques, dont le détail est susceptible de varier légèrement d’un langage à l’autre. Grosso modo, on retrouve cependant les types suivants :
 
Type Numérique	Plage
Byte (octet)	0 à 255
Entier simple	-32 768 à 32 767
Entier long	-2 147 483 648 à 2 147 483 647
Réel simple	-3,40x1038 à -1,40x1045 pour les valeurs négatives
1,40x10-45 à 3,40x1038 pour les valeurs positives
Réel double	1,79x10308 à -4,94x10-324 pour les valeurs négatives
4,94x10-324 à 1,79x10308 pour les valeurs positives
Pourquoi ne pas déclarer toutes les variables numériques en réel double, histoire de bétonner et d’être certain qu’il n’y aura pas de problème ? En vertu du principe de l’économie de moyens. Un bon algorithme ne se contente pas de « marcher » ; il marche en évitant de gaspiller les ressources de la machine. Sur certains programmes de grande taille, l’abus de variables surdimensionnées peut entraîner des ralentissements notables à l’exécution, voire un plantage pur et simple de l’ordinateur. Alors, autant prendre dès le début de bonnes habitudes d’hygiène.
En algorithmique, on ne se tracassera pas trop avec les sous-types de variables numériques (sachant qu'on aura toujours assez de soucis comme ça, allez). On se contentera donc de préciser qu'il s'agit d'un nombre, en gardant en tête que dans un vrai langage, il faudra être plus précis.
En pseudo-code, une déclaration de variables aura ainsi cette tête :
Variable g en Numérique
ou encore
Variables PrixHT, TauxTVA, PrixTTC en Numérique
### 2.2 Autres types numériques
Certains langages autorisent d’autres types numériques, notamment :
le type monétaire (avec strictement deux chiffres après la virgule)
le type date (jour/mois/année).
Nous n’emploierons pas ces types dans ce cours ; mais je les signale, car vous ne manquerez pas de les rencontrer en programmation proprement dite.
### 2.3 Type alphanumérique
Fort heureusement, les boîtes que sont les variables peuvent contenir bien d’autres informations que des nombres. Sans cela, on serait un peu embêté dès que l’on devrait stocker un nom de famille, par exemple.
On dispose donc également du type alphanumérique (également appelé type caractère, type chaîne ou en anglais, le type string – mais ne fantasmez pas trop vite, les string, c’est loin d’être aussi excitant que le nom le suggère. Une étudiante qui se reconnaîtra si elle lit ces lignes a d'ailleurs mis le doigt - si j'ose m'exprimer ainsi - sur le fait qu'il en va de même en ce qui concerne les bytes).
Dans une variable de ce type, on stocke des caractères, qu’il s’agisse de lettres, de signes de ponctuation, d’espaces, ou même de chiffres. Le nombre maximal de caractères pouvant être stockés dans une seule variable string dépend du langage utilisé.
Un groupe de caractères (y compris un groupe de un, ou de zéro caractères), qu’il soit ou non stocké dans une variable, d’ailleurs, est donc souvent appelé chaîne de caractères.
En pseudo-code, une chaîne de caractères est toujours notée entre guillemets
Pourquoi diable ? Pour éviter deux sources principales de  possibles confusions :
la confusion entre des nombres et des suites de chiffres. Par exemple, 423 peut représenter le nombre 423 (quatre cent vingt-trois), ou la suite de caractères 4, 2, et 3. Et ce n’est pas du tout la même chose ! Avec le premier, on peut faire des calculs, avec le second, point du tout. Dès lors, les guillemets permettent d’éviter toute ambiguïté : s’il n’y en a pas, 423 est quatre cent vingt trois. S’il y en a, "423" représente la suite des chiffres 4, 2, 3.
…Mais ce n'est pas le pire. L'autre confusion, bien plus grave - et bien plus fréquente – consiste à se mélanger les pinceaux entre le nom d'une variable et son contenu. Pour parler simplement, cela consiste à confondre l'étiquette d'une boîte et ce qu'il y a à l'intérieur… On reviendra sur ce point crucial dans quelques instants.
### 2.4 Type booléen
Le dernier type de variables est le type booléen  : on y stocke uniquement les valeurs logiques VRAI et FAUX.
On peut représenter ces notions abstraites de VRAI et de FAUX par tout ce qu'on veut  : de l'anglais (TRUE et FALSE) ou des nombres (0 et 1). Peu importe. Ce qui compte, c'est de comprendre que le type booléen est très économique en termes de place mémoire occupée, puisque pour stocker une telle information binaire, un seul bit suffit.
Le type booléen est très souvent négligé par les programmeurs, à tort.
Il est vrai qu'il n'est pas à proprement parler indispensable, et qu'on pourrait écrire à peu près n’importe quel programme en l'ignorant complètement. Pourtant, si le type booléen est mis à disposition des programmeurs dans tous les langages, ce n'est pas pour rien. Le recours aux variables booléennes s'avère très souvent un puissant instrument de lisibilité des algorithmes : il peut faciliter la vie de celui qui écrit l'algorithme, comme de celui qui le relit pour le corriger.
Alors, maintenant, c'est certain, en algorithmique, il y a une question de style : c'est exactement comme dans le langage courant, il y a plusieurs manières de s'exprimer pour dire sur le fond la même chose. Nous verrons plus loin différents exemples de variations stylistiques autour d'une même solution. En attendant, vous êtes prévenus : l'auteur de ce cours est un adepte fervent (mais pas irraisonné) de l'utilisation des variables booléennes.

## 3. L’instruction d’affectation
### 3.1 Syntaxe et signification
Ouf, après tout ce baratin préliminaire, on aborde enfin nos premières véritables manipulations d’algorithmique. Pas trop tôt, certes, mais pas moyen de faire autrement !
En fait, la variable (la boîte) n'est pas un outil bien sorcier à manipuler. A la différence du couteau suisse ou du superbe robot ménager vendu sur Télé Boutique Achat, on ne peut pas faire trente-six mille choses avec une variable, mais seulement une et une seule.
Cette seule chose qu’on puisse faire avec une variable, c’est l’affecter, c’est-à-dire lui attribuer une valeur. Pour poursuivre la superbe métaphore filée déjà employée, on peut remplir la boîte.
En pseudo-code, l'instruction d'affectation se note avec le signe ←
Ainsi :
```
Toto ← 24
```
Attribue la valeur 24 à la variable Toto.
Ceci, soit dit en passant, sous-entend impérativement que Toto soit une variable de type numérique. Si Toto a été défini dans un autre type, il faut bien comprendre que cette instruction provoquera une erreur. C’est un peu comme si, en donnant un ordre à quelqu’un, on accolait un verbe et un complément incompatibles, du genre « Epluchez la casserole ». Même dotée de la meilleure volonté du monde, la ménagère lisant cette phrase ne pourrait qu’interrompre dubitativement sa tâche. Alors, un ordinateur, vous pensez bien…
On peut en revanche sans aucun problème attribuer à une variable la valeur d’une autre variable, telle quelle ou modifiée. Par exemple :
```
Tutu ← Toto
```
Signifie que la valeur de Tutu est maintenant celle de Toto.
Notez bien que cette instruction n’a en rien modifié la valeur de Toto : une instruction d’affectation ne modifie que ce qui est situé à gauche de la flèche.
```
Tutu ← Toto + 4
```
Si Toto contenait 12, Tutu vaut maintenant 16. De même que précédemment, Toto vaut toujours 12.
```
Tutu ← Tutu + 1
```
Si Tutu valait 6, il vaut maintenant 7. La valeur de Tutu est modifiée, puisque Tutu est la variable située à gauche de la flèche.
Pour revenir à présent sur le rôle des guillemets dans les chaînes de caractères et sur la confusion numéro 2 signalée plus haut, comparons maintenant deux algorithmes suivants :
### Exemple n°1
```
Début
Riri ← "Loulou"
Fifi ← "Riri"
Fin
```
### Exemple n°2
```
Début
Riri ← "Loulou"
Fifi ← Riri
Fin
```
La seule différence entre les deux algorithmes consiste dans la présence ou dans l’absence des guillemets lors de la seconde affectation. Et l'on voit que cela change tout !
Dans l'exemple n°1, ce que l'on affecte à la variable Fifi, c'est la suite de caractères  R – i – r - i. Et à la fin de l’algorithme, le contenu de la variable Fifi est donc « Riri ».
Dans l'exemple n°2, en revanche, Riri étant dépourvu de guillemets, n'est pas considéré comme une suite de caractères, mais comme un nom de variable. Le sens de la ligne devient donc : « affecte à la variable Fifi le contenu de la variable Riri ». A la fin de l’algorithme n°2, la valeur de la variable Fifi est donc « Loulou ».  Ici, l’oubli des guillemets conduit certes à un résultat,  mais à un résultat différent.
A noter, car c’est un cas très fréquent, que généralement, lorsqu’on oublie les guillemets lors d’une affectation de chaîne, ce qui se trouve à droite du signe d’affectation ne correspond à aucune variable précédemment déclarée et affectée. Dans ce cas, l’oubli des guillemets se solde immédiatement par une erreur d’exécution.
Ceci est une simple illustration. Mais elle résume l’ensemble des problèmes qui surviennent lorsqu’on oublie la règle des guillemets aux chaînes de caractères. 
### 3.2 Ordre des instructions
Il va de soi que l’ordre dans lequel les instructions sont écrites va jouer un rôle essentiel dans le résultat final. Considérons les deux algorithmes suivants :
### Exemple 1
```
Variable A en Numérique
Début
A ← 34
A ← 12
Fin
```
### Exemple 2
```
Variable A en Numérique
Début
A ← 12
A ← 34
Fin
```
Il est clair que dans le premier cas la valeur finale de A est 12, dans l’autre elle est 34 .
Il est tout aussi clair que ceci ne doit pas nous étonner. Lorsqu’on indique le chemin à quelqu’un, dire « prenez tout droit sur 1km, puis à droite » n’envoie pas les gens au même endroit que si l’on dit « prenez à droite puis tout droit pendant 1 km ».
Enfin, il est également clair que si l’on met de côté leur vertu pédagogique, les deux algorithmes ci-dessus sont parfaitement idiots ; à tout le moins ils contiennent une incohérence. Il n’y a aucun intérêt à affecter une variable pour l’affecter différemment juste après. En l’occurrence, on aurait tout aussi bien atteint le même résultat en écrivant simplement :
### Exemple 1
```
Variable A en Numérique
Début
A ← 12
Fin
```
### Exemple 2
```
Variable A en Numérique
Début
A ← 34
Fin
```
Tous les éléments sont maintenant en votre possession pour que ce soit à vous de jouer !
<span style="color: #26B260">
Exercice 1.1
Exercice 1.2
Exercice 1.3
Exercice 1.4
Exercice 1.5
Exercice 1.6
Exercice 1.7
</span>
## 4. Expressions et opérateurs
Si on fait le point, on s’aperçoit que dans une instruction d’affectation, on trouve :
à gauche de la flèche, un nom de variable, et uniquement cela. En ce monde empli de doutes qu’est celui de l’algorithmique, c’est une des rares règles d’or qui marche à tous les coups : si on voit à gauche d’une flèche d’affectation autre chose qu’un nom de variable, on peut être certain à 100% qu’il s’agit d’une erreur.
à droite de la flèche, ce qu’on appelle une expression. Voilà encore un mot qui est trompeur ; en effet, ce mot existe dans le langage courant, où il revêt bien des significations. Mais en informatique, le terme d’expression ne désigne qu’une seule chose, et qui plus est une chose très précise :
Une expression est un ensemble de valeurs, reliées par des opérateurs, et équivalent à une seule valeur
Cette définition vous paraît peut-être obscure. Mais réfléchissez-y quelques minutes, et vous verrez qu’elle recouvre quelque chose d’assez simple sur le fond. Par exemple, voyons quelques expressions de type numérique. Ainsi :
7
5+4
123-45+844
Toto-12+5-Riri
…sont toutes des expressions valides, pour peu que Toto et Riri soient bien des nombres. Car dans le cas contraire, la quatrième expression n’a pas de sens. En l’occurrence, les opérateurs que j’ai employés sont l’addition (+) et la soustraction (-).
Revenons pour le moment sur l’affectation. Une condition supplémentaire (en plus des deux précédentes) de validité d’une instruction d’affectation est que :
l’expression située à droite de la flèche soit du même type que la variable située à gauche. C’est très logique : on ne peut pas ranger convenablement des outils dans un sac à provision, ni des légumes dans une trousse à outils… sauf à provoquer un résultat catastrophique.
Si l’un des trois points énumérés ci-dessus n’est pas respecté, la machine sera incapable d’exécuter l’affectation, et déclenchera une erreur (est-il besoin de dire que si aucun de ces points n’est respecté, il y aura aussi erreur !)
On va maintenant détailler ce que l’on entend par le terme d’ opérateur.
Un opérateur est un signe qui relie deux valeurs, pour produire un résultat.
Les opérateurs possibles dépendent du type des valeurs qui sont en jeu. Allons-y, faisons le tour, c’est un peu fastidieux, mais comme dit le sage au petit scarabée, quand c’est fait, c’est plus à faire.
### 4.1 Opérateurs numériques
Ce sont les quatre opérations arithmétiques tout ce qu’il y a de classique.
+ : addition
- : soustraction
* : multiplication
/ : division
Mentionnons également le ^ qui signifie « puissance ». 45 au carré s’écrira donc 45 ^ 2.
Enfin, on a le droit d’utiliser les parenthèses, avec les mêmes règles qu’en mathématiques. La multiplication et la division ont « naturellement » priorité sur l’addition et la soustraction. Les parenthèses ne sont ainsi utiles que pour modifier cette priorité naturelle.
Cela signifie qu’en informatique, 12 * 3 + 5 et (12 * 3) + 5 valent strictement la même chose, à savoir 41. Pourquoi dès lors se fatiguer à mettre des parenthèses inutiles ?
En revanche, 12 * (3 + 5) vaut 12 * 8 soit 96. Rien de difficile là-dedans, que du normal.
### 4.2 Opérateur alphanumérique : &
Cet opérateur permet de concaténer, autrement dit d’agglomérer, deux chaînes de caractères. Par exemple :
```
Variables A, B, C en Caractère
Début
A ← "Gloubi"
B ← "Boulga"
C ← A & B
Fin
```
La valeur de C à la fin de l’algorithme est "GloubiBoulga"
### 4.3 Opérateurs logiques (ou booléens) :
Il s’agit du ET, du OU, du NON et du mystérieux (mais rarissime XOR). Nous les laisserons de côté… provisoirement, soyez-en sûrs.
<span style="color: #26B260">
Exercice 1.8
Exercice 1.9
</span>
## 5. Deux remarques pour terminer
Maintenant que nous sommes familiers des variables et que nous les manipulons les yeux fermés (mais les neurones en éveil, toutefois), j’attire votre attention sur la trompeuse similitude de vocabulaire entre les mathématiques et l’informatique. En mathématiques, une « variable » est généralement une inconnue, qui recouvre un nombre non précisé de valeurs. Lorsque j’écris :  
y = 3 x + 2  
<hr>
les « variables » x et y satisfaisant à l’équation existent en nombre infini (graphiquement, l’ensemble des solutions à cette équation dessine une droite). Lorsque j’écris :
ax² + bx + c = 0   
<hr> 
la « variable » x désigne les solutions à cette équation, c’est-à-dire zéro, une ou deux valeurs à la fois…  
<hr>
En informatique, une variable possède à un moment donné une valeur et une seule. A la rigueur, elle peut ne pas avoir de valeur du tout (une fois qu’elle a été déclarée, et tant qu’on ne l’a pas affectée. A signaler que dans certains langages, les variables non encore affectées sont considérées comme valant automatiquement zéro). Mais ce qui est important, c’est que cette valeur justement, ne « varie » pas à proprement parler. Du moins ne varie-t-elle que lorsqu’elle est l’objet d’une instruction d’affectation.  
<hr>
La deuxième remarque concerne le signe de l’affectation. En algorithmique, comme on l’a vu, c’est le signe ←. Mais en pratique, la quasi totalité des langages emploient le signe égal. Et là, pour les débutants, la confusion avec les maths est également facile. En maths, A = B et B = A sont deux propositions strictement équivalentes. En informatique, absolument pas, puisque cela revient à écrire A ← B et B ← A, deux choses bien différentes. De même, A = A + 1, qui en mathématiques, constitue une équation sans solution, représente en programmation une action tout à fait licite (et de surcroît extrêmement courante). Donc, attention   ! ! ! La meilleure des vaccinations contre cette confusion consiste à bien employer le signe ← en pseudo-code, signe qui a le mérite de ne pas laisser place à l’ambiguïté. Une fois acquis les bons réflexes avec ce signe, vous n’aurez plus aucune difficulté à passer au = des langages de programmation.