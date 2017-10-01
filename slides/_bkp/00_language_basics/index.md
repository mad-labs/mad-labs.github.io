---
layout: presentation
title: Javascript language basics
description: A basic javascript tutorial
theme: night
transition: slide
background: /assets/images/grunge-danger_custom_2.jpg
---

#Introduzione a Javascript

<!-- next-slide -->

##Un po' di storia

Originariamente sviluppato alla Netscape Communications con il nome di Mochan e successivamente di LiveScript, ma in seguito è stato rinominato "JavaScript".

JavaScript è stato standardizzato per la prima volta tra il 1997 e il 1999 dalla ECMA con il nome ECMAScript.

L'ultimo standard, di giugno 2015, è ECMA-262 Edition 6.
[fonte](https://it.wikipedia.org/wiki/JavaScript)

<!-- next-slide -->

###Le caratteristiche principali di JavaScript

* è un linguaggio interpretato
* la sintassi è C-like
* è debolmente tipizzato
* è debolmente orientato agli oggetti

<!-- vertical-slide -->

###E' un linguaggio interpretato

Il Javascript è un linguaggio inerpretato. Ovvero esiste un programma che dato un listato Javascritpt lo *legge ed esegue riga per riga* il suo contenuto.

La differenza con un linguaggio compilato è che non esiste la traduzione del listato da linguaggio di alto livello a linguaggio macchina (o intermedio).

Questo implica *nessun controllo formale* ed errori di sintassi vengono alla luce solo a runtime

<!-- vertical-slide -->

###La sintassi è C-like

La sintassi C-like è una sintatssi che utilizza le stesse strutture sintattiche del C e del C++:
```c
#include <stdio.h>

main( )
{
  printf("hello, world\n");
}
```

Altri esempi di linguaggi con sintassi C-like sono:

il Java:
```Java
class HelloWorld {
  static public void main( String args[] ) {
    System.out.println( "Hello World!" );
  }
}
```

o il C#:
```csharp
class HelloWorld
{
    static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

<!-- vertical-slide -->

###E' debolmente tipizzato

Le variabili sono in genere *tipizzate dinamicamente*. Ovvero sono definite semplicemente assegnando loro un valore e *assumo così il loro tipo*.

Successivamente, assegnado un altro valore alla variabile, essa assume un nuovo tipo: quello del valore appena assegnato.

ESEMPIO
```javascript
var variabile = "UNA STRINGA";
console.log("tipo di variabile: " + typeof variabile)
```
```output
tipo di variabile: string
```
Cambiando il valore della variabile, cambia anche il tipo:

```javascript
variabile = 1;
console.log("tipo di variabile: " + typeof variabile)
```
```output
tipo di variabile: number
```

<!-- vertical-slide -->

###E' debolmente orientato agli oggetti

In javascript tutto è un oggetto o un tipo primitivo. Gli oggetti in javascript sono delle mappe chiave - valore. Il valore può essere a sua volta un primitivo o un altro oggetto:
```javascript
{
  chiave1: "stringa1",
  chiave2: 1,
  chiave3: {
    chiave1: "stringa2"
  }
}
```

<!-- next-slide -->

##JS: variabili

Per definire una variabile si utilizza la parola chiave **var**;
```javascript
var variabile = 1;
```

Le variabili definite con questa parola sono visibili solo all'interno dello scope nel quale vengono dichiarate:
```javascript
var variabile1 = 1;
console.log(variabile1);
```
```output
1
```
```javascript
function funzione1(){
  var variabile2 = 2;
}
funzione();
console.log(variabile2)
```
```output
Uncaught ReferenceError: variabile2 is not defined(…)
```

<!-- vertical-slide -->

Purtroppo la parola chiave **var** non è obbligatoria, omettendona si creano degli effetti collaterali:
```javascript
function funzione2(){
 variabile4 = 2;
}

funzione2();

console.log(variabile4)
```
```output
2
```

<!-- vertical-slide -->

In javascript ES6 esistono altre due parole chiave per definire le variabili:

**let**: definisce una variabile con block-level scope:
```javascript
{
  let name = "Simon";
}
console.log(name);
```
```output
Uncaught ReferenceError: name is not defined(…)
```

**const**: definisce una costante
```javascript
const Pi = 3.14;
const Pi = 1;
```
```output
TypeError: Identifier 'Pi' has already been declared
```

<!-- next-slide -->

##JS: tipi

I tipi del javascript sono

* Number
* String
* Boolean
* Object
  * Function
  * Array
  * Date
  * RegExp
* Symbol (new in Edition 6)
* null
* undefined

<!-- vertical-slide -->

##Number

<!-- vertical-slide -->

##String

<!-- vertical-slide -->

##Boolean

<!-- vertical-slide -->

##Object

<!-- vertical-slide -->

##Function

<!-- vertical-slide -->

##Array

<!-- vertical-slide -->

##Date

<!-- vertical-slide -->

##RegExp

<!-- vertical-slide -->

##Symbol (new in Edition 6)

<!-- vertical-slide -->

##null & undefined

<!-- next-slide -->

##JS: Operatori

I tipi del javascript sono

<!-- next-slide -->

##JS: Strutture condizionali

<!-- vertical-slide -->

##JS: Cicli

<!-- next-slide -->

##JS: Funzioni

<!-- next-slide -->

##JS: Eventi

<!-- next-slide -->

#GRAZIE

<!-- next-slide -->

###Contatti

* email: gabriele.manfredi@hotmail.it
* skype: gabriele_manfredi
* twitter: @GabOnline
* github: Gabrox999
