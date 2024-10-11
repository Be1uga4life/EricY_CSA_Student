---
layout: post
title: Unit 4 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit4/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 4

### While Loops

While loops continue looping until a certain condition is met


```Java
int index = 0; // iterating value
while (index < 5) { // condition, if this is false, the loop terminates
    System.out.println(index); // body code
    index++; // iterates the iterating value
}
```

    0
    1
    2
    3
    4


### For Loops

For loops keep looping until a condition returns false


```Java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

    0
    1
    2
    3
    4


### String Iteration 

Use the wordlength of the string to as the amount of loops, then loop through 


```Java
String word = "hello";
for (int i = 0; i < word.length(); i++) {
    System.out.println(word.charAt(i));
}
```

    h
    e
    l
    l
    o


### Nested Iteration

Nested iteration refers to a loop inside another loop. It's often used to process multi-dimensional data like matrices or grids.


```Java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {  // Outer loop for rows
            for (int j = 1; j <= 3; j++) {  // Inner loop for columns
                System.out.print(i * j + " ");  // Print the product of i and j
            }
            System.out.println();  // Move to the next line after each row
        }
    }
}

Main.main(null)
```

    1 2 3 
    2 4 6 
    3 6 9 

