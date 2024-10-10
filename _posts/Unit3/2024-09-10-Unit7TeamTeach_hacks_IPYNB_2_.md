---
layout: post
toc: True
title: Unit 7 ArrayList P3
description: A Unit of documents that overview Array Lists in Java
authors: Drishya, Arnav, Tanuj, Jason
categories: ['AP CSA']
type: ccc
permalink: /csa/unit7-p3/unit7-6
menu: nav/CSA_Units/csa_unit7_p3.html
---

## **ArrayList Coding Activity**

### **Objective:**
Students will create, manipulate, and sort an `ArrayList` of integers.

### **Activity Outline:**

1. **Create an ArrayList:**
   - **Task:** Create an `ArrayList` of integers and add 5 elements of your choice.
   - **Hint:** Use the `ArrayList` class and the `.add()` method to add elements.

2. **Modify an Element:**
   - **Task:** Change the second element (index 1) of the `ArrayList` to a new value (e.g., 100).
   - **Hint:** The `.set()` method allows you to update an element at a specific index.

3. **Remove an Element:**
   - **Task:** Remove the third element (index 2) from the `ArrayList`.
   - **Hint:** Use the `.remove()` method to delete an element by its index.

4. **Search for an Element:**
   - **Task:** Check if a specific number (e.g., 30) is in the `ArrayList` and print a message based on whether it is found or not.
   - **Hint:** The `.contains()` method can be used to check for the presence of an element.

5. **Loop Through the ArrayList:**
   - **Task:** Use a `for` loop to print each element of the `ArrayList`.
   - **Hint:** You can use a traditional `for` loop or an enhanced `for` loop (`for-each`) to iterate through the elements.

6. **Sort the ArrayList:**
   - **Task:** Sort the `ArrayList` in ascending order.
   - **Hint:** Use `Collections.sort()` to sort the `ArrayList`.

7. **Print the Sorted ArrayList:**
   - **Task:** Print the sorted `ArrayList` to see the updated order of the elements.
   - **Hint:** Use `System.out.println()` to print the sorted list.



```Java
import java.util.ArrayList;
import java.util.Collections;

public class HackYum {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(20);
        numbers.add(10);
        numbers.add(40);
        numbers.add(30);
        numbers.add(50);
        
        System.out.println("Original ArrayList: " + numbers);

        numbers.set(1, 45678);
        System.out.println("After modifying second element: " + numbers);

        numbers.remove(2);
        System.out.println("After removing the third element: " + numbers);

        int searchValue = 30;
        if (numbers.contains(searchValue)) {
            System.out.println(searchValue + " is in the ArrayList.");
        } else {
            System.out.println(searchValue + " is not in the ArrayList.");
        }

        System.out.println("Looping through the ArrayList:");
        for (int number : numbers) {
            System.out.println(number);
        }

        Collections.sort(numbers);
        System.out.println("Sorted ArrayList: " + numbers);
    }
}

HackYum.main(null);
```

    Original ArrayList: [20, 10, 40, 30, 50]
    After modifying second element: [20, 45678, 40, 30, 50]
    After removing the third element: [20, 45678, 30, 50]
    30 is in the ArrayList.
    Looping through the ArrayList:
    20
    45678
    30
    50
    Sorted ArrayList: [20, 30, 50, 45678]

