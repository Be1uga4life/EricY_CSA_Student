---
layout: post
title: Collectables Summary
permalink: /teamTeachCollectables/summary
authors: Aashray, Nikhil
menu: nav/collectables.html
---

## Diagrams:

![Image](https://github.com/user-attachments/assets/a21dbb2a-1f66-44b8-bc25-f08ac0718b6f)


![Image2](https://github.com/user-attachments/assets/073aeab1-bcd4-425b-a8d7-726d92cb8912)

### Summary & Further Reading

**Recap:**
- **Core Interfaces:** Learn the fundamental differences between `List`, `Set`, `Queue`, and `Map`.
- **Implementations:** Understand which concrete class to use for your needs (e.g., `ArrayList` for random access, `LinkedList` for frequent insertions/deletions, and `HashMap` for key-value associations).
- **Usage:** Practice adding, retrieving, updating, and removing items.
- **Advanced Features:** Explore iteration (using `Iterator`/`forEach`), sorting with `Collections.sort()`, and converting between arrays and collections.
- **Interactive Exercises:** Solve the “try it yourself” mini experiments to solidify your understanding.

**Further Reading & Resources:**
- *Effective Java* by Joshua Bloch (for best practices and deeper understanding)
- Java documentation on the [Collections Framework](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html)
- Online tutorials (Tutorialspoint, CodeJava.net, SitePoint, etc.)  
- Practice problems (w3resource.com, CodingBat, HackerRank)

## Java Collections ***Homework*** (Due Wednesday After Spring Break)

### Objectives
- Practice using **List**, **Set**, and **Deque**
- Understand when and why to use each type of collection
- Apply key collection methods and iteration techniques
- Demonstrate understanding by matching the specified output

---

### Part 1: Working with Lists

**Task:**  
Create a method named `filterEvenNumbers` that takes a `List<Integer>` as input and returns a new list containing only the **even numbers** (in the same order).

**Requirements:**
- Use `ArrayList<Integer>`.
- Use methods: `add()`, `get()`, and `size()`.
- Use a traditional loop (do not use streams).

**Intended Output Example:**

If the input list is:  
`[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`

Your program should output:  
```
Input List: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Filtered Even Numbers: [2, 4, 6, 8, 10]
```

---

### Part 2: Working with Sets

**Task:**  
Create a method called `findIntersection` that accepts two `Set<String>` objects and returns a new set containing only the **common elements** (i.e., the intersection).

**Requirements:**
- Use `HashSet<String>`.
- Use methods: `contains()`, `add()`, and iterate through one of the sets.
- The resulting set should naturally have **no duplicates**.

**Intended Output Example:**

Given:  
- Set 1: `{"apple", "banana", "cherry", "date"}`
- Set 2: `{"banana", "date", "fig", "grape"}`

The program should output:  
```
Set1: [apple, banana, cherry, date]
Set2: [banana, date, fig, grape]
Intersection: [banana, date]
```

*Note:* The actual printed order might vary since `HashSet` does not guarantee order, but the contents should include exactly `banana` and `date`.

---

### Part 3: Working with Deques

**Task:**  
Simulate a line of customers using a `Deque<String>` that behaves as both a queue and a deque. Implement the following steps:

1. **Enqueue:** Add 4 customer names to the **end** of the deque.
2. **VIP Arrival:** A VIP customer arrives—add this customer to the **front** of the deque.
3. **Process Line:** Remove the customer at the **front** (simulate serving them).
4. **Inspect Line:** Display the current front and the back of the deque.
5. **Size Check:** Print the size of the deque (the number of customers still in line).

**Requirements:**
- Use `ArrayDeque<String>`.
- Utilize these methods: `addLast()`, `addFirst()`, `removeFirst()`, `peekFirst()`, `peekLast()`, and `size()`.

**Intended Output Example:**

Assume the following names for simulation:
- Start with 4 customers added to the end: `"Alice"`, `"Bob"`, `"Charlie"`, `"Diana"`.
- Then a VIP customer, `"VIP1"`, is added to the front.
- The customer at the front is then removed.

The program should output:
```
Initial line after adding 4 customers (end): [Alice, Bob, Charlie, Diana]
After VIP arrival (added at front): [VIP1, Alice, Bob, Charlie, Diana]
After serving the customer at the front (removed): [Alice, Bob, Charlie, Diana]
Current front of the line: Alice
Current back of the line: Diana
Total number of customers waiting: 4
```

*Note:* Depending on your implementation, the printed collection format might vary slightly (e.g., using brackets or different order). The key points are that duplicates aren’t allowed by sets, queues follow FIFO (unless otherwise specified), and deques support operations at both ends.

---

### Challenge Question (Bonus, +0.01 Points)

**Question:**  
You need to store a collection of student IDs where:  
- Order **does not matter**
- Duplicate IDs must be prevented
- Frequent existence checks are required

**Answer:**  
The most efficient collection to use is a **HashSet**. This is because a `HashSet` does not allow duplicate entries, does not maintain order (which is acceptable), and provides constant-time performance for adding, removing, and checking the existence of an element.

---

### Submission Guidelines

- Provide complete source code for each part.
- Ensure your code is properly formatted with comments explaining the logic.
- Make sure your program’s output matches the intended output examples.
- Submit your solution files before the deadline.

---

### Key Takeaways

- **Lists:** Maintain order and allow duplicates; use when insertion order and indexed access are important.
- **Sets:** Store unique elements; use when duplicates must be eliminated and order is not essential (or order is dictated by the set type).
- **Deques:** Enable operations at both ends, making them versatile for simulating real-world queues and stacks.
