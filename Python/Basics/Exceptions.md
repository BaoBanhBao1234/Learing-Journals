1. Errors and Exceptions
- An error is a problem that prevents code from behaving as intended. Python reports many errors using exceptions.
- A `SyntaxError` means Python cannot parse the code, so the affected code cannot start executing.
- An exception happens while syntactically valid code is running. Examples include dividing by zero or using a missing dictionary key.
- An unhandled exception stops the current program flow and displays a traceback.

2. Reading a Traceback
- A traceback shows the call path that led to an exception, including file names, line numbers, and function calls.
- Start with the last line: it names the exception type and usually gives a short explanation.
- Read upward to find the line in your code that triggered the exception. The deepest call can be in a function called by your code.
- A caret or highlighted expression is a clue to the problem, but the actual cause may be earlier on that line or in a preceding line.

3. Common Python Exceptions
- `SyntaxError` and `IndentationError` indicate code that Python cannot parse or consistently indent.
- `NameError` means a name has not been defined in the current scope.
- `TypeError` means an operation or function received a value of an incompatible type, or the wrong kind or number of arguments.
- `ValueError` means an operation received a value of the right general type but an invalid value, such as `int("hello")`.
- `ZeroDivisionError` means a numeric division or modulo operation used zero as its divisor.
- `IndexError` means a sequence index is outside the valid range.
- `KeyError` means a mapping such as a dictionary does not contain the requested key.
- `FileNotFoundError` is a kind of `OSError` raised when a requested file cannot be found.

4. `SyntaxError` and Invalid Syntax
- Python parses code before executing it. A syntax problem prevents the affected code from running.
- Common causes include a missing colon after `if`, `for`, `while`, `def`, or `try`; unclosed quotes or brackets; missing commas; and using `=` instead of `==` in a comparison.
- `IndentationError` is a subclass of `SyntaxError` and points to inconsistent or unexpected indentation.
- The line and caret in the message identify where Python noticed a problem, which may be after the actual mistake. Check the indicated line and nearby lines.

```python
# Missing colon: invalid syntax
# if score >= 60
#     print("Passed")

# Correct form
if score >= 60:
    print("Passed")
```

5. Handling Exceptions with `try` and `except`
- Put code that may fail inside a `try` block.
- An `except` block runs when an exception of the specified type, or a subtype of it, occurs in the `try` block.
- Use specific exception types so the handler responds only to failures you expect.
- You can use multiple `except` blocks to handle different exception types separately.
- Use `as error` to bind the exception object when you need its details.

```python
try:
    age = int(input("Enter your age: "))
except ValueError:
    print("Please enter a whole number.")
else:
    print(f"Age: {age}")
```

6. `else` and `finally`
- The optional `else` block runs only when the `try` block completes without an exception. Put success-only code there.
- The optional `finally` block runs whether an exception occurred or not. It is commonly used for cleanup.
- For files and other objects that support context management, prefer `with` when it handles cleanup automatically.
- Avoid returning from a `finally` block because it can hide an exception or override a value returned from `try`.

```python
try:
    result = 10 / divisor
except ZeroDivisionError:
    print("The divisor must not be zero.")
else:
    print(result)
finally:
    print("Division attempt finished.")
```

7. Understanding and Handling `KeyError`
- A `KeyError` occurs when code looks up a key that is missing from a dictionary or another mapping.
- Check the key's spelling, capitalization, whitespace, and whether the data actually contains it.
- Use `dictionary.get(key, default)` when a missing key is expected and a fallback value is appropriate.
- Use `key in dictionary` when missing and present keys need different logic.
- Use `try`/`except KeyError` when exception-based handling is appropriate. Do not silently hide a missing key that indicates a bug.

```python
prices = {"coffee": 3.50}

price = prices.get("tea", 0.0)

if "coffee" in prices:
    print(prices["coffee"])

try:
    tea_price = prices["tea"]
except KeyError:
    tea_price = 0.0
```

8. Raising Exceptions
- Use `raise ExceptionType("message")` to report that an operation cannot continue under the current conditions.
- Raise a specific built-in exception when it accurately describes the problem, such as `ValueError` for an invalid argument value.
- Use `raise` inside an `except` block to re-raise the current exception after logging or adding context.
- Use `raise NewError(...) from error` to explain that one exception was caused by another.

```python
def set_percentage(value):
    if not 0 <= value <= 100:
        raise ValueError("percentage must be between 0 and 100")
    return value
```

9. User-Defined Exceptions
- Define a custom exception by creating a class that inherits from `Exception` or one of its subclasses.
- Use a custom exception when callers need to distinguish a specific application-level failure from other errors.
- Keep custom exceptions focused and descriptive; many programs can use the built-in exception types directly.

```python
class InvalidConfigurationError(Exception):
    pass

raise InvalidConfigurationError("Missing database URL")
```

10. Exception Handling Best Practices
- Handle exceptions where your program can take a useful action, such as asking for corrected input or selecting a fallback.
- Catch the narrowest exception type that makes sense. Avoid bare `except:` and broad handlers that hide unrelated bugs.
- Do not use exceptions as a replacement for straightforward checks when a normal condition is expected and easy to test.
- Preserve useful context when reporting errors; do not silently ignore failures.
- Use `with` for resources such as files when the context manager handles cleanup.

11. Key Takeaways
- `SyntaxError` means Python could not parse the code; an exception occurs while valid code runs.
- Read the final traceback line for the exception type and message, then follow the file and line references to your code.
- Use `try`/`except` for specific expected failures, `else` for success-only work, and `finally` for cleanup.
- Use `KeyError` handling that matches the situation: `.get()`, membership checks, or a specific `except KeyError` block.
- Raise clear, specific exceptions when invalid input or state prevents an operation from continuing.

12. Sources
- Python documentation: Errors and Exceptions https://docs.python.org/3/tutorial/errors.html#exceptions
- roadmap.sh: Python `KeyError` Exceptions https://roadmap.sh/python/keyerror
- roadmap.sh: Fixing `SyntaxError: invalid syntax` in Python https://roadmap.sh/python/invalid-syntax
- YouTube: Learn Python Exception Handling in 5 minutes! https://www.youtube.com/watch?v=V_NXT2-QIlE
