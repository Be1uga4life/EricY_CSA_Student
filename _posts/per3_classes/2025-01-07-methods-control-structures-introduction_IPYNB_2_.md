---
layout: post
title: Introduction to FRQ#1
categories: ['AP CSA']
menu: nav/CSA_Units/frqs/methods_per3.html
permalink: /methods_per3/introduction
---

##### **Question #1 on Exam - Methods + Control Structures**
- Typical questions from this category require writing methods that satisfy specific requirements through the use of expressions, conditional statements, and iterative statements.
- question typically consists of **2 parts**

#### **What Is a Java Method?**
- A method in Java is a reusable block of code that performs a specific task.
- Consists of an access modifier (e.g., public or private), a return type (e.g., void if it doesn’t return a value), a method name, optional parameters enclosed in parentheses, and a method body enclosed in curly braces.

![Method](https://media.geeksforgeeks.org/wp-content/uploads/20240717150503/1.webp)


##### **Part (a):**
- this question usually requires you to write a certain method that fits the given test cases and "rules" provided by the problem 
- rules + test cases may be provided as a table or as example method calls
- a **precondition**/**postcondition** may be provided by the problem. 
- a boilerplate segment containing a method declaration is also given

##### **Common/General Penalties:**
![image.png](https://i.ibb.co/yp2Nvt3/Image-1-7-25-at-12-33-PM.jpg)

- some of the mistakes that do not have any penalties are mainly syntax + spelling issues (however, the code should be easily understood)




##### **Satisfying the Rules:**
The rules that need to be satisfied by the method typically require the use of one or more of the following categories: 
   1. **conditional statements**
   2. **iterative statements**

##### **Example of Conditional Statements:**
**Example Question:**

![Example](https://i.ibb.co/ZddYQsN/Image-1-7-25-at-2-47-PM.jpg)

**Example Answer:**

![Solution](https://i.ibb.co/bWW0x72/Image-1-8-25-at-11-52-AM.jpg)

##### **Generalizations/Reminders:**
- Points will not be given when parameters are included when they are not necessary. 
- Parameters have to be included in the method call. 
- There is a difference between the .equals method and the .compareTo method (.equals returns boolean values) while the .compareTo method returns an integer value (you will lose points if you use the return value of .compareTo as a boolean)


##### **Example of Iterative Statements:**
**Example Question:**
![Problem Example](https://i.ibb.co/QQBfX5Z/Image-1-7-25-at-2-34-PM.jpg)

**Example Answer:**

![Problem Solution](https://i.ibb.co/dQBQW3q/Image-1-7-25-at-2-36-PM.jpg)

##### **Generalizations/Reminders:**
- All possible/needed iterations need to be accounted for precisely (no overlaps).
- The '==' sign should not be used for comparison of strings; use the equals method instead.
- Result variable has to be initialized at the start of the loop. 
- Incorrect parameter types and the order of parameters in the method declaration will not be given credit.
- Be careful of the control flow of the loop. 


##### **Part (b):**
- this part is similar to part (a) and typically asks you to write a method that satisfies the given set of rules.
- it may build upon the method created in part (a) (when this is done, it allows you to assume that the method in part (a) works as intended)


##### **Additional Resources**
- [FRQ List Based on Type](https://frccompsci.weebly.com/uploads/6/0/1/9/60195103/apcsa_frq_released_questions_by_type.pdf)
