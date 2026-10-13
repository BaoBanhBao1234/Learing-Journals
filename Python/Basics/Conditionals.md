1. What Are Conditional Statements?
- Conditional statements control program flow by choosing which block of code to execute based on a condition.
- Python evaluates a condition in a Boolean context. A condition may be a comparison, a logical expression, or another truthy/falsy value.
- The main conditional tools are `if`, `elif`, `else`, the conditional expression, and structural pattern matching with `match`/`case`.

2. `if`, `elif`, and `else`
- `if` runs its indented block when its condition is true.
- Add one or more `elif` clauses to check alternatives in order. Python runs the block for the first true condition and skips the rest.
- `else` is optional and runs when none of the preceding conditions was true. It must come last.
- Each condition header ends with a colon (`:`), and indentation defines the block.

```python
score = 82

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
else:
    grade = "C or below"
```

3. Truthy and Falsy Conditions
- Conditions do not have to be the literal values `True` or `False`; Python checks whether their values are truthy or falsy.
- Common falsy values include `False`, `None`, numeric zero, and empty strings or collections such as `""`, `[]`, `{}`, and `set()`.
- Most other values are truthy. Use `if items:` to check whether a collection is non-empty, or `if not items:` to check whether it is empty.
- If a value may be `None` and other falsy values are meaningful, test it explicitly with `value is None`.

4. Combining Conditions with `and`, `or`, and `not`
- `and` requires both conditions to be truthy. It evaluates from left to right and stops at the first falsy operand.
- `or` requires at least one condition to be truthy. It evaluates from left to right and stops at the first truthy operand.
- `and` and `or` return one of their operands, not necessarily `True` or `False`. In an `if` condition, Python uses the result’s truthiness.
- `not` reverses truthiness and returns a Boolean value.
- Use parentheses to make complex conditions easier to read. `not` is evaluated before `and`, which is evaluated before `or`.

```python
if age >= 18 and has_ticket:
    print("Entry allowed")

if is_weekend or is_holiday:
    print("No work today")

if not is_active:
    print("Account is inactive")
```

5. Conditional Expressions
- A conditional expression selects one of two values and can be used inside an assignment or another expression.
- Its form is `value_if_true if condition else value_if_false`.
- Use it for short, simple choices. A regular `if`/`else` statement is clearer for multiple steps or nested decisions.

```python
status = "adult" if age >= 18 else "minor"
```

6. `match` and `case` (Python 3.10+)
- Python’s `match` statement performs structural pattern matching. It can be useful when one value or structure needs to be checked against several patterns.
- Python checks `case` patterns from top to bottom and runs the block for the first matching pattern.
- Use literal patterns to match exact values and `case _` as a wildcard that matches anything without binding it to a name.
- A bare name such as `case other` captures the matched value in a new variable; it is not an exact comparison. Use `_` when you only need a catch-all case.
- The `|` pattern combines alternatives, and a guard such as `case number if number > 0` adds a condition after a pattern matches.
- Put specific patterns before broader patterns so a general pattern does not hide a more specific one.
- `match` and `case` are soft keywords: they have special meaning in a match statement but can be used as names elsewhere.

```python
status_code = 404

match status_code:
    case 200:
        message = "Success"
    case 404:
        message = "Not found"
    case _:
        message = "Unknown status"
```

7. Choosing a Conditional Tool
- Use `if`/`elif`/`else` for ranges, Boolean conditions, and most everyday decision-making.
- Use `match`/`case` when matching several literal values or checking the structure of data, such as tuples or mappings.
- For a simple fixed lookup from values to results, a dictionary may be shorter and easier to maintain.
- Keep branches readable and avoid deeply nested conditions when early returns or simpler conditions can express the same logic.

8. Common Mistakes
- Forgetting the colon after `if`, `elif`, `else`, `match`, or `case` headers causes a syntax error.
- Incorrect indentation changes which statements belong to a branch or causes an `IndentationError`.
- Conditions in an `if`/`elif` chain are checked in order. A broad earlier condition can prevent a later, more specific branch from running.
- `=` assigns a value; use `==` to compare values.
- Do not use `if value` when you mean to check only for `None`; empty strings, zero, and empty collections are also falsy.
- In `match`/`case`, a bare name captures a value. Use a literal, qualified constant, or wildcard `_` according to the intended pattern.

9. Key Takeaways
- `if` selects a block based on a condition; `elif` checks additional alternatives, and `else` handles the remaining case.
- Python uses truthiness, so conditions can be values other than Booleans.
- `and`, `or`, and `not` combine or reverse conditions; `and` and `or` short-circuit.
- Conditional expressions are useful for short two-way choices.
- `match`/`case` is available from Python 3.10 and supports structural patterns, guards, alternatives, and a wildcard case.

10. Sources
- Real Python: Conditional Statements in Python https://realpython.com/python-conditional-statements/
- roadmap.sh: Python Switch Statement 101 https://roadmap.sh/python/switch
- LearnPython.com: How to Use a match case Statement in Python 3.10 https://learnpython.com/blog/python-match-case-statement/
- roadmap.sh: Python `not` Operator https://roadmap.sh/python/not-operator
- roadmap.sh: The `or` Operator in Python https://roadmap.sh/python/or
