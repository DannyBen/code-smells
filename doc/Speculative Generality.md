# Speculative Generality

Developers are humans, and humans are bad guessers [[1](#sources)]. Developers tend to create additional features in preparation for the future, guessing they will be useful, but that time never came. This problem lies within the human psychological nature and, contrary to their best intentions, it just clutters the code.

## Causation

Psychologically, humans tend to anticipate scenarios and prepare for them.

## Problems

### **You Ain't Gonna Need It Principle Violation**

The whole system is trying or expecting to do more than it is supposed to.

### **Increased Complexity**

Each additional method, class, or module increases the required time and effort to understand it as a whole.

## Examples



### Smelly

Context: _Medieval Fighting Game_

```py
class Animal:
    health: int

class Human(Animal):
    name: str
    attack: int
    defense: int

class Swordsman(Human):
    ...

class Archer(Human):
    ...

class Pikeman(Human):
    ...

```

### Solution

```py
class Human:
    name: str
    health: int
    attack: int
    defense: int

class Swordsman(Human):
    ...

class Archer(Human):
    ...

class Pikeman(Human):
    ...
```



## Refactoring

- Collapse Hierarchy
- Inline Function
- Inline Class
- Rename Method

---

#### Sources

- [[1](#sources)] - Leah T. Braun, _"Guessing right – whether and how medical students give incorrect reasons for their correct diagnoses"_ (2019)
- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
