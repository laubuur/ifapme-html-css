# IFAPME - LBA 
## Prérequis

```
Pour ce cours, vous aurez besoin de:
- Un navigateur récent : Firefox, Chrome, Edge, Safari, ...
- Un éditeur de texte. Nous recommandons Visual Studio Code:

https://code.visualstudio.com/download
L'extension Live Server pour Visual Studio Code - Facultatif mais
peut être utile souvent lors du développement web
```

## Introduction

Lorsque vous allez sur internet, vous ouvrez votre navigateur et vous visitez différentes pages:
Google, Twitter, Instagram, ... ou tout autre site internet. Tous ces sites disposent d'une chose en
commun, les deux langages utilisés pour afficher du contenu à l'écran: **HTML** et **CSS**. 


Contrairement aux langages de programmation classiques (C, PHP, Python, ...), il n'existe aucun
concurrent à ces deux langages informatiques, ils sont totalement incontournables dès que vous
souhaitez afficher du contenu dans une page web car ce sont les seuls langages interprétés par
nos navigateurs pour faire cela. 


Cependant, l'HTML et le CSS ne sont pas des langages de programmation. L'HTML est un langage
de balisage - comme son nom l'indique: *HyperText Markup Language* qu'on peut traduire par 
langage de balises pour l'hypertexte - et le CSS, quant à lui, est un langage de feuille de style.
L'HTML va définir le contenu de votre page et le CSS va définir de quelle manière vous allez
l'afficher. 


Par exemple, grâce à l'HTML, vous allez pouvoir dire au navigateur  « *Je souhaite afficher un
tableau contenant une liste de voiture avec une colonne pour la marque, une colonne pour le
modèle et une colonne pour la couleur de la voiture* ». Ensuite, grâce au CSS, vous allez dire au
navigateur « *Je souhaite que le texte dans la première colonne de mon tableau soit en gras et
qu'une ligne sur deux ait un fond bleu et un texte blanc. Je souhaite aussi mettre un peu d'espace
entre chaque colonne* »

![](https://github.com/laubuur/ifapme-html-css/blob/main/images/ar-css.png)

## Premiers pas en HTML

L'HTML permet donc de définir la structure et le contenu de votre site web, on fait cela grâce à
toute une série de balises qui formeront l'intégralité d'une page. Voici à quoi ressemble la structure
de base d'une page HTML (index.html):

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mon site web</title>
  </head>
  <body>
    <h1>Titre de premier niveau</h1>
    <p>Ceci est un paragraphe</p>
  </body>
</html>
```

Nous pouvons voir que ce code se compose de balises et de contenu. Les balises en html vont, la
plupart du temps, par paire. Une balise ouvrante et une balise fermante. Ainsi, dans le contenu de
chaque balise, vous pourrez trouver d'autres balises et former ainsi une arborescence qui sera
interprétée par votre navigateur pour afficher ce que vous souhaitez.

En première ligne, on retrouve le "doctype", c'est une balise exceptionnelle car sa structure
commence par <!, aucune autre balise n'est formée comme ça. Elle est obligatoire et sert à
indiquer au navigateur ce qu'il va devoir interpréter. Toutes vos pages HTML vont donc devoir
commencer par ça.

Ensuite, dans le code exemple ci-dessus, nous pouvons voir une arborescence d'éléments:

- **<*html*>**:  Elément obligatoire pour un bon fonctionnement du navigateur, elle englobe
toujours l'intégralité du code HTML. On retrouvera donc tout le code de notre page au sein
de cette balise.
- **<*head*>**: Elément obligatoire utilisé pour passer des informations au navigateur, rien ne
sera directement affiché dans votre page. Dans ce cas-ci, on y a juste placé la balise
<*title*> qui permet de définir le titre de la page.
- **<*title*>** : Utilisé pour définir le titre de la page ("Mon site web"), affiché dans l'onglet du
navigateur. Doit obligatoirement se trouver au sein de la balise <head>. Ce titre
n'apparaitra pas au sein de la page en elle-même.
- **<*body*>** : Elément obligatoire utilisé pour le contenu de votre page, c'est dans cette
balise que vous allez ajouter tout le contenu de la page qui doit être affiché à l'écran.
- **<*h1*>** : Elément qui permet d'indiquer au navigateur qu'il s'agit d'un titre de premier
niveau, on pourra retrouver aussi des titres de 1er - 7e niveau, allant donc de <*h1*> à
<*h7*>. 
- **<*p*>** : Elément pour indiquer au navigateur que son contenu est un paragraphe.

Ce code donne ceci:
![](https://github.com/laubuur/ifapme-html-css/blob/main/images/first-ex.png)

Vous remarquerez que les deux lignes n'ont pas la même apparence, c'est parce qu'un style est
défini par défaut par chaque navigateur pour toute une série d'élément HTML. Ainsi, la balise
<*h1*>, par défaut, met le contenu en gras, en grand et ajoute une marge par-dessous le contenu. Il
faudra y ajouter du code CSS pour changer cette apparence. 

### Affichage d'une page HTML
```
Une page html est un simple fichier texte contenant l'extension .html. Vous
pouvez donc enregistrer le code ci-dessus dans un fichier "index.html" et l'ouvrir
avec un navigateur, cela fonctionnera car celui-ci est assez intelligent pour savoir
quoi faire avec. Cependant, dans la réalité, ce n'est pas une solution
envisageable, les sites et applications web deviennent vite trop complexes et
cela ne sera plus possible, il faut alors héberger vos pages web sur un serveur
web. De plus, sans serveur web, seul vous aurez accès à votre page. 
L'éditeur de texte Visual Studio Code dispose d'une extension Live Server qui
permet de créer en un seul clic un petit serveur web sur votre PC. Vous pourrez
ainsi simuler le fonctionnement d'un vrai site web directement sur votre
ordinateur pendant votre développement.

Ainsi, lorsque vous êtes sur votre fichier HTML au sein de VSCode, vous verrez
l'image suivante dans votre éditeur.
Le bouton Go Live  permet de lancer votre serveur web et d'afficher facilement
votre page HTML sans devoir ouvrir le fichier avec le navigateur.
```
![](https://github.com/laubuur/ifapme-html-css/blob/main/images/go-live.png)

## Premiers pas en CSS
Le CSS va vous permettre de modifier l'apparence des éléments de votre page web. Ce code peut
être placé à trois endroits différents: 
- Directement sur l'élément concerné par ce que vous souhaitez faire ;
- Au sein d'une balise <*style*> se trouvant sur votre page ;
- Au sein d'un fichier CSS séparé. 


Dans le cadre des premiers pas, on va inclure du code CSS au sein d'une balise <*style*>. Le code
que nous mettrons dans cette balise peut être mis dans un fichier .css séparé. 

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mon site web</title>
    <style>
    
    </style>
  </head>
  <body>
    <h1>Titre de premier niveau</h1>
    <p>Ceci est un paragraphe</p>
  </body>
</html
```

Le CSS ne fonctionne pas avec des balises mais avec des *sélecteurs*. Le but est de sélectionner un
élément de la page via un sélecteur et de lui appliquer une apparence. Par exemple, je souhaite
mettre tous les titres de niveau 1 (<*h1*>) en rouge, j'utilise le **sélecteur** *h1* et j'applique ensuite le style désiré: 

```css
h1 {
  color: red; 
}
```

Ce code va sélectionner toutes les balises <*h1*>, lui appliquer la **propriété** css color et lui donner la **valeur** *red*.
La chaine "*propriété : valeur;*" s'appelle une **déclaration**.

![](https://github.com/laubuur/ifapme-html-css/blob/main/images/desc-css.png)


Les déclarations qu'on passe à un sélecteur se fait toujours entre accolades. Plusieurs déclarations
peuvent être faites pour un seul sélecteur. 
La propriété et sa valeur doivent être séparés par un double point et la déclaration doit toujours se terminer par un point-virgule. 
Les déclarations appliquées à un sélecteur doivent toujours se trouver entre accolades


### Sélectionner une balise spécifique

Nous avons vu comment sélectionner toute les balises *h1* en css pour y appliquer un style, mais
comment faire pour sélectionner uniquement une seule balise *h1* et pas toutes les balises de ma
page ? 


Avant de répondre à cette question, nous devons d'abord nous pencher sur une spécificité du html:
**les attributs**. Un attribut est une information supplémentaire qu'on va passer à une balise pour
modifier son comportement. Il se déclare au sein d'une balise et prend généralement une valeur.

#### Attribut class et id

##### class

L'attribut le plus courant et utilisé est **class**, il permet de donner une classe à notre élément, cette classe pourra ensuite être utilisée comme sélecteur css pour définir un style.

```html
<body>
  <h1 class="premier_titre">Titre de premier niveau</h1>
  <p>Ceci est un paragraphe</p>
</body>
```

On peut voir dans ce code qu'un attribut class a été ajouté à la balise *h1*. On peut alors modifier le code css vu ci-dessus pour appliquer la couleur rouge à la classe *premier_titre* et plus à toutes les balises *h1*.

```css
.premier_titre {
  color: red; 
}
```

Vous remarquez que le nom de la classe est précédé d'un point, il est obligatoire car il permet
d'indiquer au navigateur que ce sélectionneur concerne une classe, il va donc appliquer ce code à
l'ensemble des balises contenant la classe *premier_titre*.

```
Quelques règles concernant l'attribut class:
- Le nom d'une classe ne peut jamais contenir d'espace. On utilise
généralement un "tiret bas", aussi appelé "underscore", pour séparer
les mots.
- Plusieurs classes peuvent être passées dans un attribut class, pour cela il suffit de les séparer par un espace.
- Les classes peuvent être utilisées plusieurs fois par page.
```

##### ID

L'attribut ID est similaire à l'attribut class, il fonctionne de la même manière et peut être utilisé
comme sélectionneur css. Cependant, la différence majeure est qu'un ID doit impérativement être
unique. Si vous donnez un ID à un élément de votre page, aucun autre élément de cette page ne
pourra avoir le même ID. 

Reprenons l'exemple ci-dessus:

```html
<body>
  <h1 id="premier_titre">Titre de premier niveau</h1>
  <p>Ceci est un paragraphe</p>
</body>
```
```css
#premier_titre {
 color: red; 
}
```

Nous pouvons remarquer que le sélecteur css ne commence plus par un point mais par un dièse, il
permet d'indiquer que notre sélecteur est un ID. 

```
Quelques règles concernant l'attribut id:
- Le nom d'un id ne peut jamais contenir d'espace. On utilise
généralement un "tiret bas", aussi appelé "underscore", pour séparer
les mots.
- Plusieurs id peuvent être passées dans un attribut id, pour cela il suffit
de les séparer par un espace.
- Les id ne peuvent être utilisés qu'une seule fois par page
```

#### Appliquer du code css au sein d'une balise html

Il existe une autre solution pour appliquer un style à un élément spécifique sans cibler l'ensemble
des éléments de même type: appliquer le code css directement au sein de la balise ; pour faire
cela, il suffit de placer notre déclaration css dans un attribut ***style*** de la balise qu'on souhaite
modifier, si je reprends le code ci-dessus, cela donnera :

```html
<body>
  <h1 style="color: red;">Titre de premier niveau</h1>
  <p>Ceci est un paragraphe</p>
</body>
```

Le résultat sera identique et nous pouvons insérer plusieurs déclaration au sein de cette balise.

#### Multiples déclarations css
Il est bien entendu possible, dans tous les cas montrés ci-dessus, de faire plusieurs déclarations css
en même temps :
```css
#premier_titre {
  color: red;
  font-size: 15px;
}
```

```css
.premier_titre {
  color: red;
  font-size: 15px;
}
```

```html
<body>
  <h1 style="color: red; font-size: 15px">Titre de premier niveau</h1>
  <p>Ceci est un paragraphe</p>
</body>
```

# Les bases de l'HTML

## Introduction
Nous avons vu dans le chapitre précédent les bases du HTML, du CSS et de comment ils
fonctionnent ensemble.


Nous allons maintenant rentrer un peu plus en profondeur en HTML pour mieux comprendre son
fonctionnement.

## Structure de base d'une page HTML
Nous avons déjà pu voir comment se compose une page HTML, pour rappel voici la structure de
base d'une page:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mon site web</title>
    <meta charset="utf-8">
  </head>
  <body>
  </body>
</html>
```
La plupart des éléments ci-dessus sont connus, mais nous pouvons voir qu'il y a un nouvel
élément: **meta**. 
Cette balise sert à passer des métadonnées - une donnée qui permet de décrire une autre donnée -
au navigateur. Il est très fortement conseillé de l'inclure dans toutes vos pages et d'y passer
l'attribut charset en lui donnant la valeur "utf-8". Cet attribut permet de définir un jeu de caractère,
c'est ça qui indique à votre navigateur quel jeu de caractère utiliser. Il s'agit pour votre navigateur
d'interpréter correctement les caractères affichés, ainsi si vous utilisez des caractères spéciaux
comme des accents, si le jeu de caractère n'est pas bon, le rendu dans votre navigateur ne pourrait pas être le bon. Nous n'entrerons pas dans les détails mais sachez qu'il est en général très
conseillé d'utiliser utf-8. C'est le jeu de caractère recommandé par le W3C; *Le world wide web consurtium*, l'organisation qui standardise les technologies du web comme l'html ou le css.

On peut voir aussi que cet élément ne contient pas de balise fermante, on appelle ça un **élément vide.**

## Les commentaires
Lorsque vous développez, il est très utile de commenter son code. Cela permet de donner des
indications sur ce que fait le code, ces commentaires ne seront pas affichés à l'écran mais bien
visibles dans le code, cela permet de s'organiser et de s'y retrouver plus facilement dans son code.


Cela permet aussi à d'autres développeurs de s'y retrouver plus facilement dans votre code dans le
cadre d'un travail en équipe. 
En html, un commentaire se place entre <*!--* et *--*>, ils peuvent être mono ou multiligne:
```html
<body>
  <!-- Ceci est un commentaire mono-ligne -->
  <h1>Premier titre</h1>
  <h2>Second titre</h2>
  <!-- Ceci est un commentaire
  multi-ligne -->
  <p>Ceci est un paragraphe</p>
</body>

```
## Organisation du texte
Un paragraphe se défni avec la balise **<*p*><*/p*>**

Les titres se déclarent avec les balises **<*h1*></*h1*>** à **<*h6*></*h6*>**

Un retour à la ligne s'effectue avec la balise **<*br*>** qui est un élément vide, donc qui ne prend pas

de fermeture. Aucun attribut n'est passé à cette balise, elle est simplement utilisée comme retour
à la ligne.
## Importance du texte
Un texte peut être mis en emphase via la balise **<*em*><*/em*>**

Un texte peut être déclaré comme de haute importance via la balise **<*strong*></*strong*>**

Une partie pertinente d'un texte pour être marquée via la balise **<*mark*></*mark*>**

Ces éléments ont un effet visuel mais **ils ne doivent pas être utilisés pour ça**. Un élément strong met le texte en gras, mais il ne faut pas s'en servir pour mettre du texte en gras, il faut s'en servir car l'on souhaite préciser que cet élément est de grande importance. 
## "bloc" ou "inline" ?
Chaque élément peut être soit de type *bloc*, soit de type *inline*. Un élément "bloc" essaiera de
prendre le maximum d'espace horizontal à l'écran et un retour à la ligne sera effectué à l'ouverture et la fermeture de l'élément.

A l'inverse, un élément "inline" prendra le moins d'espace horizontal possible, plusieurs élément
"inline" peuvent donc être placé côte à côte. 

Par exemple, **<*p*></*p*>** est un élément de type bloc, alors que **<*strong*></*strong*>** est un élément de type inline.
## Listes
Une liste non-ordonnée se déclare via la balise **<*ul*></*ul*>**

Une liste ordonnée se déclare via la balise **<*ol*></*ol*>**

Chaque élément d'une liste se défini via la balise **<*li*></*li*>**, donc par exemple:
```html
<!-- Liste non ordonnée -->
<ul>
  <li>Element</li>
  <li>Autre élément</li>
</ul>
<!-- Liste ordonnée -->
<ol>
  <li>Element 1</li>
  <li>Element 2</li>
</ol>
```
## Multiples pages et liens
Un lien peut être fait vers une autre page (du même site ou non) via l'élément **<*a*></*a*>**

L'attribut à indiquer pour donner le chemin vers le lien est href, le chemin peut être relatif ou
absolu:

- **Relatif**: Chemin par rapport à la page sur laquelle on se trouve. Par exemple, dans
l'exemple ci-dessous, nous sommes sur la page *index.html* et nous souhaitons naviguer
vers la page *voitures.html* se trouvant dans le dossier listes: 
![](https://github.com/laubuur/ifapme-html-css/blob/main/images/folder-img.png)
```html
<a href="liste/voitures.html">Lien vers voiture.html</a>
```

Pour faire l'inverse, et retourner au fichier *index.html* depuis la page *voitures.html*, il faut d'abord sortir du dossier pour l'ouvrir, cela se fait comme ceci:
```html
<a href="../index.html">Lien vers voiture.html</a>
```


- **Absolu**: Chemin complet vers la page qu'on souhaite ouvrir, si votre site se trouve sur le
site* www.monsite.be*, l'exemple ci-dessus donnerait :
```html
<a href="www.monsite.be/liste/voitures.html">Lien vers voiture.html</a>
<!-- Peut aussi être utilisé pour ouvrir un autre site internet -->
<a href="www.google.be">Google</a>
```

### Lien vers une ancre
Cet élément peut aussi être utilisé pour se déplacer automatiquement sur la page pour accéder à
une section voulue. Pour cela, il faut donner un id à l'élément vers lequel on souhaite se diriger et
renseigner cet id précédé d'un dièse dans l'attribut *href* de l'élément.
```html
<div id="cible">Element cible vers lequel le lien doit mener</div>
<a href="#cible">Lien pour accéder à l'élement cible</a>
```
Cela peut aussi être utilisé pour accéder à un élément d'une autre page, si cet élément cible se
trouve dans la ma page *voitures.html*:
```html
<a href="liste/voitures.html#cible">Lien pour accéder à l'élement cible d'une autre page</a>
```

### Infobulle sur lien
Pour afficher une infobulle au survol d'un lien, il faut utiliser l'attribut **title** de l'élément **a**
```html
<a href="liste/voitures.html#cible" title="lien vers voitures.html !">Lien pour accéder à 
l'élement cible d'une autre page</a>
```
### Ouverture du lien dans une autre page
Si vous souhaitez que le lien ne s'ouvre pas dans la page courante mais dans un autre onglet, il
faut utiliser l'attribut **target** et lui passer la valeur **_blank**
```html
<a href="liste/voitures.html#cible" target="_blank">Lien pour accéder à l'élement cible d'une 
autre page</a>
```
## Images
Il est possible en HTML d'afficher une image dans vos pages. Mais avant toutes choses, il faut
comprendre ce qu'est une image et les choses à éviter pour ne pas alourdir vos pages web
inutilement.

Une image sur internet est compressée, c'est à dire qu'elle prendra moins d'espace disque et sera
plus rapide à télécharger. Mais il existe différent moyen de compresser une image en les
enregistrant dans différents formats.
### Les formats à privilégier
**WEBP** est un format d'image récent qui permet de garder une excellente qualité tout en utilisant
un espace disque très réduit. Il gère aussi la transparence. La transparence permet d'avoir des
images qui ne sont pas des rectangles ou qui ont des "trous" à l'intérieur. Ce format étant récent, il
n'est parfois donc pas pris en charge par certains navigateurs plus anciens. 

**PNG** est un autre format à privilégier, il comporte les mêmes qualités que webp même si sa
compression est plus faible, les fichiers sont donc un peu plus lourd que webp.

**JPEG** est le format d'image le plus répandu, il permet d'avoir des images fortement compressées
mais avec une perte de qualité, certain logiciel permettent de modifier la compression de l'image
pour réduire son espace disque tout en dégradant sa qualité. Cette opération est irréversible. Ce
format ne supporte pas la transparence. 

**GIF** est le format d'image utilisé quand on souhaite afficher des images animées. C'est ce qu'on
appelle généralement "GIFs animés", c'est ça que vous pouvez retrouver sur vos applications de
messagerie mobile comme Messenger, Whatsapp, ... 

Il en existe d'autres mais ils sont moins fréquents. 

Tous les autres formats sont généralement à bannir sur internet. 
### Insérer une image
L'insertion d'une image au sein d'une page web se fait via l'élément **<*img*>**, il s'agit d'un élément
vide, d'une balise orpheline, il n'y a donc pas de balise de fermeture. Le chemin vers l'image peut
être absolu ou relatif comme pour l'élément **a**, cette information est renseignée via l'attribut **src**:
```html
<img src="mon_image.webp">
```
Il est fortement conseillé de renseigner aussi l'attribut **alt** pour "contenu alternatif", il s'agit d'un
texte à afficher dans le cas où l'image ne peut pas être téléchargée ou utilisé pour des personnes
utilisant des logiciels pour malvoyant. 
```html
<img src="mon_image.webp" alt="Village de montagne">
```
Comme pour l'élément **a**, un attribut title peut être défini par ajouter une infobulle à l'image
```html
<img src="mon_image.webp" alt="Village de montagne" title="Ceci est un village de montagne !">
```

Vous pouvez **redimensionner** une image directement en html via les attributs *width* pour la
largeur et *height* pour la longueur, ces valeurs doivent être indiquées en pixel. Si une seule des
deux valeurs est renseignées, l'autre valeur est calculée automatiquement pour garder le bon
format d'image. 
```html
<img src="mon_image.webp" alt="Village de montagne" title="Ceci est un village de montagne !" 
width=32>
```
## Exercice

Réaliser un site web contenant 3 pages.  Une page d'accueil index.html, une page de coordonnées
coordonnee.html et une page d'images galerie.html.

Sur chaque page il doit y avoir un menu contenant les liens d'accès aux 3 pages. 

Sur la page d'accueil doit se trouver une présentation du site sous format texte en un ou deux
paragraphes. Une partie du texte doit être mis en évidence car son contenu est jugé pertinent. 
(https://fr.lipsum.com/ pour générer du texte aléatoire)

Sur la page de coordonnées doit se trouver des coordonnées sous forme de liste, il doit au moins y
être renseigné un numéro de téléphone et une adresse. 

Sur la page de galerie doit se trouver trois images, ces trois images doivent être côte à côte et
posséder une hauteur de 200 pixels. (https://unsplash.com/ pour accéder à une grande
bibliothèque de photo libres de droit)

Aller un peu plus loin: Faire en sorte que les images soient cliquables pour les ouvrir en taille réelle
dans un nouvel onglet.

# Les bases du CSS
## Introduction
On a vu précédemment que le CSS se plaçait directement au sein de l'élément HTML concerné,
dans une balise *style* ou dans un fichier css séparé (recommandé). 

On a aussi vu que le CSS fonctionnait par sélecteur et que chaque déclaration CSS contenait une
propriété et une valeur.
## Commentaires
Un commentaire peut être ajouté à du code css en le mettant entre /* et */
## Sélecteur simple
Un sélecteur est un moyen de sélectionner un élément de notre page HTML pour y appliquer une
déclaration css. Il y a trois moyens de sélectionner un élément:  directement via le nom de
l'élément, via une classe ou via un id: 
```css
/* Sélection via le nom de l'élément */
h1 {
  color: red;
}

/* Sélection via le nom d'une classe */
.titre1 {
  color: red;
}

/* Sélection via un ID */
#titre1 {
  color: red;
}
```

## Combinateurs
On est vite limité par les sélecteurs simples, ces sélecteurs peuvent être combinés pour faire des
sélections plus complexes. 

Par exemple, nous souhaitons que les liens d'un menu soit d'une couleur spécifique mais pas tous
les liens d'une page. Vous pourriez attribuer une classe à chaque lien et appliquer le style sur cette
classe, mais ça signifie que si vous ajoutez un lien à votre menu, vous devrez penser à ajouter la
classe au nouveau lien. A la place, on peut spécifiquement sélectionner tous les liens au sein de
notre menu. 

Prenons la page html suivante:
```html
<nav>
  <ul>
  <li><a href="page1.html">Page 1</a></li>
    <li><a href="page2.html">Page 2</a></li>
  <li><a href="page3.html">Page 3</a></li>
  </ul>
</nav>
<p>
  Voici un <a href="autre_page.html">lien</a> vers une autre page
</p>
```
Pour modifier le style de tous mes liens se trouvant dans mon menu, donc au sein de l'élément *nav*
, on peut combiner ces éléments comme ceci:
```css
nav a {
 color: red;
}
```
Cela signifie que qu'on sélectionne tous les éléments a se trouvant dans le contenu d'un élément 
*nav*.

Il existe ainsi plusieurs combinaisons ayant des notations différentes, celle-ci se trouvant en gras
dans le tableau ci-dessous:

|Sélecteur|Description|
|-|-|
|*|Sélectionne tous les éléments|
|E, F|Sélectionne tous les éléments de type E et de type F|
|E F|**Sélectionne tous les éléments F à l’intérieur des éléments E**|
|E > F|Sélectionne les éléments F enfants directs des éléments E|
|E + F|Sélectionne tout élément F placé directement après un élément E|
|E~F|Sélectionne tout élément F placé après un élément E dans la page|

Ainsi, on peut voir que si on avait utilisé ce code, à priori similaire, cela n'aurait pas fonctionné:
```css
nav > a {
 color: red;
}
```
Cela n'aurait pas fonctionné car a n'est pas un enfant directeur de *nav*. *a* est un enfant direct de *li*, lui-même enfant direct de *ul*, lui-même enfant de *nav*.
## Formatage du texte
### Taille du texte
La taille d'un texte se défini avec la propriété **font-size**, la valeur à lui attribuer peut être
indiquée en *valeur absolue* ou en *valeur relative*. En valeur absolue, cela signifie qu'on donne
une taille fixe au texte quelle que soit la situation. Une taille relative signifie que qu'on donne une
taille qui est relative à un autre élément, cette manière est généralement recommandée car ça
offre plus de souplesse à l'utilisateur.

#### Valeur absolue
La taille absolue se définit en pixel, il s'agit donc d'un nombre entier suivi de "px". Ainsi, on pourra ainsi écrire
```css
p {
 font-size: 16px;
}
```
#### Valeur relative
La valeur relative peut être exprimée avec différentes unités et se basent sur une valeur de
référence. Chaque navigateur dispose d'une taille de référence qui peut être modifiée par
l'utilisateur, si celui-ci a besoin que son texte son plus grand. 

En utilisant une valeur relative, notre texte s'adaptera ainsi automatiquement à la modification
faite par l'utilisateur.

Pour donner une valeur relative, on va principalement retenir deux types d'unité: ***em*** et ***rem***. Ils
s'utilisent tous les deux de la même manière, ils font une multiplication de la valeur de référence.

Par exemple, si le navigateur défini la taille de référence à 20px et que cette taille n'a pas été
modifiée dans le code, 1rem défini la taille du texte sur 20px, 2rem défini la taille du texte sur 40px et 1.1rem donnera 22px.

La différence entre *em* et *rem* est que *em* fait référence à l'élément parent tandis que *rem* fait
référence à l'élément racine: html. 

Il est ainsi beaucoup plus simple de garder une bonne cohérence entre les différentes tailles de
texte en utilisant rem.
```css
html {
 font-size: 20px;
}
h1 {
 font-size: 2rem;
}
h2 {
 font-size: 1.8rem;
}
nav a {
 font-size: 0.9rem; /* Le 0 est optionnel, on peut aussi écrire .9rem */
}
```
### Polices
La police utilisée peut être sélectionnée via la propriété: **font-family**. 

Le problème principal est que pour qu'une police puisse être utilisée, l'utilisateur doit avoir la police
sur son appareil. Ainsi, on peut désigner des polices alternatives si la police souhaitée n'est pas
disponible: 
```css
p {
 font-family: Impact, "Arial Black", Arial, Verdana, sans-serif;
}
```
Cela signifie que on souhaite que la police "Impact" soit utilisée sur nos paragraphes, mais si celle-ci n'est pas disponibles, on souhaite utiliser "Arial Black", ... 

Si le nom d'une police ne possède pas d'espace, il peut être inscris tel quel, s'il possède un espace,
il faut mettre le nom entre guillemets.

La plupart du temps, des polices ne se trouvant pas de base sur tous les ordinateurs sont utilisées.
Grâce au CSS, on peut télécharger une police à la volée directement depuis notre code CSS.
Google dispose d'un site: https://fonts.google.com/

Grâce à la *règle CSS* import, on peut importer une police facilement, par exemple, j'ai sélectionné
une police sur google font, le site me donne cette instruction à ajouter au-dessus de ma page css:
```css
@import 
url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,700;1,400&disp
lay=swap');
``` 
Il s'agit de la police "Open Sans", il me suffit ensuite d'utiliser ça comme "font-family"

Pour appliquer cette police à toute ma page, il suffit d'appliquer cela à la balise html :

```css
html {
 font-family: "Open Sans", sans-serif;
}
```
### Style du texte
La propriété **font-style** permet de définir si le texte doit être en italique ou non.
```css
p {
 font-style: normal; 
 font-style: italic;
}
```
La propriété **text-decoration** est généralement utilisée pour souligner un texte, mais cette
propriété permet d'utiliser une ligne au-dessus, au travers ou sous le texte et de définir le style de cette ligne.
```css
p {
 text-decoration: underline; /* Souligne le texte */
 text-decoration: underline dotted; /* Souligne le texte en traits pointillés */
 text-decoration: underline dotted red; /* Souligne le texte en traits pointillés rouges */
 text-decoration: underline overline #FF3028; /* Souligne et surligne le texte en couleur #FF3028 */
}
```
Plutôt que mettre toutes les valeurs directement sur la propriété **text-decoration**, cela peut être
séparé en plusieurs propriétés: **text-decoration-color**, **text-decoration-style** et **text-decoration-line**
```css
p {
 text-decoration-line: underline; /* Souligne le texte */
 text-decoration-line: overline; /* Surligne le texte */
 text-decoration-line: line-through; /* Barre le texte */
 text-decoration-line: underline overline; /* Souligne et surligne le texte */
}
```
```css
p {
 text-decoration-style: solid; /* Ligne solide */
 text-decoration-style: double; /* Ligne double */
 text-decoration-style: dotted; /* Ligne pointillée */
 text-decoration-style: dashed; /* Ligne pointillée (plus large) */
 text-decoration-style: wavy; /* Ligne sous forme de vague */
}
```
```css
p {
 text-decoration-color: red; /* Ligne en rouge */
}
```

### Alignement du texte
Le texte peut être aligné avec la propriété **text-align**:
```css
p {
 text-align: left; /* Alignement à gauche */
 text-align: right; /* Alignement à droite */
 text-align: center; /* Texte centré */
 text-align: justify; /* Texte justifié */
}
```
### Couleur du texte
La couleur du texte se fait avec la propriété **color**
```css
p {
 color: red; 
}
```
## Gestion des couleurs
En CSS, on est très souvent confronté à devoir colorer un élément, que ça soit du texte, les cellules
d'un tableau, le fond d'un texte voir même le fond de la page. Pour définir une couleur, on doit
travailler au sein d'un espace de couleur, il en existe plusieurs en informatique mais le plus courant
et celui utilisé par la plupart des systèmes de notations css est l'espace de couleur sRGB. C'est un
espace qui existe depuis 1996 et qui est très majoritairement utilisé en informatique. On ne
passera pas en revue les systèmes de notations qui n'utilisent pas cet espace de couleur. 

Dans l'espace sRGB, il existe plus de 16 millions de couleurs différentes, il n'est donc pas
concevable d'avoir un nom pour chaque couleur. Il existe plusieurs systèmes de notation différents
que nous pouvons utiliser. Il est généralement très conseillé d'utiliser toujours le même système de
notation lorsqu'on développe un site ou une application web.
### Mots-clés
Le premier système de notation est par mot clé, par exemple red, blue, purple, transparent ... Ce
sont toute une série de couleur prédéfinie au sein de chaque navigateur. 
#### RGBa
RGB signifie Red Green Blue, cela signifie qu'on "mélange" ces trois couleurs primaires pour donner
une autre couleur. 

Deux notations possibles différentes dans ce système, soit une couleur définie sous format
hexadécimal (6 caractères hexadécimaux précédés d'un dièse). Les deux premiers caractères
définissent la "quantité" de rouge à mettre, les deux suivants le vert et les deux derniers le bleu. 

L'autre possibilité les notations fonctionnelles rgb() et rgba(). Dans les navigateurs modernes, ces
deux notations sont identiques. On peut donner 3 ou 4 paramètres à ces notations, les trois
couleurs et éventuellement une composante "alpha" définissant l'opacité. Les couleurs peuvent
être passées de deux manières, soit en pourcentage, soit avec une valeur située entre 0 et 255. 
L'opacité s'indique entre 0 et 1. 0 étant totalement transparent et 1 totalement opaque.
```css
p {
 color: #123FB1; /* Ecriture hexadécimale: 12 Rouges, 3F Vert, B1 Rouge */
 color: rgba(120, 255, 0); /* Ecriture rgba, quantité de couleur entre 0 et 255 */
 color: rgba(46%, 100%, 0); /* Ecriture rgba, quantité de couleur en pourcentage */
 color: rgba(46%, 100%, 0, .7); /* Parametre alpha, opacité à 0.7. */
}
```
#### HSL
La notation fonctionnelle hsl() exprime une couleur sRGB selon ses composantes de *teinte* (hue en
anglais), *saturation*, et *luminosité*. Une composante *alpha* optionnelle représente l'opacité de la
couleur.
```css
p {
 color: hsl(50 80% 40%);
}
```
## Arrière-plan
Vous pouvez définir la couleur d'arrière-plan via la propriété **background-color**.

Vous pouvez aussi utiliser une image d'arrière-plan grâce à la propriété **background-image**.
```css
p {
 background-color: red;
 background-image: url('test.jpg');
}
```
Si l'image de fond est trop petite, vous pouvez utiliser une propriété de répétition pour définir de
quelle manière l'image doit se répéter via **background-repeat**

Vous pouvez aussi définir la taille de l'image d'arrière-plan via la propriété **background-size**, c'est
cette propriété qui pourra être utilisée dans le cas où vous souhaiteriez que l'image s'adapte
automatiquement à la taille de votre élément, cela peut être très pratique dans le cas où vous
souhaitez qu'une image s'affiche correctement aussi bien sur PC que sur smartphone. 

Les exemples données ici ne sont pas exhaustifs, il s'agit simplement de donner un aperçu de ce
qui est possible de faire. 
```css
.box {
 background-repeat: no-repeat; /* Ne repete pas l'image */
 background-repeat: repeat-x; /* Repete l'image horizontalement */
 background-size: cover; /* Adapte l'image à la taille de l'élément */
}
```
## Bordures
Trois propriétés principales existent pour définir des bordures:
- **border-style** : pour définir l'apparence de la bordure ;
- **border-width** : pour définir l'épaisseur de la bordure ;
- **border-color** : pour définir la couleur de la bordure.

La position de la bordure peut être ajoutée si on souhaite en ajouter que sur 1 ou plusieurs cotés
mais pas les 4, par exemple: **border-left-style**, **border-top-color**, **border-bottom-width**, **border-right-style**
Il existe une notation appelée *shorthand* qui permet de regrouper un ou trois éléments sans devoir
définir chaque propriété une à une, il s'agit simplement de la propriété **border**, à laquelle on peut
aussi ajouter la position: par exemple **border-left**. Toutes les valeurs ne doivent pas
obligatoirement être passées, les valeurs par défaut de la propriété seront utilisées si elles ne sont
pas indiquées.

Quelques exemples:
```css
.box {
 border: 1px solid black; /* Bordure sur les quatres cotés, solide et noire */
 border-left: .2rem dashed red; /* Bordure sur la gauche de .2rem, pointillée et rouge */
}
```


### Arrondis
C'est via la propriété **border-radius** qu'il est possible de donner des coins arrondis à un élément.
L'effet est effectif sur tout l'arrière-plan de l'élément, aucune bordure n'est nécessaire. L'arrondi se
défini via une taille. 
```css
.box {
 border-radius: 2px;
}
```
Cela aura pour effet d'appliquer un arrondi de 2 pixels sur les quatre cotés.

On peut passer jusqu'à 4 valeurs différentes pour chaque coins, voici des exemples explicatifs de
l'ordre dans lequel écrire ces valeurs:
```css
.box {
 /* Arrondis sur les 4 coins */
 border-radius: 10px;

 /* haut-gauche et bas-droite | haut-droite et bas-gauche */
 border-radius: 10px 5px;

 /* haut-gauche | haut-droite et bas-gauche | bas-droite */
 border-radius: 2px 4px 2px;

 /* haut-gauche | haut-droite | bas-droite | bas-gauche */
 border-radius: 1px 0 3px 4px;
}
```
## Pseudo-classe
Une *pseudo-classe* est un mot-clé qui peut être ajouté à un sélecteur afin d'indiquer l'état
spécifique dans lequel l'élément doit être pour être ciblé par la déclaration. Il s'écrit directement à
la suite d'un sélecteur en commençait par un double-point. 
Il en existe beaucoup, on va se pencher sur quelques-unes ici, d'autres seront vues plus tard dans
les sections appropriées. 
- **:hover** : S'applique lorsque la souris survole l'élément 
- **:visited** : S'applique sur un lien lorsque celui-ci a déjà été visité
- **:link** : S'applique sur un lien lorsqu'il n'a pas encore été visité

```css
/* Au survol d'un élément a, mettre sa couleur en rouge */
a:hover {
 color: red;
}
/* Mettre en bleu la couleur des liens qui ont déjà été visités */
a:visited {
 color: blue; 
}
/* Mettre en bleu la couleur des liens qui n'ont pas encore été visités */
a:link {
 color: blue; 
}
```
# Structure d'une page
## Introduction
On a vu comment le html et le css fonctionnaient ensemble et quelques propriétés pour modifier
l'apparence d'un contenu. Nous allons maintenant avancer un peu plus pour voir comment
positionner des éléments à l'écran, comment par exemple dire qu'un menu sera sur la gauche de
l'écran et que le contenu se trouvera au centre.

## Modèles de boites
Avant toute chose, il faut comprendre comment fonctionne l'affichage d'un élément html, qu'on
appellera en css "boite". On a déjà vu qu'il existait deux types de boites: **inline** et **block**, boite en
ligne ou boite bloc. Certaines boites sont par défaut de type bloc et d'autre de type en ligne, par
exemple h1 est de type block alors que strong est de type en ligne.

Une boite bloc va fonctionner comme ceci:
- Elle occupe 100% de l'espace disponible en largeur ;
- Elle se positionne automatiquement sur une nouvelle ligne et crée un retour à la ligne
après elle ;
- Elle respecte les propriétés définissant sa hauteur (height) et sa largeur (width) ; 
- Les propriétés de marge (margin, padding et border) provoqueront un déplacement des
autres boites aux alentours.

Une boite en ligne va, à contrario, fonctionner comme ceci:
- Elle occupe uniquement l'espace nécessaire à l'affichage de son contenu ;
- Elle ne crée pas de retour à la ligne, les éléments vont donc s'afficher les uns à la suite
des autres horizontalement ;
- Elle ne prend pas en compte les propriétés définissant sa hauteur (height) et sa largeur
(width) ;
- Les propriétés de marges verticales seront prises en comptes mais n'affecteront pas les
boites aux alentours ;
- Les propriétés de marges horizontales seront prises en comptes et affecteront les boites
aux alentours.
### Marges
On peut en css appliquer des marges à un élément de trois manières différentes, la première:
**border**, a été vue au chapitre précédent. C'est considéré comme une marge car une bordure
occupe un espace à l'écran.

La seconde est **margin**, elle permet de définir une marge extérieure à notre élément. Cela permet
de mettre un espace en dehors de notre élément et d'ainsi mettre de l'espace entre plusieurs
éléments, entre un élément et le bord de page, ...

La dernière est **padding**, elle permet de définir une marge intérieure à notre élément. Cela permet
donc de ne pas coller notre contenu au bord de la boite. 

Ces deux propriétés sont des raccourcis, *shorthands*, chaque marge (gauche, droite, ...) peut être
définie individuellement via les propriétés complètes margin-left, padding-top, ...
![](https://github.com/laubuur/ifapme-html-css/blob/main/images/margin.png)

Les marges sont définies par une taille, plusieurs tailles peuvent être passées aux propriétés
raccourcies, voici des exemples explicatifs:
```css
.box {
 /* La propriété s'applique aux quatre côtés */
 margin: 1em;

 /* vertical | horizontal */
 margin: 5% auto;

 /* haut | horizontal | bas */
 margin: 1em auto 2em;

 /* haut | droit | bas | gauche */
 margin: 2px 1em 0 auto;
}
```

On peut voir dans l'exemple ci-dessus qu'en plus des unités classiques comme px ou em, on peut
voir "auto". Cela signifie que la marge va être calculée automatiquement. C'est utilisé pour center
un élément. 

Si on reprend donc ce code: 
```css
.box {
 /* vertical | horizontal */
 margin: 5% auto;
}
```

Cela signifie qu'on appliquera une marge de 5% en haut et en bas et de centrer horizontalement
l'élément. 
```
auto ne fonctionne pas pour centrer des éléments sur la hauteur. 
```

Ainsi, si l'on souhaite centrer un élément sans déclarer d'autre marge extérieure, on applique
simplement cette déclaration:
```css
/* Centrage d'un élément sur la largeur */
.box {
 margin: auto;
}
```

**padding** s'utilise de la même manière, on peut passer 1 à 4 valeurs de la même manière que
pour **margin**. 
Si on applique toutes ces propriétés à une boite en haut à gauche de l'écran, on peut remarquer
qu'elle est décalée du bord de l'écran et que le contenu à l'intérieur n'est pas directement contre la
bordure de l'élément:
![](https://github.com/laubuur/ifapme-html-css/blob/main/images/margin-ex.png)

```css
.box {
  border: 3px solid black;
  margin: 20px;
  padding: 14px;
  width: 500px;
  height: 200px;
}
```

### Modèle standard et alternatif
Ce qu'on vient de voir là est le **modèle standard**. Pour obtenir la taille réelle d'un élément, il faut
additionner la taille définie (width, height), sa marge intérieure (padding), sa marge extérieur
(margin) et sa bordure (border). 

Ainsi, dans l'exemple ci-dessus, on fera width + padding + margin + border, soit 500 + 14 + 20 +
3 = 537px pour connaitre la taille réelle de la boite. 

Cela peut vite être dérangeant et source de problème de devoir prendre en compte ces 4 éléments
pour avoir la taille réelle, c'est pourquoi un modèle alternatif a été mis en place. Il n'est
absolument pas obligatoire et chaque développeur a sa préférence. 

Le **modèle alternatif** consiste à ajouter la déclaration suivante à un élément: 
```
box-sizing: border-box
```

Cela aura pour effet d'inclure la marge intérieure (padding) et la bordure (border) à la taille de
l'élément. Ainsi, dans l'exemple ci-dessus, le padding de 14px sera toujours bien présent, mais la
largeur de 500px inclus maintenant ce padding et ne définit plus uniquement la taille de l'espace
de contenu. Ainsi, la taille réelle de l'élément sera de 500 + 14 = 514px au lieu de 537. 

![](https://github.com/laubuur/ifapme-html-css/blob/main/images/compare-models.png)

## Exercice
Utiliser tous les éléments vu jusqu'ici pour réaliser un CV.

Le nom de la personne doit être particulièrement mis en évidence, le CV doit comporter au
minimum 3 sections différentes, une section contenant les informations sur la personne, une
section sur l'expérience professionnelle de la personne et une section sur ses formations. 
Le CV doit faire maximum 1000px de large et doit être centré sur la page. 

Essayer d'utiliser une ou plusieurs couleurs pour la mise en évidence, quelques exemples dont
vous pouvez vous inspirez:

![](https://github.com/laubuur/ifapme-html-css/blob/main/images/cv1.png)

![](https://github.com/laubuur/ifapme-html-css/blob/main/images/cv2.png)

## Position
Pour déterminer le comportement d'affichage d'un élément, on a la propriété **position** de disponible, celle-ci est par défaut en *static*
```css
.boite {
  position: static;
}

```
L'élément est affiché lors du flux d'affichage normal de la page, les propriétés *top*, *left*, *bottom*, *right* n'ont aucun effet.


Il existe aussi les positions suivantes:

**relative**
Comme static, l'élément est affiché dans le flux de la page. Cependant les propriétés *top*, *left*, *bottom*, *right* permettent de décaller l'élément par rapport à sa position initiale, sans effet sur les boites aux alentours.

**absolute**
L'élément est retiré du flux de la page et ne prend aucune place à l'écran, cela signifique que les autres éléments vont se placer comme si cet élément n'existait pas. 
L'élément est positionné par rapport à son ancêtre positionné le plus proche - Par défaut, il se placera en haut à gauche de l'écran - il peut ensuite être déplacé via les propriétés *top*, *left*, *bottom*, *right*. 

**fixed**
Comme absolute, l'élément est retiré du flux et ne prend aucune place. Cependant, l'élément restera affiché à l'écran malgré le défilement de la page. C'est pratique pour afficher un menu par exemple, le menu restera alors affiché à l'écran en permanence, quelle que soit la taille de la page.

**sticky**
Fonctionnement similaire à absolute, cependant lors du défilement de la page, l'élément ne remontera pas en dehors de l'écran et restera collé au bord de l'écran. 


Pour plus de détail sur le fonctionnement exact de **position**, vous pouvez vous référer à la doc:
https://developer.mozilla.org/fr/docs/Web/CSS/position



## Flexbox - Modèle de boite flexible
Flexbox, ou le modèle de boîte flexible, est un modèle de mise en page en CSS qui permet de concevoir des structures de page flexibles et responsives. Il facilite grandement l'alignement et la distribution des éléments dans un conteneur, même lorsque leurs tailles sont inconnues ou dynamiques.
Grâce aux flexbox, on va pouvoir facilement placer les éléments où on veut sur l'écran. 

Le fonctionnement de flexbox est simple, on active une boite en mode "flex", et tous ses enfants directs auront un comportement flex. Pour activer flexbox sur une boite, il suffit de déclarer cette propriété CSS:
```css
.boite{
  display: flex;
}
```
En faisant cela, les boites "bloc" enfant seront flex, elles prendront par défaut l'espace nécessaire en largeur à son affichage et non plus 100% de l'espace disponible. Les autres boites bloc au même niveau viendront se coller à coté jusqu'à ce qu'il n'y ait plus de place à l'écran, les boites suivantes iront donc à la ligne.

Flex fonctionne par direction, on peut définir si les éléments flex se positionneront les uns à cotés des autres ou les uns en dessous des autres. Son axe principal est défini comme ceci:
```css
.boite {
  flex-direction: column; //Direction verticale
  flex-direction: row; //Direction horizontale - Par défaut
  flex-direction: column-reverse; //Vertical inversé (de bas en haut)
  flex-direction: row-reverse; //Horizontal inversé (de droite à gauche)
}
```
L'autre axe sera considéré comme axe secondaire.

On peut facilement gérer la manière dont les éléments vont se placer par rapport à l'axe principal via la propriété *justify-content*:
```css
.boite {
  justify-content: space-between; 
}
```
Voici les différentes valeurs possibles pour justify-content:
<table>
  <tr>
    <td>
      
  **flex-start** (valeur par défaut) :

- Aligne les éléments au début du conteneur 
- Dans un flex-direction "row", c'est à gauche
- Dans un flex-direction "column", c'est en haut


**flex-end** :

- Aligne les éléments à la fin du conteneur
- Dans un flex-direction "row", c'est à droite 
- Dans un flex-direction "column", c'est en bas


**Center** :

- Centre les éléments dans le conteneur
- L'espace restant est réparti équitablement de chaque côté
- Très utile pour centrer horizontalement du contenu


**space-between** :

- Distribue l'espace disponible entre les éléments
- Le premier élément est collé au début, le dernier à la fin
- L'espace restant est réparti équitablement entre les éléments
- Pas d'espace avant le premier ni après le dernier élément


**space-around** :

- Distribue l'espace autour de chaque élément
- Chaque élément a le même espace à sa gauche et à sa droite
- Les espaces entre les éléments sont deux fois plus grands que les espaces aux extrémités 
- Car chaque élément contribue à l'espace de son côté


**space-evenly** :

- Distribue l'espace de manière strictement égale
- L'espace entre chaque élément est identique
- Même espace entre les éléments qu'aux extrémités
- Plus récent que les autres valeurs, mais bien supporté</td>
<td><img src="https://github.com/laubuur/ifapme-html-css/blob/main/images/flex-justify-content.png" width="400" /></td>
  </tr>
</table>







