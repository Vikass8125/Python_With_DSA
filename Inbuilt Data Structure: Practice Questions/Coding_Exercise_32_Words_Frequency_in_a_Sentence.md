# Count Word Frequency

## Problem Statement

Design a Python function named `count_word_frequency` to count the frequency of words in a sentence and store the counts in a dictionary.

### Parameters:
- `sentence` (str): The input sentence where you need to count the frequency of each word.

### Returns:
- A dictionary where the keys are words from the sentence and the values are their corresponding frequencies.

---

## Examples

### Example 1:
**Input:**
```python
sentence = "hello world hello"
```
**Output:**
```python
{'hello': 2, 'world': 1}
```
**Explanation:**
- The word `hello` appears 2 times, and the word `world` appears 1 time in the sentence.

### Example 2:
**Input:**
```python
sentence = "the quick brown fox jumps over the lazy dog"
```
**Output:**
```python
{'the': 2, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1, 'over': 1, 'lazy': 1, 'dog': 1}
```
**Explanation:**
- Each word is counted for its occurrences, and the word `the` appears 2 times in the sentence.

---

## Solution Approach

### Steps to Solve:
1. **Split the Sentence:**
   - Use the `split()` method to break the sentence into words. This separates words based on spaces.
2. **Create a Dictionary:**
   - Use an empty dictionary to store each word as a key and its frequency as the value.
3. **Iterate Through Words:**
   - Loop through the list of words obtained from the split operation.
   - For each word, check if it already exists in the dictionary:
     - If yes, increment its count by 1.
     - If no, add it to the dictionary with a count of 1.
4. **Return the Dictionary:**
   - Once all words are processed, return the dictionary containing word frequencies.

---

### Code Implementation
```python
def count_word_frequency(sentence):
    # Initialize an empty dictionary to store word frequencies
    word_count = {}

    # Split the sentence into words using space as the delimiter
    words = sentence.split()

    # Iterate through each word in the list of words
    for word in words:
        # If the word is already in the dictionary, increment its count
        if word in word_count:
            word_count[word] += 1
        # If the word is not in the dictionary, add it with a count of 1
        else:
            word_count[word] = 1

    return word_count
```

---

### Code Walkthrough
1. **Splitting the Sentence:**
   - Given the input `"hello world hello"`, the `split()` method splits it into a list: `['hello', 'world', 'hello']`.

2. **Creating the Dictionary:**
   - The dictionary starts empty: `{}`.

3. **Iterating Through Words:**
   - First word: `'hello'`
     - Not in the dictionary, so add it: `{'hello': 1}`.
   - Second word: `'world'`
     - Not in the dictionary, so add it: `{'hello': 1, 'world': 1}`.
   - Third word: `'hello'`
     - Already in the dictionary, so increment its count: `{'hello': 2, 'world': 1}`.

4. **Returning the Result:**
   - The function returns the final dictionary: `{'hello': 2, 'world': 1}`.

---

### Dry Run
#### Input:
`sentence = "the quick brown fox jumps over the lazy dog"`

#### Execution Steps:
| Step | Word   | Dictionary State                                  |
|------|--------|--------------------------------------------------|
| 1    | `the`  | `{'the': 1}`                                     |
| 2    | `quick`| `{'the': 1, 'quick': 1}`                         |
| 3    | `brown`| `{'the': 1, 'quick': 1, 'brown': 1}`             |
| 4    | `fox`  | `{'the': 1, 'quick': 1, 'brown': 1, 'fox': 1}`   |
| 5    | `jumps`| `{'the': 1, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1}`|
| 6    | `over` | `{'the': 1, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1, 'over': 1}`|
| 7    | `the`  | `{'the': 2, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1, 'over': 1}`|
| 8    | `lazy` | `{'the': 2, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1, 'over': 1, 'lazy': 1}`|
| 9    | `dog`  | `{'the': 2, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1, 'over': 1, 'lazy': 1, 'dog': 1}`|

**Output:** `{'the': 2, 'quick': 1, 'brown': 1, 'fox': 1, 'jumps': 1, 'over': 1, 'lazy': 1, 'dog': 1}`

---

### Complexity Analysis

1. **Time Complexity:**
   - Splitting the sentence takes **O(n)**, where `n` is the length of the sentence.
   - Iterating through the words takes **O(m)**, where `m` is the number of words.
   - Overall time complexity: **O(n + m)**.

2. **Space Complexity:**
   - The space required for the dictionary is **O(m)**, where `m` is the number of unique words in the sentence.

