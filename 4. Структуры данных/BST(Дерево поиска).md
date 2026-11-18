
# Реализация модуля для работы с бинарными деревьями поиска (Binary Search Tree)

Необходимо реализовать модуль для работы с **бинарными деревьями поиска** (binary search tree). Подразумеваются обычные деревья, без балансировки.

**Каждая** функция модуля должна быть протестирована с помощью assert.

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
```


## C‑интерфейс
Необходимо:
- самостоятельно определить содержимое `struct tTree`;
- `tree_create` создаёт пустое дерево с заданной функцией сравнения `cmp` (функция сравнения возвращает отрицательное число, если `a < b`, ноль, если `a == b`, и положительное число, если `a > b`);
- `tree_find` возвращает хранимый в дереве элемент с данными, равными `data` согласно `cmp`, либо `NULL`, если такого нет;
- `tree_insert` вставляет `data` в дерево. Если элемент с равными данными уже есть, он **заменяется** на новый, а старый возвращается. Иначе возвращается `NULL`;
- `tree_delete` удаляет элемент с данными, равными `data`, и возвращает его; если такого нет — возвращает `NULL`;
- `tree_foreach` вызывает `func` для каждого элемента дерева в **инфиксном** (симметричном) порядке, передавая также пользовательский аргумент `arg`;
- `tree_size` возвращает текущее количество элементов;
- `tree_destroy` уничтожает дерево, освобождая всю память, выделенную внутри (узлы дерева); сами объекты, на которые указывают элементы, не освобождаются.

```C
typedef void * Pointer;

typedef int (*CmpFunc)(Pointer data1, Pointer data2);

typedef struct tBSTNode {
    Pointer data;
    /* ... */
} BSTNode;

typedef struct tBST {
    BSTNode *root;
    CmpFunc cmp_func; /* all data comparisons should be done
                         with help of this func! */
    /* ... */
} BST;

// Create empty tree
BST * bst_create(CmpFunc cmp_func);

// Clear tree but do not destroy tree struct
void bst_clear(BST *tree);

// Completely destroy tree
void bst_destroy(BST *tree);

size_t bst_size(BST *tree);

// Find element with equal data and return its data if any else NULL
Pointer bst_find(BST *tree, Pointer data);

// Return data which was replaced by this insertion if any else NULL
Pointer bst_insert(BST *tree, Pointer data);

// Delete node with equal data and return its data if any else NULL
Pointer bst_delete(BST *tree, Pointer data);



// Call foreach_func for every node's data in tree passing given extra_data
void bst_foreach(BST *tree,
                 void (*foreach_func)(Pointer data, Pointer extra_data),
                 Pointer extra_data);
```
**Пример использования:**

```c
    Tree h, n, o;
    int v10 = 10, v4 = 4, vm10 = -10, v12 = 12, v15 = 15, v13 = 13;
    int v5 = 5, vm15 = -15;
    int v_none = 0;

    tree_create(&h, cmp_abs);
    assert(tree_insert(&h, &v10) == NULL);
    assert(tree_insert(&h, &v4)  == NULL);
    assert(tree_insert(&h, &vm10) == &v10); // -10 заменил 10
    assert(tree_insert(&h, &v12) == NULL);
    assert(tree_insert(&h, &v15) == NULL);
    assert(tree_insert(&h, &v13) == NULL);

    tree_create(&n, cmp_abs);
    assert(tree_insert(&n, &v_none) == NULL);

    tree_create(&o, cmp_abs);

    assert(tree_find(&h, &v5)  == NULL);
    assert(tree_find(&h, &v4)  == &v4);
    assert(tree_find(&h, &v10) == &vm10);
    assert(tree_find(&h, &vm15) == &v15);

    assert(tree_size(&h) == 5);
    assert(tree_size(&n) == 1);
    assert(tree_size(&o) == 0);

    assert(tree_delete(&h, &vm15) == &v15);
    assert(tree_delete(&h, &vm15) == NULL);
    assert(tree_size(&h) == 4);

    tree_destroy(&h);
    tree_destroy(&n);
    tree_destroy(&o);
```
