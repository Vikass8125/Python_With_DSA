# Count Even and Odd Numbers in a List

## Problem Statement
You are given a list of integers. Write a Python program that counts and returns the number of even and odd numbers in the list.

### Parameters:
- `lst` (List of integers): The list of integers where you will count the even and odd numbers.

### Returns:
- A tuple `(even_count, odd_count)` where:
  - `even_count` is the number of even numbers.
  - `odd_count` is the number of odd numbers.

### Example:

#### Example 1:
**Input:**
```python
lst = [1, 2, 3, 4, 5]
```
**Output:**
```
(2, 3)
```
**Explanation:**
- There are 2 even numbers: 2, 4.
- There are 3 odd numbers: 1, 3, 5.

#### Example 2:
**Input:**
```python
lst = [10, 15, 20, 25, 30]
```
**Output:**
```
(3, 2)
```
**Explanation:**
- There are 3 even numbers: 10, 20, 30.
- There are 2 odd numbers: 15, 25.

---

## Explanation
The task is to count the number of even and odd integers in a given list. To determine whether a number is even or odd:
- A number is **even** if it is divisible by 2 (`num % 2 == 0`).
- Otherwise, it is **odd**.

By iterating through the list and checking each number, we can maintain counters for both even and odd numbers.

---

## Solution
We will use a simple iterative approach to count the even and odd numbers in the list.

### Implementation:
```python
def count_even_odd(lst):
    # Initialize counters for even and odd numbers
    even_count = 0
    odd_count = 0
    
    # Iterate through each number in the list
    for num in lst:
        if num % 2 == 0:  # Check if the number is even
            even_count += 1
        else:  # Otherwise, it's odd
            odd_count += 1
    
    # Return a tuple containing the counts of even and odd numbers
    return even_count, odd_count

# Example Usage:
lst = [1, 2, 3, 4, 5]
print(count_even_odd(lst))  # Output: (2, 3)
```

---

## Code Walkthrough
1. **Initialization**:
   - Define two counters: `even_count` and `odd_count`, both initialized to 0.
2. **Iteration**:
   - Loop through each element `num` in the list `lst`.
   - Check if `num % 2 == 0` (even). If true, increment `even_count`.
   - Otherwise, increment `odd_count`.
3. **Return Result**:
   - After the loop, return a tuple containing `even_count` and `odd_count`.

---

## Complexity Analysis
### Time Complexity
- **O(n)**: The loop iterates through all `n` elements in the list once.

### Space Complexity
- **O(1)**: No additional space is used apart from the counters.

---

## Alternative Solutions

### Using List Comprehensions
We can achieve the same result using list comprehensions to filter even and odd numbers.
```python
def count_even_odd(lst):
    even_count = len([num for num in lst if num % 2 == 0])
    odd_count = len([num for num in lst if num % 2 != 0])
    return even_count, odd_count

# Example Usage:
lst = [1, 2, 3, 4, 5]
print(count_even_odd(lst))  # Output: (2, 3)
```
- **Time Complexity**: O(n)
- **Space Complexity**: O(n) (due to the creation of temporary lists).

### Using the `filter` Function
Another alternative is to use the `filter` function to separate even and odd numbers.
```python
def count_even_odd(lst):
    even_count = len(list(filter(lambda x: x % 2 == 0, lst)))
    odd_count = len(list(filter(lambda x: x % 2 != 0, lst)))
    return even_count, odd_count

# Example Usage:
lst = [1, 2, 3, 4, 5]
print(count_even_odd(lst))  # Output: (2, 3)
```
- **Time Complexity**: O(n)
- **Space Complexity**: O(n) (due to the creation of temporary lists).

---

## Summary
The iterative solution is the most memory-efficient with an `O(1)` space complexity. Alternative approaches using list comprehensions or the `filter` function are more concise but require additional space. Choose the approach that best suits your needs based on readability and memory considerations.
