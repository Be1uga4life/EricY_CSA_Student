---
layout: post
toc: True
title: Unit 7 ArrayList P3
description: A Unit of documents that overview Array Lists in Java
authors: Drishya, Arnav, Tanuj, Jason
categories: ['AP CSA']
type: ccc
permalink: /csa/unit7-p3/unit7-4
menu: nav/CSA_Units/csa_unit7_p3.html
---

# **7.6 - ArrayLists, Sorting**

## Selection Sort. 
- The one of the easiest sorts to demonstrate. 
- The selection sort identifies either the **maximum** or **minimum** of the compared values and iterates over the structure checking if the item stored at the index matches that condition, if so, it will swap the value stroed at that index and continue. 
- This implementation uses a helper method to perform the swap operation since variables can hold **only one value at a time**!!!

### Let’s use this array as an example: **arr[] = {64, 25, 12, 22, 11}**
![picture 1 for selection sortin](https://i.ibb.co/0CLDsNx/Screenshot-2024-09-17-12-39-20.png)
![picture 2 for selection sortin](https://i.ibb.co/cLVWs6T/Screenshot-2024-09-17-12-41-30.png)
![picture 3 for selection sortin](https://i.ibb.co/T2KjMtR/Screenshot-2024-09-17-12-41-37.png)
![picture 4 for selection sortin](https://i.ibb.co/109NWPk/Screenshot-2024-09-17-12-41-42.png)
![picture 5 for selection sortin](https://i.ibb.co/h8vhKcQ/Screenshot-2024-09-17-12-41-57.png)




## **College Board Example code below...**


```Java
public class SelectionSort {
    public static void main(String[] args) {
        int[] numbers = {64, 25, 12, 22, 11};  // Example array of numbers

        // Perform selection sort
        for (int outerLoop = 0; outerLoop < numbers.length - 1; outerLoop++) {
            // Start by assuming the current item is the smallest
            int minIndex = outerLoop;

            // Check the rest of the array for anything smaller
            for (int inner = outerLoop + 1; inner < numbers.length; inner++) {
                // If you find something smaller, update the index
                if (numbers[inner] < numbers[minIndex]) {
                    minIndex = inner;
                }
            }

            // If the smallest item isn’t already in the right place, swap them
            if (minIndex != outerLoop) {
                // Swap numbers[outerLoop] and numbers[minIndex]
                int temp = numbers[outerLoop];
                numbers[outerLoop] = numbers[minIndex];
                numbers[minIndex] = temp;
            }
        }

        // Print the sorted array
        System.out.println("Sorted array:");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
    }
}

SelectionSort.main(null);

```

    Sorted array:
    11 12 22 25 64 

### How does the swapping actualy happen?
- We use swap-item mothod.

**Swap Algorithm**


```Java
private void swapItems(int firstIndex, int secondIndex, Object[] arrayOfStuff)
{
    // **thirdHand** temporarily holds the value from firstIndex so it doesn't get lost during the swap
    Object thirdHand = arrayOfStuff[firstIndex];
    
    // Move the value from secondIndex to firstIndex
    arrayOfStuff[firstIndex] = arrayOfStuff[secondIndex];
    
    // Place the value that was originally at firstIndex (stored in thirdHand) into secondIndex
    arrayOfStuff[secondIndex] = thirdHand;
}
// First you will see the three parameters as you can see below↓↓↓
// **The firstIndex** = The index of the first item to be swapped.
// **The secondIndex** = The index of the second item to be swapped.
// **arrayOfStuff** = The array where the swapping takes place.
```

## Some common questions:
### ***Can an enhanced for loop be used?***
- **Answer:** No, The Selection Sort algorithm needs to know the index of the item it is working with.
### ***How does the swap occur?***
- **Answer:** A third variable is needed to temporarily hold on to the swapped value from the array since variables can only hold one thing at a time.

<br><br><br><br>

## Inserting Sort
- The insertion sort is characterized by building a sorted structure as it proceeds. It inserts each value it finds at the appropriate location in the data structure. This is often accomplished by using a while loop as the inner loop.

![picture 1 for inserting sortin](https://media.geeksforgeeks.org/wp-content/uploads/20240802210251/Insertion-sorting.png)
- Consider an array having elements : {23, 1, 10, 5, 2}



***initial***:
- Current element is ***23***
- The first element in the array is assumed to be sorted.
- The sorted part until ***0th*** index is : ***[23]***

***First Pass***:
- Compare ***1*** with ***23*** (current element with the sorted part).
- Since ***1*** is smaller, insert ***1*** before ***23*** .
- The sorted part until ***1st*** index is: ***[1, 23]***

***Second Pass***:
- Compare ***10*** with ***1*** and ***23*** (current element with the sorted part).
- Since ***10*** is greater than ***1*** and smaller than ***23*** , insert ***10*** between ***1*** and ***23*** .
- The sorted part until ***2nd*** index is: ***[1, 10, 23]***

***Third Pass:***
- Compare ***5*** with ***1*** , ***10***, and ***23*** (current element with the sorted part).
- Since ***5*** is greater than ***1*** and smaller than ***10*** , insert ***5*** between ***1*** and ***10***
- The sorted part until ***3rd*** index is : ***[1, 5, 10, 23]***

***Fourth Pass:***
- Compare ***2*** with ***1***, ***5***, ***10*** , and ***23*** (current element with the sorted part).
- Since ***2*** is greater than ***1*** and smaller than ***5*** insert ***2*** between ***1*** and ***5*** .
- The sorted part until ***4th*** index is: ***[1, 2, 5, 10, 23]***

***Final Array:***
- The sorted array is: ***[1, 2, 5, 10, 23]***

## **College Board Example code below...**


```Java
import java.util.ArrayList;

public class InsertionSortExample {

    // Method to perform Insertion Sort on the list
    public static void insertionSort(ArrayList<Integer> randomList) {
        // Loop through each element in the list starting from the second element
        // (The first element is already considered sorted)
        for (int outer = 1; outer < randomList.size(); outer++) {
            
            // 'tested' is the current element we're trying to place in the correct position
            int tested = randomList.get(outer);
            
            // 'inner' represents the index of the last element in the sorted portion of the list
            int inner = outer - 1;

            // Move elements in the sorted part of the list to the right
            // until we find the correct position for 'tested'
            while (inner >= 0 && randomList.get(inner) > tested) {
                // Shift the element one position to the right to make space
                randomList.set(inner + 1, randomList.get(inner));
                inner--; // Move the 'inner' pointer to the left
            }

            // Place the 'tested' element in its correct position
            randomList.set(inner + 1, tested);
        }
    }

    public static void main(String[] args) {
        // Create an ArrayList to store the integers we want to sort
        ArrayList<Integer> randomList = new ArrayList<>();

        // Adding elements {23, 1, 10, 5, 2} to the list
        randomList.add(23);
        randomList.add(1);
        randomList.add(10);
        randomList.add(5);
        randomList.add(2);

        // Print the original list before sorting
        System.out.println("Original list: " + randomList);

        // Call the insertionSort method to sort the list
        insertionSort(randomList);

        // Print the sorted list after the insertion sort is completed
        System.out.println("Sorted list: " + randomList);
    }
}

InsertionSortExample.main(null);
```

    Original list: [23, 1, 10, 5, 2]
    Sorted list: [1, 2, 5, 10, 23]


### Another Example...

# 6th PopCorn - Hack

### **Problem: Sort the Ducks!**

You have a list of ducks, and each duck has a **name** and **weight**. Your task is to sort these ducks by weight in **ascending order**.

Choose **either Selection Sort or Insertion Sort** to do the sorting.

### Example:
Given this list:
- Duck A (4.5 kg)
- Duck B (2.1 kg)
- Duck C (5.0 kg)
- Duck D (1.9 kg)

After sorting, the output should be:
- Duck D (1.9 kg)
- Duck B (2.1 kg)
- Duck A (4.5 kg)
- Duck C (5.0 kg)

You can use this class for the ducks:

```java
class DebugDuck implements Comparable<DebugDuck> {
    String name;
    double weight;

    public DebugDuck(String name, double weight) {
        this.name = name;
        this.weight = weight;
    }

    @Override
    public int compareTo(DebugDuck other) {
        return Double.compare(this.weight, other.weight);
    }

    @Override
    public String toString() {
        return name + " (" + weight + " kg)";
    }
}
```

### Task:
- Implement **either** sorting algorithm to sort the ducks by weight.
- Print the sorted list.



```Java
import java.util.ArrayList;

class Duck implements Comparable<Duck> {
    String name;
    double weight;

    public Duck(String name, double weight) {
        this.name = name;
        this.weight = weight;
    }

    @Override
    public int compareTo(Duck other) {
        return Double.compare(this.weight, other.weight);
    }

    @Override
    public String toString() {
        return name + " (" + weight + " kg)";
    }
}

class Main {
    public static void main(String[] args) {
        Duck a = new Duck("Duck A", 4.5);
        Duck b = new Duck("Duck B", 2.1);
        Duck c = new Duck("Duck C", 5.0);
        Duck d = new Duck("Duck D", 1.9);

        ArrayList<Duck> ducks = new ArrayList<Duck>();
        ducks.add(a);
        ducks.add(b);
        ducks.add(c);
        ducks.add(d);
        System.out.println(ducks);
        
        ArrayList<Duck> sortedDucks = selectionSort(ducks);
        System.out.println(sortedDucks);
    }

    public static ArrayList<Duck> selectionSort(ArrayList<Duck> arr) {
        for (int i=0; i < arr.size()-1; i++) {
            int minIndex = i;

            for (int j=i+1; j < arr.size(); j++) {
                if (arr.get(j).compareTo(arr.get(minIndex)) < 0) {
                    minIndex = j;
                }
            }

            if (minIndex != i) {
                Duck temp = arr.get(i);
                arr.set(i, arr.get(minIndex));
                arr.set(minIndex, temp);
            }
        }

        return arr;

    }
}

Main.main(null);
```

    [Duck A (4.5 kg), Duck B (2.1 kg), Duck C (5.0 kg), Duck D (1.9 kg)]
    [Duck D (1.9 kg), Duck B (2.1 kg), Duck A (4.5 kg), Duck C (5.0 kg)]

