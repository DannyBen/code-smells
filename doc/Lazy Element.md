# Lazy Element

A Lazy Element is an element that does not do enough. If a method, variable, or class does not do enough to pay for itself (for increased complexity of the project), it should be combined into another entity.

## Causation

This smell can happen due to the aggressive refactorization process in which the functionality of a class was truncated. It can also occur due to the unnecessary pre-planning - [Speculative Generality](./speculative-generality.md) - developer made it in anticipation of a future need that never eventuates.

## Problems

### **Increased Complexity**

Projects complexity increases with the number of entities.

## Example



### Smelly

```py
class Strength:
    value: int

class Person:
    health: int
    intelligence: int
    strength: Strength
```

### Solution

```py
class Person:
    health: int
    intelligence: int
    strength: int
```



## Refactoring

- Inline Class
- Inline Function
- Collapse Hierarchy

---

#### Sources

- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
