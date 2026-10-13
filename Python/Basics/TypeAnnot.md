1. What Are Type Annotations?
- A type annotation is optional information that describes the expected type of a value, function parameter, or return value.
- Annotations can document an interface and help editors and static type checkers find inconsistent usage.
- Python remains dynamically typed. Type annotations do not automatically validate values, convert them, or prevent the program from running with a mismatched value.
- A type checker such as mypy or Pyright can analyze annotated code and report potential type errors before runtime.

2. Annotating Variables
- Use `name: type = value` to annotate a variable.
- A variable annotation without an initial value, such as `count: int`, records the intended type but does not assign a value.
- Python does not enforce that later assignments match the annotation; a static type checker can flag mismatches.

```python
name: str = "Ada"
score: int = 95
active: bool = True
count: int  # Annotated, but not assigned yet
```

3. Annotating Function Parameters and Return Values
- Add `: type` after a parameter name to annotate an argument.
- Add `-> type` after the parameter list to annotate the return value.
- Use `-> None` for a function that does not return a useful value.
- Annotate all parameters and the return value when the function is part of a public or shared interface.

```python
def greet(name: str) -> str:
    return f"Hello, {name}!"

def print_total(values: list[int]) -> None:
    print(sum(values))
```

4. Common Types and Collection Annotations
- Use built-in types such as `int`, `float`, `str`, `bool`, and `bytes` for simple values.
- Use parameterized collection types to describe their contents: `list[str]`, `set[int]`, or `dict[str, float]`.
- Use `tuple[int, str]` for a tuple with a fixed number and order of item types.
- Use `tuple[int, ...]` for a tuple containing any number of integers.
- For APIs that accept different collection implementations, prefer an appropriate abstract type such as `Sequence[str]` or `Iterable[str]` from `collections.abc` or `typing`.

```python
names: list[str] = ["Ada", "Lin"]
prices: dict[str, float] = {"tea": 2.5, "coffee": 3.0}
point: tuple[int, int] = (4, 7)
```

5. Union Types and `None`
- Use `A | B` to say that a value may have either type. This union syntax is available in Python 3.10 and later.
- Use `str | None` when a value may be a string or `None`. `Optional[str]` means the same thing and is useful in older syntax.
- A parameter with a default value can be omitted in a call; that is separate from whether its type allows `None`.
- If a value may be `None`, check for `None` before using it as the other type.

```python
def find_name(user_id: int) -> str | None:
    if user_id == 1:
        return "Ada"
    return None

name = find_name(1)
if name is not None:
    print(name.upper())
```

6. `Any` and `object`
- `Any` allows a value to be used without meaningful static type checking. It is useful at uncertain boundaries, but widespread use weakens type checking.
- `object` represents any Python object while still requiring the code to narrow the type before using type-specific operations.
- Use `isinstance()` to check and narrow a value at runtime when its type is uncertain.

```python
from typing import Any

untyped_value: Any = get_external_value()
unknown_value: object = get_external_value()

if isinstance(unknown_value, str):
    print(unknown_value.upper())
```

7. Type Annotations Do Not Perform Runtime Validation
- This annotation describes an expectation, but Python still allows a caller to pass another type unless the function's code or a runtime validation tool checks it.
- Annotations do not call constructors: `value: int = "5"` does not convert the string to an integer.
- Use explicit conversion such as `int(value)` to convert data, and explicit checks such as `isinstance(value, int)` when runtime validation is required.
- Frameworks and libraries may inspect annotations and apply their own behavior, but that behavior comes from those tools rather than the annotation syntax itself.

```python
def double(value: int) -> int:
    return value * 2

result = double("ha")  # Python permits the call; a type checker can report a mismatch.
```

8. Type Checkers and Gradual Typing
- A static type checker analyzes code without running the program and compares how values are used with their annotations.
- Annotation is optional and can be added gradually. A checker may treat unannotated values as `Any` or infer types from their use.
- Type checkers can find likely mistakes and improve editor completion, but they do not prove that a program is free of runtime errors.
- Run a type checker as part of development or CI if a project relies on static type checks; the Python interpreter does not run it automatically.

9. Forward References and Future Annotations
- A forward reference mentions a class or type before that name is available, such as referring to the class itself in a method's return type.
- A quoted annotation such as `"Node"` can defer resolving a type name.
- `from __future__ import annotations` can postpone evaluation of annotations, which is useful for forward references and some circular-import situations. Follow the rules for the Python versions and tools used by the project.

```python
from __future__ import annotations

class Node:
    def add_child(self, child: Node) -> Node:
        return child
```

10. Common Annotation Mistakes
- Assuming annotations enforce a type at runtime. Use a checker or explicit validation for that.
- Confusing an optional parameter with a nullable value: a default like `name="Guest"` makes an argument omittable; `name: str | None` allows `None` as a value.
- Using `Any` everywhere, which prevents useful type checking from catching mistakes.
- Annotating a tuple as `tuple[int, str]` when its elements can be in any order or the tuple can have a different length.
- Treating an annotation as a conversion, for example expecting `amount: int = "10"` to become `10`.

11. Key Takeaways
- Type annotations describe expected types and improve documentation, editor support, and static checking.
- Python does not enforce annotations or convert values based on them at runtime.
- Use `: type` for variables and parameters, and `-> type` for function return values.
- Use collection type parameters and unions such as `list[str]` and `str | None` to describe common data shapes.
- Distinguish `None`-accepting values from arguments that are optional to omit.
- Use a static type checker for early feedback and runtime checks when input must be validated during execution.

12. Sources
- Python Typing Documentation: Type Annotations https://typing.python.org/en/latest/spec/annotations.html
- LogRocket: Understanding Type Annotation in Python https://blog.logrocket.com/understanding-type-annotation-python/
