---
layout: post
title: Collectables Intro
categories: ['Java Spring']
permalink: /teamTeachCollectables/intro
authors: Aashray, Nikhil
menu: nav/collectables.html
---

## Lesson: Java Collections Framework

### 1. Introduction (Aashray)

**Overview:**  
Java Collections are reusable data structures that enable developers to store, retrieve, and manipulate groups of objects efficiently. Instead of manually managing arrays (which have a fixed size and limited operations), the Collections Framework provides ready-to-use implementations (e.g., `ArrayList`, `HashSet`, `HashMap`) with useful methods such as sorting, shuffling, searching, and more. This lesson will introduce the core concepts, key terms, and practical usage with code examples and interactive exercises.

**Objectives:**  
- Understand what collections are and why we use them.  
- Learn the differences between collections and arrays.  
- Identify and describe the main types of collection interfaces (List, Set, Queue, Map) and their implementations.  
- Learn key methods and how to iterate through collections.  
- Try out simple code experiments to reinforce the hands-on concepts.

---

### 2. Key Definitions & Terminology

- **Collection:**  
  An object that groups multiple elements into a single unit. Collections can grow and shrink dynamically, and (using generics) are type-safe.

- **Framework:**  
  A set of interfaces, classes, and methods that provide standardized ways to manipulate data structures. In Java, the Collections Framework is found in the `java.util` package.

- **Generics:**  
  A language feature (added in Java 5) that allows a collection to specify the type of its elements, ensuring compile-time type safety and eliminating the need for explicit casts.

- **Interface vs. Implementation:**  
  The framework defines interfaces (e.g., `List`, `Set`, `Map`) as blueprints of what operations a collection should offer. Concrete classes (like `ArrayList`, `HashSet`, `HashMap`) implement these interfaces with specific details.

- **Iterator:**  
  An object for traversing collections one element at a time. There are standard iterators (from the `Iterator` interface) as well as list-specific iterators (`ListIterator`).

- **Fail-fast vs. Fail-safe:**  
  Iterators from most collections (like those of `ArrayList`) throw a `ConcurrentModificationException` if the collection is modified during iteration (fail-fast). Some concurrent collections (such as those in `java.util.concurrent`) allow modifications during traversal (fail-safe).

---

### 3. Why Use Collections?

**Advantages over Arrays:**
- **Dynamic sizing:** Unlike arrays, collections automatically grow or shrink to fit the number of elements.
- **Predefined methods:** Framework classes provide utility methods like `sort()`, `shuffle()`, `search()`, and many more.
- **Flexibility:** Collections support advanced operations (iterators, streams, lambda expressions) and can hold objects of any type (using generics).
- **Interoperability:** The framework is designed with standard interfaces so you can switch implementations (for example, from `ArrayList` to `LinkedList`) with minimal changes in your code.
- **Thread safety options:** Classes like `ConcurrentHashMap` and utilities (e.g., `Collections.synchronizedList()`) help when developing concurrent applications.

---

### 4. Types of Collections

Java Collections fall broadly into two categories: **Collection interfaces** and **Map interfaces**.

#### A. Collection Interfaces
These include interfaces that represent groups of objects:

1. **List**  
   - **Definition:** An ordered collection that allows duplicate elements.
   - **Common Implementations:**  
     - `ArrayList` (backed by a dynamically resized array; best for random access)  
     - `LinkedList` (a doubly linked list; best for frequent insertions/deletions)  
   - **Key Methods:** `add()`, `get()`, `set()`, `remove()`, `size()`

2. **Set**  
   - **Definition:** A collection that does not allow duplicate elements. Not inherently ordered.
   - **Common Implementations:**  
     - `HashSet` (unordered, uses hashing for fast lookup)  
     - `LinkedHashSet` (preserves insertion order)  
     - `TreeSet` (stores elements in sorted order)
   - **Key Methods:** `add()`, `contains()`, `remove()`, `size()`

3. **Queue**  
   - **Definition:** A collection used to hold multiple elements prior to processing. Typically follows FIFO (first-in-first-out).
   - **Common Implementations:**  
     - `LinkedList` (can function as a queue)  
     - `PriorityQueue` (orders elements by priority)
   - **Key Methods:** `offer()`, `poll()`, `peek()`

4. **Deque (Double-Ended Queue)**  
   - **Definition:** Supports element insertion and removal at both ends.
   - **Common Implementations:**  
     - `ArrayDeque`  
     - `LinkedList`
   - **Key Methods:** `addFirst()`, `addLast()`, `removeFirst()`, `removeLast()`

![Image](https://github.com/user-attachments/assets/72331119-b8e1-46cf-a4d4-8739528bb384)

#### B. Map Interfaces
Unlike the collection interfaces above, a **Map** stores key-value pairs. Note that Map is not a subtype of Collection.

- **Map**  
  - **Definition:** An object that maps keys to values with no duplicate keys.
  - **Common Implementations:**  
    - `HashMap` (unsorted, fast access via hashing)  
    - `LinkedHashMap` (preserves insertion order)  
    - `TreeMap` (sorted by keys)  
  - **Key Methods:** `put()`, `get()`, `remove()`, `containsKey()`, `keySet()`
