---
layout: post
toc: True
title: Unit 7 ArrayList P3
description: A Unit of documents that overview Array Lists in Java
authors: Drishya, Arnav, Tanuj, Jason
categories: ['AP CSA']
type: ccc
permalink: /csa/unit7-p3/unit7-3
menu: nav/CSA_Units/csa_unit7_p3.html
---

## 7.4 DEVELOPING ALGORITHMS USING ARRAY LISTS


## Essential Knowledge


-> Iteration statements provide a means to access all the elements stored within an ArrayList. This process is referred to as "traversing the ArrayList."

-> The following methods related to ArrayLists, their functions, and appropriate use are covered in the Java Quick Reference:

    -> int size() - Returns the count of elements within the list.
    -> boolean add(E obj) - Appends the object obj to the end of the list and returns true.
    -> void add(int index, E obj) - Inserts obj at the specified index, shifting elements at and -> above that position to the right (incrementing their indices by 1) and increasing the list's size by 1.
    -> E get(int index) - Retrieves the element at the given index in the list.
    -> E set(int index, E obj) - Replaces the element at the specified index with obj and returns the previous element at that index.
    -> E remove(int index) - Deletes the element at the specified index, shifting all subsequent elements one index to the left, reducing the list's size by one, and returning the removed element.

->There exist established algorithms for ArrayLists that make use of traversals to:

    -> Insert elements.
    -> Remove elements.
    -> Apply the same algorithms commonly used with 1D arrays.



```Java
List<Integer> list1 = new ArrayList<Integer>();
list1.add(new Integer(1));
list1.add(new Integer(2));
list1.add(new Integer(3));
list1.remove(1);
```




    2



A. [2, 3]

B. [1, 2, 3]

C. [1, 2]

D. [1, 3]


```Java
List<Integer> numList = new ArrayList<Integer>();
numList.add(new Integer(1));
numList.add(new Integer(2));
numList.add(new Integer(3));
numList.set(2,new Integer(4));
numList.add(1, new Integer(5));
numList.add(new Integer(6));
```




    true



A. [1, 2, 3, 4, 5]

B. [1, 2, 4, 5, 6]

C. [1, 2, 5, 4, 6]

D. [1, 5, 2, 4, 6]


```Java
public class ArrayListExample {

    private double getMax(double[] numbers) {
        double highest = numbers[0];
        for (double num : numbers) {
            if (num > highest) {
                highest = num;
            }
        }
        return highest;
    }

    public static void main(String[] args) {
        double[] nums = {1.0, 3.8, 2.0, 2.0, 1.9, 70.2, 2.0, 4.0, 6.3, 2.1, 5.0, 10.7};
        ArrayListExample instance = new ArrayListExample();
        System.out.println(instance.getMax(nums));
    }
}

ArrayListExample.main(null);
```

    70.2


When you look at the code above you should pay attention to the getMax() method. What the method is doing is it accepts a list of doubles as input and then uses a for loop to determine the highest value in the list.

Now instead of using just a List of Doubles, lets use an ArrayList of Doubles. 


```Java

public class ArrayListExample {

    private double getMax(ArrayList<Double> numbers) {
        double highest = numbers.get(0);
        for (double num : numbers) {
            if (num > highest) {
                highest = num;
            }
        }
        return highest;
    }

    public static void main(String[] args) {
        ArrayList<Double> nums = new ArrayList<>(Arrays.asList(1.0, 3.8, 2.0, 2.0, 1.9, 70.2, 2.0, 4.0, 6.3, 2.1, 5.0, 10.7));
        ArrayListExample instance = new ArrayListExample();
        System.out.println(instance.getMax(nums));
    }
}

ArrayListExample.main(null);
```

    70.2


Finish the code below so that it uses the findSum() method and it finds the sum of the numbers. 


```Java
public class ArrayListHacks {
    private int findSum(ArrayList<Integer> values) {
        int sum = 0;
        for (int i = 0; i < values.size(); i++) {
            sum += values.get(i);
        }
        return sum;
    }

    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();
        nums.add(0);
        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(5);
        nums.add(8);

        ArrayListHacks hacks = new ArrayListHacks();
        int sum = hacks.findSum(nums);
        System.out.println(sum);
    }
}

ArrayListHacks.main(null);
```

    19


# 7.5 Searching

## We will be learning about Sequential Searching but also known as Linear Searching. 

Linear search looks for a value in unsorted data by checking each element in order that the data is in. It then returns the index if found, or -1 if the value isn’t in the list.


```Java
public class ArraySearcher {

    public static int sequentialSearch(int[] elements, int target) {
        for (int j = 0; j < elements.length; j++) {
            if (elements[j] == target) {
                return j;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] numArray = {3, -2, 9, 38, -23};
        System.out.println("Tests of sequentialSearch");
        System.out.println(sequentialSearch(numArray, 3));  // 0
        System.out.println(sequentialSearch(numArray, 9));  // Expected output: 2
        System.out.println(sequentialSearch(numArray, -23)); // Expected output: 4
        System.out.println(sequentialSearch(numArray, 99)); // Expected output: -1
    }
}


ArraySearcher.main(null);
```

    Tests of sequentialSearch
    0
    2
    4
    -1


You can also look for a String in an array or list, but be sure to use equals rather than ==. Remember that == is only true when the two references refer to the same String object, while equals returns true if the characters in the two String objects are the same.



```Java
public class SearchTest
{

    public static int sequentialSearch(String[] elements, String target)
    {
        for (int j = 0; j < elements.length; j++)
        {
            if (elements[j].equals(target))
            {
                return j;
            }
        }
        return -1;
    }

    public static void main(String[] args)
    {
        String[] arr1 = {"blue", "red", "purple", "green"};

        // test when the target is in the array
        int index = sequentialSearch(arr1, "red");
        System.out.println(index);

        // test when the target is not in the array
        index = sequentialSearch(arr1, "pink");
        System.out.println(index);
    }
}

SearchTest.main(null)

```

    1
    -1

