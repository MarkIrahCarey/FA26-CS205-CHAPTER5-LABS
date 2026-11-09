# Lab 5: Lists and Dictionaries

These labs cover dictionaries, list manipulation, 2D lists, numerical methods, and RPG game mechanics. The goal is to practice working with different data structures and creating functions that solve real-world problems.

## Chapter 5: Summary of Methods

### List Methods
| Method              | Syntax                        | Description                                                                 | Notes |
|---------------------|-------------------------------|-----------------------------------------------------------------------------|-------|
| `append()`          | `L.append(element)`           | Adds a single element to the **end** of the list                            | Mutates the list |
| `extend()`          | `L.extend(aList)`             | Adds all elements from another list/iterable to the end                     | Adds multiple items |
| `insert()`          | `L.insert(index, element)`    | Inserts an element at a specific index (shifts others right)               | Appends if index is too large |
| `pop()`             | `L.pop()` or `L.pop(index)`   | Removes and **returns** the last element (or element at given index)       | Most common removal method |
| `index()`           | `L.index(target)`             | Returns the **first index** of the target element                           | Raises error if not found |
| `sort()`            | `L.sort()`                    | Sorts the list **in place** (ascending order)                               | Mutates the original list |

**Other Important List Operations:**
- `len(L)` → Returns the number of elements
- `L[i] = value` → Replace element at index `i`
- `target in L` → Checks if an element exists
- `L1 + L2` → Concatenates two lists
- `L1 == L2` → Checks equality

### Tuples
- A **tuple** is like a list but **immutable** (cannot be changed).
- Created with parentheses: `fruits = ("apple", "banana")`
- Supports concatenation (`+`) and conversion from list: `tuple(my_list)`

### Why We Create Functions
- Functions allow us to **organize code** into reusable, logical blocks
- They make programs easier to read, debug, and maintain
- Functions support the idea of **divide and conquer** – breaking complex problems into smaller pieces

### Function Syntax
```python
def function_name(parameter1, parameter2, ...):
    """Optional docstring - describes what the function does."""
    # Body of the function
    # ... your code here ...
    return result   # Optional: returns a value
```

### Dictionary Methods

| Method                  | Syntax                              | Description                                                                      | Notes |
|-------------------------|-------------------------------------|----------------------------------------------------------------------------------|-------|
| `d[key] = value`        | `d[key] = value`                    | Adds a new key-value pair **or** replaces existing value                         | Most common operation |
| `get()`                 | `d.get(key, default)`               | Returns value if key exists, otherwise returns `default` (None if omitted)       | Safe access (no error) |
| `pop()`                 | `d.pop(key, default)`               | Removes key and returns its value; returns `default` if key not found            | Safe removal |
| `keys()`                | `list(d.keys())`                    | Returns a list of all keys                                                       | Useful for looping |
| `values()`              | `list(d.values())`                  | Returns a list of all values                                                     | Good for max/min |
| `items()`               | `for k, v in d.items()`             | Returns (key, value) pairs – best for traversing both key and value              | Most convenient |
| `clear()`               | `d.clear()`                         | Removes **all** entries from the dictionary                                      | Empties the dict |

### 2D Lists (Nested Lists)

- Created as a **list of lists**:  
  ```python
  matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

- Access/Modify: ```matrix[row][column]```
- Traverse using nested loops (outer = rows, inner = columns)
- Best practice for creation of 2D (to avoid aliasing):
```zeros = [[0 for col in range(3)] for row in range(3)]```

## Grading Criteria

Like previous labs, I will grade for functionality, but documentation will also be key components of your grade. Good documentation helps explain your logic, especially when processing data.

| Lab | Description | Comments/Documentation | Functionality | Test Cases| Total |
|-----|-------------|------------------------|---------------|-------|-----------|
| Lab5a | Typhoon Tracker | 10pts | 15pts | 5pts | 30pts 
| Lab5b | Grade Curver | 10pts | 15pts | 5pts | 30pts
| Lab5c | my_range() | 10pts | 20pts | 10pts| 40pts |
| Lab5d | RPG Level up and Use Item Manager | 20pts | 20pts | 10pts | 50pts
| Total | | 50pts | 70pts | 30pts |150pts