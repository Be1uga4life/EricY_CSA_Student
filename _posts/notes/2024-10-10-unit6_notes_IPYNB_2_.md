---
layout: post
title: Unit 6 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit6/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 6 Arrays

### Key Terms

- **Array**: A data structure that holds a group of object references.
- **Element**: A single item stored inside an array.
- **Element Index**: The location of an element in the array (starts at index 0).
- **Array Length**: Number of elements in the array.


### Enchanced For Loop

The enhanced for loop, also known as the "for-each" loop, is a simplified way to iterate over elements in array. However you cannot modify the elements in the array


```Java
public class EnhancedForLoopExample {
    public static void main(String[] args) {
        // Declare and initialize an array of integers
        int[] numbers = {10, 20, 30, 40, 50};

        // Using enhanced for loop to iterate through the array
        for (int number : numbers) {
            System.out.println("Number: " + number);
        }
    }
}

EnhancedForLoopExample.main(null)
```

    Number: 10
    Number: 20
    Number: 30
    Number: 40
    Number: 50


___
