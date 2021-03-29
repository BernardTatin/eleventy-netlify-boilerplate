---
title: La typographie de ce site
metaDescription: La typographie du site
date: 2021-03-23T16:06:39.598Z
author: Bernard Tatin
summary: J'ai tenté de travailler au mieux la typographie du site. Voici comment.
tags:
- typography
- fonts
- this site
---

Sur Internet, il existe de nombreuses pages à propos de la typographie avec ce qu'il faut faire ou ne pas faire, et ce, dans toutes les langues. On trouve souvent les _N règles fondamentales de la typographie Web_. Voici les miennes que j'ai tiré de ces pages mais aussi de ce que j'ai appris bien avant le _Web_ pour la typographie de documents imprimés.

## le choix des polices de caractères

J'ai choisi explicitement deux polices, une troisième s'est immiscée implicitement avec [MathJax](https://www.mathjax.org).

Les deux polices de mon choix sont:

- [Jost](https://indestructibletype.com/Jost.html), très proche de _Futura_, me sert comme police de base (titres, texte, ...)
- [Computer Modern Typewriter](https://checkmyworking.com/cm-web-fonts/)est utilisée pour le code uniquement.

## le choix des graisses

Les designers de profession trouveront peut-être mes choix au mieux _osés_, au pire... Cela va du _Liht_ au _Black_ en passant par 3 autres graisses avec des variations de tailles, d'espacement des caractères... Peut-être est-ce trop.

Pour la graisse la plus légère, j'ai augmenté l'espacement des caractères de manière très significative.

## le temps passé...

J'ai passé énormément de temps à chercher les polices qui me convenaient, en les essayant, en modifiant leur style (graisse, italique, espacement de caractères, ...) et en regardant le résultat sur différent navigateurs.

Esr-ce du temps perdu? Au vu du résultat, je ne sais pas trop...

## la taille des polices

En ce 29 mars 2021, elle n'est pas bonne, et la lisibilité sur mobile en souffre grandement! Pourtant, elle le fut mais les diverses modifications apportées ont cassé quelque chose.

## des exemples

Voici un exemple de code:

```c

#include <stdio.h>

int main(int argn, char *argv[]) {
    for (int i=0; i<argn; i++) {
        fprintf(stdio, "argv[%d]: %s\n",
               i,
               argv[i]);
    }
    return 0;
}
```

Voici un exemple (complètement nul) de formules mathématiques:
$$
f(x) = x^2 - 1
$$
Que l'on peut factoriser en:
$$
f(x) = (x-1)(x+1)
$$
Plus généralement, on peut démontrer que:
$$
(x-\alpha^2)=(x-\alpha)(x+\alpha)
$$

Des formules _inline_ comme $a \in E$ fonctionnent aussi. Mais elles ne passent pas directement dans le blog! Avec cette notation, \\(a \in E\\), (soit `\\(a \in E\\)`), peu esthétique dans Typora, nous obtenons le résultat escompté dans le blog.

## notes

### Typora, éditeur Markdown en mode WYSIWYG

Ce fichier a été édité avec [Typora](https://typora.io/). Bien qu'il ne soit pas *Open Source*, ce logiciel est excellent pour éditer les fichiers *Markdown*.  Il est, à ma connaissance, le seul véritable éditeur _Markdown_ **WYSIWYG**. 

Il fourni d'excellent thèmes de base et il est _facile_ d'en créer de nouveaux avec des fichiers _CSS_ (Dans les documentations, c'est _toujours_ facile... Mieux vaut partir d'un thème existant!). Il permet d'exporter sous de nombreux formats dont _PDF_ et _HTML_. 

Les blocs de code et de formules mathématiques sont faciles à créer et, évidemment, très bien rendus.

### à propos de la police Jost*

Lorsque cette police est installée sur le système, son utilisation dans les feuilles de styles se fait avec un nom parfois surprenant. En effet, la variation _Book_ se nomme simplement _Jost*_ et la variation _Book Italic_ se nomme _Jost* Italic_.