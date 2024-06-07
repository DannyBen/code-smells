# Inconsistent Names

Human brains work in a pattern-like fashion. Starting from the first class, the concept of operation and use of each subsequent class should be generalized throughout the project, facilitating and iteratively accelerating the speed of understanding how the code works.

For this reason, once we know that one class uses the method, `store()`, we should expect that another class for the very same mechanic also uses the `store()` name for that, instead of `add()`, `put()` or `place()`.

## Causation

In a team project, members could have omitted checking the existing naming in other classes [[1](#sources)]. They could also intentionally choose different naming methods to distinguish classes according to the naming convention of functions.

## Problems

### **Comprehensibility**

Standardized communication through names is vital for mental shortcuts.

### **Flow State Disruption**

The developer expects a method inside a sibling class but can't find it and has to look up synonymous variations of the method he wants.

## Example



### Smelly

```py
class Human:
    def talk():
        ...

class Elf:
    def chat():
        ...
```

### Solution

```py
class Character(ABC):
    @abstractmethod
    def talk():
        """ Converse """

class Human(Character):
    def talk():
        ...

class Elf(Character):
    def talk():
        ...
```



## Refactoring

- Rename Method

---

#### Sources

- [[1](#sources)], [Origin] - William C. Wake, _"Refactoring Workbook"_ (2004)
