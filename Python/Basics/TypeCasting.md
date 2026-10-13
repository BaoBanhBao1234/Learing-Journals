1. What Is Type Conversion?
- Type conversion changes a value from one data type to another, such as converting a string containing digits into an integer.
- Python supports implicit conversion, performed automatically in some operations, and explicit conversion, requested by the programmer.
- Explicit conversion is often called type casting. Functions such as `int()`, `float()`, `str()`, and `bool()` perform common conversions.
- A conversion may change or discard information, so check the result and its type when precision matters.

2. Implicit Type Conversion
- Python may automatically promote compatible numeric values to a common type during an operation.
- For example, adding an `int` and a `float` produces a `float` result.
- Python does not generally guess how to combine unrelated types. An expression such as `"12" + 3` raises `TypeError`.
- The `/` operator performs true division and returns a `float`, including when both operands are integers. The `//` operator performs floor division; with integer operands its result is an `int`, while a floating-point operand produces a `float` result.

```python
integer_value = 10
float_value = 2.5

result = integer_value + float_value
print(result)        # 12.5
print(type(result))  # <class 'float'>

print(7 / 2)         # 3.5
print(7 // 2)        # 3
print(7.0 // 2)      # 3.0
```

3. Explicit Numeric Conversion
- `int(value)` converts a compatible value to an integer. When converting a float, it truncates the fractional part toward zero; it does not round to the nearest integer.
- `float(value)` converts a compatible number or numeric string to a floating-point value.
- `complex(real, imag=0)` creates a complex number from compatible numeric values.
- Invalid text or unsupported conversions raise an exception such as `ValueError` or `TypeError`.

```python
print(int(8.9))       # 8
print(int(-8.9))      # -8
print(float("3.14"))  # 3.14
print(complex(2, 3))  # (2+3j)
```

4. Converting Between Strings and Numbers
- Use `str(value)` to produce a string representation of a value.
- Use `int(text)` or `float(text)` to parse a string that contains a valid numeric representation.
- Converting a number to a string makes it suitable for display or string concatenation, but the result is text and no longer behaves like a number.
- `int("3.5")` raises `ValueError`; convert to `float` first if the text contains a decimal point.

```python
age = 20
message = "Age: " + str(age)

whole_number = int("42")
decimal_number = float("3.5")
from_decimal_text = int(float("3.5"))
```

5. Converting Values to Boolean
- `bool(value)` converts a value to `True` or `False` according to Python's truth-value rules.
- Common falsy values include `False`, `None`, numeric zero, and empty strings or collections. Most other values are truthy.
- Converting a value to `bool` answers whether it is truthy; it does not check whether the value is exactly the Boolean object `True`.

```python
print(bool(0))       # False
print(bool(5))       # True
print(bool(""))      # False
print(bool("False")) # True: a non-empty string is truthy
```

6. Converting Collections
- Built-in constructors can convert between iterable collection types, for example `list(iterable)`, `tuple(iterable)`, and `set(iterable)`.
- Converting to a set removes duplicate hashable values and does not preserve a guaranteed iteration order.
- `dict(iterable_of_pairs)` creates a dictionary from key-value pairs. Keys must be hashable, and repeated keys overwrite earlier values.

```python
values = [1, 2, 2, 3]
print(tuple(values))  # (1, 2, 2, 3)
print(set(values))   # {1, 2, 3} (display order may vary)

pairs = [("name", "Ada"), ("language", "Python")]
print(dict(pairs))
```

7. Common Conversion Errors and Data Loss
- `int(4.8)` truncates to `4`; it does not round. Use `round()` when rounding is intended, while remembering that rounding follows its own rules.
- `int("4.8")` is invalid because the string is not an integer literal. Convert it to `float` first if truncation is desired.
- `int("hello")` and `float("hello")` raise `ValueError` because the text is not numeric.
- `"12" + 3` raises `TypeError`; convert one operand explicitly when combining text and numbers.
- Floating-point values have finite precision, so a conversion to `float` may not represent every decimal value exactly.

```python
text = "12"
number = int(text)
print(number + 3)  # 15

price = float("19.99")
print(price)
```

8. Choosing a Conversion Function
- Use `int()` for whole-number values, but account for truncation when the input is a float.
- Use `float()` when fractional numeric values are needed.
- Use `str()` to create display text or combine a value with other text.
- Use `bool()` when truthiness is the intended meaning.
- Use `list()`, `tuple()`, `set()`, or `dict()` when a different collection structure is needed.
- Validate or handle input that may not be convertible; use `try`/`except` for expected `ValueError` or `TypeError` cases.

```python
raw_input = "24"

try:
    quantity = int(raw_input)
except ValueError:
    quantity = 0
```

9. Key Takeaways
- Implicit conversion happens automatically for compatible operations; explicit conversion uses functions such as `int()` and `float()`.
- Python promotes an `int` to `float` in mixed numeric arithmetic, while unrelated types such as `str` and `int` usually need explicit conversion.
- `int()` truncates a float toward zero; it does not round.
- `/` returns a floating-point result; `//` floors the quotient and its result type depends on the operands.
- Check conversions for invalid input, precision loss, and changes to the value's meaning.

10. Sources
- Programiz: Python Type Conversion https://www.programiz.com/python-programming/type-conversion-and-casting
- roadmap.sh: Python Division https://roadmap.sh/python/division
