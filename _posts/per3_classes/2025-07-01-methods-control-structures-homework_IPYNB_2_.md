---
layout: post
title: Homework
categories: ['AP CSA']
menu: nav/CSA_Units/frqs/methods_per3.html
permalink: /methods_per3/homework
---

# Team Teach Homework

# **Maze Solver Problem**

## **Instructions**


Your task is to write a method `solveMaze(char[][] maze, int startX, int startY)` that determines whether a path exists from a starting point `(startX, startY)` in a 2D maze to the exit marked as `'E'`. Use recursion to explore the maze.

---

## **Requirements**

### **Input**


- A 2D array of characters (`char[][] maze`) representing the maze.  


- An integer `startX` indicating the row index of the starting point.  


- An integer `startY` indicating the column index of the starting point.

### **Output**


- Return `true` if there is a path from `(startX, startY)` to `'E'`.  


- Return `false` if no such path exists.



### **Maze Rules**


- `' '` represents an open path (you can move here).  


- `'#'` represents a wall (you cannot move here).  


- `'E'` represents the exit (this is the destination).  

### **Movement**


- You can move **up**, **down**, **left**, or **right** to adjacent cells.  


- You cannot move diagonally or leave the bounds of the maze.  


### **Marking Visited Cells**


- To avoid revisiting the same cells, mark visited cells as `'#'` temporarily during recursion. Restore them to `' '` after backtracking.

---

## **Steps to Solve**


1. Check if the current position is valid:


   - Is it within the bounds of the maze?


   - Is it an open path or the exit?


2. Check if the current position is `'E'`. If yes, return `true`.


3. Mark the current cell as visited (change it to `'#'`).


4. Recursively explore all possible directions (up, down, left, right).


5. If any direction leads to the exit, return `true`.


6. Restore the cell to `' '` after exploring (backtracking).


7. If no paths lead to the exit, return `false`.

---


```python
public class MazeSolver {
    public static void main(String[] args) {
        char[][] maze = {
            {'#', '#', '#', '#', '#'},
            {'#', ' ', ' ', '#', 'E'},
            {'#', ' ', '#', ' ', '#'},
            {'#', ' ', ' ', ' ', '#'},
            {'#', '#', '#', '#', '#'}
        };

        System.out.println(solveMaze(maze, 1, 4));
    }

    public static boolean solveMaze(char[][] maze, int startX, int startY) {
        if (startX < 0 || startX >= maze.length || startY < 0 || startY >= maze[0].length || maze[startX][startY] == '#') {
            return false;
        }

        if (maze[startX][startY] == 'E') {
            System.out.println("Exit found at (" + startX + ", " + startY + ")");
            return true;
        }

        System.out.println("Visiting (" + startX + ", " + startY + ")");
        maze[startX][startY] = '#';

        if (solveMaze(maze, startX - 1, startY) ||
            solveMaze(maze, startX + 1, startY) ||
            solveMaze(maze, startX, startY - 1) ||
            solveMaze(maze, startX, startY + 1)) {
            return true;
        }

        System.out.println("Backtracking from (" + startX + ", " + startY + ")");
        maze[startX][startY] = ' ';

        return false;
    }
}

```
