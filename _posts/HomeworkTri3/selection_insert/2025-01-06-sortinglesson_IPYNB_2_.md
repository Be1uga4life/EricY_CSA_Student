---
title: Sorting/Searching Algorithms - Sorting Lesson
description: A lesson on sorting algorithms for AP Computer Science students.
categories: ['Sorting/Searching Algorithms']
menu: nav/teamteaching.html
permalink: /sortingTT/sorting/
comments: True
---

# **Sorting Algorithms**

## Important Notes

### **Big O Notation**
- Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. It is used in computer science to describe the performance or complexity of an algorithm in terms of time and space. The notation provides an upper bound on the growth rate of a function, allowing for a comparison of the efficiency of different algorithms.

# **1. Selection Sort**
Selection sort is a simple sorting algorithm that works by selecting the smallest (or largest, depending on sorting order) element from the list and swapping it with the first unsorted element. The algorithm then finds the second smallest element and swaps it with the second unsorted element, and continues in this way until the entire list is sorted. It is similar to bubble sort, but it is more efficient as it reduces the number of swaps.


```Java
public class SelectionSort {
    public static void main(String[] args) {
        int[] list = {28, 12, 18, 8, 30, 3, 17, 14};
        
        System.out.println("Sorting process:");
        for (int currentIndex = 0; currentIndex < list.length - 1; currentIndex++) {
            int minIndex = currentIndex;
            
            // Find the minimum element in the unsorted part
            for (int i = currentIndex + 1; i < list.length; i++) {
                if (list[i] < list[minIndex]) {
                    minIndex = i;
                }
            }
            
            // Swap the current element with the minimum element
            int temp = list[currentIndex];
            list[currentIndex] = list[minIndex];
            list[minIndex] = temp;

            // Print the array after each swap
            printArray(list);
        }
        
        System.out.println("\nFinal sorted list:");
        printArray(list);
    }

    // Helper method to print the array
    private static void printArray(int[] array) {
        for (int num : array) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}

SelectionSort.main(new String[]{});
```

    Sorting process:
    3 12 18 8 30 28 17 14 
    3 8 18 12 30 28 17 14 
    3 8 12 18 30 28 17 14 
    3 8 12 14 30 28 17 18 
    3 8 12 14 17 28 30 18 
    3 8 12 14 17 18 30 28 
    3 8 12 14 17 18 28 30 
    
    Final sorted list:
    3 8 12 14 17 18 28 30 


# **2. Insertion Sort**

Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort. However, insertion sort provides several advantages: simple implementation, efficient for (quite) small data sets, more efficient in practice than most other simple quadratic (i.e., O(n2)) algorithms such as selection sort or bubble sort, adaptive, stable, in-place, online, and can be made stable.


```Java
public class InsertionSort {
    public static void main(String[] args) {
        int[] list = {28, 12, 18, 8, 30, 3, 17, 14};
        
        System.out.println("Sorting process:");
        
        // Insertion sort algorithm
        for (int i = 1; i < list.length; i++) {
            int currentValue = list[i];
            int j = i - 1;
            
            // Shift larger elements to the right
            while (j >= 0 && list[j] > currentValue) {
                list[j + 1] = list[j];
                j--;
            }
            
            // Place the current value in the correct position
            list[j + 1] = currentValue;
            
            // Print the list after each insertion
            for (int k = 0; k < list.length; k++) {
                System.out.print(list[k] + " ");
            }
            System.out.println();  // New line after each pass
        }

        // Final sorted list
        System.out.println("Sorted array:");
        for (int num : list) {
            System.out.print(num + " ");
        }
    }
}

InsertionSort.main(new String[]{});
```

    Sorting process:
    12 28 18 8 30 3 17 14 
    12 18 28 8 30 3 17 14 
    8 12 18 28 30 3 17 14 
    8 12 18 28 30 3 17 14 
    3 8 12 18 28 30 17 14 
    3 8 12 17 18 28 30 14 
    3 8 12 14 17 18 28 30 
    Sorted array:
    3 8 12 14 17 18 28 30 
