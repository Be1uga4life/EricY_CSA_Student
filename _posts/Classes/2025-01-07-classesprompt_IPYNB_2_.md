---
layout: post
title: Classes
description: Team Teach for Classes
permalink: /classeshw
comments: True
menu: nav/FRQ_teach/classesperiod3.html
sticky_rank: 1
toc: False
---

# Conclusion   (Jason)

The **"Classes"** section gives a simple guide to handling Classes FRQs in APCSA. It explains key ideas like writing class headers, constructors, and methods, and keeping instance variables private. Following these steps makes your code organized and clear, which helps earn points on the exam.

### Tips  
1. **Follow Instructions**: Always match class headers, constructors, and method details to what’s asked in the question.  

2. **Keep it Simple**: Use `this.variable = parameter;` to set instance variables in constructors.  

3. **Check Scoping**: Class and method headers should usually be `public`, and instance variables should always be `private`.  


# **Homework!** (Jason)
### 2017 FRQ, Question 2 - Classes

#### [**Homework over here...**](https://docs.google.com/forms/d/e/1FAIpQLSfh9si2edbWDec6buhsbuA_oiq-rA2lMeY582N4i8nAxtmBoQ/viewform?usp=sf_link)

![2017 FRQ, Question 2, Classes](https://i.ibb.co/VJc29TM/Screenshot-2025-01-07-at-12-39-08-PM.png)

![Example 1](https://i.ibb.co/NpF8v72/Screenshot-2025-01-07-at-12-43-04-PM.png)

![Example 2](https://i.ibb.co/pW4jVSX/Screenshot-2025-01-07-at-12-43-20-PM.png)

![Final](https://i.ibb.co/vYTv7cX/Screenshot-2025-01-07-at-12-44-12-PM.png)



```python
public class MultPractice implements StudyPractice {
    private int first; // first idle number for the statement
    private int second;// sedcond changing number for the statement

    // constructor code
    public MultPractice(int first, int second) {
        this.first = first;
        this.second = second;
    }

    //method to return problem
    // return the string in the format provided in the problem
    @Override
    public String getProblem() {
        return first + " TIMES " + second;
    }

    // method to update problem
    // increase the second number by 1
    @Override
    public void nextProblem() {
        second++;
    }
}
```
