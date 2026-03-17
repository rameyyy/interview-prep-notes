---
tags:
  - dsa
  - overview
---
## Pythonic Python

Writing code that follows Python's conventions and idioms — clean, readable, and taking advantage of Python's built-in features rather than doing things the "long way" like you might in Java or C++.

### Initialization

#### List
```python
# non pythonic
arr = list()
arr = [0, 0, 0, 0, 0]        # hardcoded zeros
arr = []
for i in range(n):
    arr.append(i)

# pythonic
arr = []
arr = [0] * n
arr = [i for i in range(n)]  # list comprehension
```

#### Dict
```python
# non pythonic
d = {}
if 'a' not in d:
    d['a'] = 0
d['a'] += 1

# pythonic
d = {}
d = defaultdict(int)          # from collections, defaults to 0
d = defaultdict(list)         # defaults to []
d['a'] += 1                   # no KeyError
```

#### Set
```python
# non pythonic
s = set()
for x in arr:
    s.add(x)                  # manual dedup

# pythonic
s = set()
s = {1, 2, 3}
s = set(arr)                  # deduplicate a list instantly
```

#### Tuple
```python
# non pythonic
t = (1,)
t = tuple([1, 2, 3])          # unnecessary

# pythonic
t = (1, 2, 3)
```

#### Counter
```python
# non pythonic
count = {}
for x in arr:
    if x not in count:
        count[x] = 0
    count[x] += 1

# pythonic
from collections import Counter
count = Counter(arr)           # frequency map eg {'a': 2, 'b': 1}
```

#### Deque
```python
# non pythonic
q = []
q.append(1)
q.pop(0)                      # O(n) — shifts entire list

# pythonic
from collections import deque
q = deque()
q.append(1)
q.popleft()                   # O(1)
```

### Iteration
```python
# non pythonic
for i in range(len(arr)):
    print(arr[i])

# pythonic
for x in arr:
    print(x)

# pythonic with index
for i, x in enumerate(arr):
    print(i, x)
```