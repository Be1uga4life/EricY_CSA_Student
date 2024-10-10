---
layout: post
title: Unit 6
description: Unit 6 Homework
categories: ['Collaboration']
courses: {'csse': {'week': 3}, 'csp': {'week': 3}, 'csa': {'week': 2}}
permalink: /Unit6
type: collab
comments: True
---

6.1 Popcorn Hack #1


```Java
String[] cityArray = {"San Diego", "Los Angeles", "San Francisco", "Sacramento"};
```


```Java
System.out.println(cityArray[0]);
System.out.println(cityArray[2]);
```

    San Diego
    San Francisco



```Java
cityArray[1] = "Sacramento";
cityArray[3] = "San Jose";
```




    San Jose




```Java
System.out.println(cityArray.length);
```

    4


6.1 Popcorn Hack #2


```Java
public class DefaultValuesArray {
    public static void main(String[] args) {
        int[] gojo = new int[4]; 
        String[] skibid = new String[4];
        double[] sigma = new double[4]; 
        boolean[] idk = new boolean[4]; 

        System.out.println(gojo[1]);
        System.out.println(skibid[1]);
        System.out.println(sigma[1]);
        System.out.println(idk[1]);
    }
}

DefaultValuesArray.main(null)

```

    0
    null
    0.0
    false


___
The correct choice is D. 

arr[arr.length - 3].indexOf(find).

arr[arr.length - 3] accesses the string at the third-to-last position in the array (because arrays are zero-indexed).


___

The correct choice is B:

The method mystery takes an array, and the code calculates:
return arr[1] + arr[4] / 2;

arr[1] = 9
arr[4] = 6

9 + 6/2 = 12


___

6.2 Popcorn Hack #1


```Java
public class thingy {
    public static int sumOfEvenNumbers(int[] arr) {
        int sum = 0; 
        for (int num : arr) {
            if (num % 2 == 0) {
                sum += num;
            }
        }
        
        return sum;
    }
    
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        System.out.println(sumOfEvenNumbers(arr)); // Output: 6
    }    
}

thingy.main(null)

```

    6


6.2 Popcorn Hack #2


```Java
public class thingy {
    public static int countOccurrences(int[] arr, int target) {
        int count = 0; // Start with no occurrences
        
        // Begin the journey through the array
        for (int num : arr) {
            // Whenever the target number is found, increase the count
            if (num == target) {
                count++;
            }
        }
        
        return count; // Return the number of times the target was encountered
    }
    
    // Example usage:
    public static void main(String[] args) {
        int[] arr = {3, 5, 3, 3, 7, 5};
        int target = 3;
        System.out.println(countOccurrences(arr, target)); // Output: 3
    }
    
}

thingy.main(null)


```

    3


6.2 Popcorn Hack #3


```Java
public class skib {
    public static int firstNegativeIndex(int[] arr) {
        int i = 0; 
        while (i < arr.length) {
            if (arr[i] < 0) {
                return i;
            }
            i++; 
        }
        
        return -1;
    }
    
    // Example usage:
    public static void main(String[] args) {
        int[] arr = {4, 7, -2, 5};
        System.out.println(firstNegativeIndex(arr));
    }
}

skib.main(null)

```

    2


6.2 MCQ Questions

C

The code loops through the list, and prints out the length of each item seperated by a _, so it would be 3_6_4_

___
E

int i = 0; i < numbers.length; i+=2

The initial starts at the first (0th term) term, and then while the iteration is less than the number of items in the list, increment by two.

___

B

i < arr.length / 2

This condition ensures the loop only runs for the first half of the array, swapping elements between the start and the end. More than that it just reverses it a second time.

6.3 Homework Hack


```Java
public class Main {

    public static int findSecondLargest(int[] arr) {
        if (arr == null || arr.length < 2) {
            return -1; // Not enough elements to find the second largest
        }

        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        boolean foundSecond = false;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] > largest) {
                secondLargest = largest;
                largest = arr[i];
                foundSecond = true; // At least two different elements exist
            } else if (arr[i] > secondLargest && arr[i] != largest) {
                secondLargest = arr[i];
                foundSecond = true;
            }
        }

        return foundSecond ? secondLargest : -1;
    }

    public static void main(String[] args) {
        int[] arr1 = {3, 1, 4, 1, 5, 9, 2, 6};
        System.out.println(findSecondLargest(arr1)); // Output: 6

        int[] arr2 = {10, 10, 10, 10};
        System.out.println(findSecondLargest(arr2)); // Output: -1
    }
}

Main.main(null)
```

    6
    -2147483648


6.3 Popcorn Hack #1


```Java
String[] languages = {"Java", "Python", "Markdown", "C++", "Go", "JavaScript", "HTML"};

for (String language : languages) {
    System.out.println(language);
}

```

    Java
    Python
    Markdown
    C++
    Go
    JavaScript
    HTML


6.3 Popcorn Hack #2


```Java
String[] myArray = {"And", "Table", "Shirts", "Tea", "School Day"};

for (String currentWord : myArray) {
    System.out.println(currentWord);
}
```

    And
    Table
    Shirts
    Tea
    School Day



```Java
private String[] myArray = {
    "And", "Table", "Shirts", "Tea", "School Day"
};

for (String currentWord : myArray) {
    System.out.println(currentWord.length());
}

```

    3
    5
    6
    3
    10



```Java
String[] myArray = {"And", "Table", "Shirts", "Tea", "School Day"};

for (String currentWord : myArray) {
    int index = currentWord.indexOf('a');
    if (index != -1) {
        System.out.println("The letter 'a' is found in \"" + currentWord + "\" at index: " + index);
    } else {
        System.out.println("The letter 'a' is not found in \"" + currentWord + "\".");
    }
}

```

    The letter 'a' is not found in "And".
    The letter 'a' is found in "Table" at index: 1
    The letter 'a' is not found in "Shirts".
    The letter 'a' is found in "Tea" at index: 2
    The letter 'a' is found in "School Day" at index: 8



```Java
String[] myArray = {"Object 1", "Object 2", "Object 3", "Object 4", "Object 5"};

for (String currentWord : myArray) { // Added type declaration
    System.out.println(currentWord); // Corrected method call
} // Removed unnecessary semicolon

```

    Object 1
    Object 2
    Object 3
    Object 4
    Object 5



```Java
public class AverageGradeCalculator {
    public static void main(String[] args) {
        // Array of initial grades
        Integer[] grades = {88, 93, 55, 68, 77};

        // Prompt user for a new grade
        System.out.print("Enter a grade: ");
        // Read the grade from the console
        java.util.Scanner scanner = new java.util.Scanner(System.in);
        int grade = Integer.parseInt(scanner.nextLine());

        // Add the new grade to the array
        grades = addGrade(grades, grade);

        // Calculate the average
        double average = calculateAverage(grades);

        // Output the updated grades and the average
        System.out.print("Updated Grades: ");
        printGrades(grades);
        System.out.println("Average Grade: " + average);
    }

    // Method to add a new grade to the grades array
    public static Integer[] addGrade(Integer[] grades, int newGrade) {
        Integer[] newGrades = new Integer[grades.length + 1];
        for (int i = 0; i < grades.length; i++) {
            newGrades[i] = grades[i];
        }
        newGrades[newGrades.length - 1] = newGrade; // Add the new grade
        return newGrades;
    }

    // Method to calculate the average of the grades
    public static double calculateAverage(Integer[] grades) {
        int sum = 0;
        for (Integer currentGrade : grades) {
            sum += currentGrade; // Add each grade to the sum
        }
        return (double) sum / grades.length; // Calculate the average
    }

    // Method to print the grades
    public static void printGrades(Integer[] grades) {
        for (int i = 0; i < grades.length; i++) {
            System.out.print(grades[i]);
            if (i < grades.length - 1) {
                System.out.print(", "); // Print comma between grades
            }
        }
        System.out.println(); // New line after printing all grades
    }
}

AverageGradeCalculator.main(null)
```

    Enter a grade: 


    ---------------------------------------------------------------------------

    java.lang.NumberFormatException: For input string: ""

    	at java.base/java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)

    	at java.base/java.lang.Integer.parseInt(Integer.java:662)

    	at java.base/java.lang.Integer.parseInt(Integer.java:770)

    	at AverageGradeCalculator.main(#34:10)

    	at .(#35:1)


___
6.4 Algorithms
___

6.4 Popcorn Hack #1


```Java
public class MaxMinInArray {

    public static void findMaxAndMin(int[] array) {
       
        if (array == null || array.length == 0) {
            System.out.println("Array is empty");
            return;
        }

        int max = array[0];
        int min = array[0];

        // Loop to find max, min, and apply the "Popcorn Hack"
        for (int i = 1; i < array.length; i++) {
            // Popcorn Hack: If the current element is greater than the next element
            if (i < array.length - 1 && array[i] > array[i + 1]) {
                System.out.println("Increase");
            }
            // Find maximum value
            if (array[i] > max) {
                max = array[i];  
            }
            // Find minimum value
            if (array[i] < min) {
                min = array[i];  
            }
        }

        System.out.println("Maximum value: " + max);
        System.out.println("Minimum value: " + min);
    }

    public static void main(String[] args) {
     
        int[] array = {3, 5, 7, 2, 8, -1, 4, 0, 12};

        findMaxAndMin(array);
    }
}

MaxMinInArray.main(null)

```

    Increase
    Increase
    Increase
    Maximum value: 12
    Minimum value: -1


6.4 HW Hack


```Java
public class ReverseArrayOutput {

    public static void main(String[] args) {
        Integer[] myArray = {0, 1, 2, 3, 4, 5};

        for (int i = myArray.length - 1; i >= 0; i--) {
            System.out.println(myArray[i]);
        }
    }
}

ReverseArrayOutput.main(null)

```

    5
    4
    3
    2
    1
    0



```Java
public class WordShifter {  
    public static void main(String[] args) {
        String[] words = {"gamma", "beta", "alpha", "delta"};
        int shiftWord = 2;

        // Shift the words in the array
        for (int count = 0; count < shiftWord; count++) {
            String temp = words[0];
            for (int index = 0; index < words.length - 1; index++) {
                words[index] = words[index + 1];
            }
            words[words.length - 1] = temp;
        }

        // Print "alpha" first, then "gamma"
        for (int i = 0; i < words.length; i++) {
            if (i % 2 == 0) { // Print words at even indices
                System.out.print(words[i] + " ");
            }
        }
    }
}

WordShifter.main(null)

```

    alpha gamma 
