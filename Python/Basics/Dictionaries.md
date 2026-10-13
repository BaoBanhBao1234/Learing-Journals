1. What Is a Python Dictionary?
- A dictionary (`dict`) is a mutable mapping of unique keys to values, written as key-value pairs.
- Dictionaries are dynamic: you can add, update, and remove pairs after creating them.
- Dictionaries preserve insertion order in Python 3.7 and later. They are accessed by key rather than by numeric position.
- Values can be any Python objects, including lists and other dictionaries. Keys must be hashable and unique.

2. Creating Dictionaries
- Write key-value pairs inside curly braces, with a colon between each key and value.
- Use `{}` or `dict()` to create an empty dictionary. Curly braces containing pairs create a non-empty dictionary.
- `dict()` can create a dictionary from keyword arguments or an iterable of key-value pairs.
- If a literal repeats a key, the last value for that key is kept.

```python
person = {
    "name": "Ada",
    "age": 36,
    "skills": ["Python", "Math"],
}

empty = {}
settings = dict(host="localhost", port=8000)
from_pairs = dict([("red", "#f00"), ("blue", "#00f")])
```

3. Keys, Values, and Hashability
- A dictionary key must be hashable: its hash must remain stable while it is used as a key.
- Common key types include strings, numbers, and tuples whose elements are all hashable.
- Lists, sets, and dictionaries are mutable and cannot be dictionary keys.
- Dictionary keys are unique. Assigning a value to an existing key replaces that key's previous value.
- Values have no such hashability restriction and may be repeated or mutable.

```python
lookup = {
    "name": "Ada",
    42: "answer",
    (2, 5): "grid coordinate",
}

lookup["name"] = "Grace"  # Replaces the value for "name"
```

4. Accessing Values and Avoiding `KeyError`
- Use `dictionary[key]` to retrieve a value when the key is expected to exist.
- If the key is missing, `dictionary[key]` raises `KeyError`.
- Use `dictionary.get(key)` when a missing key is acceptable; it returns `None` by default. Pass a second argument to provide another default value.
- Use `key in dictionary` to check whether a key exists. Membership checks keys, not values.
- Prefer direct indexing when a missing key indicates a programming error; the exception can help reveal the problem.

```python
prices = {"coffee": 3.50}

print(prices["coffee"])                  # 3.5
print(prices.get("tea"))                 # None
print(prices.get("tea", 4.00))           # 4.0
print("coffee" in prices)                 # True
```

5. Adding, Updating, and Removing Entries
- Assign to `dictionary[key]` to add a new pair or replace the value for an existing key.
- `update(other)` adds pairs from another mapping or iterable of pairs; existing keys receive the new values.
- `setdefault(key, default)` returns the current value if the key exists; otherwise, it inserts the key with the default value and returns it.
- `del dictionary[key]` removes a pair and raises `KeyError` if the key is missing.
- `pop(key)` removes a key and returns its value. You can provide a default to avoid `KeyError` if the key is absent.
- `popitem()` removes and returns the most recently inserted pair as a `(key, value)` tuple. It raises `KeyError` when the dictionary is empty.
- `clear()` removes all pairs while keeping the dictionary object.

```python
inventory = {"apples": 5, "oranges": 3}
inventory["apples"] = 8
inventory["bananas"] = 4
inventory.update({"oranges": 6, "pears": 2})
removed = inventory.pop("pears")
del inventory["bananas"]
```

6. Iterating Through a Dictionary
- Iterating directly over a dictionary visits its keys in insertion order.
- Use `.keys()` for keys, `.values()` for values, or `.items()` for `(key, value)` pairs.
- These methods return dynamic view objects that reflect changes to the dictionary.
- Use `sorted(dictionary)` when keys need to be processed in sorted order and can be compared.

```python
scores = {"Ada": 95, "Lin": 88}

for name in scores:
    print(name)

for name, score in scores.items():
    print(name, score)
```

7. Dictionary Comprehensions
- A dictionary comprehension creates a new dictionary from an iterable using the form `{key_expression: value_expression for item in iterable}`.
- Add an `if` clause to include only items that match a condition.
- If a comprehension produces the same key more than once, the later value replaces the earlier one.

```python
numbers = [1, 2, 3, 4]
squares = {number: number ** 2 for number in numbers}
even_squares = {
    number: number ** 2
    for number in numbers
    if number % 2 == 0
}
```

8. Nested Dictionaries and Common Uses
- A dictionary value can itself be a dictionary or another collection. Use consecutive keys or indexes to access nested data.
- Dictionaries are useful for records, configuration, counting, caching, and looking up values by an identifier.
- Python dictionaries are hash table implementations, often called hash maps. A hash function helps locate a key efficiently.
- Hash collisions can occur when keys map to the same internal location; Python handles collisions and resizes its internal table as needed.
- Lookup, insertion, and deletion are typically fast on average, though their exact performance depends on the workload.

```python
users = {
    "user_1": {"name": "Mina", "active": True},
    "user_2": {"name": "Ravi", "active": False},
}

print(users["user_1"]["name"])  # Mina
```

9. Common `KeyError` Cases and Fixes
- A `KeyError` usually means code tried to read or remove a key that the dictionary does not contain.
- Check spelling, capitalization, whitespace, and whether the data actually includes the key.
- Use `.get()` for a simple fallback, `in` when missing keys need separate logic, or `try`/`except KeyError` when an exception-based fallback is appropriate.
- Catch `KeyError` explicitly instead of using a bare `except`, so unrelated errors remain visible.

```python
user = {"name": "Mina"}

if "email" in user:
    email = user["email"]
else:
    email = "Not provided"

try:
    city = user["city"]
except KeyError:
    city = "Unknown"
```

10. Key Takeaways
- A dictionary maps unique, hashable keys to values and preserves insertion order in Python 3.7 and later.
- Use square brackets for required keys and `.get()` for optional keys or default values.
- Assignment adds or updates entries; `del`, `pop()`, and `clear()` remove them in different ways.
- Use `.items()` to iterate over key-value pairs and dictionary comprehensions to build mappings.
- Python dictionaries are hash maps; `KeyError` signals a missing key in direct lookup or certain removal methods.

11. Sources
- Python documentation: Dictionaries https://docs.python.org/3/tutorial/datastructures.html#dictionaries
- Real Python: Dictionaries in Python https://realpython.com/python-dicts/
- roadmap.sh: Hashmaps in Python https://roadmap.sh/python/hashmap
- roadmap.sh: Python `KeyError` Exceptions https://roadmap.sh/python/keyerror
