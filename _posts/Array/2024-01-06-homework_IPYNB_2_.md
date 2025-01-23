---
layout: post
toc: True
title: Array/Homework
description: AP CSA FRQ Array/Arraylist Homework
courses: {'csa': {'week': 1}}
type: ccc
categories: ['AP CSA']
menu: nav/CSA_Units/frqs/array.html
permalink: /teamteach/array/homework
---

# Homework

Write a program that randomly fills in 0s and 1s into an n-by-n matrix, prints the matrix, and finds the rows and columns with the most 1s. (Hint: Use two ArrayLists to store the row and column indices with the most 1s.) 

Here is a sample run of the program, printed in the console: 
```
Enter the array size n: 4
The random array is
0011
0011
1101
1010
The largest row index: 2
The largest column index: 2, 3 
```


```Java
System.out.print("Enter the array size n: ");
Scanner scanner = new Scanner(System.in);
int n = scanner.nextInt();
int[][] arr = new int[n][n];

System.out.println("The random array is");
// iterate through arr to fill it with random 0s and 1s
for (int i = 0; i < n; i++) {
    arr[i] = new int[n];
    for (int j = 0; j < n; j++) {
        arr[i][j] = Math.random() < 0.5 ? 0 : 1;
    }
}

// printing out the arr
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        System.out.print(arr[i][j] + " ");
    }
    System.out.println();
}

// find rows and cols w/ most 1s
ArrayList<Integer> rowsWithMostOnes = new ArrayList<>();
ArrayList<Integer> colsWithMostOnes = new ArrayList<>();

int maxOnesInRow = 0;
int maxOnesInCol = 0;
for (int row = 0; row < n; row++) {
    int onesInRow = 0;
    for (int col = 0; col < n; col++) {
        if (arr[row][col] == 1) {
            onesInRow++;
        }
    }
    if (onesInRow > maxOnesInRow) {
        maxOnesInRow = onesInRow;
        rowsWithMostOnes.clear();
        rowsWithMostOnes.add(row);
    } else if (onesInRow == maxOnesInRow) {
        rowsWithMostOnes.add(row);
    }
}

for (int col = 0; col < n; col++) {
    int onesInCol = 0;
    for (int row = 0; row < n; row++) {
        if (arr[row][col] == 1) {
            onesInCol++;
        }
    }
    if (onesInCol > maxOnesInCol) {
        maxOnesInCol = onesInCol;
        colsWithMostOnes.clear();
        colsWithMostOnes.add(col);
    } else if (onesInCol == maxOnesInCol) {
        colsWithMostOnes.add(col);
    }
}

// print out the rows and cols with most 1s
System.out.print("The largest row index: ");
for (int row : rowsWithMostOnes) {
    System.out.print(row + " ");
}
System.out.print("\nThe largest column index: ");
for (int col : colsWithMostOnes) {
    System.out.print(col + " ");
}
System.out.println();
```
