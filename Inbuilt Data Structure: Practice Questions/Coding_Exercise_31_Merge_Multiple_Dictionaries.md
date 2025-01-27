# Merge Three Dictionaries

## Problem Statement
Design a Python function named `merge_three_dictionaries` to merge exactly three dictionaries into one.

### Parameters:
- `dict1` (Dictionary): The first dictionary to be merged.
- `dict2` (Dictionary): The second dictionary to be merged.
- `dict3` (Dictionary): The third dictionary to be merged.

### Returns:
A single dictionary containing all key-value pairs from the three input dictionaries.

---

## Examples

### Example 1:
**Input:**
```python
{'a': 1, 'b': 2}, {'c': 3, 'd': 4}, {'e': 5, 'f': 6}
```

**Output:**
```python
{'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5, 'f': 6}
```

### Example 2:
**Input:**
```python
{'x': 10, 'y': 20}, {'z': 30}, {'a': 40, 'b': 50}
```

**Output:**
```python
{'x': 10, 'y': 20, 'z': 30, 'a': 40, 'b': 50}
```

---

## Solution

### Approach 1: Iterative Merge
In this approach, we iterate through the key-value pairs of the dictionaries and add them to a new dictionary. This ensures that no keys are overwritten in case of duplicates.

### Code:
```python
def merge_three_dictionaries(dict1, dict2, dict3):
    # Create a new dictionary that starts with the content of dict1
    merged_dict = dict1.copy()
    
    # Add the key-value pairs from dict2
    for key, value in dict2.items():
        merged_dict[key] = value
    
    # Add the key-value pairs from dict3
    for key, value in dict3.items():
        merged_dict[key] = value
    
    return merged_dict
```

### Example Walkthrough:
**Input:**
```python
{'a': 1, 'b': 2}, {'c': 3, 'd': 4}, {'e': 5, 'f': 6}
```

**Execution:**
1. Start with `merged_dict = {'a': 1, 'b': 2}`.
2. Add key-value pairs from `{'c': 3, 'd': 4}`:
    - `{'a': 1, 'b': 2, 'c': 3, 'd': 4}`.
3. Add key-value pairs from `{'e': 5, 'f': 6}`:
    - `{'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5, 'f': 6}`.

**Output:**
```python
{'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5, 'f': 6}
```

---

### Approach 2: Using Dictionary Unpacking (Python >= 3.5)
Python provides a more concise way to merge dictionaries using the unpacking operator `**`. This method is not only clean but also highly efficient.

### Code:
```python
def merge_three_dictionaries(dict1, dict2, dict3):
    # Merge dictionaries using dictionary unpacking
    merged_dict = {**dict1, **dict2, **dict3}
    
    return merged_dict
```

### Example Walkthrough:
**Input:**
```python
{'x': 10, 'y': 20}, {'z': 30}, {'a': 40, 'b': 50}
```

**Execution:**
1. Unpack all dictionaries into a single dictionary:
    - `merged_dict = {'x': 10, 'y': 20, 'z': 30, 'a': 40, 'b': 50}`.

**Output:**
```python
{'x': 10, 'y': 20, 'z': 30, 'a': 40, 'b': 50}
```

---

## Complexity Analysis

### Time Complexity:
- **Iterative Approach:** O(n), where `n` is the total number of key-value pairs in the input dictionaries.
- **Unpacking Approach:** O(n), similar to the iterative approach.

### Space Complexity:
- Both approaches require O(n) space for the merged dictionary.

---

## Final Notes
Both approaches effectively solve the problem, but if you're using Python 3.5 or higher, the unpacking method is more concise and recommended for cleaner code.
