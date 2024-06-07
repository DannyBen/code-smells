# Dubious Abstraction

The smaller and more cohesive class interfaces are the better because they tend to degrade over time. They should provide a constant abstraction level. Function interfaces should be one level of abstraction below the operation defined in their name. Robert Martin describes the above sentences as three separate code smells: _Functions Should Descend Only One Level of Abstraction_, _Code at Wrong Level of Abstraction_, _Choose Names at the Appropriate Level of Abstraction_ [[1](#sources)]. He observed that people are having trouble with it and often mix abstraction levels. Steve Smith, in his course, uses the term "Inconsistent Abstraction Levels".

I like the smells in the granularized form presented by Martin as they address the issue directly and specifically. The name _Inconsistent Abstraction Levels_ still holds the idea, but it might be misinterpreted by just recalling the meaning through its title. I suspect that it might create a situation where somewhere out there, in at least one codebase, someone might win an argument with a non-inquisitive individual, thus leaving the abstraction levels consistent... but consistently off. I wish no one ever heard, "that is how it always has been, so it must continue to be done that way".

This frequent wrong selection of abstractions is why I decided to rename it to _Dubious Abstraction_ directly addressing the potential causation of the smell - to think about the code that one just wrote. Fowler says that "there is no way out of a misplaced abstraction, and it is one of the hardest things that software developers can do, and there is no quick fix when you get it wrong". _Dubious Abstraction_ is supposed to provoke the question as soon as possible - _"Is it dubious?"_, taking a second to think about the code at hand and then move on or immediately refactor if something seems fishy: Is the `Instrument` really querying this message? Or is it the _connection device_ doing it? Maybe I should extract it? Is `percentFull` a method of `Stack` for sure?

## Causation

It is difficult to grasp whether the abstraction or naming the developer gives to various entities is proper for psychological reasons, like Tunnel Vision. A correct solution requires stepping out of the box to think whether the abstraction is accurate, and that requires continuous and conscious mental action to be undertaken.

## Problems

### **Extendibility**

Code written "too literally" is closed on extendibility. Disregarding any abstractions on the implementation ideas makes it hard to introduce new features.

### **Comprehensibility**

Creating context without specifying ungeneralised concepts might be hard to follow. Varying abstraction levels make it challenging to develop a mental map of the code workflow.

### **Single Responsibility Principle Violation**

Methods with more than one layer of abstraction are most likely doing more than one thing.

## Example



### Smelly

```py
from abc import ABC  # Abstract Base Class

class Instrument(ABC):
    adapter: ConnectionAdapter

    def reset(self):
        self.write("*RST")

    def write(self, command):
        ...
```

### Solution

```py
from abc import ABC

class Instrument(ABC):
    adapter: ConnectionAdapter

    def reset(self):
        self.adapter.write("*RST")
```



### Refactoring

- Extract Superclass, Subclass, or new Class

---

#### Sources

- [[1](#sources)] - Robert Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
- [Parentage2] - Steve Smith, _"Refactoring Fundamentals"_ (2013)
- [Parentage1] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
