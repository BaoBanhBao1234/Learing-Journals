1. What Is a Tuple?
- A tuple is an ordered sequence of values. It can contain values of different types and can be nested inside another tuple.
- Tuples are immutable: after creation, their elements cannot be replaced, added, or removed.
- Tuples are useful for grouping related values that should stay in a fixed order, such as coordinates or a function's multiple results.
- Lists are mutable and are usually chosen when the collection needs to change; tuples are immutable and often represent fixed records or sequences.

2. Creating Tuples
- Commas create a tuple; parentheses are commonly used to make the grouping clear.
- An empty tuple is `()`.
- A one-item tuple must include a trailing comma, such as `("apple",)`. `("apple")` is just a string in parentheses.
- Parentheses can be omitted in many assignment contexts because the comma is what packs the values into a tuple.

```python
empty = ()
point = (3, 5)
colors = "blue", "green", "red"
single_item = ("apple",)

print(type(single_item))  # <class 'tuple'>
print(type(("apple")))   # <class 'str'>
```

3. Accessing and Slicing Tuples
- Tuples support indexing and slicing like lists and strings. Indexes start at `0`, and negative indexes count from the end.
- A slice returns a new tuple.
- Use `len(items)` to get the number of elements and `in` to test whether a value is present.

```python
person = ("Ada", 36, "London")

print(person[0])     # Ada
print(person[-1])    # London
print(person[1:])    # (36, 'London')
print("Ada" in person)  # True
```

4. Tuple Immutability
- You cannot assign to a tuple index or change the tuple's length. An item assignment raises `TypeError`.
- A tuple can contain mutable objects, such as lists. The tuple still refers to the same list, and that list's contents can change.
- Immutability applies to the tuple's references and structure; it does not make every object inside the tuple immutable.

```python
record = ("Ada", ["Python", "Math"])
record[1].append("Science")
print(record)  # ('Ada', ['Python', 'Math', 'Science'])
```

5. Tuple Packing and Unpacking
- Tuple packing combines comma-separated values into one tuple.
- Unpacking assigns tuple elements to multiple variables. The number of variables normally must match the number of elements.
- Use a starred target such as `first, *middle, last` to collect zero or more remaining items into a list.

```python
coordinates = 10, 20  # Packing
x, y = coordinates    # Unpacking

first, *middle, last = (1, 2, 3, 4)
print(x, y)       # 10 20
print(middle)     # [2, 3]
```

6. Returning Multiple Values from a Function
- A Python function returns one object. When a `return` statement lists values separated by commas, Python packs them into a tuple.
- The caller can store the tuple as one value or unpack it into separate variables.
- Unpacking depends on the order of the returned values. The number of targets must match unless starred unpacking is used.

```python
def divide(number, divisor):
    quotient = number // divisor
    remainder = number % divisor
    return quotient, remainder

result = divide(17, 5)
quotient, remainder = divide(17, 5)
print(result)                 # (3, 2)
print(quotient, remainder)    # 3 2
```

7. Tuple Methods and Built-in Functions
- Tuples have two methods: `count(value)` returns how many times a value occurs, and `index(value)` returns the index of its first occurrence.
- `len()`, `min()`, `max()`, and `sum()` work with tuples when their values are appropriate for the operation.
- Tuples do not have list methods such as `append()` or `remove()` because their elements cannot be changed.

```python
scores = (80, 95, 80, 72)

print(scores.count(80))  # 2
print(scores.index(95))  # 1
print(max(scores))       # 95
```

8. Tuples as Dictionary Keys
- A tuple can be used as a dictionary key or set element when all of its contents are hashable.
- Tuples containing mutable values such as lists are not hashable and cannot be used as dictionary keys.
- This makes tuples of immutable values useful for representing compound keys, such as a grid coordinate `(row, column)`.

```python
locations = {(2, 4): "Library", (5, 1): "Cafe"}
print(locations[(2, 4)])  # Library
```

9. Named Tuples
- A named tuple keeps tuple behavior while letting code access fields by descriptive names as well as by position.
- Use `collections.namedtuple` for a lightweight fixed record when named fields make the data easier to understand.
- For more complex structured data, a `dataclass` may be a better fit; for flexible key-value data, consider a dictionary.

```python
from collections import namedtuple

Point = namedtuple("Point", ["x", "y"])
point = Point(3, 5)
print(point.x)  # 3
```

10. Common Tuple Mistakes
- Forgetting the comma in a one-item tuple: write `("only",)`, not `("only")`.
- Confusing immutability with deep immutability: a tuple can contain a mutable list whose contents can change.
- Unpacking the wrong number of values raises `ValueError`; verify the number and order of returned values.
- Trying to call list methods such as `append()` on a tuple raises `AttributeError`.
- A tuple containing a list cannot be used as a dictionary key because it is not hashable.

11. Key Takeaways
- A tuple is an ordered, immutable sequence, and commas define its elements.
- Use a trailing comma to create a one-item tuple.
- Tuples support indexing, slicing, iteration, packing, and unpacking.
- Returning comma-separated values from a function returns them together as a tuple.
- Use tuples for fixed groups of related values; use lists when the collection needs to change.

12. Sources
- Python documentation: Tuples and Sequences https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences
- The New Stack: Python for Beginners: When and How to Use Tuples https://thenewstack.io/python-for-beginners-when-and-how-to-use-tuples/
- roadmap.sh: Returning Multiple Values in Python https://roadmap.sh/python/return-multiple-values
- YouTube: Python Tuples https://www.youtube.com/watch?v=fR_D_KIAYrE
