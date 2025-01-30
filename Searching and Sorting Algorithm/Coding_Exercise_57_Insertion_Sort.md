# Coding Exercise 57: Insertion Sort Algorithm

## Problem Description
You are given a list of integers. Write a Python function to sort the list in ascending order using the **Insertion Sort** algorithm. Insertion Sort works by building a sorted section of the list, one element at a time, by inserting each new element into its proper position within the already sorted section.

## Parameters
- **lst (List of integers)**: The list to be sorted.

## Returns
- **A list of integers sorted in ascending order**.

---

## Example

### Input:
```python
lst = [12, 11, 13, 5, 6]
```

### Output:
```python
[5, 6, 11, 12, 13]
```

### Input:
```python
lst = [31, 41, 59, 26, 41, 58]
```

### Output:
```python
[26, 31, 41, 41, 58, 59]
```

---

## Solution Approach
1. Start with the second element.
2. Compare it with the previous elements and insert it into its correct position in the sorted part of the list.
3. Repeat the process for the rest of the elements.

---

## Pseudo Code
```plaintext
for i from 1 to length(lst) - 1:
    key = lst[i]
    j = i - 1
    while j >= 0 and lst[j] > key:
        lst[j + 1] = lst[j]
        j = j - 1
    lst[j + 1] = key
```

---

## Python Implementation

### Approach 1
```python
def insertion_sort(lst):
    # Traverse from 1 to len(lst)
    for i in range(1, len(lst)):
        key = lst[i]
        
        # Move elements of lst[0..i-1] that are greater than key
        # to one position ahead of their current position
        j = i - 1
        while j >= 0 and key < lst[j]:
            lst[j + 1] = lst[j]
            j -= 1
        
        # Insert key in its correct position
        lst[j + 1] = key
    
    return lst
```

### Approach 2
```python
def insertion_sort(lst):
    n = len(lst)
    
    for current in range(1, n):
        currentCard = lst[current]
        correctPosition = current - 1
        
        while correctPosition >= 0:
            if lst[correctPosition] < currentCard:
                break
            else:
                lst[correctPosition + 1] = lst[correctPosition]
                correctPosition -= 1
                
            lst[correctPosition + 1] = currentCard
            
    return lst
```

---

## Complexity Analysis
- **Best Case (Already Sorted List)**: `O(n)`
- **Worst Case (Reversed List)**: `O(n^2)`
- **Average Case**: `O(n^2)`

---

## Key Takeaways
- **Stable Sorting Algorithm**: Maintains relative order of equal elements.
- **In-Place Sorting Algorithm**: Does not require extra space.
- **Efficient for Small or Nearly Sorted Lists**, but inefficient for large random lists.

🚀 Happy Coding!
