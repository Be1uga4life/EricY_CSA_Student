---
layout: post
toc: True
title: Array/Strategies
description: AP CSA FRQ Array/Arraylist Strategies
courses: {'csa': {'week': 1}}
type: ccc
categories: ['AP CSA']
menu: nav/CSA_Units/frqs/array.html
permalink: /teamteach/array/strategies
---

# Array/Arraylist Review

### Array
- fixed sized
- single *or* multidimensional

![image](https://github.com/user-attachments/assets/b4cef2ae-4185-4f82-8df1-6545c06a9734)

**How to Create Arrays:**
1. Declare

```java
int[] arr1;
int[] arr2;
```
2. Initialize

```java
//separating declare and initialize
arr1 = new int[5];
arr2 = new int[]{1,2,3};

// declare and initialize at the same time
int[] arr1 = new int[5];
int[] arr2 = {1,2,3}; // an array literal
```

3. Access using `[]`

```java
arr2[0] // accesses the first element in the array
```


### Arraylist
- resizable
- uses *methods* to access and modify elements
- typically stores objects

**How to Create Arraylists:**
1. Declare and Initialize

```java
ArrayList<String> al = new ArrayList<String>();
```

2. Basic Operations

Insertion using `add()`
```java
al.add("apple");
al.add("orange");
al.add("banana");
```
Access using `get()`
```java
al.get(0); 
```
Deletion using `remove()`
```java
al.remove("orange");
```
Update using `set()`
```java
al.set(0, "kiwi");
```

## Warmup
Write a java program to sort an Arraylist


```Java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(4);
list.add(1);
list.add(3);
list.add(2);

Collections.sort(list);
System.out.println(list);
```

    [1, 2, 3, 4]


***
***

# Checklist to Maximize Points ✅
**Before Writing Code**
- Understand the *method signature* (what the methods do, the return types, access modifier)
- Paying attention to *input type* (e.g. array vs ArrayList)

**Writing Code**
- Use loops carefully (consider *bounds*)
- Check for null/empty cases

**Before Submitting Code**
- Correct return type
- Check whether syntax is used for array/ArrayList

***
***

# Common Mistakes to Avoid ❌

### `[]` vs `get` Confusion (penalty)
[]: used to access elements in **array**

get: used to access elements in **ArrayList**


```Java
int[] arr = {1,2,3};
System.out.println(arr[0]); 

ArrayList<String> al = new ArrayList<String>();
al.add("sprite");
System.out.println(al.get(0));
```

### `.length` vs `.size()` Confusion (no penalty)

.length: property for length of a **array**
.size(): method for length of an **Arraylist**


```Java
String[] colors;
colors = new String[]{"yellow", "purple", "blue"};
System.out.println(colors.length);

ArrayList<Integer> nums = new ArrayList<Integer>();
nums.add(12);
nums.add(10); 
System.out.println(nums.size());
```

### Traversing Arrays/ArrayLists 
- Ensure bounds are correct (applying the right comparison/logic)
- Account for dynamic resizing of ArrayLists for `.add()` and `.remove()`


```Java
// starts at the last index (.size() - 1)
// ends at the first index
for (int i = temps.size() - 1; temps >= 0; i--) {
    // insert code
}
```

***
***

# Scoring Criteria 📝
<img width="557" alt="image" src="https://github.com/user-attachments/assets/e82542c0-aba5-4009-b5c2-ea741c85c4fa" />

