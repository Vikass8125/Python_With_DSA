# Selection Sort Algorithm

## Problem Description:
You are given a list of integers. Write a Python function to sort the list in ascending order using the Selection Sort algorithm. Selection Sort works by repeatedly finding the minimum element from the unsorted part of the list and swapping it with the first element of the unsorted part.

## Parameters:
- `lst` (List of integers): The list to be sorted.

## Returns:
- A list of integers sorted in ascending order.

## Example:

```python
# Input:
lst = [64, 25, 12, 22, 11]
# Output:
[11, 12, 22, 25, 64]

# Input:
lst = [29, 10, 14, 37, 13]
# Output:
[10, 13, 14, 29, 37]
```

---

## Solution Approach
Selection Sort works by selecting the smallest element from the unsorted part of the list and swapping it with the first element of the unsorted part. The algorithm proceeds until the entire list is sorted.

### Pseudo Code:
```plaintext
1. Loop through the list from index 0 to n-1
2. Assume the current index is the minimum
3. Iterate through the rest of the list to find the actual minimum
4. Swap the found minimum with the first element of the unsorted part
5. Repeat the process for the next unsorted index
6. Continue until the entire list is sorted
```

### Python Implementation:
```python
def selection_sort(lst):
    """
    Function to perform Selection Sort on a given list.
    
    Parameters:
    lst (List[int]): List of integers to be sorted.
    
    Returns:
    List[int]: Sorted list in ascending order.
    """
    n = len(lst)
    
    for i in range(n):
        min_index = i  # Assume the current index has the minimum value
        
        for j in range(i + 1, n):
            if lst[j] < lst[min_index]:
                min_index = j  # Update minimum index if a smaller element is found
        
        # Swap the found minimum element with the first element of the unsorted part
        lst[i], lst[min_index] = lst[min_index], lst[i]
    
    return lst

# Example usage:
print(selection_sort([64, 25, 12, 22, 11]))  # Output: [11, 12, 22, 25, 64]
print(selection_sort([29, 10, 14, 37, 13]))  # Output: [10, 13, 14, 29, 37]
```

### Time Complexity:
- **Best Case:** O(n²) (Still needs to compare all elements)
- **Worst Case:** O(n²) (Nested loops lead to quadratic complexity)
- **Average Case:** O(n²)

### Space Complexity:
- O(1) (Sorting happens in-place, requiring no extra space)

---

## Key Takeaways:
✅ Simple sorting algorithm but inefficient for large datasets.
✅ Works well for small lists.
✅ In-place sorting with no additional memory usage.
✅ Better alternatives: Merge Sort, Quick Sort, or Heap Sort for better efficiency.

🚀 Happy Coding!
