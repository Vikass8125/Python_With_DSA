# Check if All Elements in a List are Unique

## Problem Statement
You are given a list of integers. Write a Python program that checks if all elements in the list are unique. If all elements are unique, return `True`; otherwise, return `False`.

### Parameters:
- `lst` (List of integers): The list of integers to check for uniqueness.

### Returns:
- A boolean value `True` if all elements in the list are unique, `False` otherwise.

### Example:

#### Example 1:
**Input:**
```python
lst = [1, 2, 3, 4, 5]
```
**Output:**
```
True
```

#### Example 2:
**Input:**
```python
lst = [1, 2, 3, 3, 4, 5]
```
**Output:**
```
False
```

---

## Explanation
The goal is to determine if all elements in the list are unique:
- In the first input, `[1, 2, 3, 4, 5]`, all elements are distinct, so the output is `True`.
- In the second input, `[1, 2, 3, 3, 4, 5]`, the number `3` appears twice, so the output is `False`.

---

## Solution
We will solve this problem using a set to keep track of seen elements, as sets provide efficient lookup and insertion operations.

### Brute Force Solution
In the brute force approach, for each element in the list, we check if it appears elsewhere in the list. This involves nested loops and is computationally expensive.

### Implementation:
```python
def check_unique(lst):
    # Iterate through each element in the list
    for i in range(len(lst)):
        # Check if the current element appears again in the remaining list
        if lst[i] in lst[i+1:]:
            return False
    return True

# Example Usage:
lst = [1, 2, 3, 4, 5]
print(check_unique(lst))  # Output: True
```

### Code Walkthrough
1. **Outer Loop**: Iterate through each element in the list.
2. **Inner Check**: Check if the current element appears again in the remaining part of the list.
3. **Return Result**: If any duplicate is found, return `False`. If no duplicates are found, return `True` after the loop completes.

---

### Optimal Solution
A more efficient approach uses a set to keep track of elements we have already seen. If an element is encountered that is already in the set, we return `False`. Otherwise, we add it to the set.

### Implementation:
```python
def check_unique(lst):
    # Initialize an empty set to keep track of seen elements
    seen = set()
    
    # Iterate through each element in the input list
    for num in lst:
        # If the element has been seen before, return False
        if num in seen:
            return False
        # Add the element to the seen set
        seen.add(num)
    
    # If no duplicates are found, return True
    return True

# Example Usage:
lst = [1, 2, 3, 3, 4, 5]
print(check_unique(lst))  # Output: False
```

### Code Walkthrough
1. **Initialize a Set**: Use an empty set, `seen`, to keep track of elements we have encountered.
2. **Iterate through the List**: For each element:
   - If it is already in `seen`, return `False` (duplicate found).
   - Otherwise, add it to the `seen` set.
3. **Return the Result**: If no duplicates are found, return `True` after iterating through the entire list.

---

## Complexity Analysis
### Brute Force Solution:
- **Time Complexity**: `O(n^2)` where `n` is the length of the list. For each element, we check the rest of the list for duplicates.
- **Space Complexity**: `O(1)` as no extra space is used apart from variables.

### Optimal Solution:
- **Time Complexity**: `O(n)` where `n` is the length of the list. Each element is checked and added to the set in constant time.
- **Space Complexity**: `O(n)` for the `seen` set, which stores up to `n` elements in the worst case.

---

## Summary
The brute force approach is simple but inefficient for larger lists due to its `O(n^2)` time complexity. The optimal solution, which uses a set to track seen elements, is both efficient and easy to implement. It is recommended for real-world applications.
