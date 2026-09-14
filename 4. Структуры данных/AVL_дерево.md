
### Задача: Реализовать структуру "AVL дерево"

**Структура файла `avl.py`:**

```python
class _Node:
    """Single node of a tree. Keeps references to left, right and some data."""
    pass


class Tree:
    """Tree itself. Keeps root node of a tree and a comparision function."""
    pass


def create(cmp_func):
    """Create empty tree."""


def clear(tree):
    """Clear tree but do not destroy tree itself."""


def size(tree):
    """Return number of elements."""


def find(tree, data):
    """Find element with equal data and return its data if any."""
    

def insert(tree, data):
    """Insert data into tree and return replaced data if any."""
   

def delete(tree, data):
    """Delete element with equal data and return its data if any."""


def foreach(tree, func):
    """Call func for every element's data in tree in infix-order."""


```

**Пример использования:**

```python
h = AVL.create(cmp)
AVL.insert(h, 10)
AVL.insert(h, 4)
AVL.insert(h, -10)
AVL.insert(h, 12)
AVL.insert(h, 15)
AVL.insert(h, 13)

n = AVL.create(cmp)
AVL.insert(n, None)

o = AVL.create(cmp)

assert AVL.find(h, 5) is None
assert AVL.find(h, 4) == 4
assert AVL.find(h, 10) == -10
assert AVL.find(h, -15) == 15

assert AVL.size(h) == 5
assert AVL.size(n) == 1
assert AVL.size(o) == 0
```

---
