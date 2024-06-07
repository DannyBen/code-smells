# Binary Operator in Name

This is straightforward: method or function names that have binary bitwise operators like `AND` and `OR` are obvious candidates for undisguised violators of the **Single Responsibility Principle** right out there in the open. If the method name has _`and`_ in its name and then it does two different things, then one might ask why it is not split in half to do these two other things separately? Moreover, if the method name has _`or`_ then it not only does two different things but also, most likely, it has a stinky [Flag Argument](./flag-argument.md) which is yet another Code Smell.

This code smell might happen not only in the method names, even though it is the place to look for in the vast majority of this kind of smell, but also in the variables.

## Problems

### Single Responsibility Principle Violation

Names with conjunction words strongly suggest that something is not responsible for just one thing.

## Example



### Smelly

```py
def render_and_save():
    # render logic
    ...
    # save logic
    ...
```

### Solution

```py
def render():
    # render logic
    ...

def save():
    # save logic
    ...
```

## Refactoring

- _Extract Method_

---

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
