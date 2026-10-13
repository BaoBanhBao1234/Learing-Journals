1. What Is a Python String?
- A string (`str`) is an immutable sequence of Unicode text.
- Create strings with matching single quotes, double quotes, or triple quotes: `'hello'`, `"hello"`, `'''hello'''`, or `"""hello"""`.
- Because strings are immutable, string operations return a new string instead of changing the original string.
- Use `len(text)` to get the number of characters in a string.

2. Indexing and Slicing
- String indexing starts at `0`; a negative index counts from the end, so `text[-1]` is the last character.
- A slice uses `text[start:stop:step]`. The `start` index is included and the `stop` index is excluded.
- Omitting `start` or `stop` uses the beginning or end of the string. A step of `-1` can reverse a string.

```python
text = "Python"
print(text[0])      # P
print(text[-1])     # n
print(text[1:4])    # yth
print(text[::-1])   # nohtyP
```

3. Combining and Checking Strings
- `+` concatenates strings, and `*` repeats a string: `"Py" + "thon"` and `"ha" * 3`.
- Use `in` or `not in` to check whether a substring is present: `"th" in "Python"`.
- Use `==` to compare string values. String comparisons are case-sensitive.
- Convert non-string values before concatenating them with strings, or use formatted strings: `"Age: " + str(age)` or `f"Age: {age}"`.

4. Common String Methods
- `lower()`, `upper()`, `title()`, and `capitalize()` return strings with adjusted letter case.
- `strip()`, `lstrip()`, and `rstrip()` remove whitespace from both ends, the left end, or the right end.
- `replace(old, new)` returns a string with matching text replaced.
- `find(substring)` returns the first matching index, or `-1` when there is no match. `index(substring)` raises `ValueError` if the substring is absent.
- `startswith(prefix)` and `endswith(suffix)` check a string’s beginning or end.
- `count(substring)` counts non-overlapping occurrences.
- `split(separator)` divides a string into a list. With no separator, it splits on runs of whitespace.
- `separator.join(iterable)` joins an iterable of strings using the separator.
- Methods do not modify the original string because strings are immutable.

```python
message = "  Hello, Python!  "
cleaned = message.strip().lower()
words = "red,green,blue".split(",")
joined = " | ".join(words)
```

5. New Lines, Escape Sequences, and Multiline Strings
- `\n` represents a line break, `\t` represents a tab, `\\` represents a backslash, and escaped quotes let a quote appear inside a string.
- Triple-quoted strings can contain actual line breaks and preserve the written line structure.
- Adjacent string literals can be placed next to each other, including across lines inside parentheses, and Python combines them.
- `print()` adds a newline after each call by default. Use its `end` argument to change or suppress that ending.
- `\r` is a carriage return. `\r\n` is used as a line ending in some text files; ordinary Python output commonly uses `\n`.
- Raw strings, written with an `r` prefix such as `r"C:\new\file.txt"`, treat backslashes literally in most cases. A raw string still cannot end with an odd number of backslashes.

```python
print("First line\nSecond line")

poem = """Roses are red,
Violets are blue."""
print(poem)

print("Loading...", end="")
print(" done")
```

6. Formatting Strings
- **f-strings** insert expressions into a string by placing them inside braces: `f"Hello, {name}!"`. They are usually the clearest option for combining text and values.
- **`str.format()`** uses replacement fields such as `"Hello, {}!".format(name)` or named fields such as `"Hello, {name}!".format(name=name)`.
- Format specifications after a colon control presentation, including decimal precision, alignment, and padding: `f"{price:.2f}"` displays two digits after the decimal point.
- Double braces `{{` and `}}` produce literal braces in f-strings and `str.format()` strings.
- Avoid building formatted output with repeated `+` operations when an f-string is clearer.

```python
name = "Ada"
price = 12.5
print(f"{name} paid ${price:.2f}")
print("{:<10}".format("left"))
```

7. The `string` Module
- Python’s built-in `str` type provides string values and methods. The separate standard-library `string` module provides useful constants and formatting tools.
- `string.ascii_letters` contains ASCII uppercase and lowercase letters; `string.digits` contains `0` through `9`.
- Other constants include `string.hexdigits`, `string.octdigits`, `string.punctuation`, `string.whitespace`, and `string.printable`.
- These constants are useful when building character sets or validating simple text formats. They describe ASCII characters and do not cover every Unicode letter or digit.

```python
import string

print(string.ascii_letters)
print(string.digits)
```

8. Common String Mistakes
- Strings cannot be changed in place. Assign the result of a method or operation if you need to keep the changed text: `text = text.strip()`.
- `strip(chars)` removes any of the specified characters from both ends; it does not remove one exact prefix or suffix. Use `removeprefix()` or `removesuffix()` for that purpose.
- `find()` and `index()` behave differently when there is no match: one returns `-1`, while the other raises an exception.
- `split()` returns a list of strings. Use `join()` with a string separator to combine string items.
- Remember that `print()` adds its own final newline by default; a newline inside the string may create additional line breaks.

9. Key Takeaways
- Strings are immutable Unicode sequences; indexing and slicing read parts of a string, while methods return new strings.
- Use methods such as `strip()`, `replace()`, `split()`, and `join()` to process text.
- Use `\n` or triple-quoted literals for multiline text, and `print(end=...)` to control the output ending.
- Prefer f-strings for readable interpolation and formatting.
- The `string` module is separate from the `str` type and includes ASCII-oriented constants.

10. Sources
- Python documentation: `string` — Common string operations https://docs.python.org/3/library/string.html
- roadmap.sh: Python Print New Line https://roadmap.sh/python/print-new-line
- roadmap.sh: Python Multiline Strings https://roadmap.sh/python/multiline-strings
- YouTube: String methods in Python are easy! — Bro Code https://www.youtube.com/watch?v=tb6EYiHtcXU 

