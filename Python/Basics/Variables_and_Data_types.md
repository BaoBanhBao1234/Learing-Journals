1. What Is a Variable?
- A variable is a name bound to an object, allowing a program to refer to and reuse that object.
- Assign a value with `=`: `name = "Ada"`.
- Python is dynamically typed: the object determines its type, so a name can later be reassigned to an object of another type.
- Assignment binds a name to an object; it does not automatically copy that object. Two names can refer to the same object.

```python
value = 10
value = "ten"

numbers_a = [1, 2]
numbers_b = numbers_a
numbers_b.append(3)
print(numbers_a)  # [1, 2, 3]
```

2. Naming Variables
- Names can contain letters, digits, and underscores, but cannot start with a digit.
- Names are case-sensitive: `count` and `Count` are different names.
- Python keywords such as `if`, `class`, and `return` cannot be used as variable names.
- Use descriptive `snake_case` names for variables and functions, such as `user_name` or `total_price`.
- Avoid reusing names of built-in functions and types, such as `list`, `str`, or `max`, because doing so can make them harder to use later.

3. Checking and Converting Types
- Use `type(value)` to inspect an object’s exact type.
- Use `isinstance(value, SomeType)` to check whether an object is an instance of a type or its subclass.
- Conversion functions include `int()`, `float()`, `str()`, `bool()`, `list()`, and `tuple()`.
- Conversion is not always possible: for example, `int("hello")` raises a `ValueError`.
- A type annotation can document the expected type, but it does not automatically enforce or convert the value at runtime.

```python
age = 20
print(type(age))            # <class 'int'>
print(isinstance(age, int)) # True

price: float = 9.99
```

4. Numeric Types
- **`int`**: whole numbers, including positive numbers, negative numbers, and zero. Python integers have arbitrary precision: they can grow as large as available memory allows.
- **`float`**: numbers with a fractional part or exponent notation, such as `3.14` or `1.2e3`. Floats use finite-precision binary representation, so some decimal fractions are approximate.
- **`complex`**: numbers with real and imaginary parts, written with `j`, such as `2 + 3j`.
- **`bool`**: the logical values `True` and `False`. `bool` is a subclass of `int`, but it is normally used to represent truth values.
- Python does not have a fixed maximum `int` value. `sys.maxsize` is a platform-dependent limit used for sizes and indexes in some implementation details; it is not the largest integer Python can represent.

```python
large_number = 2**100
print(large_number)

import sys
print(sys.maxsize)  # Not Python's maximum int
```

5. Text and Sequence Types
- **`str`**: an immutable sequence of Unicode text, written with single, double, or triple quotes.
- **`list`**: an ordered, mutable collection that can contain values of different types. Example: `["red", 3, True]`.
- **`tuple`**: an ordered, immutable collection. Example: `("red", 3, True)`.
- **`range`**: an immutable sequence of integers commonly used for iteration, such as `range(5)`.
- “Mutable” means an object can be changed after creation; “immutable” means it cannot be changed in place.

6. Mapping and Set Types
- **`dict`**: a mutable mapping of unique keys to values, such as `{"name": "Ada", "age": 20}`. Dictionary keys must be hashable.
- **`set`**: a mutable collection of unique, hashable elements with no guaranteed positional order, such as `{1, 2, 3}`.
- **`frozenset`**: an immutable set that can be used where a hashable set is needed.
- Empty sets use `set()`. `{}` creates an empty dictionary, not an empty set.

7. Binary Types
- **`bytes`**: an immutable sequence of byte values, often used for encoded or binary data.
- **`bytearray`**: a mutable sequence of bytes.
- **`memoryview`**: provides access to the data of a bytes-like object without necessarily copying it.
- These types are useful when working with files, network protocols, and other binary formats.

8. `None` and Missing Values
- `None` is Python’s special singleton object for representing the absence of a value or a value that is not available.
- Its type is `NoneType`. It is distinct from `0`, `False`, `""`, and empty collections, even though all of these are falsy in a Boolean context.
- Check for it with identity comparisons: `value is None` or `value is not None`.
- Functions without an explicit `return` value return `None` by default. `None` is also commonly used as a default parameter or a placeholder in a collection.
- `NaN` is a floating-point value used for undefined or invalid numeric results; it is not the same as `None`.

```python
result = None

if result is None:
    print("No result yet")
```

9. Key Takeaways
- Variables are names bound to objects, and the objects have types.
- Python’s dynamic typing allows a name to be reassigned to objects of different types.
- Choose a type based on how the data is used: for example, `list` for a changeable ordered collection, `tuple` for an immutable ordered collection, `dict` for key-value data, and `set` for unique items.
- Python `int` values have arbitrary precision; `sys.maxsize` is not the maximum integer.
- Use `is None` to check for the absence of a value, and remember that `None`, `False`, zero, and empty values are different objects or values.

10. Sources
- Real Python: Variables in Python: Usage and Best Practices https://realpython.com/python-variables/
- The New Stack: Python for Beginners: Data Types https://thenewstack.io/python-for-beginners-data-types/
- roadmap.sh: Python roadmap https://roadmap.sh/python/
- roadmap.sh: Python Null (None): Guide to Missing Values and NoneType https://roadmap.sh/python/null
- roadmap.sh: Python Max Int: Understanding Arbitrary Precision Integers https://roadmap.sh/python/max-int
- YouTube playlist: Data Types & Variables in Python | Chapter-2 | Python Programming https://www.youtube.com/playlist?list=PLBlnK6fEyqRhN-sfWgCU1z_Qhakc1AGOn 
