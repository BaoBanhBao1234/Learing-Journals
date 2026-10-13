1. What Is a Python Set?
- A set is a mutable collection of unique elements. Duplicate values are stored only once.
- Sets are unordered, so they do not provide stable positions or support indexing and slicing. Do not rely on a particular display or iteration order.
- Sets are useful for fast membership checks, removing duplicates, and comparing groups of values with set operations.
- Set elements must be hashable. Numbers, strings, and tuples of hashable values can be elements; lists and dictionaries cannot.

2. Creating Sets
- Use curly braces with comma-separated values to create a non-empty set: `colors = {"blue", "green", "red"}`.
- Use `set(iterable)` to create a set from a list, tuple, string, or another iterable.
- Use `set()` to create an empty set. `{}` creates an empty dictionary, not an empty set.
- Repeated values in the input are automatically reduced to one set element.

```python
numbers = {1, 2, 2, 3}
from_list = set(["red", "green", "red"])
empty_set = set()
empty_dictionary = {}

print(numbers)     # {1, 2, 3}
print(from_list)   # {'red', 'green'}
print(type(empty_set))        # <class 'set'>
print(type(empty_dictionary)) # <class 'dict'>
```

3. Adding and Removing Elements
- `add(value)` adds one element. Adding a value that is already present does not create a duplicate.
- `update(iterable)` adds all elements from one or more iterables.
- `remove(value)` deletes an element and raises `KeyError` if it is absent.
- `discard(value)` deletes an element if present and does nothing if it is absent.
- `pop()` removes and returns an arbitrary element; it does not remove a predictable first or last item. Calling it on an empty set raises `KeyError`.
- `clear()` removes all elements from the set.

```python
languages = {"Python", "Java"}
languages.add("Go")
languages.update(["Rust", "Java"])
languages.discard("Java")
print(languages)
```

4. Set Operations
- **Union (`|` or `union`)** returns all unique elements that are in either set.
- **Intersection (`&` or `intersection`)** returns elements shared by both sets.
- **Difference (`-` or `difference`)** returns elements in the left set that are not in the right set. The order matters: `A - B` may differ from `B - A`.
- **Symmetric difference (`^` or `symmetric_difference`)** returns elements that are in either set, but not in both.
- These operations return a new set and leave the original sets unchanged.

```python
A = {1, 2, 4, 6}
B = {1, 2, 3, 4}

print(A | B)  # {1, 2, 3, 4, 6}
print(A & B)  # {1, 2, 4}
print(A - B)  # {6}
print(A ^ B)  # {3, 6}
```

5. Subsets, Supersets, and Disjoint Sets
- `A <= B` or `A.issubset(B)` checks whether every element in `A` is also in `B`.
- `A >= B` or `A.issuperset(B)` checks whether `A` contains every element in `B`.
- `<` and `>` check proper subsets and supersets: the sets must be different.
- `A.isdisjoint(B)` is true when the sets share no elements.
- Use `in` and `not in` to test whether an element is present.

```python
all_permissions = {"read", "write", "share"}
user_permissions = {"read", "share"}

print(user_permissions <= all_permissions)  # True
print(all_permissions >= user_permissions)  # True
print(user_permissions.isdisjoint({"admin"}))  # True
print("write" in user_permissions)  # False
```

6. Iterating Over Sets
- Use a `for` loop to visit each element in a set.
- A set does not guarantee iteration order. If you need a predictable order for display or processing, use `sorted(my_set)` or convert it to a list and sort it.
- Set operations and membership checks are often convenient when order and duplicate values do not matter.

```python
unique_names = {"Mina", "Alex", "Ravi"}

for name in sorted(unique_names):
    print(name)
```

7. Set Comprehensions
- A set comprehension creates a set by applying an expression to each item in an iterable.
- Add an `if` clause to include only values that match a condition.
- Duplicate results are automatically removed because the result is a set.

```python
numbers = [1, 2, 2, 3, 4, 4, 5]
squares_of_evens = {number ** 2 for number in numbers if number % 2 == 0}
print(squares_of_evens)  # {16, 4}
```

8. Removing Duplicates from a List
- Converting a list to a set removes duplicate values, provided the values are hashable.
- Converting that set back to a list does not preserve the original list order. Use this when order is unimportant.
- If you need to preserve first-seen order while removing duplicates, use `dict.fromkeys()`.

```python
values = ["red", "blue", "red", "green", "blue"]
unique_values = list(set(values))  # Order is not guaranteed
unique_in_order = list(dict.fromkeys(values))

print(unique_in_order)  # ['red', 'blue', 'green']
```

9. Immutable Sets: `frozenset`
- `frozenset(iterable)` creates an immutable set. Its contents cannot be added or removed after creation.
- A `frozenset` supports set operations and can be used as an element of another set or as a dictionary key when its elements are hashable.
- Use a regular `set` when you need to change membership; use `frozenset` when the set itself must be immutable.

```python
roles = frozenset(["reader", "editor"])
role_lookup = {roles: "content team"}
print(role_lookup[roles])  # content team
```

10. Common Set Mistakes
- Expecting a set to keep insertion order or provide access by index. Use a list or sorted output when order matters.
- Using a list or dictionary as a set element. Set elements must be hashable.
- Writing `{}` for an empty set. Use `set()` instead.
- Calling `remove()` for a value that might not exist. Use `discard()` if absence is expected, or test membership first.
- Assuming `list(set(items))` preserves the original item order.
- Confusing a mutable set with `frozenset`, whose contents cannot be changed.

11. Key Takeaways
- Sets are mutable collections of unique, hashable elements with no guaranteed order.
- Use `set()` for an empty set and curly braces for a non-empty set.
- Use union, intersection, difference, and symmetric difference to combine or compare sets.
- Use `add()` and `update()` to add elements; `remove()` and `discard()` differ when an element is absent.
- Sets are a useful way to test membership and remove duplicates when order does not matter.
- Use `frozenset` when an immutable set is needed.

12. Sources
- Python documentation: Sets https://docs.python.org/3/tutorial/datastructures.html#sets
- LearnPython.com: An In-Depth Guide to Working with Python Sets https://learnpython.com/blog/python-sets/
- YouTube: Python Sets https://www.youtube.com/watch?v=t9j8lCUGZXo
