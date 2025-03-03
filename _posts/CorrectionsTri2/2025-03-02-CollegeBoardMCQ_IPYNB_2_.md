---
layout: post
title: CollegeBoard MCQ Corrections
description: CollegeBoard MCQ corrections
type: collab
toc: True
permalink: mcq/corrections2
comments: True
author: Eric Yu
categories: ['Collaboration']
---

### Collegeboard MCQ

### Question 7: Outer and Inner Loops with Multiples of 2 (Skill 2B)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/8b330bda-0d3b-4503-bf7b-ba2b6f48b38a)

#### Why i got the question wrong:
I thought that the entire set of even numbers (2, 4, 6) would be printed in every iteration of the outer loop. However, I did not correctly account for the fact that the inner loop starts at outer and iterates to 6, printing only the even numbers within that range. This resulted in a pattern where each row contains only the valid even numbers from outer to 6, rather than repeating the full set.

#### What I can do better next time
I need to follow the nested loops better, I had problems following the logic of the problem. I feel like writing it down on paper might help with my problems.


### Question 9: Generate random value of number cubes (Skill 1B)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/6dab27a0-95ef-4283-b928-ae94eac59bbc)

#### Why i got the question wrong:
I incorrectly assumed that (int) (Math.random() * 6) + (int) (Math.random() * 6) would correctly simulate rolling two six-sided dice. However, this approach results in values ranging from 0 to 5 (not 1 to 6), because Math.random() generates a value in the range [0,1), and multiplying by 6 followed by typecasting to int truncates the decimal part. This means the possible values are off by 1.

#### What I can do better next time
Be more careful with the boundaries of a range, I need to always double check the logic of my boundaries.

### Question 11: Mystery Method with String Parameter and Substring (Skill 4A)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/3edce0fa-b477-4a8d-bd00-8ca5c96d7c7d)

#### Why i got the question wrong:
I incorrectly understood what the method did. I assumed that it looked for identical portions between the first and second part of the word. I didn't find out it was looking for something like a palindrome, where the word is spelled the same backwards as well as forward.

#### What I can do better next time
I should manually simulate the loop, maybe write out the entire process just to make sure I don't make mistakes like those again. I can also try and look at the other answer choices and try to figure out exactly why they were eliminated, doing so could've made me realize the flaw in my line of thought.

### Question 16: Calculate Method with 2D int array parameter (Skill 5A)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/87618dfe-cbc0-437c-9fe1-97cd4f50d77b)

#### Why i got the question wrong:
I misinterpreted what result represents. The method iterates through the entire 2D array and keeps track of the largest value found and its corresponding column index (result). I mistakenly thought the method was tracking the row index instead of the column index.

#### What I can do better next time
This one I just wasn't thinking straight, nowhere in the code does it mention "columns", so reading the question over a couple of times instead of just clicking on an answer and moving on would be helpful here.

### Question 17: doWhat Method with Positive int Parameter (Skill 5A)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/e13c08f8-5dd2-4f84-95f9-9a1d75b11f65)

#### Why i got the question wrong:
Silly mistake, I didn't realize the loop variable was initialized with the value 1, and because of that I assumed that it would be one less than an odd number, which was why I chose the even number option

#### What I can do better next time
Spending enough time on each problem, and not automatically thinking a problem is easy to move on.

### Question 18: Print statement with mathematical operators (Skill 2A)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/14287991-b1f7-44c9-98d5-dbdbb829b6b5)

#### Why i got the question wrong:
Conceptual error/Careless mistake, I forgot that Java truncates results when doing integer divisions. 

#### What I can do better next time
I need to watch out for problems like these, I felt something was fishy with how "easy" the problem was but forgot about the trucnating rule for Java. So whenever a problem seems strangely easy, take some time to think about it, and also remember to review the basics so they don't trick you like this again.

### Question 27: Sorting 1D int array  (Skill 2B)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/d4b8c80c-e321-4238-9466-4b1487c8a2ee)

#### Why i got the question wrong:
I misunderstood how the algorithm works, but mainly because I'm still feeling iffy about the nested loops I got this question wrong. I accidently stopped at the second iteration of the code, which caused me to get the wrong answer. See the code run below.

#### What I can do better next time:
I genuinlly need to grab out a piece of paper or something to write everything down to keep track of my thoughts. I've noticed one of my problems was not being able to keep track of my thought process which leads to both really high time on these type of questions and not the highest accuracy in the world.


```Java
// Define the selection sort method
public static void sort(int[] data) {  
    for (int j = 0; j < data.length - 1; j++) {  
        int m = j;  
        for (int k = j + 1; k < data.length; k++) {  
            if (data[k] < data[m]) {  
                m = k;  
            }  
        }  
        int temp = data[m];  
        data[m] = data[j];  
        data[j] = temp;  
    }  
}

int[] data = {6, 3, 2, 5, 4, 1};  
sort(data);

for (int num : data) {  
    System.out.print(num + " ");  
}

```

    1 2 3 4 5 6 

### Question 28: Sorting 1d int array statement count (Skill 2D)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/41062eea-cd6a-4934-a231-57d3323ff882)

#### Why i got the question wrong:
I honestly didn't know what was going on, so I randomly guessed an answer. But I'll document what was going on down below:

The code both compares values from the unsorted portion of the array and assigns them to a temporary variable for swapping if needed. So starting from the array {1, 2, 3, 4, 5, 6}, the algorithm scans the remaining elements to find the smallest value and places it in its correct position.

Because the array is already sorted, no swaps will occur. However, the algorithm still goes through all necessary comparisons to verify that each element is in order. For each iteration of the outer loop, the inner loop checks every remaining element to confirm that no smaller value exists. This results in a total of 15 comparisons, but since no element needs to be moved, the number of swaps remains 0. The selection sort algorithm does not optimize for already sorted data, so it still performs all comparisons even when unnecessary swaps are avoided.


#### What I can do better next time:
The type of sort that was tested was a selection sort, so I should study those as I am evidently struggling with them.


```Java
public class SelectionSort {
    public static void sort(int[] data) {
        int compareCount = 0; // Counter for comparisons

        for (int j = 0; j < data.length - 1; j++) {
            int m = j;
            for (int k = j + 1; k < data.length; k++) {
                compareCount++; // Increment comparison count
                if (data[k] < data[m]) {
                    m = k;
                }
            }
            int temp = data[m];
            data[m] = data[j];
            data[j] = temp;
        }

        System.out.println("Total comparisons: " + compareCount);
    }

    public static void main(String[] args) {
        int[] data = {1, 2, 3, 4, 5, 6};
        sort(data);
        for (int num : data) {
            System.out.print(num + " ");
        }
    }
}


SelectionSort.main(null)

```

    Total comparisons: 15
    1 2 3 4 5 6 

### Quesiton 29: what method with int parameter (Skill 5A)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/dbd0ca9f-b01a-4e48-9ee1-c6bae0a5c3e9)

#### Why i got the question wrong:
I didn't fully analyze the recursive function before answering, which led me to incorrectly assume it was summing the digits instead of counting them. The function divides the number by 10 at each recursive step, effectively reducing it digit by digit until it reaches a single-digit base case. Each recursive call adds 1 to the return value, meaning it counts the number of digits rather than summing them.


#### What I can do better next time:
I need to slow down and carefully trace through recursive functions step by step to understand their behavior. Writing out a few test cases manually would help clarify what the function is actually doing before selecting an answer.

### Question 31: X and O board (Skill 2B)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/4b13a6aa-99c0-4dc3-b8fe-b35904d689a1)

#### Why i got the question wrong:
I misinterpreted how the X placement logic works in the nested loop. The loop places X diagonally whenever val is an odd number. The logic starts at (row = val, col = 0), moving diagonally downward while ensuring it stays within the bounds of the 5x5 grid. I mistakenly chose an option that didn't match the expected diagonal placements of X.

#### What I can do better next time:
I need to trace through nested loops systematically, especially when they involve conditions like val % 2 == 1. Writing out the board state after each iteration would help me visualize how values are placed. Practicing more problems with nested loops and grid manipulations will improve my ability to spot patterns in such code.


```Java
public class XandOBoard {
    public static void main(String[] args) {
        String[][] board = new String[5][5];

        for (int row = 0; row < 5; row++) {
            for (int col = 0; col < 5; col++) {
                board[row][col] = "O";
            }
        }

        for (int val = 0; val < 5; val++) {
            if (val % 2 == 1) {
                int row = val;
                int col = 0;
                while (col < 5 && row >= 0) {
                    board[row][col] = "X";
                    col++;
                    row--;
                }
            }
        }

        for (int row = 0; row < 5; row++) {
            for (int col = 0; col < 5; col++) {
                System.out.print(board[row][col] + " ");
            }
            System.out.println();
        }
    }
}

XandOBoard.main(null);

```

    O X O X O 
    X O X O O 
    O X O O O 
    X O O O O 
    O O O O O 


### Quesiton 32: StudentInfo class and averageInMajor method (Skill 1B)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/2dec55da-b17b-4ba9-8204-58f6023ceffd)

#### Why i got the question wrong:
Silly mistake/Stupid Mistake. In Java you can't just simply assign a variable like var = k.age, you must use the getter method defined in the class. Especially if this was a private method.

#### What I can do better next time
Always take note of whether a class is private or public, and also make sure to really think about your answer before moving on.

### Question 37: concatWords with String array (Skill 1B)

#### Picture of the problem
![Image](https://github.com/user-attachments/assets/179cebaa-36f9-4e89-8689-5bdfc05ad4e2)

#### Why i got the question wrong:
I incorrectly selected option II only, but the correct answer was II and III. My mistake was overlooking the fact that both solutions II and III correctly implement the intended functionality of concatenating words in reverse order starting from startIndex.

- Option II correctly iterates from the end (words.length - 1) down to startIndex, appending words in the expected order.
- Option III first constructs a reversed version of the array and then concatenates elements, which also achieves the desired outcome.
- Option I is incorrect because it incorrectly pairs elements from both ends rather than concatenating them in strict reverse order.

#### What I can do better next time
I need to carefully analyze loop structures and their effects on indexing, especially when dealing with reverse order problems. Double-checking logic by walking through a small test case manually can help prevent similar mistakes.


### Strengths and Weaknesses

Strengths:
- Conditional problems, can also solve them relatively fast
- Identifying errors in code




Weaknesses
- Iterations (especially nested loops)
- Careless mistakes

Statistics
![Image](https://github.com/user-attachments/assets/69fdabda-b68f-47a9-bbe4-51a023df6fb3)
![Image](https://github.com/user-attachments/assets/46bfbf02-f66c-4e9c-8c51-8a824be5c99f)

Time taken:
2 Hours, 11 Minutes

### Moving Forward
- Write down logic of problems (especially for nested loops) on a piece of paper
- Eliminate all choices of a problem and know why they're eliminated to potentially reveal faults in logic
- Don't rush problems
- Manage time well


