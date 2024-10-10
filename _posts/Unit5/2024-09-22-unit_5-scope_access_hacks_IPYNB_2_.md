---
layout: post
title: Scope and Access
description: Team Teach
toc: True
permalink: scope_access_examples
---

## Let's go through an example

Lets create a class called MinionMood. In order to ensure maximum productivity with the minions we have to keep track of how they're feeling throughout the day.

Then lets create some instance variables and a method to increase the happiness level of the minion based on how many bananas they have eaten, and make it such that the energy level of the minion decreases based on how many tasks they have to complete.


```Java
public class MinionMood
{
    private int happinessLevel;
    private int energyLevel;

    public MinionMood(int bananas, int tasks)
    {
        int happinessLevel = 2*bananas;
        int energyLevel = tasks;
    }
    public String toString()
    {
        return "Happiness Level: " + happinessLevel + "\nEnergy Level: " + energyLevel;
    }
}

MinionMood bob = new MinionMood(5, 2);
System.out.println(bob);

```

    Happiness Level: 0
    Energy Level: 0


## Popcorn Hack
- Figure out why the happiness level and the energy level is not showing up the way we want it to. First one to do so will get a high five from Trevor Huang.

**The reason is that we say "int energyLevel" and "int happinessLevel" inside the constructor, redeclaring a new variable instead of using the instance variable.**

## Oops...

Its very important to keep in mind that a local variable within a method that has the same name as an instance variable will just redeclare the variable. So, to make the code work the way we want it to, all that we have to do is get rid of the statements that redeclare the variable.s
