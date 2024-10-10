---
layout: post
toc: True
title: Unit 5 - Writing Classes P3
courses: {'csa': {'week': 6}}
type: ccc
categories: ['AP CSA']
author: Aashray, Lilian, Matthew, Tara, and Trevor
---

<img src="https://github.com/user-attachments/assets/b6e29141-321e-4ec4-a0fe-abf747eb6baa">

## What is a Method?!
> A method is a **block of code that belong to a class**, very similar to a function. 

Methods in Java can take inputs (parameters), perform actions, and return a value (or void if no value is returned).

Methods that are created by the programmer to perform tasks are called **user-defined methods**, while other methods can be built in (like System.out.println()).

## Types of methods:
There are many different types of methods in Java, but here I'll only highlight the two most common ones and the ones used by College board.

> Instance Methods: Methods that belong to an **instance** of a class
Instance methods require an object of the class to be used. They operate on objects of the class.
- Can access instance variables and other instance methods within the class
- Can access static variables and methods

> Static Methods: Methods that belong to the class itself trather than any instance of the class. Trhey are used for operations taht do not depend on instance-spefific data. 
- Can only directly access other static variables and methods.

## Here's a quick example!
- Example of an instance method: addMinion()
  - Adds a minion to the list of a villain
  - Parameters: String minon
  - Example call: gru.addMinion("Kevin")
- Second example of an instance method: Villain()
  - Changes instance data
  - Parameters: string Name, String evilPlan

- Example of a static method: getVillainCount()
  - Returns the total amount of Villain instances
  - No parameters
  - Example call: System.out.println("There are " + Villain.getVillainCount() + " villains in the world.");

## Popcorn hack:
- Add another static method to the Villain class
- Keep it minion themed and fun!


```Java
import java.util.ArrayList;
import java.util.List;

public class Villain {
    // Instance variables
    public String name;
    public String evilPlan;
    public List<String> minions;
    public static int villainCount = 0;

    // Constructor for name, plan, and minions
    public Villain(String name, String evilPlan) {
        this.name = name;
        this.evilPlan = evilPlan;
        this.minions = new ArrayList<>();
        villainCount++;
    }

    // Instance method to add a minion. LOOK HERE!!
    public void addMinion(String minion) {
        minions.add(minion);
        System.out.println(minion + " has been added to " + name + "'s army.");
    }

    // Instance method to describe the villain. 
    public void describeVillain() {
        System.out.println(name + " is planning to: " + evilPlan);
        System.out.println("They have " + minions.size() + " minions.");
    }

    // Static method to get the total count of villains
    public static int getVillainCount() {
        return villainCount;
    }

    public static String whoIsTheEnemy() {
        return "Gru";
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println("The enemy of all villains is " + Villain.whoIsTheEnemy());

        Villain.villainCount = 0;

        // Create new villains
        Villain gru = new Villain("Gru", "steal the moon!");
        Villain vector = new Villain("Vector", "take over the world with magnitude and direction!");

        System.out.println("=== Adding Minions ===");
        // Create some minions
        gru.addMinion("Kevin");
        gru.addMinion("Stuart");
        gru.addMinion("Bob");

        // Create some minions for Vector
        vector.addMinion("Henchman 1");

        System.out.println();

        // Describe the villains and their plans
        System.out.println("=== Villain Descriptions ===");
        gru.describeVillain();
        System.out.println();
        vector.describeVillain();
        System.out.println();

        // Get the total count of villains
        System.out.println("=== Total Villain Count ===");
        System.out.println("There are " + Villain.getVillainCount() + " villains in the world.");
    }
}

Main.main(null);
```

    The enemy of all villains is Gru
    === Adding Minions ===
    Kevin has been added to Gru's army.
    Stuart has been added to Gru's army.
    Bob has been added to Gru's army.
    Henchman 1 has been added to Vector's army.
    
    === Villain Descriptions ===
    Gru is planning to: steal the moon!
    They have 3 minions.
    
    Vector is planning to: take over the world with magnitude and direction!
    They have 1 minions.
    
    === Total Villain Count ===
    There are 2 villains in the world.


## Popcorn hack:
Dr. Nefario is busy assigning work for the minions, and he needs your help to organize his group. Your mission is to write and implement a Java classes for each minion which includes their name, gadgets, personality, and more. Get ready to make Dr. Nefario's life easier and keep the minions organized!


```Java
import java.util.ArrayList;
import java.util.List;

class Minion {
    private String name;
    private List<String> gadgets;
    private String personality;

    public Minion(String name, String personality) {
        this.name = name;
        this.personality = personality;
        this.gadgets = new ArrayList<>();
    }

    public void addGadget(String gadget) {
        gadgets.add(gadget);
        System.out.println(gadget + " added to " + name + "'s gadgets.");
    }

    public void showDetails() {
        System.out.println("Minion Name: " + name);
        System.out.println("Personality: " + personality);
        System.out.println("Gadgets: " + (gadgets.isEmpty() ? "No gadgets" : gadgets));
    }
}

public class Main {
    public static void main(String[] args) {
        Minion kevin = new Minion("Kevin", "Cheerful");
        Minion bob = new Minion("Bob", "Mischievous");

        kevin.addGadget("Banana Launcher");
        
        bob.addGadget("Shrink Ray");

        kevin.showDetails();
        bob.showDetails();
    }
}

Main.main(null);
```

    Banana Launcher added to Kevin's gadgets.
    Shrink Ray added to Bob's gadgets.
    Minion Name: Kevin
    Personality: Cheerful
    Gadgets: [Banana Launcher]
    Minion Name: Bob
    Personality: Mischievous
    Gadgets: [Shrink Ray]

