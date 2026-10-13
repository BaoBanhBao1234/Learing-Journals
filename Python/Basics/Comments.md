1. What Is a Comment?
- A comment is text in source code that Python ignores when executing the program.
- Comments can clarify a decision, explain a non-obvious step, or temporarily disable a line while debugging.
- A useful comment adds context that is not already clear from the code. Keep comments accurate when the code changes.

2. Single-Line Comments
- Start a comment with `#`. Python ignores everything from that character to the end of the line, unless it appears inside a string literal.
- A full-line comment can begin on its own line. An inline comment can follow a statement, with at least two spaces before `#` as a common style convention.
- Use a short phrase or sentence that explains the reason or intent, rather than restating what the code visibly does.

```python
# Keep the latest record for each user ID.
records_by_id = {record["id"]: record for record in records}

limit = 10  # Cap the result size for the dashboard.
```

3. Writing a Comment Across Multiple Lines
- Python has no separate block-comment syntax. Start each comment line with `#`.
- For longer explanations, use several concise lines and keep them near the code they describe.
- A triple-quoted string is a string literal, not a block comment. Do not use an unassigned multiline string as a substitute for comments.

```python
# Retry only temporary network failures.
# Invalid credentials should be reported immediately.
for attempt in range(max_attempts):
    ...
```

4. What Is a Docstring?
- A docstring is a string literal placed as the first statement in a module, function, class, or method.
- Python stores that string in the object's `__doc__` attribute. Tools such as `help()` can display it.
- A string elsewhere in the code is not automatically a docstring.
- Use docstrings to describe a public object's purpose and interface; use `#` comments for nearby implementation details.

```python
def calculate_total(prices):
    """Return the sum of the supplied prices."""
    return sum(prices)

print(calculate_total.__doc__)
help(calculate_total)
```

5. PEP 257 Docstring Conventions
- Use triple double quotes (`"""..."""`) for docstrings, including one-line docstrings.
- A one-line docstring should be a concise summary, written as a command or instruction such as “Return the total.”
- A multi-line docstring starts with a short summary line, followed by a blank line and a more detailed description.
- Keep the summary line brief and do not repeat the function signature; explain behavior that a reader cannot get from the signature alone.

```python
def find_user(user_id):
    """Find a user by ID.

    Return the matching user, or None if no user exists.
    """
    ...
```

6. What to Include in a Docstring
- A function or method docstring should describe behavior and, when relevant, its arguments, return value, side effects, exceptions, and usage restrictions.
- A class docstring should summarize the class and describe its public methods and attributes.
- A module docstring should explain the module's purpose and may list its public classes, exceptions, and functions.
- Document optional arguments and whether keyword arguments are part of the function's interface when that matters.

```python
def parse_count(text):
    """Convert text to a non-negative item count.

    Args:
        text: Text containing an integer.

    Returns:
        The parsed item count.

    Raises:
        ValueError: If text is not a non-negative integer.
    """
    ...
```

7. Comments vs. Docstrings
- A `#` comment is ignored by Python and is intended for readers of the source code.
- A docstring is a string value attached to a module, class, function, or method, so documentation tools and `help()` can access it.
- Triple quotes alone do not make a docstring; placement as the first statement in the relevant definition is what matters.
- Use comments to explain local reasoning; use docstrings to document an object's purpose and interface.

8. Common Commenting Mistakes
- Writing comments that merely repeat the code makes a file longer without explaining intent.
- Leaving a comment out of date can mislead readers; update or remove it when behavior changes.
- Using an unassigned triple-quoted string as a “multiline comment” creates a string literal, not a comment.
- Writing an explanation above a function does not make it the function's docstring; put the docstring inside the function as its first statement.
- Avoid large blocks of commented-out code. Remove unused code or keep temporary debugging changes short-lived.

9. Key Takeaways
- Use `#` for source-code comments; Python ignores the text through the end of that line.
- For multiple comment lines, prefix each line with `#`.
- A docstring is the first string-literal statement in a module, function, class, or method and is available through `__doc__`.
- Follow PEP 257: use triple double quotes, a concise summary, and a blank line before the details in a multi-line docstring.
- Write comments and docstrings to explain intent and behavior that is not obvious from the code.

10. Sources
- Python Enhancement Proposals: PEP 257 — Docstring Conventions https://peps.python.org/pep-0257/
- W3Schools: Python Comments https://www.w3schools.com/python/python_comments.asp
