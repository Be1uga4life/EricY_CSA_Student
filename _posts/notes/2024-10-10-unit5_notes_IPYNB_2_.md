---
layout: post
title: Unit 5 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit5/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 5

### Anatomy of a Class

Class Declaration: Starts with the class keyword, typically using access modifiers like public.


```Java
public class ExampleClass {
    // class body
}
```

Instance Variables: Attributes of the class, often private, accessible via getters and setters.


```Java
private String color;
private int num_eyes;
```

Constructors: Special methods to initialize objects. Can be default or overloaded to handle different parameters.


```Java
public Minions(String c, int n) { color = c; num_eyes = n; }
```

Methods: Define behaviors. Include accessor (getters) and mutator (setters) methods.


```Java
public String getColor() { return color; }
public void setColor(String c) { color = c; }
```

___

### Constructors

A constructor that does not take any parameters. Default Constructors initializes instance variables to default values

### Parameterized Constructor

A constructor that does not take any parameters. Default Constructors initializes instance variables to default values

___

### Accessor Methods

Accessory methods (also known as getter methods) are special methods in a class that allow you to access the values of private instance variables from outside the class.


```Java
public class Minion
{
    // Start by defining instance variables that you'll want to access later via the accessor methods
    private double height;
    private String name;
    private String hair;
    private int eyes;

    // Default Constructor
    //String n, int c
    public Minion()
    {
        height = 3.7;
        name = "Bob";
        hair = "None";
        eyes = 2;
    }

    // Overloaded Constructor
    public Minion(double h, String n, String hr, int e)
    {
        height = h;
        name = n;
        hair = hr;
        eyes = e;
    }
    // Accessor Methods!
    public double getHeight()
    {
        return height;
    }
    public String getName()
    {
        return name;
    }
    public String getHair()
    {
        return hair;
    }
    public int getEyes()
    {
        return eyes;
    }
}

// Create minion object Kevin
Minion kevin = new Minion(4.10,"Kevin","Sprout-Cut",2);

// Print Kevin's properties
System.out.println(kevin.getName());
System.out.println(kevin.getHeight());
System.out.println(kevin.getHair());
System.out.println(kevin.getEyes());
```

    Kevin
    4.1
    Sprout-Cut
    2


___

### Mutator Methods

Mutator methods (also known as setter methods) are special methods in a class that allow you to modify the values of private instance variables from outside the class.


```Java
public class Person {
    private String name;  // Private instance variable
    private int age;      // Private instance variable

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        setAge(age);  // Use mutator to set age
    }

    // Accessor Method for name
    public String getName() {
        return name;  // Returns the name
    }

    // Accessor Method for age
    public int getAge() {
        return age;   // Returns the age
    }

    // Mutator Method for age
    public void setAge(int age) {
        if (age >= 0) {
            this.age = age;  // Set age if valid
        } else {
            this.age = 0;    // Set to 0 if age is invalid
        }
    }
}

// Usage
public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);
        
        // Accessing values using accessor methods
        System.out.println("Name: " + person.getName()); // Output: Name: Alice
        System.out.println("Age: " + person.getAge());   // Output: Age: 30

        // Modifying the age using mutator method
        person.setAge(35);
        System.out.println("Updated Age: " + person.getAge()); // Output: Updated Age: 35

        // Attempting to set an invalid age
        person.setAge(-5); // This will set age to 0
        System.out.println("Age After Invalid Input: " + person.getAge()); // Output: Age After Invalid Input: 0
    }
}

Main.main(null)
```

    Name: Alice
    Age: 30
    Updated Age: 35
    Age After Invalid Input: 0

