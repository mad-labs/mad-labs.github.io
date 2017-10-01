---
layout: presentation
title: js for java developers
description: A js tutorial for Java developers
theme: night
transition: slide
background: /assets/images/grunge-danger_custom_2.jpg
---

## JavaScript for Java Developers
from an original post by [Vasco Ferreira C.](https://dzone.com/users/1067475/joiio.html)

This post will go over the Javascript language from the point of view of a Java developer, focusing on the differences between the two languages and the frequent pain points. We will go over the following:

* Objects Only, No Classes
* Functions are just Values
* The '**this**' Keyword
* Classic vs Prototypal Inheritance
* Constructors vs Constructor Functions
* Closures vs Lambdas
* Encapsulation and Modules
* Block Scope and Hoisting

<!-- next-slide -->

## Javascript for Java Developers
A lot of Java frontend development work is done using Java/XML based frameworks like JSF. The framework developers themselves need to know Javascript, but in principle the application developers don't.

However the reality is that
> **For doing custom component development in for example Primefaces (JSF), it's important to know Javascript and jQuery.**

The good news is that, besides a few gotchas that we will get into, Javascript is a very learneable language for a Java developer.

<!-- next-slide -->

## Objects Only - No Classes
One of the most surprising things about Javascript is that although it's an object oriented language, there are no classes (although the new [Ecmascript 6](http://wiki.ecmascript.org/doku.php?id=harmony:classes) version will have them).

<!-- vertical-slide -->

Take for example this program, that initializes an empty object and set's two properties:

```javascript
// create an empty object - no class was needed !!
var superhero = {};
superhero.name = 'Superman';  
superhero.strength = 100;
```

Javascript objects are just like a Java HashMap of related properties, where the keys are Strings only.

The following would be the 'equivalent' Java code:

```javascript
Map<String,Object> superhero = new HashMap<>();
superhero.put("name","Superman");  
superhero.put("strength", 100);
```

This means that a Javascript object is just a multi-level 'hash map' of key/value pairs, with no class definition needed.

<!-- next-slide -->

## Functions Are Just Values
Functions in Javascript are just values of type Function, it's a simple as that! Take for example:

```javascript
var flyFunction = function() {
  console.log('Flying like a bird!');
};
superhero.fly = flyFunction;
```

This creates a function (a value of type Function) and assigns it to a variable flyFunction.

<!-- vertical-slide -->

A new property named fly is then created in the superhero object, that can be invoked like this:

```javascript
// prints 'Flying like a bird!' to the console
superhero.fly();
```

Java does not have the equivalent of the Javascript Function type, but almost.

<!-- vertical-slide -->

Take for example the SuperHero class that takes a Power function:

```javascript
public interface Power {
  void use();
}

public class SuperHero {
  private Power flyPower;

  public void setFly(Power flyPower) {
    this.flyPower = flyPower;
  }
  public void fly() {
    flyPower.use();
  }
}
```

<!-- vertical-slide -->

This is how to pass SuperHero a function in Java 7

```javascript
// Java 7 equivalent
Power flyFunction = new Power() {
  @Override
  public void use() {
    System.out.println("Flying like a bird ...");
  }
};
```

<!-- vertical-slide -->

And 8:

```javascript
// Java 8 equivalent
superman.setFly(
  ()->System.out.println("Flying like a bird ...")
);
superman.fly();
```

So although a Function type does not exist in Java 8, this ends up not preventing a 'Javascript-like' functional programming style.

<!-- vertical-slide -->

But if we pass functions around, what happens to the meaning of the **this** keyword?

<!-- next-slide -->

##The '**this**' Keyword Usage

What Javascript allows to do with this is quite surprising compared to the Java world.

<!-- vertical-slide -->

Let's start with an example:

```javascript
var superman = {
  heroName: 'Superman',
  sayHello: function() {
    console.log("Hello, I'm " + this.heroName );
  }
};
superman.sayHello();
```

This program creates an object superman with two properties:
* a String: heroName
* a Function named sayHello.

Running this program outputs as expected

```javascript
Hello, I'm Superman.
```

<!-- vertical-slide -->

What if we pass the function around?

By passing around sayHello, we can easily end up in a context where there is no heroName property:

```javascript
var failThis = superman.sayHello;
failThis();
```

Running this snippet would give as output:
```javascript
Hello, I'm undefined.
```

<!-- vertical-slide -->

## Why does **this** not work anymore?

This is because the variable hello belongs to the global scope, which contains no member variable named heroName.

<!-- vertical-slide -->

To solve this: in Javascript the value of the **this** keyword is completely overridable to be anything that we want!

```javascript
// overrides 'this' with superman
hello.call(superman);
```

The snippet above would print again
```javascript
Hello, I'm Superman.
```javascript
This means that the value of **this** depends on both the context on which the function is called, and on how the function is called.

<!-- next-slide -->

##Classic vs Prototypal Inheritance

In Javascript, there is no class inheritance, instead objects can inherit directly from other objects. The way this works is that each object has an implicit property that points to a 'parent' object.

That property is called \_\_proto\_\_, and the parent object is called the object's prototype, hence the name **Prototypal** Inheritance.

<!-- vertical-slide -->

##How does prototype work?

When looking up a property, Javascript will try to find the property in the object itself. If it does not find it then it tries in it's prototype, and so on.

For example:

```javascript
var avengersHero = {
  editor: 'Marvel'
};
var ironMan = {};
ironMan.__proto__ = avengersHero;
console.log('Iron Man is copyrighted by ' + ironMan.editor);
```javascript
This snippet will output
```javascript
Iron Man is copyrighted by Marvel.
```

As we can see, although the ironMan object is empty, it's prototype does contain the property editor, which get's found.

<!-- next-slide -->

## How does this compare with Java inheritance?

Let's now say that the rights for the Avengers where bought by DC Comics:

```javascript
avengersHero.editor = 'DC Comics';  
```

If we call
```javascript
ironMan.editor
```javascript
again, we now get
```javascript
Iron Man is copyrighted by DC Comics
```

All the existing object instances with the *avengersHero* prototype now see DC Comics without having to be recreated.

This mechanism is very simple and very powerful. Anything that can be done with class inheritance can be done with prototypal inheritance.

<!-- vertical-slide -->

But what about constructors?

<!-- next-slide -->

##Constructors vs Constructor Functions

In Javascript an attempt was made to make object creation similar to languages like Java. Let's take for example:

```javascript
function SuperHero(name, strength) {  
  this.name = name;
  this.strength = strength;
}
```

Notice the capitalized *name*, indicating that it's a **constructor function**.

<!-- vertical-slide -->

Let's see how it can be used:

```javascript
var superman = new SuperHero('Superman', 100);
console.log('Hello, my name is ' + superman.name);
```

This code snippet outputs
```javascript
Hello, my name is Superman.
```

You might think that this looks just like Java, and that is exactly the point!

What this new syntax really does is to it creates a new empty object, and then calls the constructor function by forcing this to be the newly created object.

<!-- vertical-slide -->

##Why is this syntax not recommended then?

Let's say that we want to specify that all super heroes have a
*sayHello* method.

This could be done by putting the *sayHello* function in a common *prototype object*:

```javascript
function SuperHero(name, strength) {
  this.name = name;
  this.strength = strength;
}

SuperHero.prototype.sayHello = function() {
  console.log('Hello, my name is ' + this.name);
}

var superman = new SuperHero('Superman', 100);  
superman.sayHello();
```

This would output
```javascript
Hello, my name is Superman.
```

<!-- vertical-slide -->

But the syntax *SuperHero.prototype.sayHello* looks anything but Java like!

The new operator mechanism sort of half looks like Java but at the same time is completely different.

<!-- vertical-slide -->

##Is there a recommended alternative to new?
The recommended way to go is to ignore the Javascript new operator altogether and use **Object.create**:

```javascript
var superHeroPrototype = {
  sayHello: function() {
    console.log('Hello, my name is ' + this.name);
    }
};

var superman = Object.create(superHeroPrototype);  
superman.name = 'Superman';
```

<!-- vertical-slide -->

Unlike the new operator, one thing that Javascript absolutely got right where **Closures**

<!-- next-slide -->

##Closures vs Lambdas
Javascript **Closures** are not that different from Java anonymous inner classes used in a certain way. take for example the **FlyingHero** class:

```javascript
public interface FlyCommand {
  public void fly();
}

public class FlyingHero {

  private String name;

  public FlyingHero(String name) {
    this.name = name;
  }

  public void fly(FlyCommand flyCommand) {
    flyCommand.fly();
  }
}
```

<!-- vertical-slide -->

We can can pass it a fly command like this in Java 8:

```javascript
String destination = "Mars";
superMan.fly(() -> System.out.println("Flying to " +  destination ));
```javascript
The output of this snippet is
```javascript
Flying to Mars.
```

Notice that the *FlyCommand* lambda had to 'remember' the variable destination, because it needs it for executing the fly method later.

This notion of a function that remembers about variables outside it's block scope for later use is called a Closure in Javascript.

For further details, have a look at this blog post [Really Understanding Javascript Closures](http://blog.jhades.org/really-understanding-javascript-closures/).

<!-- vertical-slide -->

##What is the main difference between Lambdas and Closures?
In Javascript a closure looks like this:

```javascript
var destination = 'Mars';

var fly = function() {
  console.log('Fly to ' + destination);
}

fly();
```

The Javascript closure, unlike the Java Lambda does not have the constraint that the destination variable must be immutable (or effectively immutable since Java 8).

<!-- vertical-slide -->

This seemingly innocuous difference is actually a 'killer' feature of Javascript closures, because it allows them to be used for creating encapsulated modules.

<!-- next-slide -->

##Modules and Encapsulation
There are no classes in Javascript and no public/ private modifiers, but then again take a look at this:

```javascript
function createHero(heroName) {
  var name = heroName;
  return  {
    fly: function(destination) {
      console.log(name + ' flying to ' + destination);
    }
  };
}
```

Here a function *createHero* is being defined, which returns an object which has a function fly. The fly function 'remembers' name when needed.

<!-- vertical-slide -->

##How do Closures relate to Encapsulation?
When the createHero function returns, noone else will ever be able to directly access name, except via fly.

<!-- vertical-slide -->

Let's try this out:

```javascript
var superman = createHero('SuperMan');
superman.fly('The Moon');
```

The output of this snippet is
```javascript
SuperMan flying to The Moon.
```

But happens if we try to access name directly
```javascript
console.log('Hero name = ' + superman.name);  
```javascript
The result is
```javascript
Hero name = undefined
```

<!-- vertical-slide -->

The function createHero is said to a be a Javascript encapsulated module, with closed 'private' member variables and a 'public' interface returned as an object with functions.

<!-- next-slide -->

##Block Scope and Hoisting

Understanding block scope in Javascript is simple: there is **no block scope**!

Take a look at this example:

```javascript
function counterLoop() {
  console.log('counter before declaration = ' + i);
  for (var i = 0; i < 3 ; i++) {
    console.log('counter = ' + i);
  }
  console.log('counter after loop = ' + i);
}
counterLoop();
```

<!-- vertical-slide -->

By looking at this coming from Java, you might expect:

```javascript
error at line 3: 'variable i does not exist'
counter = 0
counter = 1
counter = 2
error at line 9: 'variable i does not exist'
```

<!-- vertical-slide -->

It turns out that only one of these three things is true, and the output is actually this:

```javascript
counter before declaration = undefined
counter = 0
counter = 1
counter = 2
counter after loop = 3
```

Because there is no block scope, the loop variable i is visible for thewhole function. This means:

line 3 sees the variable declared but not initialized
line 9 sees i after the loop has terminated

What might be the most puzzling is that line 3 actually sees the variable declared but undefined, instead of throwing i is not defined.

<!-- vertical-slide -->

This is because the Javascript interpreter first scans the function for a list of variables, and then goes back to interpret the function code lines one by one.

<!-- vertical-slide -->

The end result is that it's like the variable i was hoisted to the top, and this is what the Javascript runtime actually 'sees':

```javascript
function counterLoop() {
  var i; // i is 'seen' as if declared here!
  console.log('counter before declaration = ' + i);
  for (i = 0; i < 3 ; i++) {
    console.log('counter = ' + i);
  }
  console.log('counter after loop:  ' + i);
}
```

To prevent surprises caused by hoisting and lack of block scoping, it's a recommended practice to declare variables always at the top of functions.

<!-- vertical-slide -->

This makes hoisting explicit and visible by the developer, and helps to avoid bugs. The next version of Javascript (Ecmascript 6) [will include anew keyword 'let' to allow block scoping](http://wiki.ecmascript.org/doku.php?id=harmony:let).

<!-- next-slide -->

##Conclusion
The Javascript language shares a lot of similarities with Java, but also some huge differences. Some of the differences like inheritance and constructor functions are important, but much less than one would expect for day to day programming.

Some of these features are needed mostly by library developers, and not necessarily for day to day application programming. This is unlike some of their Java counterparts which are needed every day.

So if you are hesitant to give it a try, don't let some of these features prevent you from going further into the language.

One thing is for sure, at least some Javascript is more or less inevitable when doing Java frontend development, so it's really worth to give it a try.

<!-- next-slide -->

#THANK YOU

<!-- next-slide -->

###Credits

* email: gabriele.manfredi@hotmail.it
* skype: gabriele_manfredi
* twitter: @GabOnline
* github: Gabrox999

original post: Vasco Ferreira C.: https://dzone.com/articles/javascript-java-developers-0
