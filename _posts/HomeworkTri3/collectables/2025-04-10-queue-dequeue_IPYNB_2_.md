---
layout: post
title: Collectables Queues and Dequeues
permalink: /teamTeachCollectables/queue-dequeue
authors: Aashray, Nikhil
menu: nav/collectables.html
---

## Queue and De-queue (Nikhil)

### Java Queues and Deques: In-Depth Overview

#### What Is a Queue?

A **Queue** is a collection designed to hold elements prior to processing. It typically follows the **FIFO** (First-In-First-Out) principle—elements that are inserted first are the ones that are removed first. Queues are especially useful for tasks such as job scheduling, handling requests in order, or managing resources.

**Key Characteristics of a Queue:**
- **FIFO Order:** Items are processed in the order they were added.
- **No Random Access:** Unlike lists, queues do not offer methods to access elements by an index.
- **Basic Operations:** Include adding, peeking at, and removing elements.

#### What Is a Deque?

A **Deque** (double-ended queue) extends the functionality of a standard queue by allowing insertion and removal of elements at both the front and the back. This versatile data structure supports both FIFO (queue behavior) and LIFO (stack behavior) operations.

**Key Characteristics of a Deque:**
- **Double-Ended Operations:** You can add or remove elements from both ends.
- **Flexible Order:** Can be used as a regular queue (FIFO) or a stack (LIFO) based on the operations you choose.
- **No Indexed Access:** Similar to queues, deques do not support random access via indexes.

---

### Types of Queue and Deque Implementations in Java

1. **LinkedList**  
   - **Description:** Implements both the `Queue` and `Deque` interfaces.  
   - **Usage:** Suitable for basic FIFO queue operations and for scenarios that require double-ended operations.
   - **Behavior:** Maintains the order of insertion, but does not provide random access.

2. **PriorityQueue**  
   - **Description:** Implements the `Queue` interface, but orders its elements according to their natural order or a provided `Comparator`, rather than in FIFO order.
   - **Usage:** Ideal for situations where elements need to be processed based on priority (e.g., shortest job first).
   - **Limitation:** Does not support null values and the iteration order is not guaranteed to reflect the priority order.

3. **ArrayDeque**  
   - **Description:** A resizable array implementation of the `Deque` interface.
   - **Usage:** Often recommended for deque implementations because of its efficiency. It can be used to implement both stack and queue behaviors.
   - **Behavior:** Provides constant-time performance for adding and removing elements at both ends.
   - **Limitation:** Not thread-safe by default; external synchronization or concurrent alternatives are needed in multi-threaded environments.

4. **ConcurrentLinkedQueue** (and **ConcurrentLinkedDeque**)  
   - **Description:** Thread-safe implementations of the `Queue` and `Deque` interfaces found in the `java.util.concurrent` package.
   - **Usage:** Suitable when multiple threads need to access and modify the queue concurrently.
   - **Behavior:** Designed for high throughput in concurrent settings without locking the entire data structure.

---

### Common Operations on Queues and Deques

#### For a **Queue**:

- **Add Elements:**
  - `boolean offer(E e)`: Inserts the specified element into the queue, returning `false` if the queue is bounded and there is no space.
  - `boolean add(E e)`: Inserts the specified element; throws an exception if the element cannot be added.
  
- **Inspect Elements (without removal):**
  - `E peek()`: Retrieves, but does not remove, the head of the queue; returns `null` if empty.
  - `E element()`: Similar to `peek()` but throws an exception if the queue is empty.
  
- **Remove Elements:**
  - `E poll()`: Retrieves and removes the head of the queue; returns `null` if the queue is empty.
  - `E remove()`: Retrieves and removes the head; throws an exception if the queue is empty.

#### For a **Deque**:

- **Add Elements at Both Ends:**
  - `void addFirst(E e)` / `boolean offerFirst(E e)`: Inserts the specified element at the front.
  - `void addLast(E e)` / `boolean offerLast(E e)`: Inserts the specified element at the end.
  
- **Inspect Elements at Both Ends:**
  - `E peekFirst()`: Retrieves but does not remove the first element; returns `null` if empty.
  - `E peekLast()`: Retrieves but does not remove the last element; returns `null` if empty.
  
- **Remove Elements from Both Ends:**
  - `E removeFirst()`: Removes and returns the first element; throws an exception if empty.
  - `E removeLast()`: Removes and returns the last element; throws an exception if empty.
  - `E pollFirst()`: Removes and returns the first element; returns `null` if empty.
  - `E pollLast()`: Removes and returns the last element; returns `null` if empty.

---

### What You Can and Cannot Do with Queues and Deques

**You Can:**
- **Maintain Order:** Use queues for FIFO processing of elements.
- **Process by Priority:** Use `PriorityQueue` to process elements based on priority instead of insertion order.
- **Add or Remove from Both Ends:** Use deques to flexibly operate at both the beginning and the end.
- **Efficiently Manage Large Data:** Use concurrent versions for thread-safe operations in a multi-threaded environment.

**You Cannot:**
- **Randomly Access Elements:** Neither queues nor deques provide methods for accessing elements by index.
- **Assume Ordering:** With standard queues (like `PriorityQueue`), iteration order is based on priority criteria, not necessarily the order of insertion.
- **Store Nulls (in Some Implementations):** Implementations such as `PriorityQueue` do not permit null elements.

---

### Mini Example: Using ArrayDeque as a Queue and Deque

Below is a short Java program that demonstrates basic operations on an `ArrayDeque`, which implements the `Deque` interface:


```Java
import java.util.ArrayDeque;
import java.util.Deque;

public class QueueDequeExample {
    public static void main(String[] args) {
        // Create an ArrayDeque to use as a double-ended queue
        Deque<String> deque = new ArrayDeque<>();

        // Adding elements at the tail (end) - typical queue behavior (FIFO)
        deque.offer("First");
        deque.offer("Second");
        deque.offer("Third");
        System.out.println("Deque after offer operations: " + deque);

        // Peeking at the head of the queue
        String head = deque.peek();
        System.out.println("Head element (without removal): " + head);

        // Removing the head element using poll (FIFO removal)
        String removedHead = deque.poll();
        System.out.println("Removed head element: " + removedHead);
        System.out.println("Deque now: " + deque);

        // Using deque-specific methods: adding at the front
        deque.offerFirst("New First");
        System.out.println("Deque after offerFirst: " + deque);

        // Removing an element from the tail
        String removedTail = deque.pollLast();
        System.out.println("Removed tail element: " + removedTail);
        System.out.println("Final deque: " + deque);
    }
}

QueueDequeExample.main(null);
```

    Deque after offer operations: [First, Second, Third]
    Head element (without removal): First
    Removed head element: First
    Deque now: [Second, Third]
    Deque after offerFirst: [New First, Second, Third]
    Removed tail element: Third
    Final deque: [New First, Second]


_A simple demonstration of a priority queue (ordering by natural order):_


```Java
import java.util.PriorityQueue;
import java.util.Queue;

public class PriorityQueueDemo {
    public static void main(String[] args) {
        Queue<Integer> priorities = new PriorityQueue<>();
        priorities.offer(50);
        priorities.offer(10);
        priorities.offer(30);
        priorities.offer(20);
        
        System.out.println("Priority queue elements (in natural order):");
        while (!priorities.isEmpty()) {
            System.out.println(priorities.poll());
        }
    }
}

PriorityQueueDemo.main(null);
```

    Priority queue elements (in natural order):
    10
    20
    30
    50


**POPCORN HACK:**

*Task:*
Use an `ArrayDeque` to implement a basic double-ended queue (deque) where you can add or remove items from both ends.  
1. Add several strings using both `addFirst()` and `addLast()`.  
2. Then remove one element from each end and print the contents of the deque.

Optional:
- Convert the deque into a list and print it.
- Use a loop to empty the deque while printing each removed element.


```Java
import java.util.ArrayDeque;
import java.util.Deque;
import java.util.ArrayList;
import java.util.List;

public class DequeExperiment {
    public static void main(String[] args) {
        // Create the deque
        Deque<String> deque = new ArrayDeque<>();

        deque.addFirst("skib");
        deque.addLast("skib2");
        deque.addFirst("tralalero");
        deque.addLast("tralalero2");
        deque.addFirst("tralala");

        System.out.println("Deque after additions: " + deque);

        String removedFirst = deque.removeFirst();
        String removedLast = deque.removeLast();
        System.out.println("Removed from front: " + removedFirst);
        System.out.println("Removed from end: " + removedLast);
        System.out.println("Deque after removals: " + deque);

        List<String> dequeAsList = new ArrayList<>(deque);
        System.out.println("Deque as a List: " + dequeAsList);

        System.out.println("Emptying the deque:");
        while (!deque.isEmpty()) {
            System.out.println("Removed: " + deque.removeFirst());
        }

        System.out.println("Deque after emptying: " + deque);
    }
}

DequeExperiment.main(null);
```

    Deque after additions: [tralala, tralalero, skib, skib2, tralalero2]
    Removed from front: tralala
    Removed from end: tralalero2
    Deque after removals: [tralalero, skib, skib2]
    Deque as a List: [tralalero, skib, skib2]
    Emptying the deque:
    Removed: tralalero
    Removed: skib
    Removed: skib2
    Deque after emptying: []


**Takeaways:**
- **FIFO Behavior:** The initial `offer()` and `poll()` operations illustrate standard queue behavior.
- **Double-Ended Operations:** Methods like `offerFirst()` and `pollLast()` showcase deque functionality.
- **No Random Access:** Notice that no methods allow you to access elements by index.
- **Null Handling:** Be aware that some implementations (e.g., `PriorityQueue`) do not permit null values.
