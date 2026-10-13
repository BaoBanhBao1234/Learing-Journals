1. What Is a Function?
- A function is a reusable block of code that performs a task. Functions help organize programs into smaller, easier-to-understand parts.
- Python provides built-in functions that are available without an import, and lets you define your own functions with `def`.
- A function runs when it is called by its name followed by parentheses. Arguments can be passed inside the parentheses.

2. Defining and Calling a Function
- Start a function definition with `def`, followed by a valid name, parentheses, and a colon.
- Indent the function body. The body runs when the function is called, not when Python first reads the definition.
- Use descriptive names in `snake_case` and choose one clear task for each function.

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Ada")
```

3. Parameters and Arguments
- A parameter is a name listed in a function definition; an argument is the value supplied when the function is called.
- Positional arguments are matched by order. Keyword arguments identify a parameter by name.
- Default parameter values make arguments optional. Parameters with defaults must follow parameters without defaults.
- `*args` collects extra positional arguments into a tuple, and `**kwargs` collects extra keyword arguments into a dictionary.
- Avoid mutable default values such as `[]` or `{}`: Python evaluates defaults once when it defines the function. Use `None` and create a new collection inside the function when needed.

```python
def describe(name, role="student"):
    return f"{name} is a {role}."

print(describe("Ada"))
print(describe(name="Lin", role="teacher"))

def collect_items(*items, **options):
    return items, options
```

4. Returning Values
- `return expression` sends a value back to the caller and immediately ends that function call.
- A function that reaches its end without a `return` statement returns `None`.
- A function can return any Python object, including a collection or another function.
- A bare `return` also returns `None`.

```python
def square(number):
    return number ** 2

def show_message():
    print("Done")

result = square(4)  # 16
no_result = show_message()  # Prints "Done" and evaluates to None
```

5. Returning Multiple Values
- A function returns one object. When a `return` statement lists several comma-separated values, Python packs them into a tuple.
- The caller can keep that tuple or unpack it into separate variables.
- Unpacking usually requires the number of target variables to match the number of returned values.

```python
def divide(number, divisor):
    return number // divisor, number % divisor

result = divide(17, 5)
quotient, remainder = divide(17, 5)
print(result)                 # (3, 2)
print(quotient, remainder)    # 3 2
```

6. Docstrings and Function Scope
- A docstring is a string placed first in a function body to explain what the function does. It can be read through `help(function)` or `function.__doc__`.
- Variables assigned inside a function are local to that function by default.
- Pass values through parameters and return results instead of relying on unrelated global variables.

```python
def area(width, height):
    """Return the area of a rectangle."""
    return width * height

print(area.__doc__)
```

7. Common Built-in Functions
- Built-in functions are available directly; you do not need to import them.
- Numeric helpers include `abs()`, `round()`, `min()`, `max()`, and `sum()`.
- Collection and iteration helpers include `len()`, `range()`, `enumerate()`, `zip()`, `sorted()`, and `reversed()`.
- `any(iterable)` returns `True` if at least one item is truthy; `all(iterable)` returns `True` if every item is truthy. `all()` also returns `True` for an empty iterable, while `any()` returns `False`.
- `type(value)` reports an object's type. Use `isinstance(value, SomeType)` for most type checks, especially when subclasses should count.
- `print()` displays values; `input()` reads text from the user. Convert input explicitly when a number is expected.

```python
numbers = [3, 8, -2]

print(len(numbers))          # 3
print(abs(-2))                # 2
print(min(numbers), max(numbers))  # -2 8
print(sum(numbers))           # 9
print(any(number < 0 for number in numbers))  # True
print(all(number > 0 for number in numbers))  # False
```

8. `map()` and `filter()`
- `map(function, iterable)` applies a function to each item and returns a lazy iterator of results.
- `filter(function, iterable)` returns a lazy iterator containing items for which the function returns a truthy value.
- A lazy iterator produces values as it is consumed. Use `list(...)` to materialize all results when a list is needed.
- Both functions accept named functions, built-ins, or short `lambda` expressions. List comprehensions are often easier to read for simple transformations and filtering.

```python
numbers = [1, 2, 3, 4, 5]

squares = map(lambda number: number ** 2, numbers)
evens = filter(lambda number: number % 2 == 0, numbers)

print(list(squares))  # [1, 4, 9, 16, 25]
print(list(evens))    # [2, 4]

# Equivalent comprehension forms:
print([number ** 2 for number in numbers])
print([number for number in numbers if number % 2 == 0])
```

9. `reduce()` from `functools`
- `reduce(function, iterable, initializer)` repeatedly combines items to produce one accumulated result.
- Import it with `from functools import reduce`; unlike `map()` and `filter()`, `reduce()` is not a built-in function.
- The combining function receives the accumulated result and the current item. Its return value becomes the accumulator for the next step.
- An optional initializer supplies the starting accumulator and makes reduction of an empty iterable possible.
- Prefer a clear built-in such as `sum()`, `min()`, or `max()` when it expresses the operation more directly. Use `reduce()` when a custom cumulative operation is genuinely clearer.

```python
from functools import reduce

numbers = [1, 2, 3, 4]
product = reduce(lambda accumulated, number: accumulated * number, numbers, 1)
print(product)  # 24
```

10. Common Function Mistakes
- Defining a function does not call it; use `function_name(...)` to run it.
- Forgetting to return a value means the function returns `None`, even if it prints something.
- Passing the wrong number of required arguments raises `TypeError`.
- Passing `function()` instead of `function` to `map()`, `filter()`, or `reduce()` calls the function immediately instead of passing it as a callable.
- `filter()` and `map()` return iterators; after an iterator is consumed, it does not restart. Create a new iterator if the values are needed again.
- Avoid naming variables after built-ins, such as `list`, `sum`, or `filter`, because doing so hides the built-in name in that scope.

11. Key Takeaways
- Define reusable code with `def`, pass inputs through parameters, and send results back with `return`.
- Multiple comma-separated values in `return` are returned together as a tuple.
- Python's built-in functions are ready to use without imports; check the official reference for the full list.
- `map()` transforms items and `filter()` selects items; both return lazy iterators.
- `reduce()` comes from `functools` and folds an iterable into one result. Prefer a direct built-in when it makes the intent clearer.

12. Sources
- Python documentation: Built-in Functions https://docs.python.org/3/library/functions.html
- Real Python: Defining Your Own Python Function https://realpython.com/defining-your-own-python-function/
- roadmap.sh: Returning Multiple Values in Python https://roadmap.sh/python/return-multiple-values
- roadmap.sh: Python `filter()` https://roadmap.sh/python/filter
- roadmap.sh: Python `reduce()` https://roadmap.sh/python/reduce
