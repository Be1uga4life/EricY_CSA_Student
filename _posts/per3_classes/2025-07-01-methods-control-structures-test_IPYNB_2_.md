---
layout: post
title: Feeder Class Simulation
categories: ['AP CSA']
menu: nav/CSA_Units/frqs/methods_per3.html
permalink: /methods_per3/tester
---

# AP CSA FRQ Tester: Feeder Class Simulation (2024)

This notebook allows you to test your implementation of the `simulateOneDay` and `simulateManyDays` methods for the **Feeder** class.

The test harness will:
1. Append your code to a predefined test structure.
2. Run several test cases.
3. Display the results of the test cases.

---

## Instructions

1. Add the code as per the FRQ instructions in the //YOUR CODE HERE
2. Run both code cells to test your code for errors against provided test cases
---




```python
// Your Implementation
public class Feeder {
    private int currentFood; // Amount of food in grams in the feeder

    public Feeder(int initialFood) {
        currentFood = initialFood;
    }

    /**
     * Simulates one day with numBirds birds or possibly a bear at the feeder.
     * Precondition: numBirds > 0
     */
    public void simulateOneDay(int numBirds) {
        // YOUR CODE HERE
    }

    /**
     * Simulates numDays of activity at the feeder with numBirds birds.
     * Returns the number of days on which food was found in the feeder.
     * Precondition: numBirds > 0, numDays > 0
     */
    public int simulateManyDays(int numBirds, int numDays) {
        // YOUR CODE HERE
        return 0; // Placeholder
    }
}

```


```python
public class FeederTest {
    public static void main(String[] args) {
        StringBuilder results = new StringBuilder();

        // Test Case 1
        Feeder feeder1 = new Feeder(2400);
        feeder1.simulateOneDay(10);
        results.append("Test Case 1: Current food after one day: ").append(feeder1.currentFood).append("\n");

        // Test Case 2
        Feeder feeder2 = new Feeder(250);
        int daysWithFood2 = feeder2.simulateManyDays(10, 5);
        results.append("Test Case 2: Days with food: ").append(daysWithFood2)
               .append(", Remaining food: ").append(feeder2.currentFood).append("\n");

        // Test Case 3
        Feeder feeder3 = new Feeder(0);
        int daysWithFood3 = feeder3.simulateManyDays(5, 10);
        results.append("Test Case 3: Days with food: ").append(daysWithFood3)
               .append(", Remaining food: ").append(feeder3.currentFood).append("\n");

        // Print Results
        System.out.println(results.toString());
    }
}

// Run the Test Harness
FeederTest.main(null);

```
