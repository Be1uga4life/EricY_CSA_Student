---
layout: post
toc: True
title: Unit 7 ArrayList P3
description: A Unit of documents that overview Array Lists in Java
authors: Drishya, Arnav, Tanuj, Jason
categories: ['AP CSA']
type: ccc
permalink: /csa/unit7-p3/unit7-2
menu: nav/CSA_Units/csa_unit7_p3.html
---

# 7.3: Traversing Arrays

functions to traverse an array
- variable.get(i): retreives #i value.
- variable.remove(i): removes #i value from a list.
- variable.size(): retreives length of the array
- swapConsecutive(ArrayList<Double> myList): swaps items in an ArrayList


Possible strategies to iterate through a **for** loop:

![Conditions](https://github.com/user-attachments/assets/1a70acbb-d6d8-4a86-b0a5-583b11da8570)

regular while loops are syntaxed as follows:

![image](https://github.com/user-attachments/assets/a0eb6ae3-6dde-45e5-806b-e71bd608fcb7)


removing items within an array -> each item moves up a slot

![image](https://github.com/user-attachments/assets/0e67a4fa-52fa-4da3-8968-d803abfbf2e3)

Traversing backwards:

![image](https://github.com/user-attachments/assets/e05f5ada-57ce-4e2c-bd54-b665c5a57da8)


traversing using and enhanced for loop
    known as *for-each*
        goes from first to last order in an ArrayList
        easier to setup than for loop
structure consists of:

![image](https://github.com/user-attachments/assets/b47f5c6b-0509-40f2-b18e-ee9aae37a6b3)


Using a for each loop for same objective as before:

![image](https://github.com/user-attachments/assets/b7dd7f81-0c7e-4be8-a3bb-a726ba8867b5)

**Notes:** 
- Adding items to a for each loop will result in an exception
- modifying or adding items will not effect the Arraylist.
 Results in ConcurrentModificationException
- attempting to access an item outside of the Array bounds results in: ArrayIndexOutOfBoundsException

use this to make sure you can traverse ArrayLists


```Java
import java.util.ArrayList
```

<!-- Quiz Section -->
<section class="quiz" style="margin-top: 50px; padding: 20px; background-color: #1a1a1a; border-radius: 15px;">
  <h2 class="quiz-title">Quick Quiz</h2>
  <form id="quizForm" class="quiz-form">
    <p class="quiz-question">1. Which of the following are methods to interact with arrays?</p>
    <label><input type="radio" name="q1" value="swapConsecutive"> swapConsecutive</label><br>
    <label><input type="radio" name="q1" value="variable.get"> variable.get</label><br>
    <label><input type="radio" name="q1" value="All of the above"> All of the above</label><br><br>
    <p class="quiz-question">2. What happens when you run a command requesting the item arr[-1]?</p>
    <label><input type="radio" name="q2" value="nothing, it gets the last item"> nothing, it gets the last item</label><br>
    <label><input type="radio" name="q2" value="Your computer goes crazy and crashes"> Your computer goes crazy and crashes</label><br>
    <label><input type="radio" name="q2" value="you get the error ArrayIndexOutOfBoundsException"> you get the error ArrayIndexOutOfBoundsException</label><br><br>
    <button type="button" class="quiz-button" onclick="checkQuiz()">Submit</button>
  </form>

  <div id="result" class="quiz-result"></div>
</section>

<style>
  .quiz-title {
    color: #88bc4c;
    text-align: center;
    font-size: 32px;
    margin-bottom: 20px;
    animation: fadeIn 1s ease-in-out;
  }

  .quiz-form {
    color: #f0f0f0;
    font-size: 18px;
    animation: fadeInUp 1.5s ease-in-out;
  }

  .quiz-question {
    font-size: 22px;
    margin-bottom: 10px;
    color: #88bc4c;
    font-weight: bold;
  }

  .quiz-button {
    background-color: #88bc4c;
    padding: 10px 20px;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    font-size: 18px;
  }

  .quiz-button:hover {
    background-color: #76a742;
  }

  .quiz-result {
    margin-top: 20px;
    font-size: 22px;
    color: #88bc4c;
    text-align: center;
    opacity: 0;
    animation: fadeInResult 1.5s ease-in-out forwards;
  }

  /* Animations */
  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes fadeInResult {
    to {
      opacity: 1;
    }
  }
        
  /* From Uiverse.io by mrtqzbek11 */ 
  button {
    width: 165px;
    height: 62px;
    cursor: pointer;
    color: #fff;
    font-size: 17px;
    border-radius: 1rem;
    border: none;
    position: relative;
    background: #100720;
    transition: 0.1s;
  }
  
  button::after {
    content: '';
    width: 100%;
    height: 100%;
    background-image: radial-gradient( circle farthest-corner at 10% 20%,  rgba(136,188,76,1) 17.8%, rgba(54,99,27,1) 100.2% );
    filter: blur(15px);
    z-index: -1;
    position: absolute;
    left: 0;
    top: 0;
  }
  
  button:active {
    transform: scale(0.9) rotate(3deg);
    background: radial-gradient( circle farthest-corner at 10% 20%,  rgba(136,188,76,1) 17.8%, rgba(54,99,27,1) 100.2% );
    transition: 0.5s;
  }


  /* Smooth Radio Buttons Styling */
  input[type="radio"] {
    margin-right: 10px;
    accent-color: #88bc4c;
    transform: scale(1.5);
  }

  /* Form Spacing */
  label {
    display: block;
    margin-bottom: 10px;
  }
</style>

<script>
  function checkQuiz() {
    let score = 0;
    const answers = {
      q1: "All of the above",
      q2: "you get the error ArrayIndexOutOfBoundsException"
    };
    
    const form = document.getElementById("quizForm");
    if (form.q1.value === answers.q1) score++;
    if (form.q2.value === answers.q2) score++;
    
    document.getElementById("result").textContent = "You scored " + score + " out of 2. :))";
  }
