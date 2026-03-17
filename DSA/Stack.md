## Stack

A linear data structure that follows **LIFO** (Last In First Out) — the last element pushed is the first one popped. In Python there is no built-in stack class, just use a list since append and pop from the end are both O(1).

### Built-in Operations
| Operation | Complexity | Notes |
|-----------|------------|-------|
| `stack.append(x)` | O(1) | push |
| `stack.pop()` | O(1) | pop from top |
| `stack[-1]` | O(1) | peek at top, no removal |
| `len(stack) == 0` | O(1) | check if empty |
| `x in stack` | O(n) | not what stacks are for |

### Initialization
```python
stack = []
stack.append(1)  # push
stack.pop()      # pop
stack[-1]        # peek
```

### When to Use
- Matching/balancing brackets
- Undo operations
- DFS iteratively
- Monotonic stack problems (next greater element etc)

### Example — Valid Parentheses
```python
def isValid(s: str) -> bool:
    stack = []
    closeToOpen = { ")": "(", "]": "[", "}": "{" }
    for c in s:
        if c in closeToOpen:
            if stack and stack[-1] == closeToOpen[c]:
                stack.pop()
            else:
                return False
        else:
            stack.append(c)
    return True if not stack else False
```