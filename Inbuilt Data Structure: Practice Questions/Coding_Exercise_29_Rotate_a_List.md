# Rotate a List (Without Slicing)

## Problem Statement

You are given a list of integers and an integer `k`. Write a Python function to **rotate the list to the right by `k` positions** without using slicing. A rotation shifts elements from the end of the list to the front.

### Parameters:
- `lst` (List of integers): The list to be rotated.
- `k` (Integer): The number of positions to rotate the list.

### Returns:
- A list of integers rotated by `k` positions.

---

## Examples

### Example 1:
**Input:**
```python
lst = [1, 2, 3, 4, 5]
k = 2
```
**Output:**
```python
[4, 5, 1, 2, 3]
```
**Explanation:**
- The list `[1, 2, 3, 4, 5]` is rotated 2 positions to the right.
- After rotation, the last 2 elements `[4, 5]` move to the front, followed by the rest of the elements.

### Example 2:
**Input:**
```python
lst = [10, 20, 30, 40, 50]
k = 3
```
**Output:**
```python
[30, 40, 50, 10, 20]
```
**Explanation:**
- The list `[10, 20, 30, 40, 50]` is rotated 3 positions to the right.
- After rotation, the last 3 elements `[30, 40, 50]` move to the front, followed by the rest of the elements.

---

## Solution Approach

### Brute-Force Method (Without Slicing)
This approach uses loops to rotate the list step-by-step. Each rotation involves removing the last element of the list and inserting it at the beginning.

### Steps:
1. **Handle Edge Cases:**
   - If the list is empty, return an empty list.
   - Use modulo operation (`k = k % len(lst)`) to handle cases where `k` is greater than the length of the list.
2. **Iterative Rotation:**
   - Perform the rotation `k` times by removing the last element (`pop`) and inserting it at the start (`insert`).
3. **Return the Result:**
   - After completing the rotations, return the modified list.

---

### Code Implementation
```python
def rotate_list(lst, k):
    # Handling the case where the list is empty
    if not lst:
        return []

    # Modulo to handle the case where k is greater than the length of the list
    k = k % len(lst)

    # Brute force approach using loops
    for _ in range(k):
        last_element = lst.pop()  # Remove the last element
        lst.insert(0, last_element)  # Insert it at the front

    return lst
```

---

### Code Walkthrough:
1. **Initialization:**
   - Check if the list is empty. If true, return an empty list.
   - Use `k = k % len(lst)` to ensure `k` is within the bounds of the list's length.

2. **Rotation Loop:**
   - For each rotation (up to `k` times):
     - Remove the last element of the list using `pop()`.
     - Insert the removed element at the beginning using `insert(0, element)`.

3. **Return Result:**
   - After completing the rotations, return the updated list.

---

### Dry Run
#### Input:
`lst = [1, 2, 3, 4, 5]`
`k = 2`

#### Iteration Steps:
| Step | List          | Operation             |
|------|---------------|-----------------------|
| 0    | [1, 2, 3, 4, 5] | Initial list         |
| 1    | [5, 1, 2, 3, 4] | Move 5 to the front |
| 2    | [4, 5, 1, 2, 3] | Move 4 to the front |

**Output:** `[4, 5, 1, 2, 3]`

---

## Complexity Analysis

1. **Time Complexity:**
   - Each `pop` operation takes **O(1)** (removing the last element).
   - Each `insert(0, element)` operation takes **O(n)** (shifting elements to the right).
   - For `k` rotations, the total time complexity is **O(k * n)**, where `n` is the length of the list.

2. **Space Complexity:**
   - The space complexity is **O(1)** since no additional space is used beyond the input list.

