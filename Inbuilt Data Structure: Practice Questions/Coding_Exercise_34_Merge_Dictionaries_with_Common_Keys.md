# Coding Exercise 34: Merge Dictionaries with Common Keys

## Problem Description

Design a Python function named `merge_dicts_with_overlapping_keys` that merges multiple dictionaries into a single dictionary. If a key appears in more than one dictionary, sum up their values.

### Parameters:
- `dicts` (list): A list of dictionaries where keys might overlap.

### Returns:
- A single dictionary where values for overlapping keys are summed.

---

## Examples

### Example 1:
**Input:**
```python
[{'a': 1, 'b': 2}, {'b': 3, 'c': 4}, {'c': 5, 'd': 6}]
```
**Output:**
```python
{'a': 1, 'b': 5, 'c': 9, 'd': 6}
```
**Explanation:**
- The key `a` appears only in the first dictionary with a value of 1.
- The key `b` appears in the first and second dictionaries, so their values are summed: \( 2 + 3 = 5 \).
- The key `c` appears in the second and third dictionaries, so their values are summed: \( 4 + 5 = 9 \).
- The key `d` appears only in the third dictionary with a value of 6.

### Example 2:
**Input:**
```python
[{'x': 10, 'y': 20}, {'y': 30, 'z': 40}, {'z': 50, 'x': 60}]
```
**Output:**
```python
{'x': 70, 'y': 50, 'z': 90}
```
**Explanation:**
- The key `x` appears in the first and third dictionaries, so their values are summed: \( 10 + 60 = 70 \).
- The key `y` appears in the first and second dictionaries, so their values are summed: \( 20 + 30 = 50 \).
- The key `z` appears in the second and third dictionaries, so their values are summed: \( 40 + 50 = 90 \).

---

## Solution Approach

### Steps to Solve:
1. **Initialize an Empty Dictionary:**
   - Create an empty dictionary `result` to store the final merged result.
2. **Iterate Through the List of Dictionaries:**
   - For each dictionary in the list, loop through its key-value pairs.
3. **Check for Key Overlap:**
   - If the key already exists in `result`, add the value to the existing value.
   - Otherwise, add the key-value pair to `result`.
4. **Return the Merged Dictionary:**
   - After processing all dictionaries, return `result`.

---

### Code Implementation
```python
def merge_dicts_with_overlapping_keys(dicts):
    """
    Function to merge dictionaries with overlapping keys.

    Parameters:
    dicts (list): A list of dictionaries.

    Returns:
    dict: A dictionary with summed values for overlapping keys.
    """
    # Initialize an empty dictionary to store the result
    result = {}

    # Loop through each dictionary in the list
    for d in dicts:
        # Loop through each key-value pair in the current dictionary
        for key, value in d.items():
            # If the key is already in the result dictionary, add the new value to the existing value
            if key in result:
                result[key] += value
            # Otherwise, add the key-value pair to the result dictionary
            else:
                result[key] = value

    return result
```

---

### Optimized Solution Using `get()`
Instead of checking if the key exists in the dictionary, we can use the `get()` method to simplify the logic.

### Code:
```python
def merge_dicts_with_overlapping_keys(dicts):
    """
    Function to merge dictionaries with overlapping keys using the get() method.

    Parameters:
    dicts (list): A list of dictionaries.

    Returns:
    dict: A dictionary with summed values for overlapping keys.
    """
    # Initialize an empty dictionary to store the result
    result = {}

    # Loop through each dictionary in the list
    for d in dicts:
        for key, value in d.items():
            # Use the get method to sum values for overlapping keys
            result[key] = result.get(key, 0) + value

    return result
```

---

### Code Walkthrough
#### Example Input:
```python
[{'a': 1, 'b': 2}, {'b': 3, 'c': 4}, {'c': 5, 'd': 6}]
```
1. **Initialization:**
   - Start with an empty dictionary: `result = {}`.

2. **Processing the First Dictionary:**
   - Add `{'a': 1, 'b': 2}` to `result`:
     - `result = {'a': 1, 'b': 2}`.

3. **Processing the Second Dictionary:**
   - Add `{'b': 3, 'c': 4}` to `result`:
     - `b` exists, so add \( 2 + 3 = 5 \): `result = {'a': 1, 'b': 5}`.
     - Add `c`: `result = {'a': 1, 'b': 5, 'c': 4}`.

4. **Processing the Third Dictionary:**
   - Add `{'c': 5, 'd': 6}` to `result`:
     - `c` exists, so add \( 4 + 5 = 9 \): `result = {'a': 1, 'b': 5, 'c': 9}`.
     - Add `d`: `result = {'a': 1, 'b': 5, 'c': 9, 'd': 6}`.

5. **Final Output:**
   - `{'a': 1, 'b': 5, 'c': 9, 'd': 6}`.

---

### Complexity Analysis

1. **Time Complexity:**
   - \( O(n \cdot m) \), where \( n \) is the number of dictionaries and \( m \) is the average number of keys in each dictionary.

2. **Space Complexity:**
   - \( O(k) \), where \( k \) is the total number of unique keys across all dictionaries.

---

## Usage
This function is useful for scenarios such as:
- Aggregating data from multiple sources.
- Summing up values across overlapping categories.

### Example Usage:
```python
# Example 1
print(merge_dicts_with_overlapping_keys([{'a': 1, 'b': 2}, {'b': 3, 'c': 4}, {'c': 5, 'd': 6}]))  # Output: {'a': 1, 'b': 5, 'c': 9, 'd': 6}

# Example 2
print(merge_dicts_with_overlapping_keys([{'x': 10, 'y': 20}, {'y': 30, 'z': 40}, {'z': 50, 'x': 60}]))  # Output: {'x': 70, 'y': 50, 'z': 90}
```

---

Happy coding! 😊
