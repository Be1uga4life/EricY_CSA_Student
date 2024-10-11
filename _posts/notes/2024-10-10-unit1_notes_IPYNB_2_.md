---
layout: post
title: Unit 1 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit1/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 1 Primitave and Reference Types: 

### What is a Primitave Type?

![sdf](https://miro.medium.com/v2/resize:fit:634/1*Uw_8QIpL7QcNpQLBz59vUw.png)

Primitave Types are the most basic data types that represent simple value (str, int, etc.)



### The 8 Primitive Data Types

1. **byte**:  
   An 8-bit signed two’s complement integer.

2. **short**:  
   A 16-bit signed two’s complement integer.

3. **int**:  
   A 32-bit signed two’s complement integer.

4. **long**:  
   A 64-bit signed two’s complement integer.

5. **float**:  
   A single-precision 32-bit IEEE 754 floating point.

6. **double**:  
   A double-precision 64-bit IEEE 754 floating point.

7. **boolean**:  
   Stores either `true` or `false`.

8. **char**:  
   Stores a single 16-bit Unicode character.


### What is a Reference Type?

A Reference Type in programming refers to data types where variables store references (or memory addresses) rather than the actual data.


```Java
String a = "skibidi";
String b = a;
b = "sigma";

// a still points to "skibidi", but b now points to "sigma"

System.out.println(a);
System.out.println(b);

```

    skibidi
    sigma

