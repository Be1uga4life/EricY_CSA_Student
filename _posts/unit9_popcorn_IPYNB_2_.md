---

---

```java
public class Shape {
    protected String name;
    private int length;
    private int width;

    // Default constructor
    public Shape() {
        this.name = "Shape";
        this.length = 10;
        this.width = 5;
    }

    // Parameterized constructor
    public Shape(String name, int length, int width) {
        this.name = name;
        this.length = length;
        this.width = width;
    }

    // Getter methods
    public String get_name() {
        return this.name;
    }

    public int get_length() {
        return this.length;
    }

    public int get_width() {
        return this.width;
    }

    // Setter methods
    public void set_name(String n) {
        this.name = n;
    }

    public void set_length(int a) {
        this.length = a;
    }

    public void set_width(int b) {
        this.width = b;
    }
}

public class Circle extends Shape {
    public Circle() {
        super();
    }

    public Circle(String name, int radius) {
        super(name, radius, radius); // Using radius for both dimensions since it's a circle
    }
}

public class Hexagon extends Shape {
    public Hexagon() {
        super();
    }

    public Hexagon(String name, int sideLength) {
        super(name, sideLength, sideLength); // Using sideLength for both dimensions as a simplification
    }
}

```

### Popcorn Hack 2 (optional)


```java
public class Shape {
    protected String name;
    private int length;
    private int width;

    // Default constructor
    public Shape() {
        this.name = "Shape";
        this.length = 10;
        this.width = 5;
    }

    // Parameterized constructor
    public Shape(String name, int length, int width) {
        this.name = name;
        this.length = length;
        this.width = width;
    }

    // Getter methods
    public String get_name() {
        return this.name;
    }

    public int get_length() {
        return this.length;
    }

    public int get_width() {
        return this.width;
    }

    // Setter methods
    public void set_name(String n) {
        this.name = n;
    }

    public void set_length(int a) {
        this.length = a;
    }

    public void set_width(int b) {
        this.width = b;
    }

    // Method to calculate the area
    public double calc_area() {
        return this.length * this.width;
    }

    // Method to print the shape
    public void print_shape() {
        System.out.println("Shape: " + this.name);
    }

    // Additional method to print something
    public void print_something() {
        System.out.println("This is a shape");
    }
}

public class Rectangle extends Shape {
    public Rectangle() {
        super();
    }

    public Rectangle(String name, int length, int width) {
        super(name, length, width);
    }

    @Override
    public double calc_area() {
        return (this.get_length() * this.get_width());
    }

    @Override
    public void print_something() {
        System.out.println("This is a rectangle");
    }
}

public class Triangle extends Shape {
    public Triangle() {
        super();
    }

    public Triangle(String name, int length, int width) {
        super(name, length, width);
    }

    @Override
    public double calc_area() {
        return (get_length() * get_width() * 0.5);
    }
}


public class Ellipse extends Shape {
    public Ellipse(String name, int length, int width) {
        super(name, length, width); // Calling the superclass constructor
    }

    @Override
    public double calc_area() {
        return Math.PI * (get_length() / 2.0) * (get_width() / 2.0); // Using semi-major and semi-minor axes
    }

    @Override
    public void print_something() {
        System.out.println("This is an ellipse");
    }
}


public class Driver {
    public static void main(String[] args) {
        Shape s1 = new Shape();
        Shape s2 = new Rectangle("rectangle", 4, 10);
        Shape s3 = new Triangle("triangle", 5, 20);
        Shape s4 = new Ellipse("ellipse", 5, 20);

        System.out.println("Area of s1 = " + s1.calc_area());
        System.out.println("Area of s2 = " + s2.calc_area());
        System.out.println("Area of s3 = " + s3.calc_area());
        System.out.println("Area of s4 = " + s4.calc_area());

        s1.print_shape();
        s2.print_shape();
        s4.print_shape();

        // Using the overridden method
        s1.print_something();
        s2.print_something();
        s4.print_something();
    }
}

// Run the driver code
Driver.main(new String[0]);

```

    Area of s1 = 50.0
    Area of s2 = 40.0
    Area of s3 = 50.0
    Area of s4 = 78.53981633974483
    Shape: Shape
    Shape: rectangle
    Shape: ellipse
    This is a shape
    This is a rectangle
    This is an ellipse


### Popcorn Hack 3


```java
public class Triangle extends Shape {
    private int side1;
    private int side2;
    private int side3;

    public Triangle() {
        super("triangle", 0, 0); // Call to Shape constructor to set the name
        this.side1 = 1;
        this.side2 = 2;
        this.side3 = 3;
    }

    // Constructor that takes a name and three side lengths
    public Triangle(String name, int s1, int s2, int s3) {
        super(name, 0, 0); // Call to Shape constructor to set the name
        this.side1 = s1;
        this.side2 = s2;
        this.side3 = s3;
    }

    @Override
    public double calc_area() {
        // Semi-perimeter calculation
        double s = (side1 + side2 + side3) / 2.0;

        // Heron's formula for the area
        double area = Math.sqrt(s * (s - side1) * (s - side2) * (s - side3));

        return area;
    }
}

Triangle t1 = new Triangle("triangle", 3, 4, 5);
t1.print_shape();
System.out.println("Area of t1 = " + t1.calc_area());
```

    Shape: triangle
    Area of t1 = 6.0


### Popcorn Hack 4


```java
public class Shape {
    protected String name;
    private int length;
    private int width;

    // Default constructor
    public Shape() {
        this.name = "Shape";
        this.length = 10;
        this.width = 5;
    }

    // Parameterized constructor
    public Shape(String name, int length, int width) {
        this.name = name;
        this.length = length;
        this.width = width;
    }

    // Getter methods
    public String get_name() {
        return this.name;
    }

    public int get_length() {
        return this.length;
    }

    public int get_width() {
        return this.width;
    }

    // Setter methods
    public void set_name(String n) {
        this.name = n;
    }

    public void set_length(int a) {
        this.length = a;
    }

    public void set_width(int b) {
        this.width = b;
    }

    // Method to calculate the area
    public double calc_area() {
        return this.length * this.width;
    }

    // Method to calculate the perimeter (default implementation for shapes)
    public double calc_perimeter() {
        // Default implementation for perimeter (can be overridden by subclasses)
        return 2 * (this.length + this.width);
    }

    // Method to print the shape
    public void print_shape() {
        System.out.println("Shape: " + this.name);
    }
}

public class Triangle extends Shape {
    private int side1;
    private int side2;
    private int side3;

    public Triangle() {
        super("triangle", 0, 0); // Call to Shape constructor to set the name
        this.side1 = 1;
        this.side2 = 2;
        this.side3 = 3;
    }

    // Constructor that takes a name and three side lengths
    public Triangle(String name, int s1, int s2, int s3) {
        super(name, 0, 0); // Call to Shape constructor to set the name
        this.side1 = s1;
        this.side2 = s2;
        this.side3 = s3;
    }

    @Override
    public double calc_area() {
        // Semi-perimeter calculation
        double s = (side1 + side2 + side3) / 2.0;

        // Heron's formula for the area
        return Math.sqrt(s * (s - side1) * (s - side2) * (s - side3));
    }

    @Override
    public double calc_perimeter() {
        return side1 + side2 + side3; // Perimeter is the sum of all sides
    }
}

public class ShapeDriver {
    public static void main(String[] args) {
        Triangle ti84 = new Triangle("triangle", 3, 4, 5);
        System.out.println("Area: " + ti84.calc_area());      // Expected output: 6
        System.out.println("Perimeter: " + ti84.calc_perimeter());  // Expected output: 12
    }
}

Triangle ti84 = new Triangle("triangle", 3, 4, 5);
System.out.println(ti84.calc_area());
System.out.println(ti84.calc_perimeter());
```

    6.0
    12.0


### Popcorn Hack 5 (all of the parts are combined here)


```java
class Shape {
    public String draw() {
        return "Drawing a shape";
    }

    public double area() {
        return 0;  // Default area method, overridden by subclasses
    }
}

class Triangle extends Shape {
    private double base;
    private double height;

    public Triangle(double base, double height) {
        this.base = base;
        this.height = height;
    }

    @Override
    public double area() {
        return 0.5 * base * height;  // Area formula for a triangle
    }

    @Override
    public String draw() {
        return "Drawing a triangle";
    }
}

class Rectangle extends Shape {
    private double length;
    private double width;

    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    public double area() {
        return length * width;  // Area formula for a rectangle
    }

    @Override
    public String draw() {
        return "Drawing a rectangle";
    }
}

class Circle extends Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;  // Area formula for a circle
    }

    @Override
    public String draw() {
        return "Drawing a circle";
    }
}

class Square extends Shape {
    private double side;

    public Square(double side) {
        this.side = side;
    }

    @Override
    public double area() {
        return side * side;  // Area formula for a square
    }

    @Override
    public String draw() {
        return "Drawing a square";
    }
}

public class Main {
    public static void main(String[] args) {
        // Create instances of each shape
        Shape triangle = new Triangle(10, 5);
        Shape rectangle = new Rectangle(8, 4);
        Shape circle = new Circle(3);
        Shape square = new Square(6);

        // Output drawing and area for each shape
        System.out.println(triangle.draw() + " with area: " + triangle.area());
        System.out.println(rectangle.draw() + " with area: " + rectangle.area());
        System.out.println(circle.draw() + " with area: " + circle.area());
        System.out.println(square.draw() + " with area: " + square.area());
    }
}

Main.main(null)
```

    Drawing a triangle with area: 25.0
    Drawing a rectangle with area: 32.0
    Drawing a circle with area: 28.274333882308138
    Drawing a square with area: 36.0


### Homework Hack


```java
class Shape {
    // Base method for drawing a shape, meant to be overridden by subclasses
    public String draw() {
        return "Drawing a shape";  // Default behavior for generic shapes
    }
}

class Triangle extends Shape {
    @Override
    public String draw() {
        return "Drawing a triangle";  // Unique behavior for Triangle
    }
}

class Rectangle extends Shape {
    @Override
    public String draw() {
        return "Drawing a rectangle";  // Unique behavior for Rectangle
    }
}

class Hexagon extends Shape {
    @Override
    public String draw() {
        return "Drawing a hexagon";  // Unique behavior for Hexagon
    }
}

public class Main {
    public static void main(String[] args) {
        // Create instances of each shape
        Shape triangle = new Triangle();
        Shape rectangle = new Rectangle();
        Shape hexagon = new Hexagon();

        // Output the drawing message for each shape
        System.out.println(triangle.draw());
        System.out.println(rectangle.draw());
        System.out.println(hexagon.draw());
    }
}

Main.main(null)
```

    Drawing a triangle
    Drawing a rectangle
    Drawing a hexagon


### Popcorn Hack 6


```java
// Base class
class Animal {
    public void makeSound() {
        System.out.println("Some generic animal sound");
    }
}

// Subclass Dog
class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof! Woof!");
    }
}

// Subclass Cat
class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow! Meow!");
    }
}

// Main class to demonstrate polymorphism
public class Main {
    public static void main(String[] args) {
        // Create an array of Animal references
        Animal[] animals = new Animal[3];

        // Assign Dog and Cat objects to the Animal array
        animals[0] = new Dog();
        animals[1] = new Cat();
        animals[2] = new Dog();

        // Iterate through the array and call makeSound() on each animal
        for (Animal animal : animals) {
            animal.makeSound();  // Polymorphic call
        }
    }
}

Main.main(null)
```

    Woof! Woof!
    Meow! Meow!
    Woof! Woof!


Explanation:

Static types are defined by the variable declarations (Animal, Animal[]).
Dynamic types are determined by the actual objects instantiated at runtime (Dog, Cat).
This distinction allows for polymorphism, where the same method call (makeSound()) can result in different behavior depending on the dynamic type of the object being referenced.

Explanation of downcasting:

Down-casting is the process of converting a reference of a base class type to a reference of a derived class type. This is typically done when you have a reference to a base class (like Animal) but you want to access the specific features or methods of a derived class (like Dog or Cat). Down-casting can be risky because if the object is not actually of the derived class type, it can lead to a ClassCastException at runtime. Therefore, it's essential to ensure that the object being down-cast is indeed an instance of the derived class.




### Popcorn Hack 7


```java
class Fruit {
    private String name;

    public Fruit(String name) {
        this.name = name;
    }

    // Unchanged method from Object
    @Override
    public String toString() {
        return "This is a fruit.";
    }

    // Changed method from Object
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true; // Check if they are the same instance
        if (obj == null || getClass() != obj.getClass()) return false; // Check for null and type
        Fruit fruit = (Fruit) obj; // Down-cast
        return name.equals(fruit.name); // Compare fruit names
    }
}

public class Main {
    public static void main(String[] args) {
        Fruit apple = new Fruit("Apple");
        Fruit anotherApple = new Fruit("Apple");
        Fruit banana = new Fruit("Banana");

        // Execute the unchanged method from Object
        System.out.println(apple.toString()); // Output: This is a fruit.

        // Execute the changed method from Object
        System.out.println(apple.equals(anotherApple)); // Output: true
        System.out.println(apple.equals(banana)); // Output: false
    }
}

Main.main(null)
```

    This is a fruit.
    true
    false


___

### Homework Hacks

___

### FRQ

The Textbook class is a specialized extension of the Book class, designed to manage textbooks with additional features specific to their editions. It introduces a private integer field named edition, which represents the edition number of the textbook, along with a constructor that initializes the title, price, and edition while ensuring that the edition is a positive integer. The class includes a method, canSubstituteFor, which checks if the current textbook can substitute for another by comparing their titles and edition numbers. Furthermore, it overrides the getBookInfo method to provide a comprehensive string representation that includes the edition, enhancing the information provided by the superclass. The toString method is also overridden for convenient output, allowing users to easily access the textbook's details. Overall, this class encapsulates the additional properties of textbooks while leveraging the existing functionality of the Book class.

### MCQ

The correct answer is c) The toString() method must be public.

In Java, the toString() method is intended to be overridden from the Object class, and it should be public to ensure that it can be called when using System.out.println(myShape). Currently, the toString() method is private, which makes it inaccessible outside of the Shape class, meaning it won’t be automatically called when trying to print the object.

The correct answer is b) isSalty().

The isSalty() method is private in the Water class, which means it cannot be accessed or overridden in the Lake subclass. Although the Lake class has a public isSalty() method, it does not override the private method in the parent class, so it cannot be executed polymorphically on an instance of Water. The other methods (typeOfWater() and toString()) are public and can be executed, and getClass() is inherited from the Object class and can be called on any object.
