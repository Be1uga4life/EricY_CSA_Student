---
layout: post
title: Unit 2 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit2/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 2 Using Objects

### What is a Class?

A class in programming is like a blueprint for creating objects. It defines the properties (attributes) and behaviors (methods) that objects of that class will have.

### What is a Non-Void Method?

A non-void method is a method that returns a value when it is called. Unlike a void method, which performs an action but doesn’t return anything, a non-void method does something and sends back a result.


```Java
// Void Method
public void greet() {
    System.out.println("Hello, World!");
}

greet();
```

    Hello, World!



```Java
// Nonvoid method

public int addNumbers(int a, int b) {
    return a + b;
}

addNumbers(2,3);
```




    5



___

### What are Methods?

In Java, methods are blocks of code that perform specific tasks and can be reused throughout your program. 

___

### What is Concatentation

Concatenation allows you to add strings together.


```Java
String name1 = "Skibidi";
String name2 = "Skibidi2";

name1 += name2; 
System.out.println(name1)
```

    SkibidiSkibidi2


___

### Wrapper classes

In Java, wrapper classes are used to convert primitive data types into objects.

___

### Autoboxing

Autoboxing is the automatic conversion that the Java compiler makes from a primitive type to its corresponding wrapper class. 

### Unboxing
Unboxing is the reverse process where the Java compiler automatically converts a wrapper class back into its corresponding primitive type.


```Java
public class BoxDemo {
    public static void demo(String[] args) {
        Integer wrapped = 100;  // Autoboxing
        int unwrapped = wrapped;  // Unboxing

        System.out.println("📦wrapped = " + wrapped);
        System.out.println("unwrapped = " + unwrapped);
    }
}

BoxDemo.demo(new String[]{});
```

    📦wrapped = 100
    unwrapped = 100


___




```Java

```
