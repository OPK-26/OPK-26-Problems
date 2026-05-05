
### Задача: Реализовать структуру "Матрица" и соответствующие математические операции

В случае невозможности создания матрицы или выполнения некоторых арифметических действий (деление на 0 и т.д.) возвращать None
 
**Структура файла `matrix.py`:**

```python
class Matrix:
    """Matrix itself. Stores data as 1D list and keeps dimensions."""
    pass

def create_empty():
    """Create empty matrix."""
    ...

def create_vector(cols):
    """Create row vector (1 x cols) filled with zeros."""
    ...

def create(rows, cols):
    """Create matrix with given dimensions filled with zeros."""
    ...

def create_identity(rows, cols):
    """Create identity matrix (with min(rows,cols) ones on diagonal)."""
    ...

def create_constants(rows, cols, value):
    """Create matrix filled with constant value."""
    ...

def is_valid(mat):
    """Check if matrix has valid dimensions and data."""
    ...

def copy(mat):
    """Create deep copy of matrix."""
    ...

def destroy(mat):
    """Clear matrix data and mark as empty. Returns matrix"""
    ...

def multiply(mat1, mat2):
    """Returns new matrix (similarly in the methods below), the result of (mat1 * mat2)."""
    ...

def subtract(mat1, mat2):
    """Returns the result of (mat1 - mat2)."""
    ...

def add(mat1, mat2):
    """Returns the result of (mat1 + mat2)."""
    ...

def multiply_scalar(mat, value):
    """Multiply matrix by scalar."""
    ...

def divide_scalar(mat, value):
    """Divide matrix by scalar."""
    ...

def resize(mat, rows, cols):
    """Resize existing matrix, fill new elements with zeros (if new dimensions greater than current)."""
    ...

def get_element(mat, rowIdx, colIdx):
    """Get element at specified position."""
    ...

def set_element(mat, rowIdx, colIdx, value):
    """Set element at specified position."""
    ...

def set_identity(mat):
    """Transform matrix into identity (square only)."""
    ...

def set_zero(mat):
    """Fill matrix with zeros."""
    ...

def set_constants(mat, value):
    """Fill matrix with constant value."""
    ...

def transpose(mat):
    """Return transposed matrix."""
    ...

def inverse(mat):
    """Returns inverse matrix (square only)."""
    ...

def determinant(mat):
    """Returns determinant of square matrix."""
    ...
```
