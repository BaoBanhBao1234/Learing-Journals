1. What Is Matrix Multiplication?
- Matrix multiplication combines rows from the first matrix with columns from the second matrix. Each output value is the sum of the products of corresponding row and column elements.
- If matrix `A` has shape `(m, n)` and matrix `B` has shape `(n, p)`, their product has shape `(m, p)`.
- The number of columns in the first matrix must equal the number of rows in the second matrix. These are the inner dimensions.
- Matrix multiplication is generally not commutative: `A @ B` is usually different from `B @ A`, and one order may be invalid even when the other is valid.

2. The Python `@` Operator
- PEP 465 introduced `@` as Python's infix matrix multiplication operator in Python 3.5.
- Use `A @ B` when the objects support matrix multiplication. The syntax makes the operation clear and reads naturally in formulas.
- Python's built-in types, including lists, do not implement matrix multiplication. A library or custom type must define the behavior.
- PEP 465 added the operator syntax, not a built-in matrix type or a standard-library matrix implementation.
- The `@` operator has the same precedence and associativity as `*`.

```python
# With a library that supports matrix multiplication, such as NumPy:
result = A @ B
```

3. Matrix Multiplication with NumPy
- NumPy arrays implement `@` for matrix multiplication. Import NumPy and create arrays before using the operator.
- For two-dimensional arrays, NumPy checks that the inner dimensions match and returns an array with the outer dimensions.
- For matrices, `A @ B` is equivalent to `np.matmul(A, B)`.

```python
import numpy as np

A = np.array([[1, 2],
              [3, 4]])
B = np.array([[5, 6],
              [7, 8]])

result = A @ B
print(result)
# [[19 22]
#  [43 50]]
```

4. Matrix Multiplication vs. Element-Wise Multiplication
- In NumPy, `*` multiplies corresponding elements. It does not sum row-column products.
- `@` performs matrix multiplication, combining rows and columns according to the matrix product rule.
- Choosing the wrong operator can produce valid-looking but incorrect results, so check whether the operation should be element-wise or matrix multiplication.

```python
print(A * B)
# [[ 5 12]
#  [21 32]]

print(A @ B)
# [[19 22]
#  [43 50]]
```

5. Checking Matrix Shapes
- Use an array's `.shape` attribute to inspect its dimensions: `A.shape`.
- For shapes `(m, n)` and `(n, p)`, the product shape is `(m, p)`.
- If the inner dimensions differ, NumPy raises a `ValueError`.
- Matrix multiplication is not the same as multiplying matrices of equal shape element by element; the shape rule is based on columns of the left operand and rows of the right operand.

```python
A = np.ones((2, 3))
B = np.ones((3, 4))

print(A.shape)          # (2, 3)
print(B.shape)          # (3, 4)
print((A @ B).shape)    # (2, 4)
```

6. Vectors and Higher-Dimensional Arrays
- NumPy also accepts one-dimensional arrays with `@`. Two vectors of equal length produce a scalar dot product; a matrix and a compatible vector produce a vector.
- With arrays that have more than two dimensions, NumPy treats the final two axes as matrices and can broadcast the earlier axes as batches.
- Exact vector and higher-dimensional behavior depends on the type or library implementing `@`. Check that library's documentation when using non-NumPy objects.

```python
x = np.array([1, 2])
y = np.array([3, 4])

print(x @ y)  # 11
```

7. `@=` and Operator Methods
- `@=` is the augmented matrix multiplication assignment operator: `A @= B`.
- A type may implement `@` with `__matmul__()` and `__rmatmul__()`; `@=` may use `__imatmul__()`.
- Whether `@=` mutates an object in place depends on the type's implementation. Do not assume it always changes the existing object.

8. Common Mistakes
- Using `*` when you intend matrix multiplication: for NumPy arrays, `*` is element-wise and `@` is matrix multiplication.
- Mismatched inner dimensions: for example, `(2, 3) @ (2, 4)` is invalid because `3` does not equal `2`.
- Expecting Python lists to support `@`: convert them to a supported array type, or implement matrix multiplication yourself.
- Assuming `A @ B` equals `B @ A`: matrix multiplication is generally not commutative.
- Confusing matrix multiplication with matrix powers: `@` multiplies two operands; it is not a matrix exponentiation operator.

9. Key Takeaways
- `@` is Python's matrix multiplication operator, introduced by PEP 465 in Python 3.5.
- For two-dimensional matrices, `(m, n) @ (n, p)` produces a result with shape `(m, p)`.
- NumPy arrays support `@`; Python's built-in lists do not.
- In NumPy, use `*` for element-wise multiplication and `@` for matrix multiplication.
- Check operand shapes and the relevant library's documentation, especially for vectors and higher-dimensional arrays.

10. Sources
- Python Enhancement Proposals: PEP 465 — A dedicated infix operator for matrix multiplication https://peps.python.org/pep-0465/
- roadmap.sh: Matrix Multiplication in Python https://roadmap.sh/python-data-analysis/matrix-multiplication
