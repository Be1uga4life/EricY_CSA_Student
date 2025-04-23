---
layout: post
title: Merge Sort Team Teach
type: issues
courses: {'csa': {'week': 8}}
comments: True
permalink: /csa/team_teach/demo
---

1. If left < right, the array is divided into two halves:
    int mid = (left + right) / 2;
2. It recursively calls itself for the left half:
    mergeSort(arr, left, mid);
3. Then, it recursively calls itself for the right half:
    mergeSort(arr, mid + 1, right);
4. After both halves are sorted, the merge() function is called to combine them.




```java
import java.util.Arrays;

public class MergeSortAlgorithm {

    // Merge Sort function: Recursively splits the array into smaller parts and sorts them
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;  // Find the middle point

            // Recursively sort first and second halves
            mergeSort(arr, left, mid);  // Sort left half
            mergeSort(arr, mid + 1, right);  // Sort right half

            // Merge the sorted halves
            merge(arr, left, mid, right);
        }
    }

    // Merging two sorted subarrays into one sorted array
    private static void merge(int[] arr, int left, int mid, int right) {
        int leftSize = mid - left + 1;  // Size of left subarray
        int rightSize = right - mid;    // Size of right subarray

        // Create temporary arrays to store left and right subarrays
        int[] leftArr = new int[leftSize];
        int[] rightArr = new int[rightSize];

        // Copy data to temporary arrays
        System.arraycopy(arr, left, leftArr, 0, leftSize);
        System.arraycopy(arr, mid + 1, rightArr, 0, rightSize);

        // Merge the temporary arrays back into the original array
        int i = 0, j = 0, k = left;
        while (i < leftSize && j < rightSize) {
            // Compare elements and insert the smaller one into the original array
            if (leftArr[i] <= rightArr[j]) {
                arr[k++] = leftArr[i++];
            } else {
                arr[k++] = rightArr[j++];
            }
        }

        // Copy any remaining elements from leftArr (if any)
        while (i < leftSize) {
            arr[k++] = leftArr[i++];
        }

        // Copy any remaining elements from rightArr (if any)
        while (j < rightSize) {
            arr[k++] = rightArr[j++];
        }
    }

    // Main method to test Merge Sort
    public static void main(String[] args) {
        int[] array = {38, 27, 43, 3, 9, 82, 10};  // Unsorted array
        System.out.println("Unsorted Array: " + Arrays.toString(array));

        // Call mergeSort function to sort the array
        mergeSort(array, 0, array.length - 1);

        // Print the sorted array
        System.out.println("Sorted Array: " + Arrays.toString(array));
    }
}

```

1. mergeSort() Function (Recursive)
Splits the array into two halves.
Recursively sorts the left and right halves.
Calls merge() to combine the sorted halves.

2. merge() Function
Creates temporary arrays for left and right halves.
Merges the elements in order back into the main array.

3. main() Function
Defines an unsorted array.
Calls mergeSort() to sort it.
Prints the sorted array.
