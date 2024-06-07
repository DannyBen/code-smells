# Parallel Inheritance Hierarchies

This occurs when an inheritance tree depends on another inheritance tree by
composition, and to create a subclass for a class, one finds that he has to
make a subclass for another class. Fowler specified that this is a special case
of [Shotgun Surgery](Shotgun%20Surgery.md) code smell.

## Causation

This smell can happen naturally when trying to model a problem in a domain. The
problem arises when these hierarchies are created artificially and
unnecessarily (for example, by adding a standard prefix throughout the
classes).

## Problems

### Duplication

Requires additional work to be done, which might be redundant.

## Examples



### Smelly

```py
class User(ABC):
    ...
    functions: Functions

class Functions(ABC):
    ...



class BasicUser(User):
    ...

class BasicFunctions(Functions):
    ...




class PremiumUser(User):
    ...

class PremiumFunctions(Functions):
    ...

# each time a new user is added, so is a new function subclass with the same prefix

```

### Solution

When solving, one must be cautious to not violate the
_Single Responsibility Principle_.

```py
class Animal(ABC):
    ...
    food: Food

class Food(ABC):
    ...



class Elephant(Animal):
    ...
    food: Vegan

class Vegan(Animal):
    ...




class Lion(Animal):
    ...
    food: Carnivore

class Carnivore(Food):
    ...

# domain-like mapping might eventually be reused
```



## Refactoring

- Move Method
- Move Field
- Create Partial
- Fold Hierarchy into One

---

#### Sources

- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
