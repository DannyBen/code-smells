# Mutable Data

Mutable data are harmful because they can unexpectedly fail other parts of the
code. It is a rich source of bugs that are hard to spot because they can occur
under rare conditions. Fowler says that this is a significant factor which
contributed to the rise of the new programming school, functional programming,
in which one of the principles is that the data should never change. While
these languages are still relatively small, he states that developers should
not ignore the advantages of immutable data [[1](#sources)]. It is hard to
reason about these variables, especially when they have several reassignments.

## Causation

In Object-Oriented Programming, the immutability of objects was not addressed
audibly, if at all, in the context of something desirable. This is a relatively
new concept.

## Problems

### Error-Prone

Mutable Data is a rich source of hidden bugs that might be spotted only when
specific rare conditions are met.

### Hard to Understand

Data that might change at any moment is hard to reason about without excluding
every corner case.

## Examples



### Smelly

```py
@dataclass
class Foo:
    name: str
    value: float
    premium: bool

# foo object instance will be passed around and modified
```

### Solution

```py
@dataclass(frozen=True)
class Foo:
    name: str
    value: float
    premium: bool

# foo object instance will be passed around and, if that is necessary,
# recreated, thus making the state change explicit for everyone and handled
```



## Refactoring

- Remove Setting Method
- Choose Proper Access Control
- Separate Query from Modifier
- Change Reference to Value
- Replace Derived Variable with Query
- Extract Method
- Encapsulate Variable
- Combine Methods into Class

---

#### Sources

- [[1](#sources)], [Origin] - Martin Fowler, "Refactoring: Improving the Design of Existing Code (3rd Edition)" (2018)
