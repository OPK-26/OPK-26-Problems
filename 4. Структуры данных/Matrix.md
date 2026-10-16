
### Задача: Реализовать структуру "Матрица" и соответствующие математические операции

В случае невозможности создания матрицы или выполнения некоторых арифметических действий (деление на 0 и т.д.) возвращать None
 
**Структура файла `matrix.py/matrix.c`:**

Python:
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
    """Transform matrix into identity (square part only)."""
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
    """Returns determinant of matrix (square only)."""
    ...
```

C:
```c
typedef struct {
...
} Matrix;

Matrix* create_empty();
Matrix* create_vector(size_t cols);
Matrix* create(size_t rows, size_t cols);
Matrix* create_identity(size_t rows, size_t cols);
Matrix* create_zero(size_t rows, size_t cols);
Matrix* create_constants(size_t rows, size_t cols, double value);
void destroy(Matrix* mat);

Matrix* multiply(Matrix* mat1, Matrix* mat2);
Matrix* subtract(Matrix* mat1, Matrix* mat2);
Matrix* add(Matrix* mat1, Matrix* mat2);
Matrix* multiply_scalar(Matrix* mat, double value);
Matrix* divide_scalar(Matrix* mat, double value);

bool is_valid(Matrix* mat);
void resize(Matrix* mat, size_t rows, size_t cols);

double get_element(Matrix* mat, size_t rowIdx, size_t colIdx);
void set_element(Matrix* mat, size_t rowIdx, size_t colIdx, double value);

void set_identity(Matrix* mat);
void set_zero(Matrix* mat);
void set_constants(Matrix* mat, double value);

void set_identity_resize(Matrix* mat, size_t rows, size_t cols);
void set_zero_resize(Matrix* mat, size_t rows, size_t cols);
void set_constants_resize(Matrix* mat, size_t rows, size_t cols, double value);

Matrix* transpose(Matrix* mat);
Matrix* inverse(Matrix* mat);
double determinant(Matrix* mat);
```

- `create_empty` - Создает пустую невалидную матрицу;
- `create_vector` - Создает вектор-строку заданного размера;
- `create` - Создает матрицу заданного размера;
- `create_identity` - Создает единичную матрицу заданного размера;
- `create_zero` - Создает нулевую матрицу заданного размера;
- `create_constants` - Создает матрицу с постоянными значениями заданного размера;
- `destroy` - Освобождает память, занятую матрицей;
- `multiply` - Выполняет умножение двух матриц;
- `subtract` - Выполняет вычитание двух матриц;
- `add` - Выполняет сложение двух матриц;
- `multiply_scalar` - Умножает матрицу на скалярное значение;
- `divide_scalar` - Делит матрицу на скалярное значение;
- `is_valid` - Проверяет валидность матрицы;
- `resize` - Изменяет размер матрицы;
- `get_element` - Возвращает значение элемента по индексам;
- `set_element` - Устанавливает значение элемента по индексам;
- `set_identity` - Преобразует существующую матрицу в единичную;
- `set_zero` - Заполняет матрицу нулевыми значениями;
- `set_constants` - Заполняет матрицу постоянным значением;
- `set_identity_resize` - Изменяет размер матрицы и делает её единичную;
- `set_zero_resize` - Изменяет размер матрицы и заполняет нулями;
- `set_constants_resize` - Изменяет размер матрицы и заполняет постоянным значением;
- `transpose` - Возвращает транспонированную матрицу;
- `inverse` - Возвращает обратную матрицу;
- `determinant` - Вычисляет определитель матрицы;
