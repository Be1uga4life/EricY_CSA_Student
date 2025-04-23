---
layout: post
title: Collectables Lists
permalink: /teamTeachCollectables/lists
authors: Aashray, Nikhil
menu: nav/collectables.html
---

## Lists (Nikhil)

In Java, a **List** is an ordered collection that allows for the storage and manipulation of elements in a sequence. Unlike arrays, lists can dynamically resize themselves, accommodating additions and removals of elements without the need to specify an initial size. This flexibility makes them particularly useful for scenarios where the number of elements may change over time.

### Types of Lists in Java

The Java Collections Framework provides several implementations of the `List` interface, each tailored to specific use cases:

1. **ArrayList**: This implementation uses a dynamic array to store elements. It offers fast random access (`O(1)` time complexity for `get` operations) but may be slower for insertions and deletions, especially in the middle of the list, as elements need to be shifted. It's ideal when frequent read operations are required. 

2. **LinkedList**: Implemented as a doubly-linked list, this class excels in scenarios involving frequent insertions and deletions, particularly at the beginning or middle of the list. However, accessing elements by index is slower (`O(n)` time complexity) compared to `ArrayList`.

3. **Vector**: Similar to `ArrayList`, but with synchronized methods, making it thread-safe. Due to this synchronization, it may exhibit performance overhead in single-threaded scenarios.

4. **Stack**: A subclass of `Vector` that implements a last-in-first-out (LIFO) stack. It provides methods like `push`, `pop`, and `peek` to manipulate the stack. 

### Common Operations on Lists

Lists support a variety of operations that facilitate the manipulation and retrieval of elements:

- **Adding Elements**:
  - `add(E e)`: Appends the specified element to the end of the list.
  - `add(int index, E element)`: Inserts the specified element at the specified position in the list.

- **Removing Elements**:
  - `remove(int index)`: Removes the element at the specified position in the list.
  - `remove(Object o)`: Removes the first occurrence of the specified element from the list, if it is present.

- **Accessing Elements**:
  - `get(int index)`: Returns the element at the specified position in the list.
  - `set(int index, E element)`: Replaces the element at the specified position in the list with the specified element.

- **Querying the List**:
  - `size()`: Returns the number of elements in the list.
  - `isEmpty()`: Returns `true` if the list contains no elements.

- **Searching within the List**:
  - `indexOf(Object o)`: Returns the index of the first occurrence of the specified element in the list, or -1 if the list does not contain the element.
  - `lastIndexOf(Object o)`: Returns the index of the last occurrence of the specified element in the list, or -1 if the list does not contain the element.

- **Iteration**:
  - `iterator()`: Returns an iterator over the elements in the list in proper sequence.
  - `listIterator()`: Returns a list iterator over the elements in the list (in proper sequence).

### Example Usage

Here's an example demonstrating some of these operations using an `ArrayList`. In this example, we perform various operations such as adding, inserting, accessing, replacing, and removing elements from the list, as well as iterating over the list to print its contents.


```Java
import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        // Creating a list of strings
        List<String> fruits = new ArrayList<>();

        // Adding elements
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        // Inserting an element at a specific position
        fruits.add(1, "Blueberry"); // Inserts "Blueberry" at index 1

        // Accessing elements
        System.out.println(fruits.get(2)); // Outputs: Banana

        // Replacing an element
        fruits.set(2, "Blackberry"); // Replaces "Banana" with "Blackberry"

        // Removing elements
        fruits.remove("Apple"); // Removes "Apple"
        fruits.remove(0); // Removes the element at index 0 ("Blueberry")

        // Iterating over the list
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}

ListExample.main(null);
```

    Banana
    Blackberry
    Cherry



```Java
// ITERATION:
import java.util.List;
import java.util.Arrays;

public class ListIterationExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry");

        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}

ListIterationExample.main(null);

```

    Apple
    Banana
    Cherry


**POPCORN HACK:**

*Task:*
Create an `ArrayList` of at least 10 integers.  
1. **Sort** the list in ascending order using `Collections.sort()`.  
2. **Filter** out all the odd numbers using an enhanced for loop (or with streams if you prefer) and then print the even numbers.

**Hint (using streams in Java 8+):**

Optional:
- Display only the odd numbers instead.
- Find and print the largest even number from the filtered list.


```Java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.stream.Collectors;

public class ListExperiment {
    public static void main(String[] args) {
        // create your array list
        List<Integer> skib = new ArrayList<>();
        List<Integer> skib2 = new ArrayList<>();

        // add 10 integers
        for (int i = 0; i < 10; i++) {
            skib.add(i);
        }
        
        // sort your list
        Collections.sort(skib);

        // filter using even numbers and print
        for (int chig : skib) {
            if (chig % 2 != 0) {
                skib2.add(chig);
            }
        }

        for (int chig : skib2) {
            System.out.println(chig);
        }
    }
}

ListExperiment.main(null);
```

    1
    3
    5
    7
    9


### How Iterable Integrates with Collection

- The **Collection** interface inherits from **Iterable**, which means that all subinterfaces and classes like **List**, **Set**, and others automatically support iteration.
- By extending **Iterable**, collections provide the **iterator()** method, enabling seamless use of the enhanced for-loop (`for-each` loop).
- This design eliminates the need for manual index management, making iteration more concise and readable.
- Starting with Java 8, the **forEach** method—enabled through **Iterable**—allows collections to be iterated using lambda expressions for cleaner, functional-style code.
