---
layout: post
title: CollegeBoard MCQ Corrections
description: CollegeBoard MCQ corrections
type: collab
toc: True
permalink: mcq/corrections
comments: True
author: Eric Yu
categories: ['Collaboration']
---

### Collegeboard MCQ

Question 4

![sdf](https://cdn.discordapp.com/attachments/1285436912823435264/1308207625988604016/image.png?ex=673d1acb&is=673bc94b&hm=8d0ad974e0966d28a1832111a57a8eba7b8528f7a22f321e9b114e4802165021&)

The class type is int, and int class types can't display decimals, so it would be 2 (rounding down)



Question 6

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308207785695117372/image.png?ex=673d1af1&is=673bc971&hm=8e79243ef42c1ec0ff41f7b09e32dfdd3318cd13516e8ce176cb1d412d7b92f4&=&format=webp&quality=lossless&width=935&height=587)

The two numbers that are being subtracted must be lower than the tolerance value. In the option I chose greater than, which would only return true if the differences between the two were greater than the allowed limit. 


```java

```

Question 16

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308208314923876422/image.png?ex=673d1b6f&is=673bc9ef&hm=bbb7412d2495a57cbe818908ca4a0199b9b6bf21be83ed50ff495cec5d79422f&=&format=webp&quality=lossless&width=1033&height=587)

There are three arrays in this example, the newly created "results" array, and a1 and a2. The first function populates the result array with a1. The second code increment then needs to append the a2 to the results. Because our index starts exactly where a1 ends off, we need to add one to shift the appending one over.

Question 21

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308208665475682314/image.png?ex=673d1bc3&is=673bca43&hm=7373139dff55710f13cd8690a3d7d187417f6a63b799f7d63d478bdfc17a5a65&=&format=webp&quality=lossless&width=857&height=587)

The new number that is found, needs to be subtracted from the value, and the difference between the two needs to be found. We need an absolute value in case the value is greater than the number. We also need to make sure that the difference is smaller than the mindiff variable, therefore D is the correct answer.

Question 23

![sdf](https://cdn.discordapp.com/attachments/1285436912823435264/1308209094783668314/image.png?ex=673d1c29&is=673bcaa9&hm=71b8d257a8ccfdf198765f686dcdc4150ff5a066278373bb405cd81a2c8866d0&)

The code starts at the very end of the array and iterates backwards. There is a conditional that checks if the letter at position 0 is "b". Then it moves the string back by the iteration(k) back. 

Therefore the only words that should be moved are bear, bass, baboon

However as you follow the iterations, you realize that the words eventually get replaced as you follow the logic, and the array doesn't actually get changed.

Question 24

![sdf](https://cdn.discordapp.com/attachments/1285436912823435264/1308209271430844486/image.png?ex=673d1c53&is=673bcad3&hm=9f6bd2fd41df019a69251c658649b0e61cabf60454eb25f96b9ea4f358bd3210&)

The code starts by intializing a 3x3 matrix that is empty. Then it starts iterating through the rows, until it reaches the third row, in which it will stop iterating through rows and move to columns. Then the cycle repeats. Therefore the numbers will start counting down from the column, and then keep moving. Therefore it will print the first row and third column (which will be 7).

Question 28

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308209747694190632/image.png?ex=673d1cc5&is=673bcb45&hm=e2c8704d11e23d36b1cf3c80f265284e40992dcd60a692325bbf8d0939bc5dd7&=&format=webp&quality=lossless&width=793&height=587)

The conditional within the loop quite legitmatley says while n>2, therefore there is no way for n to be anything other than greater than 2 at point b.

Question 31

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308237941361086494/image.png?ex=673d3707&is=673be587&hm=8389827384627a92c91c5601d41082e90faecf2c0139e29210784c536b06d6ab&=&format=webp&quality=lossless&width=921&height=587)

The code keeps executing by adding the next number from the arry onto the next item on the array. Therefore it goes:

5, 7, 8, 11, 19

Therefore the answer choice C is correct.

Question 34

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308210375912587354/image.png?ex=673d1d5a&is=673bcbda&hm=b79795efcf337b22cea5c360acad834c6165dfde4bd98281766e83490502c5a7&=&format=webp&quality=lossless&width=848&height=587)

Option 1: does not use the provided a and b values for the center.

Option 2: initializes center by passing a and b to the Point constructor, correctly setting the x and y coordinates.

Option 3: uses x and y, but they are private in the Point class, so direct access is not allowed.

Therefore only option 2 is correct

Question 36

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308210952440905799/image.png?ex=673d1de4&is=673bcc64&hm=f517504a92afd5d50b812d1004a58314c04104a58f5e8d7c535b2eadd916c4db&=&format=webp&quality=lossless&width=920&height=587)

There are three conditionals, whether the number is even, if it is greater than 9, and everything else (if the number is either less than 9 or 9)

The only option that has all these three conditions satisified is C

Question 38

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308211535432126524/image.png?ex=673d1e6f&is=673bccef&hm=22729929e59bc26c9065b6c8efc75915de31cfc10396fc76ba2eef6ff0165795&=&format=webp&quality=lossless&width=1203&height=587)

y is greater than 10000 OR y is greater than 1000 but less than 1500

is the same as saying

y is greater than 10000 or x is greater than 1500, OR y is greater than 100000 or greater than 1000

Therefore option A is correct

Question 39

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308212050064838756/image.png?ex=673d1eea&is=673bcd6a&hm=5de92e2ca186c9e46860d3642ddcf5b3c3271e9082ccbbdcb0f5bb45aca3334a&=&format=webp&quality=lossless&width=1145&height=586)

Keeps on repeating until invalid output.

27 / 3 = 9
9 * 2 = 18
18 / 3 = 6
6 * 2 = 12
12 / 3 = 4
4 * 2 = 8
8 * 2 = 16

Answer is 16

Question 40

![sdf](https://media.discordapp.net/attachments/1285436912823435264/1308212255803834448/image.png?ex=673d1f1b&is=673bcd9b&hm=b4145a054419aea176fa1904cae5ec8ce387bb9c5a7740df14de8a0f024445a1&=&format=webp&quality=lossless&width=852&height=587)

The method recursively reduces the string by removing its last character until its length is 1, then prints each reduced version as a result of each recurison. 

Therefore the output would be:

W  
WA  
WAT  
WATC

### Strengths and Weaknesses

Strengths:

- Understanding how full-stacks work and the logic behind them
- Collaborating with the team to solve issues
- Decent base in Java 

Weaknesses

- Sometimes may be careless or inefficient with Java (carelessness while coding)
- Can be unorganized at times
- Javascript is one of my weaker languages
