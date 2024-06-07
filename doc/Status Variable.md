# Status Variable

Status Variables are mutable primitives that are initialized before an operation to store some information based on the process and are later used as a switch for some action.

The _Status Variables_ can be identified as a distinct code smell, although they are just a signal for five other code smells:

- [Clever Code](./clever-code.md),
- [Imperative Loops](./imperative-loops.md),
- [Afraid To Fail](./afraid-to-fail.md),
- [Mutable Data](./mutable-data.md),
- [Special Case](./special-case.md).

They come in different types and forms, but common examples are the `success: bool = False`-s before performing an operation block or `i: int = 0` before a loop statement. The code that has them increases in complexity by a lot, and usually for no particular reason because there most likely exists a proper solution using first-class functions. Sometimes, they clutter the code, demanding other methods or classes to make [additional checks](./special-case.md) before execution resulting in [Required Setup/Teardown Code](./required-setup-or-teardown-code.md).

## Causation

The developer might have special cases that could be handled only inside a loop and could not figure out a better solution.

## Problems

### **Comprehensibility**

It is more difficult to understand the inner workings of a method than the declarative solution.

## Examples



### Smelly

```py
def find_foo_index(names: list[str]):
    found = False
    i = 0
    while not found:
        if names[i] == 'foo':
            found = True
        else:
            i += 1
    return i
```

### Solution

Solution, which removes the usage of Status Variables.

```py
def find_foo_index(names: list[str]):
    for index, value in enumerate(names):
        if value == 'foo':
            return index
```

### Solution

Solution, which removes the usage of Status Variables and [Clever Code](./clever-code.md).

```py
def find_foo_index(names: list[str]):
    return names.index('foo')
```



## Refactoring

- Replace with Built-In
- Extract Method
- Remove Status Variables

---

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
