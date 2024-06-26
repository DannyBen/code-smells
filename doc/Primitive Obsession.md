# Primitive Obsession

Whenever a variable that is just a simple `string`, or an `int` simulates being
a more abstract concept, which could be an object, we encounter a _Primitive
Obsession_ code smell. This lack of abstraction quickly becomes a problem
whenever there is the need for any additional logic, and also because these
variables easily spread wide and far in the codebase. This alleged verbal
abstraction is just a "supposed" object, but it should have a real object
instead.

## Causation

Possibly a missing class to represent the concept in the first place. Mäntylä
gives an example of representing money as primitive rather than creating a
separate class [[1](#sources)], and so does Fowler, who states that many
programmers are reluctant to create their own fundamental types.
[[2](#sources)]. Higher-level abstraction knowledge is needed to clarify or
simplify the code. [[3](#sources)]

## Problems

### Hidden Intention

The type does not correspond to a variable's value (i.e., phone number as a
string).

### Lack of Encapsulation

These primitives often go in groups, and there’s a lack of written relations
between them, and nothing protects them from external manipulation.

## Example



### Smelly

```py
birthday_date: str = "1998-03-04"
name_day_date: str = "2021-03-20"
```

### Solution

```py
@dataclass(frozen=True)
class Date:
    year: int
    month: int
    day: int

    def __str__(self):
      return f"{self.year}-{self.month}-{self.day}"

birthday: Date = Date(1998, 03, 04)
name_day: Date = Date(2021, 03, 20)
```

_Note:_ the above solution is a technical solution example. Practically it is a
[Clever Code](Clever%20Code.md) code smell - in Python there is built-in
[`datetime`](https://docs.python.org/3/library/datetime.html).



## Refactoring

- Replace Data Value with Object
- Extract Class
- Introduce Parameter Object
- Replace Array with Object
- Replace Type Code with Class
- Replace Type Code/Conditional Logic with State/Strategy
- Move Embellishment to Decorator

---

#### Sources

- [[1](#sources)] - Mika Mäntylä, _"Bad Smells in Software - a Taxonomy and an Empirical Study"_ (2003)
- [[2](#sources)] - Martin Fowler, "Refactoring: Improving the Design of Existing Code (3rd Edition)" (2018)
- [[3](#sources)] - Joshua Kerievsky, _"Refactoring to Patterns"_ (2005)
- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
