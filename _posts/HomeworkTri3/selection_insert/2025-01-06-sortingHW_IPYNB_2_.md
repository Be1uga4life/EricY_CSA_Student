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


```java
import java.util.Arrays;

// Test Array
int[] supplies = {29, 10, 14, 37, 13, 18, 25, 30, 4, 9, 12, 40, 50, 23, 28};

// Insertion Sort
public static void insertionSort(int[] arr) {
    System.out.println("Insertion Sort:\n");

    for (int i = 1; i < arr.length; i++) {
        int key = arr[i];
        int j   = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }

        arr[j + 1] = key;
    }
    
    System.out.println("\nFinal Result: " + Arrays.toString(arr));
    System.out.println("=================================================");
}


// Selection Sort
public static void selectionSort(int[] arr) {
    int currentMin;
    String results;
    int tempVar;
    int minIndex;
    
    System.out.println("Selection Sort: ");
    for (int i = 0; i < arr.length; i++) {
        currentMin = arr[i];
        minIndex= i;

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

    System.out.println("\n Final Result: " + results);
    System.out.println("=================================================");
}

insertionSort(supplies);
selectionSort(supplies);
```

    Insertion Sort:
    
    
    Final Result: [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    =================================================
    Selection Sort: 
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    
     Final Result: [4, 9, 10, 12, 13, 14, 18, 23, 25, 28, 29, 30, 37, 40, 50]
    =================================================

