---
layout: post
title: CollegeBoard FRQ Reflection Hard
description: CollegeBoard FRQ Reflection Hard
type: collab
toc: True
permalink: FRQ/corrections2015hard
comments: True
author: Eric Yu
categories: ['Collaboration']
---

### Collegeboard FRQ

# AP Computer Science A - FRQ Analysis

## Question: Guessing Game

### My Score Breakdown

I implemented the `HiddenWord` class, and according to the rubric, here’s how I did:

| Points | Criteria | Status |
|--------|----------|--------|
| **+1** | Used the correct class, constructor, and method headers | ✅ |
| **+1** | Declared `private` instance variable | ✅ |
| **+1** | Initialized the instance variable properly in the constructor | ✅ |
| **+6** | Implemented `getHint` method: | ✅ |
| **+1** | Looped through all letters in both `guess` and `hiddenWord` without index errors | ✅ |
| **+4** | Processed each letter correctly: | ✅ |
| **+1** | Extracted and compared letters from `guess` and `hiddenWord` | ✅ |
| **+1** | Checked if letters were in the same position | ✅ |
| **+1** | Checked if letters were in the word but in the wrong spot | ✅ |
| **+1** | Added the correct character (`letter`, `+`, or `*`) to the hint | ✅ |
| **+1** | Constructed and returned the hint string | ✅ |

### Possible Deductions

| Possible Deduction | Reason |
|-------------------|--------|
| **-1** | If I used `.get()` instead of `charAt()` to access letters in strings |
| **-2** | If I accidentally used the wrong variable name instead of `hiddenWord` |

### Additional Consideration

It is possible I lose points for multiple letters? 

For example, in `SHARP`, if I already got the first `S` correct but guessed `S` for the last character, should it show a `+` or a `*`? 

### Final Thoughts

I managed this one pretty well, although  the time was slightly edge.



```Java
public class HiddenWord {
    private String hiddenWord;

    public HiddenWord(String hiddenWord) {
        this.hiddenWord = hiddenWord;
    }

    public String getHint(String guess) {
        StringBuilder hint = new StringBuilder();
        for (int i = 0; i < guess.length(); i++) {
            char guessChar = guess.charAt(i);
            if (guessChar == hiddenWord.charAt(i)) {
                hint.append(guessChar);
            } else if (hiddenWord.indexOf(guessChar) != -1) {
                hint.append('+'); 
            } else {
                hint.append('*'); 
            }
        }
        return hint.toString();
    }

    public static void main(String[] args) {
        HiddenWord puzzle = new HiddenWord("HARPS");
        System.out.println(puzzle.getHint("AAAAA"));
        System.out.println(puzzle.getHint("HARPS"));
        System.out.println(puzzle.getHint("SHARP")); 
    }
}

HiddenWord.main(null)
```

    +A+++
    HARPS
    +++++

