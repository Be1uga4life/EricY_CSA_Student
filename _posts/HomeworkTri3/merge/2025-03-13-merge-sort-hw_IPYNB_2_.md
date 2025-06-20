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




```java
public class sorryimlatepleasedontdockmetoomuch {

    private static int comparisonCount = 0;

    public static void mergeSort(int[] array) {
        comparisonCount = 0;
        mergeSort(array, 0, array.length - 1, 0);
    }

    private static void mergeSort(int[] array, int left, int right, int depth) {
        printWithIndent(depth, "mergeSort(" + left + ", " + right + ")");
        if (left >= right) return;

        int mid = (left + right) / 2;

        mergeSort(array, left, mid, depth + 1);
        mergeSort(array, mid + 1, right, depth + 1);
        merge(array, left, mid, right, depth);
    }

    private static void merge(int[] array, int left, int mid, int right, int depth) {
        printWithIndent(depth, "Merging: " + arrayToString(array, left, mid) + " + " + arrayToString(array, mid + 1, right));
        
        int[] temp = new int[right - left + 1];
        int i = left, j = mid + 1, k = 0;

        while (i <= mid && j <= right) {
            comparisonCount++;
            if (array[i] <= array[j]) {
                temp[k++] = array[i++];
            } else {
                temp[k++] = array[j++];
            }
        }

        while (i <= mid) temp[k++] = array[i++];
        while (j <= right) temp[k++] = array[j++];

        System.arraycopy(temp, 0, array, left, temp.length);

        printWithIndent(depth, "Result:   " + arrayToString(array, left, right));
    }

    private static void printWithIndent(int depth, String message) {
        System.out.println("  ".repeat(depth) + message);
    }

    private static String arrayToString(int[] arr, int start, int end) {
        StringBuilder sb = new StringBuilder("[");
        for (int i = start; i <= end; i++) {
            sb.append(arr[i]);
            if (i < end) sb.append(", ");
        }
        sb.append("]");
        return sb.toString();
    }

    public static void main(String[] args) {
        int[] arr = {5, 2, 9, 1, 6, 3};
        System.out.println("Original array: " + arrayToString(arr, 0, arr.length - 1));
        mergeSort(arr);
        System.out.println("\nSorted array:   " + arrayToString(arr, 0, arr.length - 1));
        System.out.println("Total comparisons: " + comparisonCount);
    }
}

sorryimlatepleasedontdockmetoomuch.main(null);

```

    Original array: [5, 2, 9, 1, 6, 3]
    mergeSort(0, 5)
      mergeSort(0, 2)
        mergeSort(0, 1)
          mergeSort(0, 0)
          mergeSort(1, 1)
        Merging: [5] + [2]
        Result:   [2, 5]
        mergeSort(2, 2)
      Merging: [2, 5] + [9]
      Result:   [2, 5, 9]
      mergeSort(3, 5)
        mergeSort(3, 4)
          mergeSort(3, 3)
          mergeSort(4, 4)
        Merging: [1] + [6]
        Result:   [1, 6]
        mergeSort(5, 5)
      Merging: [1, 6] + [3]
      Result:   [1, 3, 6]
    Merging: [2, 5, 9] + [1, 3, 6]
    Result:   [1, 2, 3, 5, 6, 9]
    
    Sorted array:   [1, 2, 3, 5, 6, 9]
    Total comparisons: 11

