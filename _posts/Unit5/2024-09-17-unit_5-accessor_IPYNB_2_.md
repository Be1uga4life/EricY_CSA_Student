---
layout: post
title: Accessory Methods
description: Team Teach
toc: True
permalink: access_methods
---

## What is an Accessory Method?

An accessor method, also known as getter methods allows other objects to obtain the value of instance variables or **static** variables.

## Purpose of Accessor Methods
- Allows safe access to instance variables
- Accessor Methods keep data access private and secure
- If you need to access instance variables form a different class, accessor methods are necessary

## Lets Make Our Own Accessor Methods


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
public class Main {
    public static void main(String[] args){        
        // Create minion object Kevin
        Minion kevin = new Minion(4.10,"Kevin","Sprout-Cut",2);

        // Print Kevin's properties
        System.out.println(kevin.getName());
        System.out.println(kevin.getHeight());
        System.out.println(kevin.getHair());
        System.out.println(kevin.getEyes());
    }
}

Main.main(null)
```

    Kevin
    4.1
    Sprout-Cut
    2


## Things to keep in mind when creating your Accessor Methods
- The accessor method must be public so that you can retrieve your instance variables outside of the class
- The return Type must match the type of the instance variable accessed
- The naming convention is often getNameOfVariable
- There should be **no** parameters in your getter methods

![image](https://github.com/user-attachments/assets/17c57fb1-3572-4e6d-b695-914285cc867b)


## Popcorn Hack
Gru is preparing for his big mission to steal the moon, and he needs to assign his minions various tasks based on their skills. Create a Minion class with the attributes ``name, task, and skillLevel.`` Implement some getter accessor methods, and then create a ``Minion`` object to retrieve its values.


```Java
class Minion {
    String name;
    String task;
    int skillLevel;

    public Minion(String name, String task, int skillLevel) {
        this.name = name;
        this.task = task;
        this.skillLevel = skillLevel;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getTask() {
        return task;
    }

    public void setTask(String task) {
        this.task = task;
    }

    public int getSkillLevel() {
        return skillLevel;
    }

    public void setSkillLevel(int skillLevel) {
        this.skillLevel = skillLevel;
    }
}

Minion kevin = new Minion("Kevin", "jumping", 10);
System.out.println(kevin.getName() + ", the minion tasked with " + kevin.getTask() + ", is currently level " + kevin.getSkillLevel() + ", yet he just leveled up!");
kevin.setSkillLevel(100);
System.out.println("They are now at level " + kevin.getSkillLevel());
```

    Kevin, the minion tasked with jumping, is currently level 10, yet he just leveled up!
    They are now at level 100

