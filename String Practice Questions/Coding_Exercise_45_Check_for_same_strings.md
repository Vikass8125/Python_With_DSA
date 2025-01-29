# Check If Two Strings Are Equal

## Problem Statement

You are given two strings `s` and `t`. Your task is to check if the two strings are equal. Two strings are considered equal if they have the same length and the same characters at each position. You are **not** allowed to use any built-in string comparison functions.

### Parameters:
- `s` (str): The first string.
- `t` (str): The second string.

### Returns:
- A boolean value (`True` or `False`) indicating whether the two strings are equal.

---

## Examples

### Example 1:
**Input:**
```python
s = "hello"
t = "hello"
```
**Output:**
```python
True
```
**Explanation:**
- Both strings have the same length and identical characters in the same order.

### Example 2:
**Input:**
```python
s = "hello"
t = "world"
```
**Output:**
```python
False
```
**Explanation:**
- The two strings have different characters at multiple positions.

### Example 3:
**Input:**
```python
s = "abcd"
t = "abcde"
```
**Output:**
```python
False
```
**Explanation:**
- The lengths of the strings are different, so they cannot be equal.

---

## Solution Approach

### Brute Force Approach

### Steps to Solve:
1. **Manually Compute String Lengths:**
   - Iterate through each character in `s` and `t` to determine their lengths.
2. **Compare Lengths:**
   - If the lengths are different, return `False` immediately.
3. **Compare Each Character:**
   - Loop through both strings and compare corresponding characters.
   - If a mismatch is found, return `False`.
   - If all characters match, return `True`.

### Code Implementation
```python
def are_equal_strings(s, t):
    """
    Function to check if two strings are equal without using built-in functions.
    
    Parameters:
    s (str): The first string.
    t (str): The second string.
    
    Returns:
    bool: True if the strings are equal, False otherwise.
    """
    len_s = 0
    len_t = 0
    
    # Calculate lengths of both strings manually
    while len_s < len(s):
        len_s += 1
    while len_t < len(t):
        len_t += 1
    
    # If lengths are not equal, the strings can't be equal
    if len_s != len_t:
        return False
    
    # Compare characters one by one
    for i in range(len_s):
        if s[i] != t[i]:
            return False  # If a character doesn't match, return False
 
    return True  # If all characters match, return True
```

---

## Optimized Approach

### Steps to Solve:
1. **Check Lengths First:**
   - If the lengths of `s` and `t` are different, return `False` immediately.
2. **Use While Loop for Comparison:**
   - Iterate through both strings simultaneously, comparing character by character.
   - If any mismatch is found, return `False`.
   - If the loop completes without finding a mismatch, return `True`.

### Optimized Code Implementation
```python
def are_equal_strings(s, t):
    """
    Function to check if two strings are equal without using built-in functions.
    
    Parameters:
    s (str): The first string.
    t (str): The second string.
    
    Returns:
    bool: True if the strings are equal, False otherwise.
    """
    if len(s) != len(t):
        return False
    
    is_same = True
    s_pos = 0
    t_pos = 0
    
    while s_pos < len(s) and t_pos < len(t):
        if s[s_pos] != t[t_pos]:
            is_same = False
            break
        s_pos += 1
        t_pos += 1
        
    return is_same
```

---

## Complexity Analysis

1. **Brute Force Approach:**
   - **Time Complexity:** `O(n)`, where `n` is the length of the strings (looping through characters).
   - **Space Complexity:** `O(1)`, since only a few integer variables are used.

2. **Optimized Approach:**
   - **Time Complexity:** `O(n)`, as we iterate through the strings only once.
   - **Space Complexity:** `O(1)`, using only a few integer variables for indexing.

---
