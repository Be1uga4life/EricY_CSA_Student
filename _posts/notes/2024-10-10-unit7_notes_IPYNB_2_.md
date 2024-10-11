---
layout: post
title: Unit 7 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit7/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 7: Arraylists

### What is an ArrayList
Resizable array that allows dynamic size changes, unlike static arrays, which have a fixed size.

### Declaring ArrayLists

Usually needs to declare a type aswell. (can be voided but not recommended)


```Java
ArrayList<String> wordList = new ArrayList<String>(); // with data type
ArrayList blankList = new ArrayList(); // without data type
System.out.println(wordList);
```

    []


#### variable.get(i):

The get(int index) method retrieves the element at the specified index i in the ArrayList. This allows you to access specific elements without modifying the list.


```Java
ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Cherry");

// Retrieve the element at index 1
String fruit = fruits.get(1);
System.out.println("Element at index 1: " + fruit); // Output: Banana

```

    Element at index 1: Banana


#### variable.remove(i)

The remove(int index) method removes the element at the specified index i from the ArrayList. After removal, the subsequent elements are shifted to the left, and the size of the list is decreased by one.


```Java
ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Cherry");

// Remove the element at index 1
fruits.remove(1);
System.out.println("After removal: " + fruits); // Output: [Apple, Cherry]

```

    After removal: [Apple, Cherry]


#### variable.size()

The size() method returns the current number of elements in the ArrayList. This helps in determining how many items are present, which can be useful for iteration and checks.


```Java
ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Cherry");

// Remove the element at index 1
fruits.remove(1);
System.out.println("After removal: " + fruits); // Output: [Apple, Cherry]

```

    After removal: [Apple, Cherry]


#### swapConsecutive(ArrayList myList)

The swapConsecutive(ArrayList myList) function swaps every pair of consecutive elements in the provided ArrayList. This function is useful for reordering elements based on specific criteria.


```Java
import java.util.ArrayList;

public class ArrayListManipulation {
    public static void swapConsecutive(ArrayList<Integer> myList) {
        for (int i = 0; i < myList.size() - 1; i += 2) {
            // Swap elements at indices i and i + 1
            int temp = myList.get(i);
            myList.set(i, myList.get(i + 1));
            myList.set(i + 1, temp);
        }
    }

    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(1);
        numbers.add(2);
        numbers.add(3);
        numbers.add(4);
        numbers.add(5);

        System.out.println("Original List: " + numbers);
        swapConsecutive(numbers);
        System.out.println("List after swapping: " + numbers); // Output: [2, 1, 4, 3, 5]
    }
}

```

___

### Linear Search

Linear search is a straightforward search algorithm that checks each element in the list sequentially until the desired element is found or the end of the list is reached. It works with both sorted and unsorted arrays.


```Java
public class SearchAlgorithms {
    public static int linearSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; // Return the index if the element is found
            }
        }
        return -1; // Return -1 if the element is not found
    }

    public static void main(String[] args) {
        int[] numbers = {5, 3, 8, 4, 2};
        int target = 4;
        int result = linearSearch(numbers, target);

        if (result != -1) {
            System.out.println("Element found at index: " + result); // Output: Element found at index: 3
        } else {
            System.out.println("Element not found.");
        }
    }
}

SearchAlgorithms.main(null)

```

    Element found at index: 3


### Binary Search

Binary search is a more efficient algorithm for finding an element in a sorted array. It works by repeatedly dividing the search interval in half. If the value of the target element is less than the item in the middle of the interval, it narrows the interval to the lower half. Otherwise, it narrows it to the upper half. This process continues until the target is found or the interval is empty.


```Java
public class SearchAlgorithms {
    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (arr[mid] == target) {
                return mid; // Return the index if the element is found
            }
            if (arr[mid] < target) {
                left = mid + 1; // Narrow down to the upper half
            } else {
                right = mid - 1; // Narrow down to the lower half
            }
        }
        return -1; // Return -1 if the element is not found
    }

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9}; // Must be sorted
        int target = 6;
        int result = binarySearch(numbers, target);

        if (result != -1) {
            System.out.println("Element found at index: " + result); // Output: Element found at index: 5
        } else {
            System.out.println("Element not found.");
        }
    }
}

SearchAlgorithms.main(null)
```

    Element found at index: 5



```Java

```


```Java

```
