---
title: Sorting/Searching Algorithms - Sorting Homework
description: A homework on sorting algorithms for AP Computer Science students.
categories: ['Sorting/Searching Algorithms']
menu: nav/teamteaching.html
permalink: /sortingTT/sorting/hw/
comments: True
---

# **Objective:**
- Insertion Sort: Sort an array in ascending order using the Insertion Sort algorithm.
- Selection Sort: Sort an array in ascending order using the Selection Sort algorithm.


```Java
import java.util.Arrays;

// Test Array
int[] supplies = {29, 10, 14, 37, 13, 18, 25, 30, 4, 9, 12, 40, 50, 23, 28};

// Insertion Sort
public static void insertionSort(int[] arr) {
    int currentMin;
    String results;
    int tempVar;
    int minIndex;
    
    for (int i = 0; i < arr.length; i++) {
        currentMin = arr[i];

        for (int c = 0; c < (arr.length - i); c++) {
            if (arr[c + i] < currentMin) {
                currentMin = arr[c + i];
                minIndex = c + i;
            }
        }

        tempVar = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = tempVar;
        
        results = Arrays.toString(arr);

        System.out.println(results);
    }

    results = Arrays.toString(arr);

    System.out.println("Insertion Sort: " + results);
}

// Selection Sort
public static void selectionSort(int[] arr) {
    // TODO: Implement Selection Sort
    // Sort the array using selection sort algorithm
    System.out.println("Selection Sort: " + results);
}

insertionSort(supplies);
// selectionSort(supplies);
```


    |           arr[i] = arr[minIndex];

    variable minIndex might not have been initialized

    

    |   public static void insertionSort(int[] arr) {

    Modifier 'static' not permitted in top-level declarations, ignored

    

