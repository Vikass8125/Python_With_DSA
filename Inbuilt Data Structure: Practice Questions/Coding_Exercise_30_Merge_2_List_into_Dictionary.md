# Merge Lists to Dictionary

## Problem Statement

Design a Python function named `merge_lists_to_dictionary` to merge two lists into a dictionary where elements from the first list act as keys and elements from the second list act as values.

### Parameters:
- `keys` (List): A list of keys.
- `values` (List): A list of values.

### Returns:
- A dictionary containing merged key-value pairs.

---

## Examples

### Example 1:
**Input:**
```python
keys = ['a', 'b', 'c']
values = [1, 2, 3]
```
**Output:**
```python
{'a': 1, 'b': 2, 'c': 3}
```
**Explanation:**
- Each element in the `keys` list is paired with the corresponding element in the `values` list to form key-value pairs.
- The resulting dictionary is `{'a': 1, 'b': 2, 'c': 3}`.

### Example 2:
**Input:**
```python
keys = ['x', 'y', 'z']
values = [10, 20, 30]
```
**Output:**
```python
{'x': 10, 'y': 20, 'z': 30}
```
**Explanation:**
- The first element of `keys` (`'x'`) is paired with the first element of `values` (`10`), and so on.
- The resulting dictionary is `{'x': 10, 'y': 20, 'z': 30}`.

---

## Solution Approach

### Steps to Solve:
1. **Check Boundary Conditions:**
   - Verify that the lengths of the `keys` and `values` lists are the same. If not, return `False` as merging would be incomplete.
2. **Create an Empty Dictionary:**
   - Initialize an empty dictionary to store the key-value pairs.
3. **Iterate Through Lists:**
   - Use a loop to iterate through both lists simultaneously by index.
   - Add each key-value pair to the dictionary.
4. **Return the Result:**
   - Return the final dictionary after processing all elements.

---

### Code Implementation
```python
def merge_lists_to_dictionary(keys, values):
    # Boundary Condition to check for equal length of keys and values.
    if len(keys) != len(values):
        return False

    # Create an empty dictionary to store the result
    result = {}

    # Use a loop to iterate through both lists
    for i in range(len(keys)):
        # Add each key-value pair to the dictionary
        result[keys[i]] = values[i]

    return result
```

---

### Code Walkthrough:
1. **Boundary Check:**
   - Compare the lengths of `keys` and `values`.
   - If they are unequal, merging is not possible, and the function returns `False`.

2. **Iteration and Dictionary Construction:**
   - Use a loop with `range(len(keys))` to iterate through indices of the lists.
   - For each index `i`, map `keys[i]` to `values[i]` in the dictionary.

3. **Return the Result:**
   - After iterating through all elements, return the constructed dictionary.

---

### Dry Run
#### Input:
`keys = ['a', 'b', 'c']`
`values = [1, 2, 3]`

#### Execution Steps:
| Step | Key   | Value | Result Dictionary |
|------|-------|-------|-------------------|
| 1    | `'a'` | `1`   | `{'a': 1}`        |
| 2    | `'b'` | `2`   | `{'a': 1, 'b': 2}`|
| 3    | `'c'` | `3`   | `{'a': 1, 'b': 2, 'c': 3}`|

**Output:** `{'a': 1, 'b': 2, 'c': 3}`

---

### Complexity Analysis

1. **Time Complexity:**
   - The function iterates through the lists once, so the time complexity is **O(n)**, where `n` is the length of the shorter list (or both if they are equal).

2. **Space Complexity:**
   - The space complexity is **O(n)** due to the dictionary storing `n` key-value pairs.

