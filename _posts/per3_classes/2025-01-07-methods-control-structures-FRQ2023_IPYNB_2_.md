---
layout: post
title: 2023 FRQ Review
categories: ['AP CSA']
menu: nav/CSA_Units/frqs/methods_per3.html
permalink: /methods_per3/frq_example
---

# 2023 FRQ

![image](https://github.com/user-attachments/assets/649677f2-64d7-4de1-91e8-300368053438)


![image](https://github.com/user-attachments/assets/90c68b8e-329f-4941-b88e-0edbf78ca3cb)


![image](https://github.com/user-attachments/assets/4413252d-bfd0-4e8d-a3c1-41af3054d1ff)

## findFreeBlock


This method finds the first block of consecutive free minutes in a given period, with a duration long enough for the requested appointment. If no such block exists, it returns -1.

Key Steps:

1. Loop through the period from minute 0 to 59.


    - Track the count of consecutive free minutes using a variable (freeMinutes).
    - Reset freeMinutes to 0 whenever a busy minute is encountered.


2. Check each minute using the isMinuteFree(period, minute) helper method.


    - Increment freeMinutes if the minute is free.
    - Once freeMinutes matches the requested duration, return the starting minute of the block.


3. If no valid block is found after checking all minutes, return -1.


```python
public int findFreeBlock(int period, int duration) {
    int freeMinutes = 0;

    for (int minute = 0; minute <= 59; minute++) {
        if (isMinuteFree(period, minute)) {
            freeMinutes++;
            if (freeMinutes == duration) {
                return minute - duration + 1; // Start of the block
            }
        } else {
        }
    }

    return -1; // No block found
}

```

## Explaination

1. Tracks Consecutive Free Minutes:

    - The freeMinutes variable keeps count of consecutive free minutes as it loops through the 60 minutes of the given period.


2. Checks Free Minutes:

    - Uses the helper method isMinuteFree(period, minute) to determine whether each minute is free.


3. Finds the Start of the Block:

    - When freeMinutes equals duration, it calculates and returns the starting minute of the block using the formula minute - duration + 1.


4. Handles Resets:

    - If a busy minute is encountered, freeMinutes resets to 0, ensuring only consecutive free minutes are counted.


5. Returns -1 if No Block Found:

    - If the loop completes without finding a suitable block, the method returns -1.

![image](https://github.com/user-attachments/assets/667903e7-5f69-48ab-92b2-6d287d353dcc)

![image](https://github.com/user-attachments/assets/e7ba3a75-0b0a-4ff9-8297-6c5331cde18f)

## makeAppointment

This method searches multiple periods, from startPeriod to endPeriod, to find the earliest block of free minutes. If found, it reserves the block and returns true. Otherwise, it returns false.


1. Loop through each period from startPeriod to endPeriod.

    - Use findFreeBlock(period, duration) to check for an available block in the current period.


2. If findFreeBlock returns a valid starting minute:
    - Use reserveBlock(period, startMinute, duration) to reserve the block.


3. Return true.
    - If no block is found after checking all periods, return false.



```python
public boolean makeAppointment(int startPeriod, int endPeriod, int duration) {
    for (int period = startPeriod; period <= endPeriod; period++) {
        int startMinute = findFreeBlock(period, duration);
        if (startMinute != -1) {
            reserveBlock(period, startMinute, duration); // Reserve the block
            return true;
        }
    }

    return false; // No block found in any period
}

```

## Explaination


1. Iterating through the periods from startPeriod to endPeriod.




2. Using the findFreeBlock method to check for an available block of minutes in each period.




3. Reserving the block with reserveBlock(period, startMinute, duration) when a valid block is found.




4. Returning true upon successfully reserving a block or false if no suitable block is found.
