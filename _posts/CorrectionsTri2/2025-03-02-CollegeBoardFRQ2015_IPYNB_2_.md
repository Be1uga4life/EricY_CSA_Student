---
layout: post
title: CollegeBoard FRQ Reflection
description: CollegeBoard FRQ Reflection
type: collab
toc: True
permalink: FRQ/corrections2015
comments: True
author: Eric Yu
categories: ['Collaboration']
---

### Collegeboard FRQ

# 2015 AP CSA Practice Exam FRQ - Grading & Code

## **Part (a): `arraySum`**
### **Score: 4/4 (Full Credit)**
#### **Explanation:**
- ✅ Correctly initializes `sum` to 0.
- ✅ Uses a `for` loop to iterate through the array.
- ✅ Correctly accumulates the sum of all elements.
- ✅ Returns the correct sum.

```java
public static int arraySum(int[] arr) {
    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    return sum;
}
```

## **Part (b): `rowSums`**  
**Score: 4/4 (Full Credit)**  
### **Explanation:**
✅ Creates a new array `sums` with the correct size.  
✅ Iterates through each row of the 2D array.  
✅ Calls `arraySum` correctly for each row.  
✅ Stores the computed sum in the correct index of `sums`.  
✅ Returns the expected array.  

```java
public static int[] rowSums(int[][] arr2D) {
    int[] sums = new int[arr2D.length];
    for (int i = 0; i < arr2D.length; i++) {
        sums[i] = arraySum(arr2D[i]);
    }
    return sums;
}
```

## **Part (): `isDiverse`**  
**Score: 4/4 (Full Credit)**  
### **Explanation:**
✅ Calls rowSums(arr2D) correctly.
✅ Uses nested loops to compare each pair of sums.
✅ If duplicate sums are found, returns false.
✅ If no duplicates exist, returns true.
```java
public static boolean isDiverse(int[][] arr2D) {
    int[] sums = rowSums(arr2D);
    for (int i = 0; i < sums.length; i++) {
        for (int j = i + 1; j < sums.length; j++) {
            if (sums[i] == sums[j]) {
                return false;
            }
        }
    }
    return true;
}
```

### Strengths and Weaknesses

Strengths:
- Decently good at FRQs, not too much trouble


Weaknesses
- Sometimes code can be slightly inefficient and timing may be an issue
