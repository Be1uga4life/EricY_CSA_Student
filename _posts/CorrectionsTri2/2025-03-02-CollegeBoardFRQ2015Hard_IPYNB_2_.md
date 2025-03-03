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

- **+1** Used the correct class, constructor, and method headers ✅
- **+1** Declared `private` instance variable ✅
- **+1** Initialized the instance variable properly in the constructor ✅
- **+6** Implemented `getHint` method:
  - **+1** Looped through all letters in both `guess` and `hiddenWord` without index errors ✅
  - **+4** Processed each letter correctly:
    - **+1** Extracted and compared letters from `guess` and `hiddenWord` ✅
    - **+1** Checked if letters were in the same position ✅
    - **+1** Checked if letters were in the word but in the wrong spot ✅
    - **+1** Added the correct character (`letter`, `+`, or `*`) to the hint ✅
  - **+1** Constructed and returned the hint string ✅


### Final Thoughts

Overall, my code follows the rubric closely, but I need to double-check for any small mistakes, like how I access characters and making sure I use the right variable names everywhere. If I fix those, I should get full points! 🎯



```Java
public class HiddenWord {
    private String hiddenWord;

    public HiddenWord(String hiddenWord) {
        this.hiddenWord = hiddenWord;
    }

    public String getHint(String guess) {
        StringBuilder hint = new StringBuilder();
        int[] letterCount = new int[26]; // Track frequency of letters in hiddenWord

        // First pass: Identify exact matches
        for (int i = 0; i < hiddenWord.length(); i++) {
            if (guess.charAt(i) == hiddenWord.charAt(i)) {
                hint.append(guess.charAt(i)); // Correct position
            } else {
                hint.append('.'); // Placeholder for second pass
                letterCount[hiddenWord.charAt(i) - 'A']++; // Count letter occurrences
            }
        }

        // Second pass: Identify misplaced letters
        for (int i = 0; i < hiddenWord.length(); i++) {
            if (hint.charAt(i) == '.') { // Only check non-matching positions
                char guessChar = guess.charAt(i);
                if (letterCount[guessChar - 'A'] > 0) {
                    hint.setCharAt(i, '+'); // Right letter, wrong position
                    letterCount[guessChar - 'A']--; // Reduce count
                } else {
                    hint.setCharAt(i, '*'); // Letter not in word
                }
            }
        }

        return hint.toString();
    }

    public static void main(String[] args) {
        HiddenWord puzzle = new HiddenWord("HARPS");
        System.out.println(puzzle.getHint("AAAAA")); // Expected Output: "*A+++"
        System.out.println(puzzle.getHint("HARPS")); // Expected Output: "HARPS"
        System.out.println(puzzle.getHint("SHARP")); // Expected Output: "+HARP"
    }
}

HiddenWord.main(null)

```

    *A***
    HARPS
    +++++

