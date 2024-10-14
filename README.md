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
