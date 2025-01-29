# Remove Duplicate Characters from a String

## Problem Statement

You are given a string `s`. Your task is to remove duplicate characters from the string while preserving the order of their first occurrences and return the modified string.

### Parameters:
- `s` (str): The input string, where the length of `s` is between 1 and 1000.

### Returns:
- A string containing only the first occurrence of each character from the input string, preserving their original order.

---

## Examples

### Example 1:
**Input:**
```python
s = "programming"
```
**Output:**
```python
"progamin"
```
**Explanation:**
- The characters `p`, `r`, `o`, `g`, `a`, `m`, `i`, and `n` appear for the first time in the input string in this order. Duplicate characters are removed.

### Example 2:
**Input:**
```python
s = "Hello, World!"
```
**Output:**
```python
"Helo, Wrd!"
```
**Explanation:**
- Each character is added to the result string the first time it is encountered. Subsequent duplicates are ignored.

---

## Solution Approach

### Steps to Solve:
1. **Initialize a Set or List to Track Seen Characters:**
   - Use a data structure (e.g., list or set) to keep track of characters that have already been added to the result.
2. **Iterate Through the Input String:**
   - Loop through each character in the string.
   - If the character is not in the tracking data structure, add it to both the result and the tracking structure.
3. **Build the Result String:**
   - Append characters to the result string as they are encountered for the first time.
4. **Return the Result String:**
   - The result contains only unique characters in the order of their first occurrences.

---

### Code Implementation

#### Solution 1: Using a List to Track Seen Characters
```python
def remove_duplicates(s):
    """
    Function to remove duplicate characters from the input string.

    Parameters:
    s (str): The input string from which duplicates need to be removed.

    Returns:
    str: The modified string with duplicates removed.
    """
    result = ''  # Initialize an empty string to store the result
    seen = ''  # Initialize an empty string to track seen characters

    # Loop through each character in the input string
    for char in s:
        # Check if the character has not been seen before
        if char not in seen:
            seen += char  # Add the character to seen
            result += char  # Add the character to the result string

    return result  # Return the modified string with duplicates removed
```

#### Solution 2: Using a List for Simplicity
```python
def remove_duplicates(s):
    """
    Function to remove duplicate characters from the input string.

    Parameters:
    s (str): The input string from which duplicates need to be removed.

    Returns:
    str: The modified string with duplicates removed.
    """
    my_lst = []

    for cha in s:
        if cha not in my_lst:
            my_lst.append(cha)

    my_str = "".join(my_lst)

    return my_str
```

---

### Code Walkthrough

1. **Input String:**
   - Example: `s = "programming"`
2. **Iteration Process:**
   - `char = 'p'`: Not in `seen`, add to `result` and `seen`. Result = "p".
   - `char = 'r'`: Not in `seen`, add to `result` and `seen`. Result = "pr".
   - `char = 'o'`: Not in `seen`, add to `result` and `seen`. Result = "pro".
   - Continue for all characters.
3. **Final Result:**
   - Result = "progamin".

---

### Complexity Analysis

1. **Time Complexity:**
   - Iterating through the string takes **O(n)**, where `n` is the length of the string.
   - Checking membership in a list/set is **O(1)** for a set and **O(n)** for a list. Hence:
     - Using a list: **O(n^2)** in the worst case.
     - Using a set: **O(n)**.

2. **Space Complexity:**
   - The space required for the `seen` data structure is proportional to the number of unique characters in the string: **O(u)**, where `u` is the number of unique characters.

