---

---

```java
import java.util.ArrayList;

public class PopcornHacks {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");
        fruits.add("Date");
        fruits.add("Elderberry");

        // Task 1: Print the size of the ArrayList
        System.out.println("Task 1: Size of the ArrayList: " + fruits.size());

        // Task 2: Add "Fig" to the end of the list
        fruits.add("Fig");
        System.out.println("Task 2: " + fruits);

        // Task 3: Insert "Grape" at index 2
        fruits.add(2, "Grape");
        System.out.println("Task 3: " + fruits);

        // Task 4: Replace the element at index 4 with "Guava"
        fruits.set(4, "Guava");
        System.out.println("Task 4: " + fruits);

        // Task 5: Remove the element at index 1
        fruits.remove(1);
        System.out.println("Task 5: " + fruits);

        // Task 6: Retrieve and print the element at index 3
        System.out.println("Task 6: Element at index 3: " + fruits.get(3));

        // Final state of the ArrayList
        System.out.println("Final state of the ArrayList: " + fruits);
    }
}
```

### MCQ

1. Which of the following are methods to interact with arrays?

variable.get

2. What happens when you run a command requesting the item arr[-1]?
Answer: You get the error ArrayIndexOutOfBoundsException

Java doesn't allow for the -1 option, only python has that




```java
import java.util.ArrayList;
import java.util.List;

List<Integer> list1 = new ArrayList<>();
list1.add(new Integer(1));
list1.add(new Integer(2));
list1.add(new Integer(3));

// Removing the element at index 1 (which is the value 2)
list1.remove(1);

// Correct way to print the ArrayList
System.out.println(list1);

// Answer D is correct

```

    [1, 3]



```java
List<Integer> numList = new ArrayList<Integer>();
numList.add(new Integer(1));
numList.add(new Integer(2));
numList.add(new Integer(3));
numList.set(2,new Integer(4));
numList.add(1, new Integer(5));
numList.add(new Integer(6));

System.out.println(numList);

// Answer D is correct
```

    [1, 5, 2, 4, 6]


### Ducks Popcorn Hack


```java
import java.util.ArrayList;

class DebugDuck implements Comparable<DebugDuck> {
    String name;
    double weight;

    public DebugDuck(String name, double weight) {
        this.name = name;
        this.weight = weight;
    }

    @Override
    public int compareTo(DebugDuck other) {
        return Double.compare(this.weight, other.weight);
    }

    @Override
    public String toString() {
        return name + " (" + weight + " kg)";
    }
}

public class DuckSorter {
    // Selection sort algorithm to sort ducks by weight
    public static void selectionSort(ArrayList<DebugDuck> ducks) {
        int n = ducks.size();
        for (int i = 0; i < n - 1; i++) {
            // Assume the minimum element is at i
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (ducks.get(j).compareTo(ducks.get(minIndex)) < 0) {
                    minIndex = j;
                }
            }
            // Swap the found minimum element with the first element
            DebugDuck temp = ducks.get(i);
            ducks.set(i, ducks.get(minIndex));
            ducks.set(minIndex, temp);
        }
    }

    public static void main(String[] args) {
        // Creating an ArrayList of ducks
        ArrayList<DebugDuck> ducks = new ArrayList<>();
        ducks.add(new DebugDuck("Duck A", 4.5));
        ducks.add(new DebugDuck("Duck B", 2.1));
        ducks.add(new DebugDuck("Duck C", 5.0));
        ducks.add(new DebugDuck("Duck D", 1.9));

        // Print the list before sorting
        System.out.println("Before sorting:");
        for (DebugDuck duck : ducks) {
            System.out.println(duck);
        }

        // Sort the ducks by weight
        selectionSort(ducks);

        // Print the list after sorting
        System.out.println("\nAfter sorting:");
        for (DebugDuck duck : ducks) {
            System.out.println(duck);
        }
    }
}
```

### 7th Mini Hack 


```java
ArrayList<String> userData = new ArrayList<>();
userData.add("John Doe");
userData.add("john@example.com");

// Once you're done using the data
userData.clear(); // Removes all entries
userData = null;  // turn it into null
```

### Homework Hacks


```java
import java.util.ArrayList;
import java.util.Collections;

public class ArrayListActivity {
    public static void main(String[] args) {
        // Task 1: Create an ArrayList of integers and add 5 elements
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);
        numbers.add(50);
        System.out.println("Task 1: " + numbers);

        // Task 2: Change the second element (index 1) to a new value (e.g., 100)
        numbers.set(1, 100);
        System.out.println("Task 2: " + numbers);

        // Task 3: Remove the third element (index 2)
        numbers.remove(2);
        System.out.println("Task 3: " + numbers);

        // Task 4: Check if 30 is in the ArrayList
        if (numbers.contains(30)) {
            System.out.println("Task 4: 30 is found in the list.");
        } else {
            System.out.println("Task 4: 30 is not found in the list.");
        }

        // Task 5: Loop through the ArrayList and print each element
        System.out.println("Task 5: Looping through the list:");
        for (int number : numbers) {
            System.out.println(number);
        }

        // Task 6: Sort the ArrayList in ascending order
        Collections.sort(numbers);
        System.out.println("Task 6: Sorted ArrayList: " + numbers);
    }
}

```
