---

---

```Java
public class Student {
    private String name;
    private int score;

    // Default constructor
    public Student() {
        name = "";
        score = 0;   
    }

    // Overloaded constructor
    public Student(String n, int s) {
        name = n;
        setScore(s); // Ensure validation for score
    }

    // Accessor Methods
    public String getName() {
        return name;
    }

    public int getScore() {
        return score;
    }

    // Mutator Methods
    public void setName(String n) {
        name = n;
    }

    public void setScore(int s) {
        if (s < 0 || s > 100) {
            score = 0; // default value if invalid score
        } else {
            score = s;
        }
    }

    // Method to check if the student passes
    public boolean pass() {
        return score > 70;
    }
}
```

### Popcorn Hack 2


```Java
public class Student {
    private String name;
    private int score;

    // Default constructor
    public Student() {
        name = "";
        score = 0;   
    }

    // Overloaded constructor with name and score
    public Student(String name, int score) {
        this.name = name;
        setScore(score); // Using the setter method to validate the score
    }

    // New overloaded constructor with only name
    public Student(String name) {
        this.name = name;
        this.score = 0; // default score
    }

    // Accessor Methods
    public String getName() {
        return name;
    }

    public int getScore() {
        return score;
    }

    // Mutator Methods
    public void setName(String name) {
        this.name = name;
    }

    public void setScore(int score) {
        if (score < 0 || score > 100) {
            this.score = 0; // default value if invalid score
        } else {
            this.score = score;
        }
    }

    // Method to check if the student passes
    public boolean pass() {
        return score > 70;
    }
}

```

### Popcorn Hack 3


```Java
public class Minion {
    private String name;
    private String task;
    private int skillLevel; // Create skillLevel instance variable

    // Constructor to initialize name, task, and skillLevel
    public Minion(String name, String task, int skillLevel) {
        this.name = name;
        this.task = task;
        this.skillLevel = skillLevel;
    }

    // Getter Methods
    public String getName() {
        return name;
    }

    public String getTask() {
        return task;
    }

    // Getter method for skillLevel
    public int getSkillLevel() {
        return skillLevel;
    }
}

// Create a Minion object and print values
Minion Stuart = new Minion("Stuart", "Developing propulsion system", 7);
System.out.println(Stuart.getName());
System.out.println(Stuart.getTask());
System.out.println(Stuart.getSkillLevel()); // Print skillLevel

```

    Stuart
    Developing propulsion system
    7


### Popcorn Hack 4


```Java
public class Minion {
    // Instance variables
    private double height;
    private String name;
    private String hair;
    private int eyes;

    // Default Constructor
    public Minion() {
        height = 3.7;
        name = "Bob";
        hair = "None";
        eyes = 2;
    }

    // Overloaded Constructor
    public Minion(double h, String n, String hr, int e) {
        height = h;
        name = n;
        hair = hr;
        eyes = e;
    }

    // toString method to return all instance variables as a formatted string
    public String toString() {
        return "Minion{name='" + name + "', height=" + height + " feet, hair='" + hair + "', eyes=" + eyes + "}";
    }
}

// Create minion object Kevin
Minion kevin = new Minion(4.10, "Kevin", "Sprout-Cut", 2);

// Print Kevin object
System.out.println(kevin);

```

    Minion{name='Kevin', height=4.1 feet, hair='Sprout-Cut', eyes=2}


### Popcorn Hack 5 (Your Turn 5.5)


```Java
public class Book {
    private String title;
    private String author;
    private int pages;

    // Constructor to initialize all the fields
    public Book(String title, String author, int pages) {
        this.title = title;
        this.author = author;
        this.pages = pages;
    }

    // Getter method for title
    public String getTitle() {
        return title;
    }

    // Setter method for pages
    public void setPages(int pages) {
        if (pages > 0) { // Ensure pages are positive
            this.pages = pages;
        } else {
            System.out.println("Invalid page count! Pages must be greater than 0.");
        }
    }

    // Getter method for pages (just for printing)
    public int getPages() {
        return pages;
    }

    // toString method to print Book details
    public String toString() {
        return "Book{title='" + title + "', author='" + author + "', pages=" + pages + "}";
    }
}

// Example usage:
public class krill {
    public static void main(String[] args) {
        // Create a Book object using the constructor
        Book myBook = new Book("The Great Adventure", "John Doe", 350);
        
        // Print the initial details of the book
        System.out.println(myBook);

        // Use the getter to retrieve the book's title
        System.out.println("The book title is: " + myBook.getTitle());

        // Use the setter to update the number of pages
        myBook.setPages(400);

        // Print the updated details of the book
        System.out.println("Updated book details: " + myBook);
    }
}

krill.main(null)

```

    Book{title='The Great Adventure', author='John Doe', pages=350}
    The book title is: The Great Adventure
    Updated book details: Book{title='The Great Adventure', author='John Doe', pages=400}


### Popcorn Hack 6


```Java
import java.util.ArrayList;
import java.util.List;

public class Villain {
    // Instance variables
    public String name;
    public String evilPlan;
    public List<String> minions;
    public static int villainCount = 0;

    // Constructor for name, plan, and minions
    public Villain(String name, String evilPlan) {
        this.name = name;
        this.evilPlan = evilPlan;
        this.minions = new ArrayList<>();
        villainCount++;
    }

    // Instance method to add a minion
    public void addMinion(String minion) {
        minions.add(minion);
        System.out.println(minion + " has been added to " + name + "'s army.");
    }

    // Instance method to describe the villain
    public void describeVillain() {
        System.out.println(name + " is planning to: " + evilPlan);
        System.out.println("They have " + minions.size() + " minions.");
    }

    // Static method to get the total count of villains
    public static int getVillainCount() {
        return villainCount;
    }

    // New static method for a fun battle between villains
    public static void battleOfVillains(Villain v1, Villain v2) {
        System.out.println("=== Villain Battle! ===");
        System.out.println(v1.name + " vs " + v2.name);

        if (v1.minions.size() > v2.minions.size()) {
            System.out.println(v1.name + " wins the battle with more minions!");
        } else if (v2.minions.size() > v1.minions.size()) {
            System.out.println(v2.name + " wins the battle with more minions!");
        } else {
            System.out.println("It's a tie! Both villains have the same number of minions.");
        }
    }
}

public class skibidi {
    public static void main(String[] args) {
        Villain.villainCount = 0;

        // Create new villains
        Villain gru = new Villain("Gru", "steal the moon!");
        Villain vector = new Villain("Vector", "take over the world with magnitude and direction!");

        System.out.println("=== Adding Minions ===");
        // Create some minions for Gru
        gru.addMinion("Kevin");
        gru.addMinion("Stuart");
        gru.addMinion("Bob");

        // Create some minions for Vector
        vector.addMinion("Henchman 1");
        vector.addMinion("Henchman 2");

        System.out.println();

        // Describe the villains and their plans
        System.out.println("=== Villain Descriptions ===");
        gru.describeVillain();
        System.out.println();
        vector.describeVillain();
        System.out.println();

        // Get the total count of villains
        System.out.println("=== Total Villain Count ===");
        System.out.println("There are " + Villain.getVillainCount() + " villains in the world.");
        System.out.println();

        // Villain battle to see who has more minions
        Villain.battleOfVillains(gru, vector);
    }
}

skibidi.main(null)

```

    === Adding Minions ===
    Kevin has been added to Gru's army.
    Stuart has been added to Gru's army.
    Bob has been added to Gru's army.
    Henchman 1 has been added to Vector's army.
    Henchman 2 has been added to Vector's army.
    
    === Villain Descriptions ===
    Gru is planning to: steal the moon!
    They have 3 minions.
    
    Vector is planning to: take over the world with magnitude and direction!
    They have 2 minions.
    
    === Total Villain Count ===
    There are 2 villains in the world.
    
    === Villain Battle! ===
    Gru vs Vector
    Gru wins the battle with more minions!


### Popcorn Hack 7


```Java
import java.util.List;
import java.util.ArrayList;

public class Minion {
    // Instance variables
    private String name;
    private List<String> gadgets;
    private String personality;
    private String task;

    // Constructor
    public Minion(String name, String personality) {
        this.name = name;
        this.personality = personality;
        this.gadgets = new ArrayList<>(); // Initialize gadgets as an empty list
        this.task = "None assigned yet"; // Default task
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Getter for personality
    public String getPersonality() {
        return personality;
    }

    // Setter for task
    public void assignTask(String task) {
        this.task = task;
    }

    // Getter for task
    public String getTask() {
        return task;
    }

    // Add a gadget to the minion's list of gadgets
    public void addGadget(String gadget) {
        gadgets.add(gadget);
        System.out.println(gadget + " has been added to " + name + "'s gadgets.");
    }

    // Display all gadgets of the minion
    public void displayGadgets() {
        System.out.println(name + "'s gadgets: " + String.join(", ", gadgets));
    }

    // Describe the minion with its attributes
    public void describeMinion() {
        System.out.println("Name: " + name);
        System.out.println("Personality: " + personality);
        System.out.println("Task: " + task);
        displayGadgets();
    }
}

public class Main {
    public static void main(String[] args) {
        // Create a few minions
        Minion kevin = new Minion("Kevin", "Brave");
        Minion stuart = new Minion("Stuart", "Playful");
        Minion bob = new Minion("Bob", "Cheerful");

        // Assign tasks to minions
        kevin.assignTask("Lead the moon-stealing mission.");
        stuart.assignTask("Develop the rocket's propulsion system.");
        bob.assignTask("Manage the distraction team.");

        // Add gadgets to each minion
        kevin.addGadget("Shrink Ray");
        kevin.addGadget("Jetpack");

        stuart.addGadget("Banana Blaster");

        bob.addGadget("Fart Gun");

        // Describe each minion
        System.out.println("=== Minion Descriptions ===");
        kevin.describeMinion();
        System.out.println();
        stuart.describeMinion();
        System.out.println();
        bob.describeMinion();
    }
}

Main.main(null)
```

    Shrink Ray has been added to Kevin's gadgets.
    Jetpack has been added to Kevin's gadgets.
    Banana Blaster has been added to Stuart's gadgets.
    Fart Gun has been added to Bob's gadgets.
    === Minion Descriptions ===
    Name: Kevin
    Personality: Brave
    Task: Lead the moon-stealing mission.
    Kevin's gadgets: Shrink Ray, Jetpack
    
    Name: Stuart
    Personality: Playful
    Task: Develop the rocket's propulsion system.
    Stuart's gadgets: Banana Blaster
    
    Name: Bob
    Personality: Cheerful
    Task: Manage the distraction team.
    Bob's gadgets: Fart Gun


### Popcorn Hack #8


```Java
import java.util.ArrayList;
import java.util.List;

public class Gadget {
    public static int totalGadgets = 0;  // Static variable to track total gadgets made
    private String gadgetName;  // Instance variable to store the name of the gadget
    private double cost;  // Instance variable to store the cost of the gadget
    public static List<Gadget> gadgetsList = new ArrayList<>();  // Static list to track all gadgets

    // Constructor to set the gadget name and cost, increment totalGadgets
    public Gadget(String gadgetName, double cost) {
        this.gadgetName = gadgetName;
        this.cost = cost;
        totalGadgets++;  // Increment the total gadgets count
        gadgetsList.add(this);  // Add this gadget to the static list
    }

    // Getter method for the gadget name
    public String getGadgetName() {
        return gadgetName;
    }

    // Getter method for the cost
    public double getCost() {
        return cost;
    }

    // Static method to calculate the total cost of all gadgets
    public static double calculateTotalCost() {
        double totalCost = 0;
        for (Gadget g : gadgetsList) {
            totalCost += g.getCost();  // Add the cost of each gadget to the total cost
        }
        return totalCost;
    }

    // Static method to display all gadgets created
    public static void displayAllGadgets() {
        System.out.println("All gadgets created:");
        for (Gadget g : gadgetsList) {
            System.out.println("- " + g.getGadgetName() + " (Cost: $" + g.getCost() + ")");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        // Create three gadgets with their costs
        Gadget g1 = new Gadget("Freeze Ray", 200.50);
        Gadget g2 = new Gadget("Banana Blaster", 150.75);
        Gadget g3 = new Gadget("Lipstick Taser", 120.00);

        // Print the total number of gadgets
        System.out.println("Total gadgets made: " + Gadget.totalGadgets);

        // Display all the gadgets with their costs
        Gadget.displayAllGadgets();

        // Calculate and print the total cost of all gadgets
        double totalCost = Gadget.calculateTotalCost();
        System.out.println("Total cost of all gadgets: $" + totalCost);
    }
}

Main.main(null)
```

    Total gadgets made: 3
    All gadgets created:
    - Freeze Ray (Cost: $200.5)
    - Banana Blaster (Cost: $150.75)
    - Lipstick Taser (Cost: $120.0)
    Total cost of all gadgets: $471.25


### Popcorn Hack 9


```Java
public class MinionMood {
    private int happinessLevel;  // Instance variable to store happiness level
    private int energyLevel;      // Instance variable to store energy level

    // Constructor to initialize happiness and energy levels based on bananas and tasks
    public MinionMood(int bananas, int tasks) {
        this.happinessLevel = 2 * bananas;  // Assign to instance variable
        this.energyLevel = tasks;             // Assign to instance variable
    }

    // Override toString method to display happiness and energy levels
    public String toString() {
        return "Happiness Level: " + happinessLevel + "\nEnergy Level: " + energyLevel;
    }
}

// Main method to create a MinionMood object
public class Main {
    public static void main(String[] args) {
        MinionMood bob = new MinionMood(5, 2);
        System.out.println(bob);
    }
}

Main.main(null)
```

    Happiness Level: 10
    Energy Level: 2


### Popcorn Hack 10


```Java
public class Minion {
    private String name;
    private double height;  // Height in meters
    private double speed;   // Speed in meters per second

    // Constructor
    public Minion(String name, double height, double speed) {
        this.name = name;
        this.height = height;
        this.speed = speed;
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public double getHeight() {
        return height;
    }

    public double getSpeed() {
        return speed;
    }

    // Method to compare two minions based on height and speed
    public static void compareMinions(Minion minion1, Minion minion2) {
        System.out.println("Comparing " + minion1.getName() + " and " + minion2.getName() + ":");

        // Compare height
        if (minion1.getHeight() > minion2.getHeight()) {
            System.out.println(minion1.getName() + " is taller.");
        } else if (minion1.getHeight() < minion2.getHeight()) {
            System.out.println(minion2.getName() + " is taller.");
        } else {
            System.out.println("Both minions are of the same height.");
        }

        // Compare speed
        if (minion1.getSpeed() > minion2.getSpeed()) {
            System.out.println(minion1.getName() + " is faster.");
        } else if (minion1.getSpeed() < minion2.getSpeed()) {
            System.out.println(minion2.getName() + " is faster.");
        } else {
            System.out.println("Both minions have the same speed.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        // Create minion objects
        Minion kevin = new Minion("Kevin", 1.2, 3.5);  // Height in meters, speed in m/s
        Minion bob = new Minion("Bob", 1.1, 4.0);
        Minion stuart = new Minion("Stuart", 1.2, 3.0);

        // Compare minions
        Minion.compareMinions(kevin, bob);
        System.out.println();
        Minion.compareMinions(kevin, stuart);
        System.out.println();
        Minion.compareMinions(bob, stuart);
    }
}

Main.main(null)
```

    Comparing Kevin and Bob:
    Kevin is taller.
    Bob is faster.
    
    Comparing Kevin and Stuart:
    Both minions are of the same height.
    Kevin is faster.
    
    Comparing Bob and Stuart:
    Stuart is taller.
    Bob is faster.


### Explanation/Questions things

1. What is the output of the statement System.out.println(“minion 1 speed: “ + minion1.speed())? Explain why the this keyword is useful in the getSpeed() method.

Output of System.out.println("minion 1 speed: " + minion1.speed()): This line will cause a compilation error because there is no speed() method. You should use minion1.getSpeed() instead.

2. What does the isTallerThan() method compare?

The isTallerThan() method compares the height of one minion to another. It checks if the current minion is taller than the other minion passed to it.

3. What happens to the result of System.out.println(“Is minion1 taller than minion2? “ + minion1.isTallerThan(minion2)) after minion2.setHeight(50) is called?

After setting minion2's height to 50, when you check if minion1 is taller, it will return false because minion1 (43) is not taller than minion2 (50).









```Java

```
