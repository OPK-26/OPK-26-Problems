
### Задача: Реализовать структуру "AVL дерево"

**Структура файла `avl.py`/avl.h:**
См. задачу BST(Дерево поиска): 
https://github.com/OPK-26/OPK-26-Problems/blob/main/4.%20%D0%A1%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D1%8B%20%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85/BST(%D0%94%D0%B5%D1%80%D0%B5%D0%B2%D0%BE%20%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%B0).md

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
