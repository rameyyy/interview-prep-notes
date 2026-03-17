---
tags:
  - dsa
  - overview
---
## Data Structures
1. **List** - an ordered, mutable sequence of elements that allows duplicates and supports indexing
	1. Initialize a list: `arr = list()` or `arr = []`
2. **Tuple** - an ordered, immutable sequence of elements that allows duplicates and supports indexing
	1. Immutable meaning you can not add, remove, or modify elements
	2. ie: `t = (1,2), t[0] = 3 # TypeError - can not modify`
3. **Set** - an unordered collection of unique elements with O(1) lookup, insertion, and deletion
	1. valid set: `set([1,1,3,(1,2),(1,2)]) -> {1,3,(1,2)}`
	2. invalid set: `set([1,1,[1,2],[1,2]])` won't work, all elements must be *hashable*
4. **Dict** - an unordered collection of key-value pairs with O(1) lookup, insertion, and deletion by key. Keys must be unique and hashable.
5. **Heap** - A complete binary tree that satisfies the heap property. In a **min heap** the parent is always smaller than its children so the minimum element is always at the root. In a **max heap** the parent is always larger. Python's `heapq` is a min heap by default.
	1. ```python
	   import heapq
	   h = [] # empty heap
	   heapq.heapify([3, 1, 2]) # [1, 3, 2] — heapified in place
	   ```
	2.  Python only has min heap — negate values to simulate max heap:
		   ```python
		   import heapq
		   h = []
		   heapq.heappush(h, -5)    # push as negative
		   val = heapq.heappop(h) * -1  # negate on pop to get original
		   ```