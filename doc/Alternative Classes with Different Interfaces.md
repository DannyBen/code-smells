# Alternative Classes with Different Interfaces

If two classes have the same functionality but different implementations, developers should merge them, or developers should extract a superclass to limit [Code Duplication](Duplicated%20Code). This smell occurs whenever a class can operate on two alternative classes (for example, take `Zombie` and `Snowman`). However, the interface to these alternative classes is different - when it operates with `Zombie`, it calls `hug_zombie()`, and with `Snowman`, it has to call `hug_snowman()`.

## Causation

This may happen due to the oversight that a functionally equivalent class already exists or when two or more developers are working on code to handle a similar situation. However, they did not know about the other's work — lack of abstract methods that enforce the common implementation method names.

## Problems

### **Don't Repeat Yourself Violation**

_DRY Principle_ - as the name suggests - is aimed to reduce repetition of the same code implementations.

## Example



### Smelly

Each individual of Humanoid have similar but personalised logic but under different method names

```py
class Snowman(Humanoid):
    def hug_snowman():
        ...

class Zombie(Humanoid):
    def hug_zombie():
        ...
```

### Solution

Use common method.

```py
class Snowman(Humanoid):
    def hug():
        ...

class Zombie(Humanoid):
    def hug():
        ...
```



## Refactoring

- _Change Function Declaration_
- _Move Function_
- _Extract Superclass_

---

#### Sources

- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
