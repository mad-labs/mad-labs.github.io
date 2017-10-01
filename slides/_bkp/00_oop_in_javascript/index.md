---
layout: presentation
title: OOP in Javascript
description: Introduction to Object Oriented Programming in Javascript
theme: night
transition: slide
background: /assets/images/grunge-danger_custom_2.jpg
---

#Javascript OOP

<!-- next-slide -->

##JS: oggetti

Come dicevamo dgi oggetti in javascript sono delle mappe chiave - valore. Il valore può essere a sua volta un prmitivo o un altro oggetto:
```javascript
{
  chiave1: "stringa1",
  chiave2: 1,
  chiave3: {
    chiave1: "stringa2"
  }
}
```

<!-- vertical-slide -->

###Literal notation

La **literal notation** è un modo di definire gli oggetti dichiarandone le proprieta:

```javascript
var oggetto = {
  chiave1: "stringa1",
  chiave2: 1,
  chiave3: {
    chiave1: "stringa2"
  }
}
```

<!-- vertical-slide -->

###Costructtore Object()

Un altro modo di creare gli oggetti è utilizzare il funzione costruttore *Object()*, messa a disposizione dal linguaggio e l'operatore *new*

```javascript
var oggetto = new Object();
oggetto.chiave1 = "stringa1";
oggetto.chiave2 = 1;

var oggetto2 = new Object();
oggetto2.chiave1: "stringa2"

oggetto.chiave3 = oggetto2;
```

<!-- vertical-slide -->

###Funzioni costruttori

Oppure gli oggetti possono essere creati con apposite funzioni chiamate *costruttori*:

```javascript
function MyObject(valore1, valore2, valore3) {
  this.chiave1 = valore1;
  this.chiave2 = valore2;
  this.chiave3 = valore3;
}

var oggetto = new MyObject( "stringa1", 1, {chiave1: "stringa2" });
```

<!-- vertical-slide -->

Per accedere alle proprietà di un oggetto ci sono due modi equivaleti:

```javascript
console.log(oggetto.chiave1);
```
```output
stringa1
```
```javascript
console.log(oggetto["oggetto"]);
```
```output
stringa1
```

<!-- next-slide -->###L'ereditarietà avviene tramite *prototipi*

Ovvero oggetti che vengono usati come "modello" dalle funzioni construttori:
```javascript
function Animal(name) {
  this.name = name;
  this.move = function () {
    console.log(this.name + ' in moving');
  }
}
Animal.prototype.sleep = function () {
  console.log(this.name + ' in sleeping');
}
function Dog(name){
  Animal.call(this, name);
  this.speak = function () {
    console.log(this.name + ' barks.');
  }
}
Dog.prototype = Object.create(Animal.prototype);

var d = new Dog('Mitzie');
d.speak();
d.move();
d.sleep();
```

L'ereditarietà si concretizza perchè se una proprietà non si trova in un oggetto viene cercata nel suo prototipo.

<!-- vertical-slide -->

Dalla versione ES6 sono disponibili dei costrutti per definitre "classi":
```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(this.name + ' makes a noise.');
  }
}

class Dog extends Animal {
  speak() {
    console.log(this.name + ' barks.');
  }
}

var d = new Dog('Mitzie');
d.speak();
```

La notazione è zucchero sintattico sull'ereditarietà tramite prototipi.

<!-- next-slide -->

###Literal notation

La **literal notation** è un modo di definire gli oggetti dichiarandone le proprieta:

```javascript
var oggetto = {
  chiave1: "stringa1",
  chiave2: 1,
  chiave3: {
    chiave1: "stringa2"
  }
}
```

<!-- vertical-slide -->

###Costructtore Object()

Un altro modo di creare gli oggetti è utilizzare il funzione costruttore *Object()*, messa a disposizione dal linguaggio e l'operatore *new*

```javascript
var oggetto = new Object();
oggetto.chiave1 = "stringa1";
oggetto.chiave2 = 1;

var oggetto2 = new Object();
oggetto2.chiave1: "stringa2"

oggetto.chiave3 = oggetto2;
```

<!-- vertical-slide -->

###Funzioni costruttori

Oppure gli oggetti possono essere creati con apposite funzioni chiamate *costruttori*:

```javascript
function MyObject(valore1, valore2, valore3) {
  this.chiave1 = valore1;
  this.chiave2 = valore2;
  this.chiave3 = valore3;
}

var oggetto = new MyObject( "stringa1", 1, {chiave1: "stringa2" });
```

<!-- vertical-slide -->

Per accedere alle proprietà di un oggetto ci sono due modi equivaleti:

```javascript
console.log(oggetto.chiave1);
```
```output
stringa1
```
```javascript
console.log(oggetto["oggetto"]);
```
```output
stringa1
```

<!-- next-slide -->

#GRAZIE

<!-- next-slide -->

###Contatti

* email: gabriele.manfredi@hotmail.it
* skype: gabriele_manfredi
* twitter: @GabOnline
* github: Gabrox999
