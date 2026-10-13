1. What Is a Python List?
- A list is an ordered, mutable collection that stores multiple items in one variable.
- Create a list with comma-separated items inside square brackets: `colors = ["blue", "green", "red"]`.
- Lists can contain values of different types, though a list often stores items of the same kind.
- An empty list is written as `[]`. Use `len(items)` to get the number of items.

2. Creating and Accessing Lists
- List indexes start at `0`, so the first item is at index `0` and the last item is at index `len(items) - 1`.
- Negative indexes count from the end: `items[-1]` is the last item.
- Accessing an index outside the valid range raises `IndexError`.
- A list can be nested inside another list. Use multiple indexes to access nested items.

```python
fruits = ["apple", "pear", "cherry"]

print(fruits[0])    # apple
print(fruits[-1])   # cherry
print(len(fruits))  # 3

matrix = [[1, 2], [3, 4]]
print(matrix[1][0])  # 3
```

3. Slicing and Combining Lists
- A slice uses `items[start:stop:step]`. The start index is included, and the stop index is excluded.
- Omitting `start` or `stop` selects from the beginning or through the end. Negative indexes and steps can also be used.
- Slicing returns a new list containing the selected items; it does not change the original list.
- The `+` operator concatenates lists and returns a new list. The `*` operator repeats a list's contents.

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])   # [20, 30, 40]
print(numbers[:3])    # [10, 20, 30]
print(numbers[::-1])  # [50, 40, 30, 20, 10]
print(numbers + [60]) # [10, 20, 30, 40, 50, 60]
```

4. Lists Are Mutable
- A list is mutable, which means its contents can be changed after it is created.
- Assign to an index to replace an item, or assign to a slice to replace, insert, or remove a range of items.
- Most list methods that change a list operate in place and return `None`; do not assign their return value back to the list.

```python
colors = ["blue", "green", "red"]
colors[1] = "yellow"
colors[1:2] = ["orange", "purple"]
print(colors)  # ['blue', 'orange', 'purple', 'red']
```

5. Adding Items
- `append(item)` adds one item to the end of a list. If `item` is itself a list, it is added as one nested item.
- `extend(iterable)` adds each item from an iterable to the end of the list.
- `insert(index, item)` inserts an item before the given index.
- These methods modify the original list and return `None`.

```python
numbers = [1, 2]
numbers.append([3, 4])
print(numbers)  # [1, 2, [3, 4]]

numbers = [1, 2]
numbers.extend([3, 4])
numbers.insert(1, 10)
print(numbers)  # [1, 10, 2, 3, 4]
```

6. Removing Items
- `remove(value)` removes the first item equal to `value`. It raises `ValueError` if the value is not present.
- `pop(index)` removes and returns the item at `index`. If no index is supplied, it removes and returns the last item. An invalid index raises `IndexError`.
- `del items[index]` removes an item by index. `del items[start:stop]` removes a slice; the stop index is excluded.
- `clear()` removes all items but keeps the list object. `del items` deletes the name binding, rather than just emptying the list.
- To remove every occurrence of a value or filter items by a condition, a list comprehension is usually clear and creates a new list.

```python
pets = ["cat", "dog", "cat", "bird"]
pets.remove("cat")               # Removes only the first "cat"
last_pet = pets.pop()             # Removes and returns "bird"
del pets[0]                       # Removes the item at index 0

pets = ["cat", "dog", "cat", "bird"]
without_cats = [pet for pet in pets if pet != "cat"]
print(without_cats)                # ['dog', 'bird']
```

7. Iterating Over a List
- A `for` loop visits each item in order.
- Use `enumerate(items)` when you need both the index and the item.
- Avoid removing items from a list while iterating over that same list, because changing its positions can cause items to be skipped. Build a filtered list or iterate over a copy instead.

```python
for fruit in ["apple", "pear", "cherry"]:
    print(fruit)

for index, fruit in enumerate(["apple", "pear"], start=1):
    print(index, fruit)
```

8. List Comprehensions
- A list comprehension creates a new list by evaluating an expression for each item in an iterable.
- Add an `if` condition to include only items that match a rule.
- Use a regular loop when the transformation has multiple steps or a comprehension would be difficult to read.

```python
numbers = [1, 2, 3, 4, 5]
squares = [number ** 2 for number in numbers]
even_squares = [number ** 2 for number in numbers if number % 2 == 0]

print(squares)       # [1, 4, 9, 16, 25]
print(even_squares)  # [4, 16]
```

9. Assignment and Copying
- Assigning a list to another variable does not copy it. Both names refer to the same list, so a mutation through either name is visible through both.
- A slice such as `items[:]` or the `items.copy()` method creates a shallow copy. The outer list is new, but nested mutable objects are still shared.
- Use `copy.deepcopy()` when an independent copy of nested mutable objects is needed.

```python
original = ["red", "green"]
alias = original
alias.append("blue")
print(original)  # ['red', 'green', 'blue']

copy_of_list = original.copy()
copy_of_list.append("yellow")
print(original)       # ['red', 'green', 'blue']
print(copy_of_list)   # ['red', 'green', 'blue', 'yellow']
```

10. Common List Mistakes
- Remember that indexes start at `0`; an index equal to the list length is out of range.
- `remove()` takes a value, while `pop()` takes an index and returns the removed item.
- `remove()`, `append()`, `extend()`, `insert()`, `sort()`, and `clear()` mutate the list and generally return `None`.
- `append([a, b])` adds one nested list; `extend([a, b])` adds `a` and `b` as separate items.
- A list comprehension creates a new list, so the original remains unchanged unless you assign the result back.
- Do not assume assignment copies a list; use `.copy()` or slicing for a shallow copy.

11. Key Takeaways
- Lists are ordered, mutable collections written with square brackets.
- Indexing accesses one item; slicing creates a new list of selected items.
- Use `append()` to add one item, `extend()` to add multiple items, and `insert()` to add before an index.
- Use `remove()` for the first matching value, `pop()` for an indexed item, `del` for indexes or slices, and `clear()` to empty a list.
- List comprehensions are useful for making transformed or filtered lists.
- Assignment creates an alias, not a copy.

12. Sources
- Python documentation: An Informal Introduction to Python — Lists https://docs.python.org/3/tutorial/introduction.html#lists
- The New Stack: Python for Beginners: Lists https://thenewstack.io/python-for-beginners-lists/
- roadmap.sh: Python Remove from List https://roadmap.sh/python/remove-item-from-list
- YouTube: Python list tutorial https://www.youtube.com/watch?v=n0krwG38SHI
