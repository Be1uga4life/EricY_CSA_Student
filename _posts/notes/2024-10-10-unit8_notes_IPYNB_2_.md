---
layout: post
title: Unit 8 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit8/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 8: 2D Arrays in Java

### 2D Arrays in Java

- **Array**: A data structure for storing multiple values of the same type.
- **2D Array**: An array of arrays, representing a matrix or a collection of related data organized in rows and columns.
- **Element**: A single value within an array.
- **Index**: The position of an element in an array, starting at 0 in Java.
- **Length of an Array**: The total number of elements in an array; it's a public final attribute that cannot change after creation.

##### To Initialize an Array:


```Java
int[][] 2DArrayName = new datatype[# of rows][# of columns];
```

##### To Initialize a 2D Array:


```Java
int[][] grades = {
    {90, 85, 88, 92}, 
    {75, 80, 78, 85},
    {60, 65, 70, 75}
};
```

### How to modify a 2d array


```Java
matrix[rowIndex][columnIndex] = newValue;
```
