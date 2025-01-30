# Bubble Sort Algorithm

## Problem Description

You are given a list of integers. Write a Python function to sort the list in ascending order using the **Bubble Sort algorithm**. Bubble Sort repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The process is repeated until the list is sorted.

### Parameters:
- `lst` (List of integers): The list to be sorted.

### Returns:
- A list of integers sorted in ascending order.

## Example

```python
# Input:
lst = [64, 34, 25, 12, 22, 11, 90]
# Output:
[11, 12, 22, 25, 34, 64, 90]

# Input:
lst = [5, 1, 4, 2, 8]
# Output:
[1, 2, 4, 5, 8]
```

---

## Pseudo Code

```
BubbleSort(arr):
    n = length of arr
    for i from 0 to n-1:
        for j from 0 to n-i-1:
            if arr[j] > arr[j+1]:
                swap arr[j] and arr[j+1]
    return arr
```

---

## Solution

In each pass through the list, compare adjacent elements. If the first element is greater than the second, swap them. Repeat this process until no swaps are needed, which indicates that the list is sorted.

```python
def bubble_sort(lst):
    n = len(lst)
    
    # Traverse through all elements in the list
    for i in range(n):
        # Last i elements are already sorted, so we skip them
        for j in range(0, n - i - 1):
            # Swap if the element found is greater than the next element
            if lst[j] > lst[j + 1]:
                lst[j], lst[j + 1] = lst[j + 1], lst[j]
    
    return lst

# Example usage:
print(bubble_sort([64, 34, 25, 12, 22, 11, 90]))  # Output: [11, 12, 22, 25, 34, 64, 90]
print(bubble_sort([5, 1, 4, 2, 8]))  # Output: [1, 2, 4, 5, 8]
```

---

## Complexity Analysis

- **Best Case (Already Sorted List):** O(n)
- **Average Case:** O(n²)
- **Worst Case (Reverse Sorted List):** O(n²)

### Space Complexity:
- **O(1)** (Sorting is done in place, requiring no extra space)

---

## Explanation
1. The algorithm loops through the list multiple times.
2. Each iteration moves the largest unsorted element to its correct position.
3. The process repeats until the entire list is sorted.
4. The inner loop gradually decreases in size as elements get sorted.

---

## Alternative Approach (Optimized Bubble Sort)
We can optimize Bubble Sort by adding a **swapped** flag. If no swaps occur during a pass, the list is already sorted, and we can terminate early.

```python
def optimized_bubble_sort(lst):
    n = len(lst)
    for i in range(n):
        swapped = False
        for j in range(0, n - i - 1):
            if lst[j] > lst[j + 1]:
                lst[j], lst[j + 1] = lst[j + 1], lst[j]
                swapped = True
        if not swapped:
            break  # Exit early if no swaps were made
    return lst
```

This optimization improves performance for nearly sorted lists, reducing the best-case complexity to **O(n)**.

---

## Conclusion
Bubble Sort is a simple but inefficient sorting algorithm. While it works well for small datasets or nearly sorted lists, it is not suitable for large datasets due to its O(n²) time complexity. Other sorting algorithms like **Merge Sort, Quick Sort, or Heap Sort** are preferred for better efficiency.

Happy Coding! 🚀
