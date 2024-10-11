---
layout: post
title: Unit 3 Notes
description: A summary of everything we did
type: collab
toc: True
permalink: notes/Unit3/
menu: nav/CSA_Units/csa_notes.html
comments: True
author: Eric Yu
---

# Unit 3 

### Boolean Expressions

- **Equal to:** `==`
- **Not equal to:** `!=`
- **Less than:** `<`
- **Greater than:** `>`
- **Less than or equal to:** `<=`
- **Greater than or equal to:** `>=`


### If conditionals in Java



```Java
if (condition) {
    // Code to execute if condition is true
} else if (anotherCondition) {
    // Code to execute if anotherCondition is true
} else {
    // Code to execute if none of the above conditions are true
}
```


```Java
// AND (both conditions must be true)
if (condition1 && condition2) {
    // Code executes if both condition1 and condition2 are true
}

// OR (either condition must be true)
if (condition1 || condition2) {
    // Code executes if either condition1 or condition2 is true
}

// NOT (negates the condition)
if (!condition) {
    // Code executes if condition is false
}

// Example with compound expression
if ((age > 18 && hasLicense) || isExperiencedDriver) {
    // Code executes if both age > 18 and hasLicense are true, 
    // OR if isExperiencedDriver is true
}
```

### Compound Boolean Operators

- **`&&` (AND):**  
  Returns true only if both conditions are true.  
  **Example:** `(condition1 && condition2)` is true if both `condition1` and `condition2` are true.

- **`||` (OR):**  
  Returns true if at least one of the conditions is true.  
  **Example:** `(condition1 || condition2)` is true if either `condition1` or `condition2` (or both) are true.

- **`!` (NOT):**  
  Negates the value of a condition; returns true if the condition is false, and vice versa.  
  **Example:** `!(condition)` is true if `condition` is false.


- **Short-Circuited Evaluation:**
  - In expressions with `&&` or `||`, evaluation stops once the result is determined by the first operand.

- **Comparing Objects in Java:**
  - `==` Operator: Compares if two references point to the same memory location.
  - `equals()` Method: Compares the actual content (values) of objects, not their references.

- **Short-Circuit Example (JavaScript):**
  - `&&`: Evaluates the first condition (`isEven`). If false, the second condition (`isPositive`) is skipped.

- **Popcorn Hack - Comparing Objects:**
  - Override the `equals()` method in custom classes to compare objects by their values, not references.

