1. What Is a Loop?
- A loop repeats a block of code, which is useful when processing collections or repeating work until a condition changes.
- Python has two main loop statements: `for` iterates over an iterable, while `while` repeats as long as a condition is truthy.
- The loop body must be indented. A loop header ends with a colon (`:`).

2. `for` Loops and Iterables
- A `for` loop takes items from an iterable one at a time and runs its body for each item.
- Common iterables include lists, tuples, strings, dictionaries, sets, files, and `range` objects.
- The loop variable receives the current item during each iteration.

```python
for color in ["red", "green", "blue"]:
    print(color)
```

3. How a `for` Loop Works Internally
- Python calls `iter(iterable)` to get an iterator.
- It repeatedly requests the next item from that iterator and assigns the item to the loop variable.
- When the iterator is exhausted, it raises `StopIteration`; the `for` loop handles this internally and ends normally.
- This iterator protocol lets `for` work with many kinds of objects without needing to know their internal structure.

4. Using `range()` and Common Iteration Helpers
- `range(stop)` produces numbers starting at `0` up to, but not including, `stop`.
- `range(start, stop, step)` lets you choose a starting value and step. The `stop` value is still excluded.
- Use `enumerate(iterable)` when you need both an item and its index.
- Use `zip(iterable_a, iterable_b)` to process items from multiple iterables in parallel. By default, iteration stops when the shortest iterable is exhausted.
- Iterating over a dictionary directly gives its keys. Use `.values()` for values and `.items()` for key-value pairs.
- Use `_` as the loop variable when the item is intentionally unused, such as `for _ in range(3):`.

```python
for index, fruit in enumerate(["apple", "pear"], start=1):
    print(index, fruit)

for name, score in {"Ada": 95, "Lin": 88}.items():
    print(name, score)
```

5. `while` Loops
- A `while` loop checks its condition before each iteration. If the condition is truthy, its body runs; otherwise, the loop ends.
- The body may run zero times if the condition is false at the start.
- Use `while` when repetition depends on a condition or when the number of iterations is not known in advance.
- Make sure the loop can reach a stopping condition, for example by updating a counter or accepting a sentinel input.

```python
remaining = 3

while remaining > 0:
    print(remaining)
    remaining -= 1
```

6. `break` and `continue`
- `break` exits the innermost loop immediately. Execution continues with the first statement after that loop.
- `continue` skips the rest of the current iteration and starts the next one.
- In nested loops, `break` exits only the innermost loop where it appears.

```python
for number in range(1, 6):
    if number == 3:
        continue
    if number == 5:
        break
    print(number)
```

7. The Loop `else` Clause
- A `for` or `while` loop can have an optional `else` block.
- The `else` block runs when the loop finishes normally, including when a `for` iterable is exhausted or a `while` condition becomes false.
- The `else` block does not run if the loop exits with `break`.
- Loop `else` is useful for search logic: use `break` when a match is found, and handle “not found” in `else`.

```python
numbers = [2, 4, 6]
target = 5

for number in numbers:
    if number == target:
        print("Found")
        break
else:
    print("Not found")
```

8. Nested Loops
- A nested loop is a loop inside another loop. The inner loop runs to completion for each iteration of the outer loop unless it exits early.
- Nested loops are useful for working with grids, tables, and pairs of values.
- A `break` inside the inner loop exits only that inner loop; it does not automatically stop the outer loop.

9. Avoiding Common Loop Problems
- **Infinite `while` loop**: the condition never becomes false. Check that the loop updates the state used by its condition or has a deliberate exit such as `break`.
- **Off-by-one errors**: remember that `range()` excludes its stop value.
- **Unexpected skipping while changing a collection**: modifying a list while iterating over it can lead to skipped items or confusing behavior. Iterate over a copy or build a new collection instead.
- **Manual index tracking**: prefer `enumerate()` when you need both an index and item.
- Prefer a `for` loop when processing each item in an iterable; use `while` when continuing depends on a condition.

10. Key Takeaways
- `for` loops iterate over items using Python’s iterator protocol; `while` loops repeat while a condition is truthy.
- `range()` is useful for numeric sequences, and `enumerate()` and `zip()` simplify common iteration patterns.
- `break` exits a loop; `continue` skips to its next iteration.
- A loop’s `else` block runs after normal completion and is skipped when `break` exits the loop.
- Always make the loop’s stopping behavior clear, especially with `while` loops.

11. Sources
- Real Python: Python `while` Loops: Repeating Tasks Conditionally https://realpython.com/python-while-loop/
- Real Python: Python `for` Loops: The Pythonic Way https://realpython.com/python-for-loop/#the-guts-of-the-python-for-loop
- YouTube: For loops in Python are easy https://www.youtube.com/watch?v=KWgYha0clzw (The video title was accessible, but the video itself could not be reviewed directly.)
