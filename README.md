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

```
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

```
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

```
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

```
<body>
  <h1 class="premier_titre">Titre de premier niveau</h1>
  <p>Ceci est un paragraphe</p>
</body>
```

On peut voir dans ce code qu'un attribut class a été ajouté à la balise *h1*. On peut alors modifier le code css vu ci-dessus pour appliquer la couleur rouge à la classe *premier_titre* et plus à toutes les balises *h1*.

```
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

```
<body>
  <h1 id="premier_titre">Titre de premier niveau</h1>
  <p>Ceci est un paragraphe</p>
</body>
```
```
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