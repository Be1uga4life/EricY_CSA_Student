---
layout: post
title: Unit 2 - Using Objects
description: Team Teach Unit 2 Using Objects (By Shuban, Eric, Aadit, and Rahul)
type: issues
comments: True
---

## Topics (Collegeboard subsections)

- 2.1 Object - Instances of Classes
- 2.2 Creating and Storing Objects
- 2.3 Calling a Void Method
- 2.4 Calling a Void Method with Parameters
- 2.5 Calling a Non-Void Method
- 2.6 String Objects - Concatenation, Literals, and More
- 2.7 String Methods
- 2.8 Wrapper Classes - Integer and Double
- 2.9 Using the Math class


## Section 2.1: What is an Object? (Rahul)

## Section 2.2: Creating and Store Objects (Rahul)

## Section 2.3: Calling a Void Methods (Rahul)

## Section 2.4: Calling a Void Method with Parameters (Shuban)

## Section 2.5: Calling a Non-Void (Shuban)

## Section 2.6: String Objects - Concatenation, Literals, and More (Eric)

#### Creating Strings:


```java
public class stringobjects
{
    public static void main(String[] args)
    {
        String name1 = "Skibidi";
        String name2 = new String("Sigma");
        String name3 = new String(name1);

        System.out.print(name1);
    }
}

stringobjects.main(null);
```

    Skibidi

---

### 📝 Three Ways to Create a String: Let's Break it Down!

---

#### **First Option:**

<iframe
  src="https://carbon.now.sh/embed?bg=rgba%28171%2C+184%2C+195%2C+1%29&t=seti&wt=none&l=text%2Fx-java&width=680&ds=true&dsyoff=20px&dsblur=68px&wc=true&wa=true&pv=0px&ph=0px&ln=false&fl=1&fm=Hack&fs=14px&lh=133%25&si=false&es=2x&wm=false&code=String%2520name1%2520%253D%2520%2522Skibidi%2522%253B"
  style="width: 235px; height: 84px; border:0; transform: scale(1); overflow:hidden;"
  sandbox="allow-scripts allow-same-origin">
</iframe>


<span style="color:purple;">Class:</span> Defines the type of variable (String, Integer, Array, etc.)

<span style="color:turqoise;">Variable Name:</span> Represents the name assigned to the variable.

<span style="color:yellow;">String:</span> The actual string value assigned to the variable.

---

#### **Second Option:**

<iframe
  src="https://carbon.now.sh/embed?bg=rgba%28171%2C+184%2C+195%2C+1%29&t=seti&wt=none&l=text%2Fx-java&width=680&ds=true&dsyoff=20px&dsblur=68px&wc=true&wa=true&pv=0px&ph=0px&ln=false&fl=1&fm=Hack&fs=14px&lh=133%25&si=false&es=2x&wm=false&code=String%2520name2%2520%253D%2520new%2520String%28%2522Sigma%2522%29%253B"
  style="width: 319px; height: 79px; border:0; transform: scale(1); overflow:hidden;"
  sandbox="allow-scripts allow-same-origin">
</iframe>

Class: What type of variable will it be? (String, Integers, Arrays, etc.)

Variable name: The name of the variable

Java Keyword: The new keyword in Java is used to explicitly create a new object.

Class: The string that will be assigned to the variable

String: The string to be defined into the variable


---

#### **Third Option:**

<iframe
  src="https://carbon.now.sh/embed?bg=rgba%28171%2C+184%2C+195%2C+1%29&t=seti&wt=none&l=text%2Fx-java&width=680&ds=true&dsyoff=20px&dsblur=68px&wc=true&wa=true&pv=0px&ph=0px&ln=false&fl=1&fm=Hack&fs=14px&lh=133%25&si=false&es=2x&wm=false&code=String%2520string1%2520%253D%2520%2522YIPEE%2522%250AString%2520name2%2520%253D%2520new%2520String%28string1%29%253B"
  style="width: 318px; height: 96px; border:0; transform: scale(1); overflow:hidden;"
  sandbox="allow-scripts allow-same-origin">
</iframe>

Class: What type of variable will it be? (String, Integers, Arrays, etc.)

Variable name: The name of the variable

Java Keyword: The new keyword in Java is used to explicitly create a new object.

Class: The string that will be assigned to the variable


String Objects are immutable (can't be changed after assignment)

### 📝 What are Concatentations?

Concatentations are the joining of strings using operators such as "+=" and "+". 

There are two primary ways to combine strings:

- '+=' : Adds the two strings, redefines the variable
- '+' : Adds the two strings, but doesn't redfine the variable


```java
public class concatentations
{
    public static void main(String[] args)
    {
        String name1 = "Skibidi";
        String name2 = new String("Sigma");
        String name3 = new String(name1);

        int number1 = 1;
        int number2 = 2;
        String combine = name1 + "" + number1;
        name1 += number2; 

        System.out.println(name1); 
        System.out.println(combine);
    }
}

concatentations.main(null);
```

    Skibidi2
    Skibidi1


### 📝 Backwards and Forwards slashes and their purpose

\ = Used to start escape sequences
/ = Comments and division operators


#### Backslashes

\" = Print a double quote character

\\ = Prints a backslash character

\n = Prints on a new line




```java
public class SlashDemo {
    public static void main(String[] args) {
        // Using backslashes for escape sequences:
        System.out.println("This is a double quote: \"");  // Prints a double quote
        System.out.println("This is a backslash: \\");     // Prints a backslash
        System.out.println("This prints on a new line:\nSecond line starts here");

        // Using forward slashes for division and comments:
        int a = 10;
        int b = 2;
        int result = a / b; // Division operation

        System.out.println("Result of 10 / 2 is: " + result); // Prints the result of the division
    }
}

SlashDemo.main(null)
```

    This is a double quote: "
    This is a backslash: \
    This prints on a new line:
    Second line starts here
    Result of 10 / 2 is: 5


### 📝 String methods

| Method                                  | Description                                                                                             |
|-----------------------------------------|---------------------------------------------------------------------------------------------------------|
| `String(String str)`                    | Constructs a new `String` object that represents the same sequence of characters as `str`                |
| `int length()`                          | Returns the number of characters in a `String` object                                                    |
| `String substring(int from, int to)`    | Returns the substring beginning at index `from` and ending at index `to - 1`                             |
| `String substring(int from)`            | Returns `substring(from, length())`                                                                      |
| `int indexOf(String str)`               | Returns the index of the first occurrence of `str`; returns `-1` if not found                            |
| `boolean equals(String other)`          | Returns `true` if this is equal to `other`; returns `false` otherwise                                    |
| `int compareTo(String other)`           | Returns a value `< 0` if this is less than `other`; returns zero if this is equal to `other`; returns a value `> 0` if this is greater than `other` |




```java
public class intDemo {
    public static void main(String[] args) {
        String wordOfDay = new String("Skibidi");


        System.out.println("This should return the length of the word 'Skibidi'");
        System.out.println(wordOfDay.length());

    }
}

intDemo.main(null)
```

    This should return the length of the word 'Skibidi'
    7



```java
public class indexOfDemo {
    public static void main(String[] args) {
        String wordOfDay = new String("Skibidi");

        System.out.println("\nThis should return -1, since there is no n in the string");
        System.out.println(wordOfDay.lastIndexOf("n"));

        System.out.println("\nThis should display the index of d (5)");
        System.out.println(wordOfDay.lastIndexOf("d"));
    }
}

indexOfDemo.main(null)
```

    
    This should return -1, since there is no n in the string
    -1
    
    This should display the index of d (5)
    5



```java
public class substringOfDemo {
    public static void main(String[] args) {
        String word = new String("skibidi");

        System.out.println("\nThis should display the letters between the 2nd and 6th");
        System.out.println(word.substring(2,6));
    }
}

substringOfDemo.main(null)
```

    
    This should display the letters between the 2nd and 6th
    ibid



```java
public class compareToDemo {
    public static void main(String[] args) {
        String word = new String("skibidi");
        String word2 = new String("skibidi1");
        String word3 = new String("skibidi");

        System.out.println("\nThis displays if word1 = word2, if false it returns -1, if true it returns 0");
        System.out.println(word.compareTo(word2));

        System.out.println("\nThis displays if word1 = word3, if false it returns -1, if true it returns 0");
        System.out.println(word.compareTo(word3));
    }
}

compareToDemo.main(null)
```

    
    This displays if word1 = word2, if false it returns -1, if true it returns 0
    -1
    
    This displays if word1 = word2, if false it returns -1, if true it returns 0
    0



```java
public class equalToDemo {
    public static void main(String[] args) {
        String word = new String("skibidi");
        String word2 = new String("skibidi1");
        String word3 = new String("skibidi");

        System.out.println("\nThis displays if word1 = word2, if false it returns false, if true it returns true");
        System.out.println(word.equals((word2)));

        System.out.println("\nThis displays if word1 = word3, if false it returns false, if true it returns true");
        System.out.println(word.equals((word3)));
    }
}

equalToDemo.main(null)
```

    
    This displays if word1 = word2, if false it returns false, if true it returns true
    false
    
    This displays if word1 = word3, if false it returns false, if true it returns true
    true


## Section 2.8: Wrapper Classes - Integer and Double (Aadit)

## Section 2.9: Using the Math class (Aadit)






