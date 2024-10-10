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


```Java
public class stringobjects2_6
{
    public static void main(String[] args)
    {
        String name1 = "Skibidi";
        String name2 = new String("Sigma");
        String name3 = new String(name1);
    }
}
```

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


```Java
public class main
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


```

## Section 2.7: String Methods (Eric)



## Section 2.8: Wrapper Classes - Integer and Double (Aadit)

## Section 2.9: Using the Math class (Aadit)






