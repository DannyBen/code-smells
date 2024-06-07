# Temporary Field

Temporary Field is a variable created where it is not needed. It refers to
variables only used in some situations [[1](#sources)] or specific areas of a
program. This uniqueness can be confusing when the purpose of using the
variable cannot be explained or cannot be found outside of its scope
[[2](#sources)]. It might be misplaced at the class level when the functionality
it provides is specific only to a particular method [[2](#sources)]. One should
expect an object to need all of its fields.

## Problems

### Hard to Understand

Additional fields clutter the code and strain the cognitive load by keeping in
mind useless attributes.

## Examples



Consider the following example, when `full_date` is used only for an object to
string conversion.

### Smelly

```py
@dataclass
class MyDateTime:
    def __init__(self, year, month, day):
        self.year = year
        self.month = month
        self.day = day
        self.full_date = f"{year}, {month}, {day}"

    def foo(self):
        ...

    def goo(self):
        ...

    def hoo(self):
        ...

    def __str__(self):
        return self.full_date
```

### Solution

```py
@dataclass
class MyDateTime:
    def __init__(self, year, month, day):
        self.year = year
        self.month = month
        self.day = day

    def foo(self):
        ...

    def goo(self):
        ...

    def hoo(self):
        ...

    def __str__(self):
        return f"{self.year}, {self.month}, {self.day}"
```



## Refactoring

- Introduce Null Object
- Extract Class
- Move Function

---

#### Sources

- [[1](#sources)] - Mika Mäntylä, _"Bad Smells in Software - a Taxonomy and an Empirical Study"_ (2003)
- [[2](#sources)] - MS Haque, J Carver, T Atkison, _"Causes, impacts, and detection approaches of code smell: A survey"_ (2018)
- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code (3rd Edition)"_ (1999)
