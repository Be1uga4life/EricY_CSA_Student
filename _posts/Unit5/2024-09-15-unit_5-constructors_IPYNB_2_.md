---
layout: post
title: Constructors
description: Unit 5 Classes and Objects - Constructors
toc: True
permalink: /apcsa/classes/constructors/
---

<img src="https://github.com/user-attachments/assets/c53b4b5d-d58c-4e06-b6d1-09df8b7ee78a" width="500px" height="auto">

## Definition

Constructors are like methods but are called as soon as an object of a class is made. They have the same name as the class and have no return type.


```Java
public class Minion {
    Minion() {
        // constructor body
    }
}
```

## Cool example 🥶


```Java
class Minion
{
    // our name variable
    String name;

    // constructor
    Minion()
    {
        name = "Bob"; // set the name to something
    }
}
// Create minion object
Minion myMinion = new Minion();
System.out.println("Name is: " + myMinion.name);
```

    Name is: Bob


### Your turn (yes this is a popcorn hack)

- Make your own class with an integer variable
- Make a constructor for that
- Create an object and print the variable


```Java
class Monkey
{
    private int age;
    
    public Monkey(int age) {
        this.age = age;
    }

    public int getAge() {
        return this.age;
    }
}

Monkey bob = new Monkey(10);
System.out.println(bob.getAge());
```

    10


## Constructor types (wait, theres more???)

### No-Arg Constructors

A constructor with no parameters (arguments). Basically the one I just showed.

```java
Minion(/* there are no paremeters here*/) {
    name = "Bob";
}
```

You can have a private and public version.


```Java
// private no-arg constructor

class Minion
{
    // our name variable
    String name;

    // constructor
    private Minion() {
        name = "Bob"; // set the name to something
    }

    public static void main(String[] args) {
        Minion myMinion = new Minion();
    }
}

// you can't make the object out of the class like below:
// you will get an error

Minion myMinion = new Minion();
```


    |   Minion myMinion = new Minion();

    Minion() has private access in Minion

    



```Java
// public no-arg constructor

class Minion
{
    // our name variable
    String name;

    // constructor
    public Minion() {
        name = "Bob"; // set the name to something
    }
}

// i can run this outside of the class now
Minion myMinion = new Minion();
```

### Paremeterized Constructors

A constructor WITH parameters (arguments).

```java
Minion(String n) {
    name = n;
}
```

That's cool, but why use this???

Well, what if I don't want the name to be "Bob"? What if I want it to be named "mitochondria"? That's what a parameterized constructor helps with!


```Java
class Minion
{
    // our name variable
    String name;

    // constructor
    Minion(String n) {
        name = n; // set the name to something
    }
}

// demo:
Minion myMinion = new Minion("mitochondria");
System.out.println("Name is: " + myMinion.name);

Minion myOtherMinion = new Minion("Democratic Republic of Congo");
System.out.println("Name is: " + myOtherMinion.name);
```

    Name is: mitochondria
    Name is: Democratic Republic of Congo


### Default Constructors

**You can run but you can't hide (from constructors).**

If you don't specify a constructor, Java will automatically make a no-arg constructor when you execute the constructor. You can think of it like a hidden constructor.


```Java
class Minion
{
    // our name variable
    String name;

}

Minion myMinion = new Minion();
System.out.println("Name is: " + myMinion.name);

// output should be null since we didn't give a value
```

    Name is: null


### Your turn (aren't you having fun!!!)

Using the code you wrote before (you did do the previous popcorn hack... right?), complete the following
- Make a no-arg constructor
- Make a parameterized constructor
- "Make" a default constructor

Please seperate all of those three into different code cells.

Also, you don't actually have to use your previous code. I just thought it would be a good template.


```Java
class Monkey
{
    private int age;

    public Monkey() {
        this.age = 1000;
    }

    public int getAge() {
        return this.age;
    }
}

Monkey bob = new Monkey();
System.out.println(bob.getAge());
```

    1000



```Java
class Monkey
{
    private int age;
        
    public Monkey(int age) {
        this.age = age;
    }

    public int getAge() {
        return this.age;
    }
}

Monkey bob = new Monkey(10);
System.out.println(bob.getAge());
```

    10



```Java
class Monkey
{
    private int age;

    public int getAge() {
        return this.age;
    }
}

Monkey bob = new Monkey();
System.out.println(bob.getAge());
```

    0


## Notes on contructors
- Constructors are always made by default
- To make a constructor:
  - Constructor name should be same as class name
  - Constructor has no return type
- Constructor types:
  -  No-Arg Constructor - a constructor that does not accept any arguments
  -  Parameterized constructor - a constructor that accepts arguments
  -  Default Constructor - a constructor that is automatically created by the Java compiler if it is not explicitly defined.
-  Constructor cannot be `abstract`, `static`, or `final`
-  A constructor can be overloaded (see below)


```Java
// overloaded constructor
// (i put this last since it's a bit complicated)

class Minion
{
    String name;

    // no-arg constructor
    Minion() {
        this.name = "Bob";
    }

    // parameterized constructor
    // notice how it has the same name as the no-arg
    Minion(String n) {
        this.name = n;
    }

    public String getName() {
        return name;
    }

}

Minion myMinion = new Minion(); // no parameters
Minion myOtherMinion = new Minion("Kevin"); // with parameters

System.out.println(myMinion.getName());
System.out.println(myOtherMinion.getName());
```

    Bob
    Kevin


### Your turn

- Make a overloaded constructor


```Java
class Monkey
{
    private int age;
    
    public Monkey() {
        this.age = 10000;
    }

    public Monkey(int age) {
        this.age = age;
    }

    public int getAge() {
        return this.age;
    }
}

Monkey bob = new Monkey(10);
System.out.println(bob.getAge());

Monkey grandpa = new Monkey();
System.out.println(grandpa.getAge());
```

    10
    10000

