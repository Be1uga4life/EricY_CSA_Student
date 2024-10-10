---

---

```Java
String[][] grades = {
    {"Hello", "World"},
    {"Java", "Array"}
};

// The code above are defined with Strings, not integers, thus "String" would be used instead of "int"
```

#### Popcorn Hack #2, How many total elements can this 2D array hold, and how would you calculate it?


```Java

// There are two rows and columns, therefore there are 6 elements since 2 times 3 is 6.
int[][] matrix = new int[2][3];
System.out.println(Arrays.deepToString(matrix));
```

    [[0, 0, 0], [0, 0, 0]]


### Popcorn Hack #3, MCQ Question

How would you write the code to access the last score? MC

![something](https://github.com/user-attachments/assets/4bae6ef7-dee0-4b6f-ba92-bd05af8fa84d)

A. grades[6][3]

B. grades[7][4]

C. grades[grades.length - 1] [grades[0].length - 1]

D. A and C


The ansewr is be D


Try it on your own, declare + initlialize the 2D array.


```Java
public class ArrayPractice {
    public static void main(String[] args) {
        // Write the code to declare and initialize the 2D array here
        

        // Print the array
        System.out.println(java.util.Arrays.deepToString(array));
    }
}

ArrayPractice.main(null)
```

Try it on your own. Change from Java to Programming


```Java
String[][] hack = {
    {"Hello", "World"},
    {"Java", "Array"}
};

hack[1][0] = "Programming";
System.out.println(Arrays.deepToString((hack)));
```

    [[Hello, World], [Programming, Array]]


Popcorn Hack, Change Australia to Athens:

![something](https://github.com/user-attachments/assets/72f2ff0f-7d8b-4d5b-90e4-da9403a5570b)

Answer: B


___

Lesson 8.2

___

Popcorn Hack #1, find the specific number and return specific index


```Java
public class Main {
    public static void main(String[] args) {
        int find[][] = {
            {10, 20, 30},
            {40, 55, 60},
            {70, 80, 90},
        };

        for (int row = 0; row < find.length; row++) {
            for (int col = 0; col < find[row].length; col++) {
                if (find[row][col] == 55) {
                    System.out.println("Number: " + find[row][col]);
                    System.out.println("Row: " + row);
                    System.out.println("Column: " + col);
                    return;  // Exit after finding the number
                }
            }
        }
    }
}

Main.main(null);

```

    Number: 55
    Row: 1
    Column: 1


Binary Search/Linear Search Popcorn Hack


```Java
public class Main {
    public static void main(String[] args) {
        // Custom 2D array with sorted rows
        int[][] array = {
            {1, 5, 9, 14},
            {18, 22, 25, 30},
            {32, 36, 40, 45},
            {50, 55, 60, 65}
        };
        
        int target = 36;

        // Linear Search
        System.out.println("Linear Search:");
        linearSearch(array, target);
        
        // Binary Search
        System.out.println("Binary Search:");
        binarySearch2D(array, target);
    }

    // Linear Search implementation
    public static void linearSearch(int[][] array, int target) {
        for (int row = 0; row < array.length; row++) {
            for (int col = 0; col < array[row].length; col++) {
                if (array[row][col] == target) {
                    System.out.println("Found " + target + " at row " + row + ", column " + col);
                    return;  // Exit after finding the number
                }
            }
        }
        System.out.println(target + " not found in the array.");
    }

    // Binary Search implementation for 2D array
    public static void binarySearch2D(int[][] array, int target) {
        for (int row = 0; row < array.length; row++) {
            int left = 0;
            int right = array[row].length - 1;
            
            while (left <= right) {
                int mid = left + (right - left) / 2;
                
                if (array[row][mid] == target) {
                    System.out.println("Found " + target + " at row " + row + ", column " + mid);
                    return;  
                } else if (array[row][mid] < target) {
                    left = mid + 1;  // Search right half
                } else {
                    right = mid - 1;  // Search left half
                }
            }
        }
        System.out.println(target + " not found in the array.");
    }
}

Main.main(null);

```

    Linear Search:
    Found 36 at row 2, column 1
    Binary Search:
    Found 36 at row 2, column 1


Popcorn Hack, Write a code that performs global sorting on the 2D array


```Java
public class PopcornHack {
    public static void main(String[] args) {
        int[][] array = {
            {9, 2, 5},
            {7, 4, 3},
            {6, 8, 1}
        };

        array = globalSort(array);

        int target = 4;

        int[] result = linearSearch(array, target);
        // Uncomment the below line to use binary search
        // int[] result = binarySearch(array, target);

        // Step 5: Output the result
        if (result[0] != -1) {
            System.out.println("Element found at: Row " + result[0] + ", Column " + result[1]);
        } else {
            System.out.println("Element not found.");
        }
    }

    // Global sorting method
    public static int[][] globalSort(int[][] array) {
        int rows = array.length;
        int cols = array[0].length;
        int[] temp = new int[rows * cols];
        
        // Flatten the 2D array into 1D array
        int index = 0;
        for (int[] row : array) {
            for (int value : row) {
                temp[index++] = value;
            }
        }
    
        java.util.Arrays.sort(temp);
        
        index = 0;
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                array[i][j] = temp[index++];
            }
        }
        return array;
    }

    public static int[] linearSearch(int[][] array, int target) {
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                if (array[i][j] == target) {
                    return new int[] {i, j};
                }
            }
        }
        return new int[] {-1, -1};
    }

    public static int[] binarySearch(int[][] array, int target) {
        int rows = array.length;
        int cols = array[0].length;
        int low = 0;
        int high = rows * cols - 1;
        
        while (low <= high) {
            int mid = (low + high) / 2;
            int midValue = array[mid / cols][mid % cols];
            
            if (midValue == target) {
                return new int[] {mid / cols, mid % cols};
            } else if (midValue < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return new int[] {-1, -1};
    }
}

PopcornHack.main(null)

```

    Element found at: Row 1, Column 0


___
Homework Hacks
___

### HW Hack for 8.1:


```Java
public class Main {
    public static void main(String[] args) {
        String[][] array = {{"My", "A"}, {"AP", "Class"}, {"CS", "Rocks!"}};
        
        for (int col = 0; col < array[0].length; col++) {
            for (int row = 0; row < array.length; row++) {
                System.out.print(array[row][col] + " ");
            }
        }
    }
}

Main.main(null);
```

    My AP CS A Class Rocks! 

#### The correct option is B:

There are three rows, and two columns. If following the rows from left to right, and from top to bottom, it matches up with the code.

### HW Hack for 8.2:


```Java
public class GradeSearch {
    public static String searchGrade(String[][] grades, String name) {
        for (String[] student : grades) {
            if (student[0].equals(name)) {
                return student[1];
            }
        }
        return "Student not found";
    }

    public static void main(String[] args) {
        String[][] grades = {
            {"John", "93"},
            {"Alice", "85"},
            {"Bob", "78"},
            {"Eve", "92"}
        };

        String nameToSearch = "John";
        String grade = searchGrade(grades, nameToSearch);
        System.out.println(nameToSearch + "'s grade: " + grade);

        nameToSearch = "Charlie";
        grade = searchGrade(grades, nameToSearch);
        System.out.println(nameToSearch + "'s grade: " + grade);
    }
}

GradeSearch.main(null);

```

    John's grade: 93
    Charlie's grade: Student not found

