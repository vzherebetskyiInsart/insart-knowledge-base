# Python Data Types: Reference Guide

Python is a **dynamically typed** language, meaning you do not need to explicitly declare a variable's type before using it. The Python interpreter infers the data type automatically at runtime based on the value assigned.

---

## 1. Quick Overview Matrix

| Category     | Data Type                 | Mutability              | Syntax Example             |
| :----------- | :------------------------ | :---------------------- | :------------------------- |
| **Text**     | `str`                     | Immutable               | `"Hello World"`            |
| **Numeric**  | `int`, `float`, `complex` | Immutable               | `42`, `3.14`, `2 + 3j`     |
| **Sequence** | `list`                    | **Mutable**             | `[1, 2, 3]`                |
| **Sequence** | `tuple`                   | Immutable               | `(1, 2, 3)`                |
| **Sequence** | `range`                   | Immutable               | `range(0, 10)`             |
| **Mapping**  | `dict`                    | **Mutable**             | `{"key": "value"}`         |
| **Set**      | `set`                     | **Mutable**             | `{1, 2, 3}`                |
| **Set**      | `frozenset`               | Immutable               | `frozenset([1, 2, 3])`     |
| **Boolean**  | `bool`                    | Immutable               | `True` or `False`          |
| **Binary**   | `bytes`, `bytearray`      | Immutable / **Mutable** | `b"Hello"`, `bytearray(5)` |
| **None**     | `NoneType`                | Immutable               | `None`                     |

---

## 2. Core Data Types Deep Dive

### Numeric Types

Python handles three primary types of numerical data:

- **`int`**: Whole numbers of unlimited precision (e.g., `10`, `-500`).
- **`float`**: Floating-point numbers representing decimal values (e.g., `3.14159`, `-0.001`).
- **`complex`**: Numbers with a real and imaginary part, represented with a `j` suffix (e.g., `4 + 5j`).

```python
# Numeric examples
age = 25              # int
pi = 3.14159          # float
coordinate = 3 + 2j   # complex
```

### Text Sequence Type

- **`str`**: Strings are immutable sequences of Unicode characters. They can be enclosed in single, double, or triple quotes (for multi-line blocks).

```python
# String examples
name = "Alice"
multiline_speech = """This is a string
spanning across multiple
lines of text."""
```

### Sequence Types (Collections)

- **`list`**: Ordered, mutable collections that can hold mixed data types.
- **`tuple`**: Ordered, immutable collections. They are often faster than lists and protect data from accidental modification.
- **`range`**: Represents an immutable sequence of numbers, commonly used for looping a specific number of times.

```python
# Sequence examples
shopping_list = ["apple", "banana", "cherry"]  # Mutable list
fixed_dimensions = (1920, 1080)               # Immutable tuple
loop_counter = range(1, 6)                     # Generates 1, 2, 3, 4, 5
```

### Mapping Type

- **`dict`**: Unordered (but preserves insertion order since Python 3.7) collections of key-value pairs. Keys must be unique and immutable (hashable), while values can be of any type.

```python
# Dictionary example
user_profile = {
    "username": "coder99",
    "followers": 1420,
    "is_active": True
}
```

### Set Types

- **`set`**: An unordered collection of unique items. Useful for eliminating duplicate values and performing mathematical set operations (unions, intersections).
- **`frozenset`**: An immutable version of a standard set. Because it is immutable, a frozenset can be used as a dictionary key.

```python
# Set examples
unique_ids = {101, 102, 103, 101} # Duplicates are automatically removed
frozen_ids = frozenset([1, 2, 3])
```

### Boolean and None Types

- **`bool`**: Represents logical values: `True` or `False`.
- **`NoneType`**: Represented by the keyword `None`. It signifies the absence of a value or a null pointer state.

```python
# Boolean and None examples
is_logged_in = False
database_connection = None
```

---

## 3. Checking and Converting Types

### Type Identification

You can use `type()` to inspect an object's exact type, or `isinstance()` to check if an object belongs to a specific class layout.

```python
x = [1, 2, 3]

print(type(x))             # Output: <class 'list'>
print(isinstance(x, list)) # Output: True
```

### Explicit Type Conversion (Casting)

You can convert variables between types using constructor functions:

```python
# Converting a float to an integer (truncates the decimal)
integer_version = int(5.9) # Result: 5

# Converting an integer to a string
string_version = str(42)   # Result: "42"

# Converting a list to a set to remove duplicates
deduplicated = list(set([1, 2, 2, 3, 3, 3])) # Result: [1, 2, 3]
```
