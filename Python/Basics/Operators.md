1. What Is an Operator?
- An operator performs an operation on one or more values or variables. The values it acts on are called operands.
- For example, in `total = price + tax`, `+` adds two values and `=` assigns the result to `total`.
- Python operators include arithmetic, comparison, logical, assignment, identity, membership, and bitwise operators.

2. Arithmetic Operators
- `+` adds numbers. It can also concatenate sequences such as strings and lists.
- `-` subtracts one number from another.
- `*` multiplies numbers. It can also repeat a sequence, such as `"ha" * 3`.
- `/` performs true division and returns a `float`, including when both operands are integers.
- `//` performs floor division: it rounds the quotient down toward negative infinity.
- `%` returns the remainder from division.
- `**` raises a number to a power.
- Division or modulo by zero raises `ZeroDivisionError`.

```python
print(7 / 2)     # 3.5
print(7 // 2)    # 3
print(-7 // 3)   # -3
print(7 % 3)     # 1
print(2 ** 3)    # 8
```

3. Division and Modulo Details
- Floor division is not the same as truncating toward zero. For example, `-7 // 3` is `-3` because `-7 / 3` is approximately `-2.33` and floor division rounds down.
- For integers, Python’s quotient and remainder satisfy `a == (a // b) * b + (a % b)` when `b` is not zero.
- The remainder has the same sign as the divisor, or is zero. Therefore, `-7 % 3` is `2`, while `7 % -3` is `-2`.
- Modulo is useful for checking divisibility and repeating patterns: `number % 2 == 0` checks whether an integer is even.

```python
print(-7 // 3)  # -3
print(-7 % 3)   # 2
print(7 % -3)   # -2
```

4. Exponentiation
- The `**` operator raises the left operand to the power of the right operand: `base ** exponent`.
- Exponentiation groups from right to left: `2 ** 3 ** 2` means `2 ** (3 ** 2)`, which is `512`.
- Exponentiation binds more tightly than a leading minus sign: `-3 ** 2` means `-(3 ** 2)`, or `-9`. Use `(-3) ** 2` to get `9`.
- The built-in `pow(base, exponent)` also performs exponentiation. `pow(base, exponent, modulus)` efficiently computes the result modulo a value.

5. Comparison Operators
- `==` tests whether two values are equal; `!=` tests whether they are different.
- `<`, `<=`, `>`, and `>=` compare values and return `True` or `False`.
- Comparisons can be chained, such as `0 <= score <= 100`.
- Use `==` to compare values. The `is` operator checks whether two references point to the same object; it is not a replacement for ordinary value comparison.

6. Logical Operators: `and`, `or`, and `not`
- `and` evaluates operands from left to right and stops when it finds a falsy value. Otherwise, it returns the last operand.
- `or` evaluates operands from left to right and stops when it finds a truthy value. If none is truthy, it returns the last operand.
- `and` and `or` return one of their operands, not necessarily a `bool`. Use comparisons or `bool(value)` when a Boolean result is needed.
- `not` returns the opposite truth value: `not True` is `False`, and `not 0` is `True`.
- Python considers values such as `0`, `""`, `None`, and empty collections falsy; most other values are truthy.
- Because `or` returns an operand, `value or default` uses `default` when `value` is any falsy value. Use an explicit `is None` check when only `None` should trigger the default.
- `not` has higher precedence than `and`, and `and` has higher precedence than `or`. Parentheses can make complex conditions easier to read.

```python
is_adult = age >= 18
has_ticket = True
can_enter = is_adult and has_ticket

name = supplied_name or "Guest"  # Uses "Guest" for any falsy supplied_name
is_missing = supplied_name is None
```

7. Assignment Operators
- `=` assigns a value to a name; it does not test equality.
- Augmented assignment operators combine an operation with assignment: `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, and `**=`.
- For example, `count += 1` is similar to `count = count + 1`.
- Augmented assignment may update a mutable object in place, depending on the object and operator.

8. Identity and Membership Operators
- `is` and `is not` test object identity: whether two expressions refer to the same object.
- Use `value is None` or `value is not None` to check for `None`.
- `in` and `not in` test membership in a sequence, set, or mapping. For dictionaries, membership checks keys.

```python
items = ["apple", "pear"]
print("pear" in items)  # True

user = None
print(user is None)     # True
```

9. Bitwise Operators
- Bitwise operators work on the binary representation of integers.
- `&` is bitwise AND, `|` is bitwise OR, `^` is bitwise XOR, `~` is bitwise NOT, `<<` shifts bits left, and `>>` shifts bits right.
- These operators are different from the logical keywords `and`, `or`, and `not`.
- Bitwise operators are useful in tasks such as masks and low-level data manipulation; most everyday Boolean conditions should use logical operators instead.

10. Operator Precedence
- Precedence determines which operations are evaluated first. Parentheses can override the default order.
- Exponentiation is evaluated before multiplication, division, and addition. Comparisons are evaluated before `not`, then `and`, then `or`.
- When an expression is difficult to read, add parentheses even when Python’s precedence rules would make them optional.

```python
result = (2 + 3) * 4
is_valid = (age >= 18) and has_ticket
```

11. Key Takeaways
- `/` performs true division; `//` floors the quotient; `%` returns a remainder whose sign follows the divisor.
- `**` performs exponentiation and groups from right to left.
- Comparisons return Boolean values, while `and` and `or` can return one of their operands.
- `==` compares values; `is` checks identity; `in` checks membership.
- Learn operator precedence, and use parentheses to make intent clear.

12. Sources
- W3Schools: Python Operators https://www.w3schools.com/python/python_operators.asp
- roadmap.sh: Python Division https://roadmap.sh/python/division
- roadmap.sh: Python Modulo Operator https://roadmap.sh/python/modulo
- roadmap.sh: Python `not` Operator https://roadmap.sh/python/not-operator
- roadmap.sh: The `or` Operator in Python https://roadmap.sh/python/or
- roadmap.sh: Python Exponent https://roadmap.sh/python/exponent
