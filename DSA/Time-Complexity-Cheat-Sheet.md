---
tags:
  - dsa
  - overview
---

## Python Built-in Operations

### List
| Operation | Complexity | Notes |
|-----------|------------|-------|
| `list.append(x)` | O(1) | amortized |
| `list.pop()` | O(1) | from end |
| `list.pop(i)` | O(n) | from middle, shifts |
| `list.insert(i, x)` | O(n) | shifts elements |
| `list.sort()` | O(n log n) | Timsort |
| `sorted(list)` | O(n log n) | returns new list |
| `list.reverse()` | O(n) | |
| `x in list` | O(n) | linear search |
| `min(list)` / `max(list)` | O(n) | |
| `len(list)` | O(1) | |

### Set
| Operation | Complexity | Notes |
|-----------|------------|-------|
| `set.add(x)` | O(1) | |
| `set.update([x, y])` | O(k) | k = number of elements added |
| `set.remove(x)` | O(1) | raises KeyError if missing |
| `set.discard(x)` | O(1) | no error if missing |
| `x in set` | O(1) | hash lookup |
| `set(list)` | O(n) | builds the set |
| `len(set)` | O(1) | |

### Dict
| Operation     | Complexity | Notes                      |
| ------------- | ---------- | -------------------------- |
| `dict[k] = v` | O(1)       |                            |
| `dict.get(k)` | O(1)       | returns None if missing    |
| `dict[k]`     | O(1)       | raises KeyError if missing |
| `del dict[k]` | O(1)       |                            |
| `k in dict`   | O(1)       | checks keys only           |
| `len(dict)`   | O(1)       |                            |

### Tuple
| Operation | Complexity | Notes         |
| --------- | ---------- | ------------- |
| `t[i]`    | O(1)       | index access  |
| `x in t`  | O(n)       | linear search |
| `len(t)`  | O(1)       |               |

## Heaps
| Operation | Complexity | Notes |
|-----------|------------|-------|
| `heapq.heappush(h, x)` | O(log n) | |
| `heapq.heappop(h)` | O(log n) | removes and returns min |
| `h[0]` | O(1) | peek at min, no removal |
| `heapq.heapify(list)` | O(n) | convert list to heap in place |
| `heapq.nlargest(k, list)` | O(n log k) | top k largest |
| `heapq.nsmallest(k, list)` | O(n log k) | top k smallest |
