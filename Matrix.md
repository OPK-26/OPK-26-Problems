
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
    """Clear matrix data and mark as empty."""
    ...

def multiply(mat1, mat2):
    """Multiply two matrices (mat1 * mat2)."""
    ...

def subtract(mat1, mat2):
    """Subtract mat2 from mat1."""
    ...

def add(mat1, mat2):
    """Add two matrices."""
    ...

def multiply_scalar(mat, value):
    """Multiply all matrix elements by scalar."""
    ...

def divide_scalar(mat, value):
    """Divide all matrix elements by scalar."""
    ...

def resize(mat, rows, cols):
    """Resize matrix, fill new elements with zeros."""
    ...

def get_element(mat, rowIdx, colIdx):
    """Get element at specified position."""
    ...

def set_element(mat, rowIdx, colIdx, value):
    """Set element at specified position."""
    ...

def set_identity(mat):
    """Transform matrix into identity (square part only)."""
    ...

def set_zero(mat):
    """Fill matrix with zeros."""
    ...

def set_constants(mat, value):
    """Fill matrix with constant value."""
    ...

def set_identity_resize(mat, rows, cols):
    """Resize and then set as identity."""
    ...

def set_zero_resize(mat, rows, cols):
    """Resize and then fill with zeros."""
    ...

def set_constants_resize(mat, rows, cols, value):
    """Resize and then fill with constant value."""
    ...

def transpose(mat):
    """Return transposed matrix."""
    ...

def inverse(mat):
    """Return inverse matrix (square only)."""
    ...

def determinant(mat):
    """Return determinant of square matrix."""
    ...
```
