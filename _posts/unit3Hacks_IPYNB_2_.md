---

---

## Popcorn Hack 1


```java
String myName = "Alisha";  // Use double quotes for string literals

boolean isNotAnika = !myName.equals("Anika");  // Use .equals() for string comparison
boolean isAlisha = myName.equals("Alisha");
```

String literals need to be enclosed in double quotes. You need to use .equals() to compare strings also.

## HW

The precondition for num is stated in the comments of the provided code. It mentions:

- The number of digits in num must be between 1 and 6, inclusive.
- Additionally, it specifies that num >= 0.

These conditions must be met for the getCheck method to work correctly as intended.

# Unit 3.2

## Popcorn Hack


```java
class Main{
    public static void main(String[] args) {
        // Test case 1: Age is less than 16
        int myAge = 15;  // Change to an age less than 16
        System.out.println("Current age: " + myAge);
        
        if (myAge >= 16) {
            System.out.println("You can start learning to drive!");
        }

        System.out.println("On your next birthday, you will be " + (myAge + 1) + " years old!");
        
        System.out.println();  // Just to separate test cases

        // Test case 2: Age is even younger
        myAge = 10;  // Another test case where age is less than 16
        System.out.println("Current age: " + myAge);
        
        if (myAge >= 16) {
            System.out.println("You can start learning to drive!");
        }

        System.out.println("On your next birthday, you will be " + (myAge + 1) + " years old!");
    }
}

Main.main(null);

```

    Current age: 15
    On your next birthday, you will be 16 years old!
    
    Current age: 10
    On your next birthday, you will be 11 years old!


# Unit 3.3

1. Based on this code, if you were younger than 16 what would it print out?
   1. The code would say that "you are not old enough for a license yet." This is because your age would be under 16.
2. Write your own if else statement


```java
int grade = 90;

if (grade >= 90) {
    System.out.println("you have an A!");
}
else {
    System.out.println("you don't have an A");
}
```

    you have an A!


# Unit 3.4


1. If I was 19 what would it print out?
   1. It would print out that you can register to vote and that you are old enough for a driver's license. This is because 19 is >= 19. The code evaluates to true, and it prints the above.
2. If I was 13 what would it print out?
   1. Your age would be printed, but nothing else would be printed. It would go through all the test cases and evaluate to false. Once at the end, it will finish.
3. Create your if statement with one else if condition.



```java
int grade = 85;

if (grade >= 90) {
    System.out.println("you have an A!");
}
else if (grade >= 80) {
    System.out.println("you have a B");
}
else {
    System.out.println("you don't have an A");
}
```

    you have a B


# Unit 3.5

## Popcorn Hack 1


```java
function checkMembershipEligibility() {
    // Get user input
    let age = parseInt(prompt("Enter your age:"));  // Age input
    let income = parseFloat(prompt("Enter your annual income:"));  // Annual income input
    let isStudent = prompt("Are you a student? (yes/no):").toLowerCase() === 'yes';  // Student status input

    // Initialize an empty array to hold results
    let results = [];

    // Check eligibility for different memberships

    // Basic Membership
    if (age >= 18 && income >= 20000) {
        results.push("You qualify for Basic Membership.");
    }

    // Premium Membership
    if (age >= 25 && income >= 50000) {
        results.push("You qualify for Premium Membership.");
    }

    // Student Discount
    if (isStudent) {
        results.push("You are eligible for a Student Discount.");
    }

    // Senior Discount
    if (age >= 65) {
        results.push("You qualify for a Senior Discount.");
    }

    // If no eligibility, provide a default message
    if (results.length === 0) {
        results.push("You do not qualify for any memberships or discounts.");
    }

    // Output all results
    results.forEach(result => console.log(result));
}

// Call the function to execute
checkMembershipEligibility();

```


    |       let isStudent = prompt("Are you a student? (yes/no):").toLowerCase() === 'yes';  // Student status input

    illegal start of expression

    

    |       let isStudent = prompt("Are you a student? (yes/no):").toLowerCase() === 'yes';  // Student status input

    unclosed character literal

    

    |       let isStudent = prompt("Are you a student? (yes/no):").toLowerCase() === 'yes';  // Student status input

    unclosed character literal

    

    |       let isStudent = prompt("Are you a student? (yes/no):").toLowerCase() === 'yes';  // Student status input

    not a statement

    

    |       let results = [];

    illegal start of expression

    

    |       if (results.length === 0) {

    illegal start of expression

    

    |       results.forEach(result => console.log(result));

    illegal start of expression

    


The purpose of the checkMembershipEligibility function is to determine which memberships or discounts a user qualifies for based on three inputs:

1. Age
2. Annual income
3. Whether the user is a student

Based on these inputs, the function checks the user’s eligibility for:

1. Basic Membership
2. Premium Membership
3. Student Discount
4. Senior Discount

The function stores all eligible membership/discounts in the results array and then prints the results.

- `if (age >= 18 && income >= 20000)`
  - The user qualifies for Basic Membership if their age is 18 or older and their annual income is 20,000 or more.
- `if (age >= 25 && income >= 50000)`
  - The user qualifies for Premium Membership if they are 25 or older and have an annual income of 50,000 or more.
- `if (isStudent)`
  - The user qualifies for a Student Discount if they answer "yes" to being a student.
- `if (age >= 65)`
  - The user qualifies for a Senior Discount if they are 65 or older.
- `if (results.length === 0)`
  - If none of the conditions are met, a default message is added to the results array: "You do not qualify for any memberships or discounts."

**Output for Input:**

- Age: 20
- Annual income: 1500
- Student status: yes

Step-by-Step Evaluation:

1. Basic Membership:
- age = 20 (greater than or equal to 18) ✅
- income = 1500 (less than 20,000) ❌
- Result: Does not qualify for Basic Membership.

2. Premium Membership:
- age = 20 (less than 25) ❌
- Result: Does not qualify for Premium Membership.

3. Student Discount:
- isStudent = true (since the user is a student) ✅
- Result: Eligible for Student Discount.

4. Senior Discount:
- age = 20 (less than 65) ❌
- Result: Does not qualify for Senior Discount.

Since the user qualifies for the Student Discount, the output will be: "You are eligible for a Student Discount."


## Popcorn Hack 2


```java
public class Main {
    public static void main(String[] args) {
        int age = 30; // Change this value for testing
        boolean isStudent = true; // Change this value for testing

        // Check for discounts based on age and student status
        if (age < 25) {
            System.out.println("You qualify for the Youth Discount.");
        } else if (age >= 70) {
            System.out.println("You qualify for the Senior Discount.");
        } else if (isStudent) {
            System.out.println("You qualify for the Student Discount.");
        } else {
            System.out.println("Sorry, you do not qualify for any discounts.");
        }
    }
}

Main.main(null);

```

    You qualify for the Student Discount.


# Unit 3.6

## Popcorn Hack


1. What is `!(x == 0)` equivalent to?
- De Morgan's Law states that the negation of a conjunction (AND) or disjunction (OR) can be expressed as a disjunction or conjunction of the negations. It gives us rules like:
  - `!(A && B)` is equivalent to `!A || !B`
  - `!(A || B)` is equivalent to `!A && !B`
- However, in the expression `!(x == 0)`, we don't have a conjunction or disjunction; we just have a single condition. But we can still apply simple negation rules.
- `x == 0` checks if x is equal to 0.
- `!(x == 0)` negates that condition, meaning that x is not equal to 0.
- So, `!(x == 0)` is equivalent to:
  - `x != 0`
2. Negate the expression `(x < -5 || x > 10)`.
- Here, we are given the expression `(x < -5 || x > 10)` and asked to negate it. We can apply De Morgan's Law to rewrite it.

- The original expression is a disjunction (`||`), so we use the rule for negating a disjunction:
  - `!(A || B)` is equivalent to `!A && !B`
- Now, let’s break down the expression:
  - `A` is `x < -5`
  - `B` is `x > 10`
- Using De Morgan's Law:
  - `!(x < -5 || x > 10)` becomes `!(x < -5) && !(x > 10)`
- Negating the individual conditions:
  - `!(x < -5)` is equivalent to `x >= -5`
  - `!(x > 10)` is equivalent to `x <= 10`
- Thus, the negation of `(x < -5 || x > 10)` is:
  - `(x >= -5 && x <= 10)`
3. TLDR:
   1. `!(x == 0)` is equivalent to `x != 0.`
   2. The negation of `(x < -5 || x > 10)` is `(x >= -5 && x <= 10)`.

# Unit 3.7


```java
class House {
    private String color;
    private int size;

    public House(String color, int size) {
        this.color = color;
        this.size = size;
    }

    // Override equals method to compare House objects by content
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;  // Check if same object reference
        if (obj == null || getClass() != obj.getClass()) return false;  // Check if same class
        House house = (House) obj;
        return size == house.size && color.equals(house.color);  // Compare attributes
    }
}

public class Main {
    public static void main(String[] args) {
        House myHouse = new House("green", 150);
        House anikasHouse = new House("green", 150);
        House sharonsHouse = new House("green", 150);

        // Correct comparison using equals()
        System.out.println(myHouse.equals(sharonsHouse));  // This should return true
    }
}

Main.main(null)

```

    true


Yes, **Sharon's house and your house would be considered the same** according to the implementation of the `House` class.

- The `House` class has an overridden `equals()` method that compares two `House` objects based on their attributes, specifically the `color` and `size`.
- The `equals()` method first checks if the object references are the same, and if not, it proceeds to compare the `color` and `size` of the houses.


- **`myHouse`** is created as `new House("green", 150)`.
- **`sharonsHouse`** is created as `new House("green", 150)`.

Both houses have the same `color` ("green") and `size` (150). Since the `equals()` method compares both these attributes and finds them equal, it will return `true` when you check `myHouse.equals(sharonsHouse)`.

According to the `equals()` method, **Sharon's house and your house are the same** because their `color` and `size` match.

# Unit 3.8 - HW


```java
import java.util.Scanner;

public class PrimeClubMembership {
    public static void main(String[] args) {
        // Create a Scanner object to read user input
        Scanner scanner = new Scanner(System.in);

        // Prompt user for input
        System.out.print("Enter your age: ");
        int age = Integer.parseInt(scanner.nextLine());

        System.out.print("Enter your annual income: ");
        double income = Double.parseDouble(scanner.nextLine());

        System.out.print("Are you a student? (yes/no): ");
        boolean isStudent = scanner.nextLine().equalsIgnoreCase("yes");

        System.out.print("What is your employment type? (full-time, part-time, unemployed): ");
        String employmentType = scanner.nextLine().toLowerCase();

        // Initialize result variables
        boolean qualifiesForBasic = age >= 18 && income >= 20000;
        boolean qualifiesForPremium = age >= 25 && income >= 50000;
        boolean qualifiesForStudent = isStudent;
        boolean qualifiesForSenior = age >= 65;

        // Check for all memberships and discounts
        if (qualifiesForPremium) {
            System.out.println("You qualify for Premium Membership.");
        } else if (qualifiesForSenior) {
            System.out.println("You qualify for Senior Discount.");
        } else if (qualifiesForStudent) {
            System.out.println("You qualify for Student Discount.");
        } else if (qualifiesForBasic) {
            System.out.println("You qualify for Basic Membership.");
        } else {
            System.out.println("You do not qualify for any memberships or discounts.");
        }

        // Close scanner
        scanner.close();
    }
}

PrimeClubMembership.main(null);
```

    Enter your age: Enter your annual income: Are you a student? (yes/no): What is your employment type? (full-time, part-time, unemployed): You qualify for Student Discount.

