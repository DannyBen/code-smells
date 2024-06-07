# Indecent Exposure

Unnecessarily exposing internal details is an _Indecent Exposure_ code smell. The methods and variables of a class that works only with other same class methods should be kept private.

Otherwise, it might lead to [Insider Trading](./insider-trading.md) or [Feature Envy](./feature-envy.md) code smells. One should always strive to hide as many variables and methods from other classes as possible. Exposing irrelevant code contributes to the complexity of a design.

## Causation

The developer could have a habit of creating all the methods public at first but then forgets to change the access levels to appropriate ones.

## Problems

### **Error-Prone**

Fields accessible from outside the class baits for unnecessary coupling issues.

### **Information Overload**

There is no need to expose all information to everyone.

## Example



### Smelly

Variable `count` is accessible by its name and can be freely changed.

```py
@dataclass
class Counter:
    count: int = field(init=False)

    def bump(self) -> None:
        self.count += 1

counter = Counter()
counter.bump()
print(f"Count: {counter.count}")
```

### Solution

Variable `count` is accessible only via exposed methods and is pseudo-protected from external direct changes.

```py
@dataclass
class Counter:
    __count: int = field(init=False)

    @property
    def count() -> int:
        return self.__count

    def bump(self) -> None:
        self.__count += 1

    def reset(self) -> None:
        self.__count = 0

counter = Counter()
counter.bump()
print(f"Count: {counter.count}")
```



## Refactoring

- Choose Proper Access Control
- Encapsulate Field
- Encapsulate Collection
- Hide Behind Method
- Hide Behind Abstract Class or Interface

---

#### Sources

- [Origin] - Joshua Kerievsky, _"Refactoring to Patterns"_ (2005)
