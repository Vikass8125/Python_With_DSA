# Check Substring

## Problem Statement

You are given two strings, `s` and `t`. Your task is to determine if the string `t` is a substring of the string `s`. A substring is a contiguous sequence of characters within a string. Do not use any built-in functions for string operations and do not use recursion.

### Input:
- Two strings `s` and `t`, where `1 <= len(s), len(t) <= 1000`.

### Output:
- A boolean value (`True` or `False`) indicating whether `t` is a substring of `s`.

---

## Examples

### Example 1:
**Input:**
```python
s = "hello world"
t = "world"
```

**Output:**
```python
True
```

**Explanation:**
The string `t` ("world") is a contiguous part of the string `s` ("hello world").

---

### Example 2:
**Input:**
```python
s = "hello world"
t = "worlds"
```

**Output:**
```python
False
```

**Explanation:**
The string `t` ("worlds") is not found as a contiguous part of the string `s` ("hello world").

---

## Solution Approach

### Brute Force Approach:
1. **Iterate through `s`:**
   - Check each possible starting position in `s` where `t` could fit.
2. **Character Comparison:**
   - For each starting position in `s`, compare the characters in `t` one by one.
3. **Early Exit:**
   - If all characters match, return `True`.
   - If no match is found after checking all possible positions, return `False`.

---

### Code Implementation (Brute Force)
```python
def is_substring(s, t):
    """
    Function to check if string t is a substring of string s without using built-in functions and recursion.
    
    Parameters:
    s (str): The main string.
    t (str): The string to check as a substring.
    
    Returns:
    bool: True if t is a substring of s, False otherwise.
    """
    len_s = 0
    len_t = 0
    
    # Calculate lengths of s and t
    while s[len_s:]:
        len_s += 1
    while t[len_t:]:
        len_t += 1
    
    # If t is longer than s, it cannot be a substring
    if len_t > len_s:
        return False
 
    # Check for substring
    for i in range(len_s - len_t + 1):  # Only check up to len_s - len_t
        j = 0
        while j < len_t and s[i + j] == t[j]:  # Check each character
            j += 1
        if j == len_t:  # If we matched the whole t
            return True
 
    return False  # t is not a substring of s
```

---

### Code Walkthrough

1. **Length Calculation:**
   - First, manually calculate the lengths of `s` and `t` by iterating over each character.
   - For example, for `s = "hello world"`, the length is 11, and for `t = "world"`, the length is 5.

2. **Early Check:**
   - If the length of `t` is greater than `s`, immediately return `False` because `t` cannot be a substring.

3. **Iterate Through `s`:**
   - For each possible starting position in `s`, attempt to match the characters of `t`.
   - Example: For `s = "hello world"` and `t = "world"`, start checking from index 6.

4. **Character Comparison:**
   - Compare characters of `t` with the corresponding characters in `s`.
   - If all characters match, return `True`.
   - Otherwise, continue to the next starting position in `s`.

5. **Return Result:**
   - If no match is found after checking all positions, return `False`.

---

### Dry Run

#### Input:
```python
s = "hello world"
t = "world"
```

#### Execution Steps:
| Step | `i` (Index in `s`) | Characters Compared     | Result  |
|------|---------------------|--------------------------|---------|
| 1    | 0                   | `hello` vs `world`      | No Match|
| 2    | 1                   | `ello ` vs `world`      | No Match|
| 3    | 2                   | `llo w` vs `world`      | No Match|
| 4    | 6                   | `world` vs `world`      | Match   |

**Output:**
```python
True
```

---

## Complexity Analysis

1. **Time Complexity:**
   - Outer loop runs up to `len(s) - len(t) + 1` times.
   - Inner loop compares up to `len(t)` characters for each starting position.
   - Worst-case time complexity: **O(n * m)**, where `n` is the length of `s` and `m` is the length of `t`.

2. **Space Complexity:**
   - No extra space is used apart from a few variables.
   - Space complexity: **O(1)**.

---

## Optimal Approach (Optional):
Using sliding window or hash-based techniques can further optimize the solution when built-in functions are allowed.

---
