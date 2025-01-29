# Reverse a String

## Problem Statement
You are given a string `s`. Your task is to return the reversed version of the string.

### Parameters:
- `s` (str): A single string with a length between 1 and 1000.

### Returns:
- A single string that is the reverse of the input string.

---

## Examples

### Example 1:
**Input:**
```python
s = "hello"
```
**Output:**
```python
"olleh"
```

### Example 2:
**Input:**
```python
s = "Python"
```
**Output:**
```python
"nohtyP"
```

---

## Solution Approach

### Brute Force Solution

#### Steps to Solve:
1. Initialize an empty string `reversed_str`.
2. Loop through the given string from the last character to the first.
3. Append each character to `reversed_str`.
4. Return the `reversed_str`.

#### Code Implementation:
```python
def reverse_string(s):
    """
    Function to return the reversed version of the input string.
    
    Parameters:
    s (str): The input string to be reversed.
    
    Returns:
    str: The reversed string.
    """
    # Initialize an empty string to hold the reversed version
    reversed_str = ''
    
    # Loop through the string in reverse order
    for i in range(len(s) - 1, -1, -1):
        # Concatenate each character to the reversed string
        reversed_str += s[i]
    
    # Return the reversed string
    return reversed_str
```

### Code Walkthrough
1. Given `s = "hello"`, we initialize an empty string `reversed_str = ""`.
2. We iterate through `s` from the last character to the first.
   - 'o' is added → `reversed_str = "o"`
   - 'l' is added → `reversed_str = "ol"`
   - 'l' is added → `reversed_str = "oll"`
   - 'e' is added → `reversed_str = "olle"`
   - 'h' is added → `reversed_str = "olleh"`
3. The function returns `"olleh"`.

### Complexity Analysis
- **Time Complexity:** `O(n)`, where `n` is the length of the string (since we traverse each character once).
- **Space Complexity:** `O(n)`, since we store the reversed string.

---

## Optimal Solution

Instead of manually iterating over the string, we can use Python slicing to reverse it efficiently.

#### Code Implementation:
```python
def reverse_string(s):
    """
    Function to return the reversed version of the input string using slicing.
    
    Parameters:
    s (str): The input string to be reversed.
    
    Returns:
    str: The reversed string.
    """
    return s[::-1]
```

### Explanation:
- The slice notation `s[::-1]` means:
  - Start from the end (`-1` step) and go backward to the beginning.
- This creates a reversed version of the string in `O(n)` time complexity but is more concise.

### Complexity Analysis
- **Time Complexity:** `O(n)`, since slicing needs to traverse the string once.
- **Space Complexity:** `O(n)`, since a new string is created.

---

## Summary
| Approach | Time Complexity | Space Complexity | Explanation |
|----------|----------------|------------------|-------------|
| Brute Force | `O(n)` | `O(n)` | Iterates through each character in reverse and appends to a new string. |
| Optimal (Slicing) | `O(n)` | `O(n)` | Uses Python's slicing mechanism to reverse the string efficiently. |

For Python, the slicing approach is preferred because it is more concise and utilizes built-in optimizations.
