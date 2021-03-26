---
title: Currying
metaDescription: Le concept de curryfication et ce qu'il peut apporter.
date: 2021-03-14T16:16:39.598Z
author: Bernard Tatin
summary: Le concept de currification et ce qu'il peut apporter. Avec des exemples en Scheme.
tags:
- coding
- currying
- closures
- Scheme
- Functional programming
---

## Le concept
Wikipedia introduit le concept de curryfication de cette manière:

> In _mathematics_ and _computer science_, **currying** is the technique of ***converting*** a function that takes multiple arguments into a sequence of functions that each take a single argument. For example, currying a function \\(f\\) that takes three arguments creates three functions:
> $$
> x = f ( a , b , c )
> $$
> becomes:
> $$
> h = g ( a ), i = h ( b ), x = i ( c )
> $$
> or called in sequence:
> $$
> x = g ( a ) ( b ) ( c )
> $$

<cite>
    <a href="https://en.wikipedia.org/wiki/Currying">Wikipedia: Currying</a>
</cite>

## Mise en pratique
### Avec _Scheme_
Voici un exemple de code:

```scheme
#lang racket

;; function with 2 arguments
(define add (lambda (x y)
              (+ x y)))

;; currying: first fonction
(define add1 (lambda (x)
               (lambda (y)
                 (+ x y))))

;; currying: second fonction, here, identity function
(define add2 (lambda (y)
               y))

(define test (lambda (x y f f1 f2)
               (display (f x y))
               (display " =? ")
               (display ((f1 x) (f2 y)))
               (newline)))

(test 1 2 add add1 add2)
(test 2 3 add add1 add2)
(test 3 4 add add1 add2)

(define distdist (lambda(x y)
               (+ (* x x) (* y y))))

(define distdist1 (lambda(x)
                    (lambda(y)
                      (+ (* x x) y))))

(define distdist2 (lambda(x)
                    (* x x)))

(test 1 2 distdist distdist1 distdist2)
(test 2 3 distdist distdist1 distdist2)
(test 3 4 distdist distdist1 distdist2)
```

Il affiche:

```
3 =? 3
5 =? 5
7 =? 7
5 =? 5
13 =? 13
25 =? 25
```

Et maintenant ? En dehors du fait que nous utilisons des _fermetures_, qu'avons-nous réellement gagné ?
