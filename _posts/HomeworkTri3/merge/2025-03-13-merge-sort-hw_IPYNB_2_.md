---
layout: post
title: Merge Sort Homework
type: issues
courses: {'csa': {'week': 8}}
comments: True
permalink: /csa/team_teach/merge_sort_hw
---

What is the time complexity of merge sort in the best, worst, and average cases? Explain why.
The time complexities of merge sort in the best, worst, and average cases are all nlog(n). The merge sort algorithm will always divide the array into halves (which is the log(n) part) and will then always merge them back linearly (which results in the n part). The splitting actions and merging actions will always occur no matter how ordered the array is, thus the time complexity is the same for all cases.

Compare merge sort with bubble sort and quicksort. When might merge sort be preferred?
Merge sort has a stable time complexity of nlog(n) compared to bubble sort and quicksort.

Bubble sort has an average time complexity of n^2, which makes sorting on average slower than Merge Sort.

Quicksort has an average time complexity of nlog(n), but has a time complexity of n^2 as its worst case scenario, making it less reliable on time complexity.

Why is merge sort considered a “divide and conquer” algorithm?
Merge sort divides the array (the divide part), and then sorts each divided array. Essentially it splits up the work that it does which is why it's called the "divide and conquered" algorithm. 

Is merge sort stable? Why does this matter?
Merge sort keeps equal elements in the same order they appeared in the input, therefore it is stable. If there are multiple keys in a database that need to be sorted, the key pairs need to remain paired or "stable". 

# Instructions
Task:
Write a function in Java that implements merge sort.

Bonus task:
Modify your merge sort function to count how many comparisons are made during sorting.


