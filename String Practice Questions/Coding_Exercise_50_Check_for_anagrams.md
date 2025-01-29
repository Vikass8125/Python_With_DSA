# Check for Anagram

## Problem Description
You are given two strings `s` and `t`. Your task is to determine if string `t` is an anagram of string `s`. An anagram is a word or phrase formed by rearranging the characters of a different word or phrase, using all the original characters exactly once.

### Input:
Two strings `s` and `t` where both lengths are between 1 and 1000.

### Output:
Return `True` if `t` is an anagram of `s`, and `False` otherwise.

---

## Examples

### Example 1:
**Input:**
```python
s = "anagram"
t = "nagaram"
```
**Output:**
```python
True
```
**Explanation:**
- The characters in `t` are a rearranged version of the characters in `s`, so `t` is an anagram of `s`.

### Example 2:
**Input:**
```python
s = "rat"
t = "car"
```
**Output:**
```python
False
```
**Explanation:**
- The characters in `t` cannot be rearranged to form `s`, so `t` is not an anagram of `s`.

---

## Solution Approach

### Steps to Solve:
1. **Check Lengths:**
   - If the lengths of `s` and `t` are not equal, return `False` immediately.
   
2. **Count Character Frequencies:**
   - Create an array or dictionary to store the frequency of each character in `s` and `t`.
   - Compare the character frequencies for both strings.

3. **Sorting Approach:**
   - Alternatively, sort both strings and compare if they are equal.

---

### Solution 1: Character Frequency Count
```python
def is_anagram(s, t):
    """
    Function to check if t is an anagram of s without using built-in functions.

    Parameters:
    s (str): The first input string.
    t (str): The second input string.

    Returns:
    bool: True if t is an anagram of s, False otherwise.
    """
    # If the lengths of s and t are not equal, they cannot be anagrams
    if len(s) != len(t):
        return False

    # Create two arrays to count character frequencies for both strings
    char_count_s = [0] * 26  # Assuming lowercase a-z characters
    char_count_t = [0] * 26  # Assuming lowercase a-z characters

    # Loop through the characters in the first string (s) and count occurrences
    for char in s:
        char_count_s[ord(char) - ord('a')] += 1

    # Loop through the characters in the second string (t) and count occurrences
    for char in t:
        char_count_t[ord(char) - ord('a')] += 1

    # Compare the character frequency arrays for both strings
    for i in range(26):
        if char_count_s[i] != char_count_t[i]:
            return False  # If there is a mismatch in frequencies, return False

    return True  # If all frequencies match, return True
```

---

### Solution 2: Sorting Approach
```python
def is_anagram(s, t):
    """
    Function to check if t is an anagram of s.

    Parameters:
    s (str): The first input string.
    t (str): The second input string.

    Returns:
    bool: True if t is an anagram of s, False otherwise.
    """
    # If lengths are not equal, they cannot be anagrams
    if len(s) != len(t):
        return False

    # Sort both strings and compare
    s_sorted = sorted(s)
    t_sorted = sorted(t)

    return s_sorted == t_sorted
```

---

### Code Walkthrough
1. **Frequency Count Method:**
   - Input: `s = "anagram", t = "nagaram"`
   - Count frequencies:
     - `s`: `[3, 0, 0, 0, 1, 0, 0, 0, 1, ...]` (3 for `a`, 1 for `n`, etc.)
     - `t`: `[3, 0, 0, 0, 1, 0, 0, 0, 1, ...]` (same as `s`)
   - Result: Both frequency arrays match, so return `True`.

2. **Sorting Method:**
   - Input: `s = "rat", t = "car"`
   - Sort both strings:
     - `s_sorted = ["a", "r", "t"]`
     - `t_sorted = ["a", "c", "r"]`
   - Result: Sorted strings do not match, so return `False`.

---

### Complexity Analysis

1. **Frequency Count Method:**
   - Time Complexity: **O(n)**
     - Loop through both strings once to count character frequencies.
   - Space Complexity: **O(1)** (constant space for frequency arrays).

2. **Sorting Method:**
   - Time Complexity: **O(n log n)**
     - Sorting both strings takes `O(n log n)`.
   - Space Complexity: **O(n)** (space for sorted arrays).

