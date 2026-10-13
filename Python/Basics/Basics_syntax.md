1. What Is Python Syntax?
- Syntax is the set of rules that defines how Python code must be written and structured.
- Python parses code before executing it. If the code cannot be parsed, Python raises a `SyntaxError` and does not execute the affected code.
- A syntax error is different from a runtime error: syntax errors prevent valid parsing, while runtime errors happen as valid code runs.
- Python can be used interactively in the interpreter or by running a `.py` script file.

2. Statements and Code Blocks
- A simple statement usually ends at a newline. Write one statement per line for readability.
- Compound statements such as `if`, `for`, `while`, `def`, and `class` end their header with a colon (`:`).
- Indentation defines the body of a code block. Use consistent indentation; the Python style guide recommends four spaces per level.
- Python does not use braces to mark code blocks.

```python
if score >= 60:
    print("Passed")
else:
    print("Try again")
```

3. Identifiers, Variables, and Keywords
- An identifier is a name used for a variable, function, class, or other object.
- Identifiers may contain letters, digits, and underscores, but cannot start with a digit. For example, `user_name` and `score2` are valid; `2score` is not.
- Python identifiers are case-sensitive: `total`, `Total`, and `TOTAL` are different names.
- Reserved keywords such as `if`, `for`, `class`, `True`, and `None` cannot be used as ordinary variable names.
- Common naming styles include `snake_case` for variables and functions and `PascalCase` for classes.

4. Strings, Quotes, and Escape Sequences
- Strings can use matching single or double quotes: `'Hello'` or `"Hello"`.
- Triple quotes (`'''...'''` or `"""..."""`) allow strings to span multiple lines. They are also commonly used for docstrings.
- A backslash introduces escape sequences inside regular strings. For example, `\n` represents a newline and `\t` represents a tab.
- Use matching opening and closing quotes. For a quote inside a string, choose the other quote style or escape the quote.

5. Comments and Blank Lines
- A `#` starts a single-line comment outside a string. Python ignores the comment through the end of that line.
- Use comments to explain intent or important decisions, not to repeat what the code already says.
- Blank lines can separate related sections and improve readability; they do not create code blocks.
- Triple-quoted strings are string values, not Python’s syntax for comments. Use `#` for comments and docstrings for documentation.

6. New Lines and the `print()` Function
- `print()` writes its values and adds a newline at the end by default.

```python
print("Hello")
print("World")
```

- Use `\n` inside a string to insert a line break within one printed value: `print("Hello\nWorld")`.
- The `end` parameter changes what `print()` writes after its output. For example, `print("Hello", end=" ")` keeps the next output on the same line with a space.
- The `sep` parameter changes the text placed between multiple values passed to `print()`. For example, `print("red", "blue", sep="\n")` prints each value on its own line.
- `\r` is a carriage return, not a newline by itself. `\r\n` is a line-ending sequence used in some text files; for ordinary Python output, `\n` is usually sufficient.

7. Multiple-Line Statements
- Use parentheses, brackets, or braces to continue an expression across lines without a backslash. This is usually the clearest approach.

```python
total = (
    first_value
    + second_value
    + third_value
)
```

- A backslash (`\`) can explicitly continue a statement, but it is easy to break accidentally and is usually less readable than using parentheses.
- Python allows semicolons between simple statements, but placing each statement on its own line is clearer and more common.

8. Common Syntax Errors
- **Missing colon**: add `:` after a compound statement header, such as `if condition:`.
- **Mismatched or unclosed delimiters**: check matching pairs of `()`, `[]`, and `{}`.
- **Unclosed or mismatched quotes**: check that every string starts and ends with the intended quote.
- **Using `=` instead of `==` in a comparison**: `=` assigns a value; `==` compares values.
- **Missing commas**: separate items in lists, tuples, dictionaries, and function arguments with commas.
- **Invalid identifier**: names cannot start with a digit or use reserved keywords.
- **Incorrect indentation**: indent the body of a block consistently and avoid unexpected indentation.
- **Python 2 syntax in Python 3**: use `print("Hello")`, not the Python 2 form `print "Hello"`.

9. Reading and Fixing a `SyntaxError`
- Read the exception name and message, such as `SyntaxError: expected ':'` or `IndentationError: expected an indented block`.
- Use the file name and line number as a starting point. The actual mistake may be on an earlier line, especially when a quote or delimiter was left unclosed.
- Check the indicated line and nearby lines for colons, matching delimiters, quotes, commas, operators, and indentation.
- Newer Python versions may provide a caret or a suggested fix. Treat these as clues and verify the code’s intent.
- Fix one issue at a time, then run the program again.

10. Key Takeaways
- Python relies on newlines and indentation to organize code.
- Compound statement headers end with a colon, and their bodies must be indented consistently.
- Names are case-sensitive, cannot begin with a digit, and cannot be reserved keywords.
- `print()` adds a newline by default; `\n`, `end`, and `sep` let you control line breaks in output.
- When Python reports invalid syntax, inspect the flagged line and the lines immediately before it.

11. Sources
- TutorialsPoint: Python - Syntax https://www.tutorialspoint.com/python/python_basic_syntax.htm
- roadmap.sh: Fix "Invalid Syntax" in Python https://roadmap.sh/python/invalid-syntax
- roadmap.sh: Python Print New Line https://roadmap.sh/python/print-new-line
- YouTube: Python for Beginners - Learn Coding with Python in 1 Hour https://www.youtube.com/watch?v=kqtD5dpn9C8 

