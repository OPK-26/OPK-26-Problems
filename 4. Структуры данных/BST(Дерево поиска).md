
# Реализация модуля для работы с бинарными деревьями поиска (Binary Search Tree)

Необходимо реализовать модуль для работы с **бинарными деревьями поиска** (binary search tree). Подразумеваются обычные деревья, без балансировки.

Каждая функция модуля должна быть протестирована с помощью assert.

Необходимо предусмотреть нагрузочное тестирование: добавление большого числа случайных элементов в дерево, затем извлечение всех элементов, которые были добавлены.

## Python‑интерфейс

```python
class _Node:
    """Single node of a tree. Keeps references to left, right and some data."""
    pass

class Tree:
    """Tree itself. Keeps root node of a tree and a comparison function."""
    pass

def create(cmp_func):
    """Create empty tree."""
    ...

def clear(tree):
    """Clear tree but do not destroy tree itself."""
    ...

def size(tree):
    """Return number of elements."""
    ...

def find(tree, data):
    """Find element with equal data and return its data if any."""
    ...

def insert(tree, data):
    """Insert data into tree and return replaced data if any."""
    ...

def delete(tree, data):
    """Delete element with equal data and return its data if any."""
    ...

def foreach(tree, func):
    """Call func for every element's data in tree in infix-order."""
    ...
