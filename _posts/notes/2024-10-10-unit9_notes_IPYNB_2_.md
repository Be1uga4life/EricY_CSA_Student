---
layout: post
title: Unit 9 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit9/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 9: Inheritance

### What is Inheritance?

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows one class (the subclass) to inherit fields and methods from another class (the superclass). This promotes code reusability and establishes a natural hierarchical relationship between classes.


```Java
public class Subclass extends Superclass {
    // Subclass-specific fields and methods
}
```

#### Superclass and Subclass:

Superclass: A general class that contains common attributes and methods shared with its subclasses (also known as a parent class).


Subclass: A class that extends the functionality of a superclass by inheriting its properties and methods while also introducing its own unique features (child class).

___

#### Polymorphism

## Polymorphism in Object-Oriented Programming (OOP)

Polymorphism is a core concept in object-oriented programming (OOP) that allows methods to perform different actions based on the object they are acting upon. It enables a single interface to represent various underlying forms (data types). 

In Java, polymorphism can be achieved through:

### 1. Method Overriding
Subclasses provide specific implementations of methods that are already defined in their superclass.

### 2. Method Overloading
Multiple methods can have the same name but different parameter lists (type, number, or both).



```Java
// Superclass
class Animal {
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

// Subclass Cat
class Cat extends Animal {
    @Override
    public void sound() {
        System.out.println("Cat meows");
    }
}

// Subclass Dog
class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

// Driver class
public class PolymorphismExample {
    public static void main(String[] args) {
        // Creating objects of subclasses
        Animal myCat = new Cat();
        Animal myDog = new Dog();
        
        // Polymorphism in action
        myCat.sound(); // Output: Cat meows
        myDog.sound(); // Output: Dog barks
    }
}

```
