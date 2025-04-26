---
layout: post
title: Merge Sort Team Teach
type: issues
courses: {'csa': {'week': 8}}
comments: True
permalink: /csa/team_teach/merge_sort
---

# What is Merge Sorting?
![Image](https://github.com/user-attachments/assets/274b1e6c-1ff9-45c3-8064-1d11606e0e34)
- Highly efficient sorting algorithm that uses "**divide and conquer**" to sort a list
- Repeatedly divides sublists until the list has one element, then merges sublists to a sorted list

### Pros
1. Efficiency
- Time complexity of O(nlogn)
    - Time taken to sort data grows slowly as size of data increases, so good for large datasets
2. Stability
- **Stable sorting algorithm** - preserves the order of elements with equal values during sorting

![Image](https://github.com/user-attachments/assets/ad53eeb8-4618-49d1-ba91-e25b67dcc9c8)

# Merge Sort vs. Other Sorting Algorithms

| **Algorithm**     | **Time Complexity (Best)** | **Average Time Complexity** | **Stable?** | **Notes**                                                                 |
|-------------------|----------------------------|------------------------------|-------------|----------------------------------------------------------------------------|
| **Merge Sort**     | O(n log n)                 |    O(nlog(n))                          | ✅ Yes      | Great for linked lists & large datasets. Predictable performance.          |
| **Quick Sort**     | O(n log n)                 |   O(nlog(n))                           | ❌ No       | Very fast in practice, but not stable.                                     |
| **Bubble Sort**    | O(n)                       |     O(n²)                        | ✅ Yes      | Educational and simple, but inefficient for large datasets.                |
| **Selection Sort** | O(n²)                      |    O(n²)                          | ❌ No       | Inefficient and not stable, but easy to understand.                        |
| **Insertion Sort** | O(n)                       |     O(n²)                         | ✅ Yes      | Excellent for nearly sorted or small datasets. Often used in hybrids.      |


# Why Not Quick Sort?
![Image](https://github.com/user-attachments/assets/de84e48a-e1ed-42ca-b011-cd91c4c54170)
- Selection of pivot matters 
    - Program picks position in the unsorted array, which may not be the "middle" value
- If value is too large or too small, may become inefficient 
- Also unstable if equal values in array 
    - Order of equal values may not be preserved, increases instability 

# Merge Sort Process
Step 1: Divide the Array 
- Find the middle of the array.
- Split the array into two halves.
- Repeat this until each half has only one element (base case).
Step 2: Conquer - Sort Each Half 🎯
- Since an array with one element is already sorted, start merging.
Step 3: Merge the Halves 🏗️
- Take two sorted halves.
- Compare elements from each half and merge them into a single sorted array.
- Continue merging until the entire array is sorted.

# Odd Number Array 
![Image](https://github.com/user-attachments/assets/127d05d5-6213-4c18-8e9f-78c79e5d54fc)
- Divide into almost halves
    - Left half has extra element
- Pretend single element has partner element, conduct same process

### Popcorn Hack

 Write a Java program that merges two already sorted arrays into one sorted array without using extra sorting functions.


```java
public class imsorrythisislate {
    public static void main(String[] args) {
        int[] sorted1 = {1,2,3,4,5};
        int[] sorted2 = {6,7,8,9,10};
        ArrayList<Integer> mergeSorted = new ArrayList<>();


        for (int i = 0; i < sorted1.length; i++) {
            mergeSorted.add(sorted1[i]);
        }
        for (int i = 0; i < sorted2.length; i++) {
            mergeSorted.add(sorted2[i]);
        }

        String results = mergeSorted.toString();
        System.out.println(results);
    }
}

imsorrythisislate.main(null);
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

