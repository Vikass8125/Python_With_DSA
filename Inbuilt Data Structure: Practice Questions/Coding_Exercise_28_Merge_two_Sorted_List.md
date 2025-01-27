# Merge Two Sorted Lists

## Problem Statement

You are given two sorted lists of integers. Write a Python function to **merge these two sorted lists** into one sorted list. The resulting list should also be in **non-decreasing order**.

### Parameters:
- `list1` (List of integers): The first sorted list.
- `list2` (List of integers): The second sorted list.

### Returns:
- A single list of integers, containing all elements from `list1` and `list2`, sorted in non-decreasing order.

---

## Examples:

### Example 1:
**Input:**
```python
list1 = [1, 3, 5]
list2 = [2, 4, 6]
```
**Output:**
```python
[1, 2, 3, 4, 5, 6]
```
**Explanation:**
Both lists are already sorted. By comparing elements one by one, we merge them into a single sorted list.

### Example 2:
**Input:**
```python
list1 = [1, 4, 7]
list2 = [2, 3, 5, 8]
```
**Output:**
```python
[1, 2, 3, 4, 5, 7, 8]
```
**Explanation:**
The elements from both lists are merged in non-decreasing order.

---

## Solution Approach

### Two-Pointer Technique
The optimal solution uses the **two-pointer technique** to merge the lists in sorted order. This approach efficiently traverses both lists, comparing elements and appending the smaller one to the result list. After finishing one list, the remaining elements from the other list are added directly to the result.

### Steps:
1. Initialize two pointers, `i` and `j`, for `list1` and `list2`, respectively. Start both at `0`.
2. Initialize an empty list `result` to store the merged result.
3. Compare elements at `list1[i]` and `list2[j]`:
   - Append the smaller element to `result` and move the pointer of the list from which the element was taken.
4. Continue until one of the lists is fully traversed.
5. Append the remaining elements of the other list to `result`.
6. Return the merged list.

---

### Code Implementation
```python
def merge_two_sorted_lists(list1, list2):
    # Initialize pointers for both lists
    i, j = 0, 0
    result = []  # Initialize an empty list to store the merged result
 
    # Traverse both lists and merge them in sorted order
    while i < len(list1) and j < len(list2):
        if list1[i] < list2[j]:
            result.append(list1[i])  # Add the smaller element to the result list
            i += 1
        else:
            result.append(list2[j])  # Add the smaller element to the result list
            j += 1
 
    # If there are remaining elements in list1, add them to the result
    while i < len(list1):
        result.append(list1[i])
        i += 1
 
    # If there are remaining elements in list2, add them to the result
    while j < len(list2):
        result.append(list2[j])
        j += 1
 
    return result  # Return the merged sorted list
```

---

### Code Walkthrough:
1. **Initialization:**
   - Pointers `i` and `j` are set to `0`.
   - An empty list `result` is created to store the merged output.

2. **Comparison Loop:**
   - In the `while` loop, elements from `list1` and `list2` are compared.
   - The smaller element is added to `result`, and the respective pointer (`i` or `j`) is incremented.

3. **Appending Remaining Elements:**
   - After exiting the loop, any remaining elements in `list1` or `list2` are appended to `result`.

4. **Return Result:**
   - The merged sorted list is returned.

---

### Dry Run:
#### Input:
`list1 = [1, 3, 5]`
`list2 = [2, 4, 6]`

#### Iteration Steps:
| `i` | `j` | `result`        | Comparison      | Action               |
|-----|-----|-----------------|-----------------|----------------------|
| 0   | 0   | []              | 1 < 2           | Append `1` from list1|
| 1   | 0   | [1]             | 3 > 2           | Append `2` from list2|
| 1   | 1   | [1, 2]          | 3 < 4           | Append `3` from list1|
| 2   | 1   | [1, 2, 3]       | 5 > 4           | Append `4` from list2|
| 2   | 2   | [1, 2, 3, 4]    | 5 < 6           | Append `5` from list1|
| 3   | 2   | [1, 2, 3, 4, 5] | list1 exhausted | Append `6` from list2|

**Output:** `[1, 2, 3, 4, 5, 6]`

---

## Complexity Analysis:

1. **Time Complexity:**
   - The algorithm iterates through both lists exactly once, making the time complexity **O(n + m)**, where `n` and `m` are the lengths of `list1` and `list2`, respectively.

2. **Space Complexity:**
   - The space complexity is **O(n + m)** for storing the merged list.

